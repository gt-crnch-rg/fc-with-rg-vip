
---

## Near-Memory Getting Started Resources

This subteam is focused on near-memory computation and acceleration. A traditional computer system will use "caches" as part of their memory system to keep track of often-used data. A good example is if you are updating an array or matrix that contains elements of an image - you will likely iterate of each row and column of the image in order and you may reuse some rows/columns as you compute on the input image. This type of data can easily be cached and reused to speed up processing. "Near-memory computing" tries to move computation closer to the data it uses to avoid some of the effects of building large caches.

**Why do we need to avoid big caches?** Some data sets are "sparse" - that is, they have a large number of non-valid elements, like zeroes. Accesses to a sparse data structure cannot be easily cached or predicted because most of the data is not useful, and the data structure itself might be much bigger than a "dense" matrix. A good example of this is data that can be [easily represented as a graph](https://www.educative.io/edpresso/what-is-a-graph-data-structure). As an example, Facebook uses graphs to represent how you and your friends are connected. While a graph data structure can be converted to other formats like a matrix, it is often difficult to process large graphs with today's systems.

## What are some concepts you should understand?

* Linux - Missing Semester concepts from MIT
* Introduction to Parallel Computing - [see the LLNL tutorial on this!](https://hpc.llnl.gov/documentation/tutorials/introduction-parallel-computing-tutorial) - Understanding a bit about what parallel computing means is key!
* What is a graph and how are they used?
* What is a CPU cache and why are they important in today's systems?
* What is OpenMP and parallel programming in general?
* What is Cilk and how does it differ from OpenMP? 


### General Resources:
* [Baeldung on Sparse and Dense Graphs](https://www.baeldung.com/cs/graphs-sparse-vs-dense)
* [How L1 and L2 CPU Caches Work, and Why They’re an Essential Part of Modern Chips](https://www.extremetech.com/extreme/188776-how-l1-and-l2-cpu-caches-work-and-why-theyre-an-essential-part-of-modern-chips)
* [Introduction to Parallel Programming](https://hpc.llnl.gov/documentation/tutorials/introduction-parallel-computing-tutorial)
* [OpenMP Programming Model](https://hpc-tutorials.llnl.gov/openmp/programming_model/)
* [Cilk Tutorial](https://cilk.scripts.mit.edu/pact21/program.html)

### Lucata-specific resources
* [Lucata Pathfinder tutorial](https://github.com/gt-crnch-rg/lucata-pathfinder-tutorial)
