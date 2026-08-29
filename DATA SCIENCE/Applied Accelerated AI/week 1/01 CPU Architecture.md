CPU MICROARCHITECTURE PIPELINE:- The Building Blocks

A CPU (Central Processing Unit) doesn't execute an instruction in one step.
Instead, every instruction goes through several stages.

![[Screenshot 2026-07-11 at 8.11.21 PM.png]]
Stage 1:- Instructions are fetched
Stage 2:- Instructions are decoded and cpu understands the meaning of it 
Stage 3:- Execution takes place
Stage 4:- Memory is accessed to either read data or to write data
Stage 5:- Result is written back

To make it more efficient we superscale this method in this way:-
![[Pasted image 20260829195721.png]]

 Modern processors also follow Out-of-Order (OoO) execution which means that if instruction 4 is waiting for some data and instruction 5 is ready to be written then instruction 5 will be written. here order of execution changes. 

Cache Hierarchy(intel xeon example):-
Cache hierarchy is the arrangement of different levels of fast memory between the CPU/GPU and main RAM
![[Screenshot 2026-08-29 at 8.09.36 PM.png|546]]
How it affects AI 
AI workloads process huge amounts of data, so memory speed matters a lot.
- If frequently used data is in cache → faster processing
- If data isn't in cache → CPU/GPU has to fetch it from RAM → slower
- Better cache usage means less waiting, higher throughput, and lower latency
Example: During neural-network training, weights and activations that are reused frequently can benefit from being kept in fast cache, reducing expensive memory accesses.
Cache hierarchy can bottleneck AI when the processor is faster than the memory system can feed it data.
### Parallelism
When Cpu does multiple task/operations at the same time instead of doing them one after another we call it parallelism. Lets discuss some cpu parallelism types:-
1)-Instruction level paralllism(ILP):- 
- Here a superscalar cpu issue 4-6 instructions per cycle via multiple execution ports
- OoO execution helps by rearranging independent instructions in these cpu
- Sometimes some instructions are dependent which limits the amount of parallelism possible during that time. 
- It is useful on small level for ai but cpus have limited amount of instruction level parallelism
2)- SIMD- Data level Parallelism:- 
SIMD does multiple operations in one instruction. Many calculations are done together which makes the process really fast. 
SSE (128-bit) chip can perform operations on 4 FP32(32-bit Floating Point) numbers at once.
AVX-512(512-bit) chip can perform operations on 16 FP32 numbers at once
AMX: Designed specifically to accelerate matrix operations like those used in neural networks.


AI models require billions of mathematical operations.
A CPU can perform some operations in parallel using ILP + SIMD, but a GPU has thousands of parallel compute units, so it can perform vastly more operations simultaneously.
Thats why GPU>CPU for large neural network workdloads

![[Pasted image 20260829205103.png]]

Here also we can see how Gpu is clearly able to see how gpu can do more parallelism than cpu 

### Vonn NeuMannBottleneck & Memory Wall
bandwidth= How much data can be transferred per second
Latency = how long it takes to get the data started/returned

The Vonn Neumann Bottleneck talks about a basic problem:- A processor can calculate extremely quickly, but it constantly needs to get data from memory. If memory cant provide data fast enough the processor sits idle.
This is the memory wall/ von neumann bottleneck. 
Computation becomes faster much more quickly than memory can supply data.

GPUs are also affected by the Von Neumann bottleneck / memory wall.
The difference is that GPUs are designed to hide and reduce the impact of memory delays using:
- Very high memory bandwidth → moves huge amounts of data quickly.
- Massive parallelism→ while some threads wait for memory, others can compute.
- Caches + shared/on-chip memory → keeps frequently used data closer to the compute units.
But it still exists.
AI performance isn't just about having a powerful CPU/GPU. Getting data to the processor fast enough is equally important.
Impact of this on AI workload:-
As the number of tokens n increases (request from ai). the amount of data that needs to be accessed can grow very quickly.
Which might bring in vonn neumann bottleneck soon. 
more tokens = more memory traffic

LLM interference:- LLM inference is often memory-bound.
Why?
For generating each new token, the system needs to access a large amount of the model's weights.
So even if the GPU can calculate extremely fast:
If weights can't be delivered fast enough → GPU waits → inference slows down.
This is a major reason memory bandwidth is extremely important for LLMs.

DNN training:- Training with large mini-batches can keep the GPU's compute units busy.So it tends to be compute-bound:
GPU has plenty of data → spends most of its time doing calculations.

![[Pasted image 20260829210444.png]]

The 70B example
A 70-billion parameter model in FP16:
`70B × 2 bytes ≈ 140 GB`
So, roughly 140 GB of weights need to be accessed.
If the system had 400 GB/s memory bandwidth:
`140 GB ÷ 400 GB/s ≈ 0.35 seconds`
That's 350 ms just to move the weights, assuming they all have to be read from that memory level.
That's the bottleneck: the computation may be extremely fast, but moving the data takes time.



### CPU In AI Pipeline
Here lets discuss of cpu in ai pipelines:-
1):- Pre/Post processing:- Cpu are good at task that are irregular and involve lots of decision making such as reading/loading data, tokenization, Image/Audio processing, Shuffling and batching datasets. So Cpu can handle these tasks in AI workdloads.

2)- Some model components stay on cpu and they handle sparse operations, control flow, small/light weight models.

3)- Hetrogenous Computing:- Modern Ai systems use both cpu and gpu. 
CPU:- Controls things, prepares data, handles I/O
GPU:- Performs massive parallel tensor operations

Important: Transfer overhead
CPU and GPU have separate memory systems, so data often has to travel through PCIe. PCIe (Peripheral Component Interconnect Express) is the high-speed connection/bus used to connect devices to the CPU, especially things like GPUs, SSDs, and network cards
The slide says roughly:

PCIe 4.0 x16: ~16 GB/s 
GPU memory: ~3.35 TB/s
That's a huge difference.
So if you send lots of tiny operations from CPU → GPU → CPU, the transfer time can be greater than the computation time.

So in conclusion Cpu is good at orchestration + irregular task in ai workloads