_Last updated: 10-29-19_

# Tips for VIP Notebooks



## Why does VIP require notebooks?

One of the questions we get often is "What makes a good notebook for VIP?" To help answer that, we first should discuss why VIP requires notebooks in the first place. VIP requires notebooks for a few reasons:

1) Researchers in an industrial setting will often keep paper notebooks for *legal* reasons when filing patents. These notebooks are typically paper and each page is dated and signed to provide a verifiable record that can then be used to prove if/when an idea was developed and who has first claim to a patentable idea. Since you are taking VIP for credit and not pay, all the ideas that are developed are your own and you can develop them or patent them as you see fit. 
2) We use them to create a *record* that students in future semesters can use to understand what you have tried already and what worked or did not work. 
3) VIP requires notebooks for grading purposes. This along with peer evaluations are used to give you a letter grade at the end of the semester. These notebooks are also used for accreditation, so we have to keep copies of them after the semester ends. 

## Why do we use digital notebooks?

Our VIP team uses a wiki-based notebook system for the following reasons:
1) Using a wiki with commit history or a Github repository with commit log serves a similar purpose in terms of digital timestamps as a paper notebook. 
2) Paper notebooks are hard to search and difficult for future students to utilize.
3) We don't want to ask you to pay on a semester basis for services like [LabArchives](https://www.labarchives.com/).

## What makes a good notebook? 
With all that background, what actually makes a good notebook? It should be detailed enough to 1) show problems you are working on each week in the form of a ToDo List with items you are specifically working on and checking off each week, 2) subteam meeting notes, and 3) technical notes or references to material you have worked on or collected. It may be easiest for you to fill out your notebook _as part of your weekly subteam meeting_ while you are discussing specific research items and ToDos!

It's perfectly fine to point to a team Github repository and/or wiki for code or references you have collected, and this is encouraged as it helps future students find code you have written and papers you found useful. 

VIP has a [page](https://www.vip.gatech.edu/vip-notebooks) on what makes a good paper notebook with a detailed paper notebook [example](https://www.vip.gatech.edu/sites/default/files/design%20notebook%20sample%201.pdf). We also have several simple grading rubrics that you can look at to see what is generally expected for notebooks - these are included in this git repo [here](https://github.gatech.edu/crnch-rg/vip-rg).

## What might a sample digital notebook entry look like?
As an example, a student might be working on the Emu team looking at creating some new graph algorithms and testing them on the simulator and hardware platform. Note this is not the only way to do this, but we want to include some 1) ToDos specifically focused on your contributions 2) Team meeting notes/discussion 3) Any technical discussion or references that are relevant to the team or your ToDos. You don't have to include all of these items, but the key thing to note is that _**a notebook should probably have more than one line per week on what you are working on!**_

```
Week of 10-29-19
-----
My work items:
* Read through tutorial on breadth first search BFS algorithm design. [DONE]
* Write a CPU serial version of BFS
* Testing sample Emu Hello World code on the simulator. Code crashes with an error! 
* Look at Emu debugging tips using [CRNCH wiki](https://github.gatech.edu/crnch-rg/rogues-docs/wiki/%5BEmu%5D-Debugging-Tips-and-Strategy)

Team Meeting Notes (Can copy items from your weekly update slide for class here): 
* We discussed different types of graph algorithms. We are focusing on BFS, SSSP, and triangle counting.
* We looked at a paper that does triangle counting on the Emu Chick.
* Bert is going to work on SSSP while I will focus on BFS.

Technical Notes:
* The Emu Programming Guide has a section on compiling with the simulator versus running on the hardware. We need to remember to use `-- 0 0` when running code on the hardware. These numbers are the timeouts for running on the hardware!
* Added some sample Emu code snippets on our subteam github repo [here]().
```