title: Automated deployment with Cuisine and Fabric
date: 2013-07-19 11:47:11
tags: [python, deployment, cuisine, fabric]
---

Following on from the previous post on installing a new node.js project, let's look at deploying it automatically with [Cuisine](https://github.com/sebastien/cuisine) and [Fabric](https://github.com/fabric/fabric).

What is Fabric?

> Fabric is a Python (2.5 or higher) library and command-line tool for streamlining the use of SSH for application deployment or systems administration tasks.

What is Cuisine?

> Cuisine provides chef-like functionality for Fabric.

Great, so with Cuisine we can automate deployment with Python, and all we need on the target machine is an SSH connection.

{% gist 1e039c7b88051190c143 fabfile.py %}