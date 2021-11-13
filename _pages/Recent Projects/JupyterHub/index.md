---
layout: page
title:  "Notes on Managing JupyterHub Setup on a Free AWS Server"
permalink: "/Recent Projects/JupyterHub/"
---

# Motivation:
As part of a class (or course, whichever you prefer) on the foundations of programming languages, I was assigned the task of finding a project related to programming languages.

I am a fan of the Jupyter ecosystem, it is an excellent tool to organize work within and exporting the notebook to latex then a PDF is straightforward if time consuming. For this reason my mind went to the fact that interactive kernels for different programming languages have proliferated, many of them available to Jupyter users. The project was thus defined as creating a JupyterHub environment with multiple different kernels for students to explore.

# Setup:

Setup was composed of two parts: 
- Building the server on AWS, which was relatively easy thanks to <a href = "https://tljh.jupyter.org/en/latest/install/amazon.html">this tutorial.</a>
- Configuring the kernels.

Configuring the kernels was a hurdle. The optimal solution would allow students to log in to the JupyterHub server and be presented with all the available interpreted kernels on the server. Unfortunately, installing multiple kernels within the same environment is likely to break that environment. The next best solution was thus to configure one environment for each language then inform the students of the commands for searching the list of virtual envs:


<code>conda env list</code>

From there the environments would be named after languages, with some adjustments to make them commandline friendly (C++ becomes cpp for example). The student then interacts with the server by opening a terminal window and typing:

<code>conda activate cpp</code>

This was considered sub-optimal but adequate given the limitations of both time and technical knowledge. 