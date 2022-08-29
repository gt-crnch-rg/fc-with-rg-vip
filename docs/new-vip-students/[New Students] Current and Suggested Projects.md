_Last updated: 8/29/22_

Broadly, we have 3-4 sub-teams focused on different research topics related to novel architectures and mapping algorithms to unique or "rogue" platforms.

## Required Skills for all Projects ##
If you don't already have these skills we can help you pick them up, but all VIP team members will need to be familiar with the following skills: a basic understanding of using Linux and/or the terminal, ssh, accessing X-based software remotely, and some general experience with programming in C, C++, or Python (usually taught in CS 1301).

Reviewing the following is highly suggested. You don't have to be an expert but having some familiarity will be highly helpful!
* [Linux](https://github.com/gt-crnch-rg/fc-with-rg-vip/blob/main/docs/linux/%5BLinux%5D-General-Linux-FAQs.md) - Focus on the MIT Missing Semester and basic Linux command-line skills
* [C and C++ Programming](https://github.com/gt-crnch-rg/fc-with-rg-vip/blob/main/docs/development/%5BDevelopment%5D-Resources-C-Plus-Plus.md)

## Near-memory ##

* **What's the goal?** This research aims to map novel architectures to the Emu Chick. This platform is novel because it moves the computation to the data instead of moving the data through a traditional cache hierarchy.
* **What current work is going on with this sub-team?** 
    * In 2022, we are looking at evaluating the GraphBLAS API as a high-level method for implementing codes on the Lucata Pathfinder system. 
* **What are some previous projects for this sub-team?**
    * In Spring 2020, a student mapped prefix sum, an important algorithm for parallel computation to the Emu Chick and evaluated its performance.
    * The Emu sub-team worked on mapping SciKit-Learn algorithms to the Emu Chick using Python and SWIG in 2019. 
* **Required skills:** Experience with programming in C or C++ would be a big benefit as well as experience with parallel programming.
* **Desired skills:** Experience with Cilk, scikit-learn, or parallel programming with a language like OpenMP (CX 4220).
* **Relevant courses**: CX 4220, CS 6220, CS/CSE 6290
* **Future opportunities:** This work is of relevance to national labs working on the "Exascale Computing Project" and can lead to opportunities in either parallel programming or further massively parallel implementations of graph, machine learning, or sparse algorithms. 

### Suggested Near-Memory Projects for 2022
We currently have received four new "Lucata Pathfinder" systems, which provide some opportunity for running larger scale applications written in the Cilk programming language. We would suggest the following as interesting projects that students could tackle:
* Help run Graph500 benchmarking at scale and profile it with the Lucata tools.
* Develop and run the Stream and gather/scatter benchmarks for Pathfinder via Jupyter notebook.
* Revisit using scikit-learn to run basic ML tasks on the Pathfinder platform.
* Test out and develop the GraphBLAS or Kokkos API for the Pathfinder system with key benchmarks (BFS, Jaccard, etc.).

### Near-memory Resources
* [Main Pathfinder Getting Started Page](https://gt-crnch-rg.readthedocs.io/en/main/lucata/lucata-getting-started.html)
* [GT Github for the VIP team](https://github.gatech.edu/crnch-rg/vip-near-mem-team)

## Neuromorphic ##

* **What's the goal?** This research aims to build neural-inspired accelerators that use spiking neural networks instead of traditional digital neural networks to **efficiently** solve AI-related problems.
* **What current work is going on with this sub-team?** 
    * The current team has worked on "NeuroCar", a spiking neural network powered autonomous vehicle platform. Previously, they have designed simulation environments using TensorFlow and Nengo and they are looking to map these trained models to a physical Raspberry Pi-based car platform.
* **Required skills:** Experience with C data structures (CS 1332) is often needed to understand some of the code used. 
* **Desired skills:** Experience with neuromorphic tools like Nengo, BRIAN, or machine learning frameworks like TensorFlow or PyTorch. 
* Relevant courses: CS 3600 (Intro to AI) and CS 3630 (Intro Robotics and Perception), ECE 3400 (Analog Electronics) for working with the FPAA
* **Future opportunities:** 

### Suggested Neuromorphic Projects
* Continue work on the NeuroCar platform and map existing simulation infrastructure and models to a Raspberry PI-based vehicle platform
* Work with the [Field Programmable Analog Array](https://en.wikipedia.org/wiki/Field-programmable_analog_array) device to design an interface between the PYNN simulator and this novel hardware.
* Evaluate TensorFlow and eventually Nengo implementations for tasks defined by the [OpenAI Gym](https://gym.openai.com/). These types of tasks are more complicated benchmarks that provide examples of complicated problems that neuromorphic systems could solve efficiently. 

#### Nengo FPGA or FPAA Backend
* The Nengo-FPGA backend supports one ensemble all on a small board. We could extend this to support multiple ensembles.
* Adding a RISC-V or Arm backend for Nengo
* See [this page](https://github.com/gt-crnch-rg/fc-with-rg-vip/blob/main/docs/students/%5BResearch%20Ideas%5D%20Nengo%20Neuromorphic%20Backends.md) for Nengo-related research ideas.

## Reconfigurable ##
* **What's the goal?** The reconfigurable subteam is focused on building new and unique accelerators based on the RISC-V architecture.
* **What current work is going on with this sub-team?** 
    * Most recently the reconfigurable subteam  
* **Required skills:** Experience with programming in Verilog, VHDL, Chisel, or OpenCL is very much desired.
* **Desired skills:** Experience designing a digital logic circuit in either Verilog, VHDL, or Chisel via class or other projects.
* **Relevant courses**: CS 2210, CS 3320
* **Future opportunities:**  

### Suggested Reconfigurable Projects
* Work on new accelerators for the RISC-V ecosystem and test them with BOOM and the ROCC interface
* Prof. Hyesoon Kim's lab currently has a project where they are mapping Robotic Operating System to a RISC-V BOOM core. This project involves less Chisel work but is focused on deploying an application to a soft-core RISC-V CPU that runs in an FPGA with a Linux software stack. 

## Quantum ##

* **What's the goal?** This research aims to build student knowledge in the use of quantum computing tools and software and to use these skills to evaluate and develop new ways of running quantum algorithms
* **What current work is going on with this sub-team?** 
    * Spring 2020 - students looked at both a minimal QX mapping problem and at quantifying noise with Qiskit-related simulations. Students worked on a plugin for the XACC quantum compiler framework.      
* **Required skills:** Linear algebra is a required prerequisite. 
* **Desired skills:** Experience with programming in C or C++ would be a big benefit as would any physics course that covers topics in quantum mechanics.
* Relevant courses: MATH 1553/1554 (linear algebra), PHYS/MATH 4782, ECE 8863/8853
* **Future opportunities:** GTRI's CIPHER group is pursuing several quantum and NISQ-related topics and are often looking for student interns. Additionally, Georgia Tech has ties to projects at DoE National Labs including [QCAT/QCOR](https://qcor.ornl.gov/).

### Suggested Quantum Projects
* Continue work on a minimal QX mapping plugin for the XACC compiler framework. Test using a simulated quantum backend.
* Work with GT's Quantum Student Association to develop new training tools to get undergrads up to speed with quantum computing frameworks. 
* Look at the ionQ backend for the XACC tool and test implementing a simple algorithm  (e.g., Shor's). A goal of this project would be to understand better how we could modify the ionQ backend for XACC to support GTRI's ion trap system.
