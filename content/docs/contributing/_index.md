---
title: "Contributing"
weight: 3
---

## GitHub Repositories
BrickSim is an open-source project. This means that everyone can help improve the program. All files are on GitHub, divided into two repositories.  
The main repo [https://github.com/bb1950328/BrickSim/](https://github.com/bb1950328/BrickSim/) contains all files for the program itself and a `docs/` folder which has contains the project website. 
This folder is not meant to be edited by hand because the source files are in another repo ([BrickSimWeb](https://github.com/bb1950328/BrickSimWeb/)).  
Of course, it would be better if the `docs/` folder was in the `BrickSimWeb` repository too, but the URL for GitHub Pages is the same as the repository name.

[This GitHub Action Workflow](https://github.com/bb1950328/BrickSimWeb/actions?query=workflow%3A%22Hugo+Static+Site+Build%22) synchronizes all changes from `BrickSimWeb` to `BrickSim/docs`.

If you want to contribute to the website (writing manuals etc.), you need to clone `BrickSimWeb`. More about contributing to the website can be found [here](web).  
If you want to contribute to the program itself, you need to clone BrickSim.

## GitHub Issue Tracker
All issues that only have something to do with the documentation or the website should go on [BrickSimWeb/issues](https://github.com/bb1950328/BrickSimWeb/issues). 
Everything else goes to [BrickSim/issues](https://github.com/bb1950328/BrickSim/issues).

If you have found a bug, have a question or feature request, check if there's already something in the docs about it.
If there's nothing about it in the docs, search on GitHub Issues.
In case you still don't have a satisfactory answer, don't hesitate to create a new issue.

## Security Issues
Every program has bigger or smaller bugs. Unfortunately, some of them are security vulnerabilities. 
It is safer for all users if these are not publicly reported. If you found one, please write an e-mail directly to the creator of BrickSim ([bb1950328@gmail.com](mailto:bb1950328@gmail.com)).