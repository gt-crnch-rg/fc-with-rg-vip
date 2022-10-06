## Why is This an Important Research Topic?
Nengo provides a common abstraction for developing SNNs using neurons and ensembles. Mapping new backends enables us to use the same codebase to target new and novel architectures.

## Current Status
This project was initiated by Terry Stewart and others at the 2021 Telluride workshop.

[Relevant repo from Terry Stewart](https://github.com/neuromorphs/ant-nengo-backends]

## Neuron models
* Creating the neuron and the I/O flow are the key pieces of developing a backend. 
* Could write a simple neuron model in C code
     * Rectified linear neurons as a starting point
* FPAA model could interface with Scilab/XCOS
     * Does the IO happen all at once (batch) or does it happen in a feedback loop type format?
     * An online, real-time  closed-loop system 
     * Can pass input data to TextAPI but it would be more offline and batch 
     * Loihi and BrainDrop can be operated in "batch" mode with precomputing the inputs
