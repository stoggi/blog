title: Node.js + Express + Git setup
date: 2013-07-19 10:41:38
tags: [node, express, git]
---

This post explains how to set up a new node.js web application. For the sake of the example, we'll call it broccoli.

## Install Node.js

I've found the easiest way to get the latest version of node is to build it from source. It's a clean build with no dependencies, and only takes a few minutes.

First you need to be able to compile. On Ubuntu, this is as simple as installing the `build-essential` meta package:

```plain
$ sudo apt-get install build-essential
```

Get the latest version from http://nodejs.org, extract, compile and install:

```plain
$ wget http://nodejs.org/dist/v0.10.13/node-v0.10.13.tar.gz
$ tar -xzvf node-v0.10.13.tar.gz
$ cd node-v0.10.13
$ ./configure
$ make
$ sudo make install
```

All done, we now have node installed with `node` and the node package manager `npm` on our path.

## Install Express

[Express](http://expressjs.com) is a pretty neat wep application framework for node. It also includes a handy command line script to set up your project. Install it globally like so:

```plain
$ sudo npm install -g express
```

## Create your project

Then you can initialise your express application. I like to add session support `-s`, and use the stylus css engine `-c stylus`. Choose your own options from `express --help`.

```plain
$ express -s -c stylus broccoli
$ cd broccoli
$ npm install
```

That's it. You can start hacking away at the web application. However, before you start, version control!

## Git

If you need to, install git, and maybe set your name and email (will be useful later):

```plain
$ sudo apt-get install git
$ git config --global user.name "Your Name"
$ git config --global user.email you@example.com
$ git config --global color.ui auto
```

Then, in the folder `broccoli` we can initialise the git repo:

```plain
$ git init
```

Also, let's exclude the `node_modules` folder from our repository, since it really shouldn't be included.

Create a file in your `broccoli` directory called `.gitignore` with the following content:

```plain
node_modules
```

Now you are ready to add your files and commit.

```plain
$ git add .
$ git commit -m "Initial commit of expressjs node webapp."
```

## Gitlab

Create a new project in the Gitlab web interface, and follow the instructions to push your newly created repository called `broccoli`.

```plain
$ git remote add origin git@hostname:broccoli.git
$ git push -u origin master
```

In the next post, we look at automated deployment of broccoli with Cuisine and Fabric.