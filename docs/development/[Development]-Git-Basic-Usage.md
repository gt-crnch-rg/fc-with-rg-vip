_Last updated: 1/9/22_

# Git and Revision Control #

Revision control serves two purposes for research: 1) It allows you to easily work on and update code between machines, provides a minimal backup of your codebase, and allows you to work collaboratively with others. 2) It also allows you to publish your research code, further helping your career and the usage of your software. 

In fact, students often ask "What is the best way to show a potential employer that I have experience with <X>?" Having a public git presence with some of your code projects for courses and general research is a great way to demonstrate your skills related to programming languages or even specialized topics like quantum computing. 

At Georgia Tech, we use Git as our primary revision control system, and students have access to an enterprise Github repo that can be used for development or basic backups, [https://github.gatech.edu/](https://github.gatech.edu/). This site provides students with unlimited public and private repos, and more information on using it can be found [here](https://drupal.gatech.edu/handbook/github-georgia-tech). 

### GT Enterprise Github versus Public Github
Note that repos in the GT enterprise site cannot be posted publicly, so it is suggested that you also have a public github.com account for any projects you want to share more widely. Thisivision exists to help secure internal research and coursework repositories, so it's up to you to talk to any research advisors before publishing your code more widely. 

### Getting Started with Git ###
Github has a really good list of resources for learning how to use Git [here](https://help.github.com/articles/good-resources-for-learning-git-and-github/).

Of these, I'd suggest starting with Github's [flow guide](https://guides.github.com/introduction/flow/) and 
the [Hello world example](https://guides.github.com/activities/hello-world/).

### More interactive Tutorials ###

If you'd like to learn via an interactive, online tutorial (before installing git locally), there are two good options for a basic and more intermediate tutorial:

- [Try Git](https://try.github.io): Provides a 15 minute online tutorial including all the basics including adding, commiting, pushing files and handling history and merges.

- [Understanding Git branching](http://learngitbranching.js.org/): This comprehensive tutorial goes through git branching in great detail. 
   
- [Software Carpentry Git Novice](https://swcarpentry.github.io/git-novice/): A comprehensive git basics tutorial.

### More Advanced Git Resources

A researcher with NVIDIA, Graham Lopez, has compiled a nice [site](http://www.grahamlopez.net/git) that goes into more details based on his experiences with a large codebase, QMCPack.

### GUI Client Options ###

While commandline seems to be the best option, especially for development on remote servers, there are several different GUI tools for different OSes listed [here](https://git-scm.com/download/gui/win). Of these, [GitHub Desktop](https://desktop.github.com/) (Mac/Win) and [SourceTree](https://www.sourcetreeapp.com/) (Mac/Win) are some of the most well known and are also free. 	

### Other Resources 

[Git Book](https://git-scm.com/book/en/v2)

[Git Immersion](http://gitimmersion.com/): A tutorial that requires you download a git repo but that provides a detailed walkthrough of basic git commands.


### Useful git tricks

* How do I store my username/password when not using keys?
    * From the git directory run the following command: `git config credential.helper 'cache --timeout=300'`
* How can I speed up cloning of very large repos (e.g., cloning spack or something similar)
    * If you don't need all the commit history you can use the `--depth <N>` parameter. As an example `git clone --depth 1 https://github.com/spack/spack.git` will not pull any history but will also be about 6x faster to clone.
    * You can also use git config features like manyFiles for very large repos (LLVM, Linux kernel). As an example, `git clone -c feature.manyFiles=true https://github.com/spack/spack.git` OR `git config feature.manyFiles true`
