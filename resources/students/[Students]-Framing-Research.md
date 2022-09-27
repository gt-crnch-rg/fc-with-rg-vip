* _Last updated: 4/16/20_

   # How should you frame your research?
   When you write a paper, invariably you will get reviews that implicitly or explicitly ask "why is this research important?". In a sense, reviewers and other readers are asking why they should use your approach over another technique that may be available. For this reason, it is important to _frame_ the research problem you are working on and why your solution helps to move the state-of-the-art. 

   One popular way to think through the framing of your work is by using the [Heilmeier Catechism](https://www.darpa.mil/work-with-us/heilmeier-catechism). This is a series of questions that a former DARPA director, George Heilmeier, created to determine which projects were worthy of funding. These questions are as important today as when they were first posed, so it is good to think through them for your work before you start writing or running experiments. 

   ## An example of the Heilmeier Catechism in Action
   This is based on existing research for an NSF project called [SuperSTaRLU](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1710371&HistoricalAwards=false).

   * What are you trying to do? 
       * We are trying to create optimized gather/scatter primitives for a widely used sparse linear solver, [SuperLU](https://crd.lbl.gov/departments/applied-mathematics/scalable-solvers/research-areas/superlu-dist/).
   * How is it done today, and what are the limits of current practice?
       * Currently, researchers focus on optimizing dense matrix multiplication kernels but avoid optimizing time-consuming sparse kernels like gather and scatter. 
   * What is new in your approach and why do you think it will be successful?
       * Our approach is 
   * Who cares? If you are successful, what difference will it make?
      * A large number of users and applications depend on the SuperLU solver to accelerate their codes. If we are able to speed sparse kernels up, we can provide a large boost to these users. 
   * What are the risks?
      * How might we fail or what pitfalls are there?
   * How much will it cost?
      * You can usually avoid this one if you are working in a research lab. However, this can be tied into how long it might take?
   * How long will it take?
   * What are the mid-term and final “exams” to check for success?