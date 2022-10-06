_Last updated: 3/20/20_

# Code Documentation Strategies

Documenting your code is an extremely important skill and one that will pay dividends as you revisit old projects in the future. It also helps communicate your intent for complex code regions to other programmers and even users of your codebase. Here we review some tips for code documentation and for general wiki documentation. 

Most importantly, the best documentation is the documentation that you actually write in or near the process of writing code. **Documentation doesn't have to be perfect, but any attempt to improve the documentation of your code and experimental setup will pay off in the long run.**

## Source code documentation
* [How to document source code responsibly - Andrew Goldis](https://medium.com/@andrewgoldis/how-to-document-source-code-responsibly-2b2f303aa525)
* [Write good documentation - Steve Konves](https://hackernoon.com/write-good-documentation-6caffb9082b4)
* [A beginner’s guide to writing documentation - Write the Docs](https://www.writethedocs.org/guide/writing/beginners-guide-to-docs/)
* [Clean Code book](https://www.oreilly.com/library/view/clean-code/9780136083238/) - available through the GT library

## Best practices from Berkeley library

I've relisted and have annotated the best practices from a nice guide put out by the Berkeley library [here](https://guides.lib.berkeley.edu/how-to-write-good-documentation).

Best practices for writing documentation:
---
1) Include a README file that contains:
    * A brief description of the project - what does it do and why?
    * Installation instructions - how do I build it?
    * A short example/tutorial - how can I get started with using this project?
2) Create an issue tracker for others to use to log new issues for bugfixes, questions, and other requests related to your codebase. Github and Gitlab have built-in issue trackers, and it is recommended that you learn how to use them [here](https://guides.github.com/features/issues/). 
3) Write an API documentation using a tool like [Doxygen](http://doxygen.nl/) or [Sphinx](https://www.sphinx-doc.org/en/stable/) to automate docs generation. It should include:
 * What a function does at a high level
 * What the function's parameters or arguments are
 * What a function returns
4) Document your code using inline documentation for tricky features within functions
5) Apply coding conventions or style, such as file organization, comments, naming conventions, programming practices, etc.
6) Include information for contributors in your code repo
7) Include citation information - you can create a [DOI](https://guides.github.com/activities/citable-code/) with a service like Zenodo to allow easier citation of your repo. 
8) Include licensing information - typically we use an open license like BSD or MIT but not one with strong copy-left protections. See [this site](https://choosealicense.com/) for more information on open-source licenses. 
9) Link to your public e-mail address in the README if you want to be contacted
10) List the version information for the files along with the major edits you did in each version. A good way to think of this is to list the major features that are included in a specific versioned release.


## Using wikis and Markdown for high-level documentation
As a secondary type of documentation, user guides via wiki pages and Markdown are extremely useful to give users better information on how to build and use your code. 

1) You can create github.io sites from a basic markdown page as in the example at [spatter.io](https://hpcgarage.github.io/spatter/) which is generated from the official [README](https://github.com/hpcgarage/spatter/blob/master/README.md).
2) You can create Github or Gitlab wiki pages similar to this wiki using Markdown or ReStructuredText (RST). A table of contents or sidebar can be useful to help organize pages by topic. The use of code regions `like this` allow for including snippets of code and examples of program execution that can help explain how a program works.
3) ReadTheDocs provides nicely formatted documentation built around the use of RST and Sphinx. This is the most common option especially for machine learning and Python-related projects, but it does take a little bit of setup using webhooks to create a useful page. 
    * [Using webhooks to set up ReadTheDocs with Github and Gitlab](https://docs.readthedocs.io/en/stable/webhooks.html)
    * [Simple Github and ReadTheDocs Setup](https://tutos.readthedocs.io/en/latest/source/git_rtd.html)

### What are some good examples of Github wikis that are easy to navigate?
* [Omniauth](https://github.com/omniauth/omniauth/wiki)
* [Netflix Hystrix](https://github.com/Netflix/Hystrix/wiki)
* [Snowplow](https://github.com/snowplow/snowplow/wiki)