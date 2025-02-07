# Cache-Simulator

## **Overview**
This project implements a **cache simulator** that models a CPU cache’s behavior when reading from and writing to memory. It supports different **cache associativity** types and **replacement policies** while tracking hits, misses, reads, and writes.

## **Files**
- **`first.c`** – Implements the cache simulator, including memory reads, writes, and eviction policies.
- **Input Trace File** – The program reads memory access traces to simulate cache behavior.

## **Features**
- **Configurable Cache Parameters**:
  - Cache size (`csize`)  
  - Block size (`bsize`)  
  - Associativity (`direct`, `assoc`, `assoc:N`)  
  - Replacement policy (`fifo`, `lru`)  

- **Cache Operations**:
  - **Reads (`R`)**: Checks if data is in the cache; if not, loads it from memory.  
  - **Writes (`W`)**: Writes data into the cache and updates memory if necessary.  

- **Replacement Policies**:
  - **FIFO (First-In-First-Out)**: Removes the oldest block when cache is full.  
  - **LRU (Least Recently Used)**: Removes the least recently accessed block when cache is full.  

- **Performance Metrics**:
  - **Memory Reads** – Number of times data is loaded from memory.  
  - **Memory Writes** – Number of times data is written back to memory.  
  - **Cache Hits** – Number of times requested data is found in the cache.  
  - **Cache Misses** – Number of times requested data is not in the cache, requiring memory access.  

## **How to Compile & Run**
### **Compilation**
```sh
gcc -o cache_sim first.c
```

### **Running the Simulator**
```sh
./cache_sim <cache_size> <block_size> <replacement_policy> <associativity> <trace_file>
```
Example:
```sh
./cache_sim 8192 64 lru assoc:4 trace.txt
```
Where:
- `8192` → Cache size (in bytes)
- `64` → Block size (in bytes)
- `lru` → Replacement policy (FIFO or LRU)
- `assoc:4` → 4-way set associative (use `direct` for direct-mapped, `assoc` for fully associative)
- `trace.txt` → Input memory access trace file

## **Expected Output**
The program will print:
```
Memory reads: <count>
Memory writes: <count>
Cache hits: <count>
Cache misses: <count>
```
