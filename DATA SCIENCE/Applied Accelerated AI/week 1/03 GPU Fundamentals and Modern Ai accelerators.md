### Gpu Architecture SIMT & Streaming multiprocessor

What is SIMT:- SIMT stands for single instruction multiple threads. the basic idea is that the GPU runs many threads together, with groups of 32 threads following the same instruction.
Imagine you have:
Thread 1 → A[1] × B[1]
Thread 2 → A[2] × B[2]
Thread 3 → A[3] × B[3]
Thread 32 → A[32] × B[32]

These 32 threads can execute the same multiplication instruction at the same time, but on different data.
This is conceptually similar to SIMD:

SIMD:
ONE instruction → many data values
SIMT:
ONE instruction → many threads → each thread has its own data

What is CUDA?
CUDA is a parallel computing platform and programming model created by Nvidia that lets software use graphics processing units (GPUs) for general-purpose computing instead of just rendering images.
A CUDA thread is the smallest and most basic unit of programmable execution in NVIDIA's [CUDA programming model](https://developer.nvidia.com/blog/cuda-refresher-cuda-programming-model/), designed to perform parallel tasks on a graphics processing unit (GPU).]

What is a Warp?
A warp = 32 CUDA threads.
The GPU groups 32 threads together and schedules them as a unit.
For example:
```
             WARP
┌───────────────────────────────┐
│ T1 T2 T3 T4 ... T29 T30 T31 T32 │
└───────────────────────────────┘
                ↓
       Same instruction
                ↓
       Different data
```

Suppose we're doing:

```
C[i] = A[i] + B[i]
```

The 32 threads can simultaneously do:

```
T1  → C[1]  = A[1]  + B[1]
T2  → C[2]  = A[2]  + B[2]
T3  → C[3]  = A[3]  + B[3]
...
T32 → C[32] = A[32] + B[32]
```
That's where the GPU gets its massive data-level parallelism.

What is Warp divergence?
Warp divergence is a performance bottleneck in GPU computing where threads inside a single warp (typically 32 threads executing together in lockstep) take different execution paths due to conditional branching like `if-else` statements. Because the hardware can only run one instruction at a time for the whole warp, it must serialize the paths, leaving some threads idle while others run
- Control Flow Split: When a conditional statement evaluates differently across threads (e.g., half are true, half are false), the hardware cannot process both branches simultaneously
- Masking and Serialization: The GPU disables or "masks off" threads that take the alternate path, runs the first path, and then reverses the mask to run the second path
Impact on Performance:
- Wasted Cycles: Execution time increases because paths are evaluated sequentially rather than concurrently.
- Reduced Efficiency: Efficiency drops proportionally to the number of distinct branch paths taken within the warp

What is Streaming MultiProcessor (Most important):-
A Streaming Multiprocessor (SM) is the main processing engine inside an NVIDIA graphics card that runs thousands of parallel computing tasks at the same time. SM contains multiple warp which work on instructions.![[Screenshot 2026-08-30 at 8.21.24 PM.png|650]]

In this slide we are discussing H100 gpu which has 132 SMs. Each Sm contains Warps which contains cuda cores. These are for general add multiply arithmetic. 

Cuda Thread Hierarchy:-
Smallest unit is a thread which does one instruction on one data
then comes a warp with 32 threads which does one instruction on multiple data
then comes a block which contains multiple warp. it can contain upto 1024 threads on h100 architecture. one block is assigned to one sm. 
Then comes a grid and a grid contains many blocks

#### Where does AI fit into this?
Suppose we're multiplying two huge matrices:
```
A × B = C
```
There may be billions of individual calculations.
CUDA can divide the work:
```
                 Matrix multiplication
                         ↓
                       Grid
            ┌────────────┼────────────┐
            ↓            ↓            ↓
         Block 0      Block 1      Block 2
            ↓            ↓            ↓
          Warps         Warps        Warps
            ↓            ↓            ↓
         Threads       Threads      Threads
```
Now thousands of threads can work on different parts of the matrix simultaneously.
This is the massive parallelism that makes GPUs excellent for AI.

#### Tensor Cores 
This is extremely important for modern AI.
Tensor cores are specialised fixed function unit performing D = A* B + C( matrix multiply accumulate) per cycle.
Instead of using general CUDA cores for every individual multiplication, Tensor Cores can perform large matrix operations extremely efficiently.
That's why modern NVIDIA GPUs can have enormous AI performance.

CUDA cores vs Tensor Cores
Think:
CUDA cores:
 General-purpose GPU computation
Tensor Cores:
 Specialized hardware for matrix/tensor operations → extremely useful for AI
So when you see:
 H100 = 16,896 CUDA cores + 528 Tensor Cores
Don't think Tensor Cores are just "extra CUDA cores."
They are specialized compute units optimized for certain operations.


Some more gpu you should know for AI 
![[Screenshot 2026-08-30 at 9.04.06 PM.png|609]]


### Gpu memory and Vram optimisation
The main idea:
LLM training needs a LOT of VRAM, and VRAM capacity can become the limiting factor.
1- Why training needs so much VRAM
VRAM must hold multiple things at once:
- Model weights
- Gradients
- Optimizer states
- Activations
For example, GPT-3 has 175B parameters. At FP16, just the weights are roughly **350 GB**, already too large for one 80 GB H100

2-  ZeRO 
ZeRO = Zero Redundancy Optimizer.
Instead of every GPU storing the same copies of everything, split (shard) the data across GPUs.
- ZeRO-1: Split optimizer states
- ZeRO-2: Split optimizer states + gradients
- ZeRO-3: Split optimizer states + gradients + model parameters
So each GPU stores only part of the total data → much less VRAM per GPU.
ZeRO-Offload: Move some optimizer data from GPU VRAM → CPU RAM.
![[Screenshot 2026-08-30 at 9.14.12 PM.png|652]]

3-  training vs inference memory
The slide's useful formulas:
FP16 inference:
`VRAM ≈ 2 × number of parameters`
So a 70B model:
`70B × 2 bytes ≈ 140 GB`
INT8 inference:
`VRAM ≈ 1 × number of parameters`
→ 70B model ≈ 70 GB
Training needs much more memory because of gradients, optimizer states, activations, etc.![[Screenshot 2026-08-30 at 9.15.50 PM.png|884]]


