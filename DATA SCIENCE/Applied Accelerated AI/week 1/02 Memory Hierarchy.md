### DRAM Fundamentals: DDR , LPDDR and HBM
 A Dynamic Ram has small capacitors and these capacitors store 1 bit of data. this data can be lost overtime so refresh counter exists in a dram which refreshes these capacitors from time to time so the data stays. This refresh counter adds up to latency (can be 64milisecond) 

Double data rate (DDR):- Dram transfers data on both rising and falling clock edges
DDR is usually used in computers and big machines. 
DDR5 is currently the most advance DDR ram. 
12-channel EPYC(DDR5) has 614GB/s system bandwidth at its peak

In mobiles/Edge AI we use LPDDR
Currently LPDDR5 is the latest
Apple M2 Ultra: 800GB/S unified memory bandwidth is provided. (LPDDR5)
![[Screenshot 2026-08-29 at 10.48.49 PM.png|515]]
Ecc memory in AI servers:- 
ecc means error correcting codes. It is memory designed to detect and correct small data errors automatically.
- 1-bit error → corrected automatically
- 2-bit error → detected (but generally not corrected)

HBM: Game changer for accelerators
HBM stacks multiple dram dies vertically on a silicon interposer. many gpu come with hbm which makes a complete graphic card. These are 10 times faster than ur usual ddr5 ram
 
### Storage Tiers & the Data Ingestion Pipeline![[Screenshot 2026-08-29 at 10.55.51 PM.png|962]]



### NUMA Architecture In Multi Socket AI servers
Non uniform memory access
here we will study multi cpu systems
The main idea in a server with multiple cpus is that each cpu has its own local ram. 
cpu 0 -- ram 0
|
amd infinity fabric
|
cpu 1 -- ram 1

cpu 0 can access ram 0 faster than cpu 1. That's why it's called non-uniform: memory access time depends on where the memory is locate
Why does this matter for AI?
In a multi-GPU server:
```
CPU 0 → GPU 0,1,2,3
CPU 1 → GPU 4,5,6,7
```
Ideally, GPU 0–3 should mostly use CPU 0's memory, and GPU 4–7 should use CPU 1's memory.
If GPU 0 needs data from CPU 1's RAM:
Cross-NUMA access → higher latency + lower bandwidth → slower AI workload.
 Remember: NUMA = each CPU has nearby/local memory, and accessing another CPU's memory is more expensive.

### Memory Bandwidth Summary 

This slide compares the data-transfer speeds of different connections.
The important part is understanding the hierarchy:

|Connection|Approx. bandwidth|
|---|---|
|DDR5-4800, 1 channel|38.4 GB/s|
|EPYC, 12-channel DDR5|~460 GB/s|
|PCIe 5.0 ×16|128 GB/s|
|NVLink 4|900 GB/s|
|H100 HBM3|**3.35 TB/s**|

What does this tell us?
The GPU's own HBM3 memory is extremely fast:
**3.35 TB/s = 3350 GB/s**
But getting data from the CPU through PCIe's much slower:
**128 GB/s**
So you don't want to constantly do:
```
CPU RAM
   ↓ PCIe
GPU
   ↓
GPU memory
```
because the connection can become a bottleneck.

### Data Movement The Hidden Performance Tax

Moving data can be much more expensive than actually computing on it.

1-  Why data movement matters:-
The slide gives a striking example:
- Moving **1 byte across PCIe** → ~700 pJ energy
- Doing a **FP32 MAC on-chip** → ~1 pJ
So moving data can cost **hundreds of times more energy** than the computation itself.
Also, the H100 can compute extremely fast, but its CPU↔GPU PCIe connection is much slower.
Therefore, **keeping data close to the compute units is extremely important.**

2)How do we reduce data movement? 
Operator Fusion  
Combine multiple operations into one GPU operation.
Instead of:
`LayerNorm → move data → Dropout → move data → Activation`
do:
`LayerNorm + Dropout + Activation → ONE GPU kernel`
Less movement between memory and compute.
**Tiling**  
Break a huge matrix into smaller pieces that fit in **fast cache/on-chip memory**.
```
Huge Matrix
┌────┬────┐
│tile│tile│
├────┼────┤
│tile│tile│
└────┴────┘
```
Process each tile while keeping it in fast memory → **reuse data instead of repeatedly fetching from DRAM.**
**Gradient Checkpointing**  
Instead of storing every intermediate result during training, store only some and **recalculate others when needed**.
Trade-off:
Less memory usage ↔ more computation.
**Prefetching**  
Start moving the next piece of data **while the GPU is still computing** on the current data.

3)- Why these techniques matter
**Flash Attention** is a great example.
It doesn't magically make the GPU's arithmetic much faster. Instead, it **reduces unnecessary memory movement** by using tiling and efficient memory access.
Result → **much faster attention.**
Mixed Precision
Using **BF16/FP16 instead of FP32** means each number takes less memory:
`FP32 = 4 bytes`  
`FP16/BF16 = 2 bytes`
So you need to move **roughly half as much data**.