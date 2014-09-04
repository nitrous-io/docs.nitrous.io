---
layout: overview
mitem: overview
---

##Nitrous.IO Beta


Nitrous.IO has always been about making it easier for developers to easily work collaboratively without having to fightwith their environment. In this Beta - We are extending our existing environment few important ways. 


First - Many of you asked for the ability to be able to run in previleged mode. Now you can. Install any packages that you need to do - image magick, specific PHP tools or even visualization and data science libraries.


Second, this upgrade allows teams to snapshot the entire set of installed tools and configured environment. This means that anyone on the team can  create and share their templates not just the four available from Nitrous.IO. 


Finally, We are leveraging a technology called Docker to implement our containers. If you already have a DockerFile or Image you can use it with Nitrous.IO. If you don't already use Docker - no problem you can still enjoy all the benefits of Nitrous.IO's easy to use environments without having to learn yet another set of tools. 


We will be continuously improving this experience over the next few weeks as we add easier ways to update the snapshots, connect to your local filesystem.  We would love to hear what you think - Please email us with your thoughts and questions: [support@nitrous.io](mailto:support@nitrous.io)



## Getting Started: New Concepts

Nitrous.IO uses a variety of terms to describe an application consisting of containers. Some of the most frequent include:

_Container:_ A portable, lightweight runtime that enables apps to be quickly assembled.

_Host:_  A virtual machine that runs Docker containers and your workloads. A Host will run one or more Containers.

_Image:_ A Docker Image that is stored in Repository that is used as a template for new containers.

_DockerFile:_ A set of instructions to build an Image.


## Getting Started: A 3 Step Tutorial 

### Step 1

First, let us get familiar with the Nitrous.IO service with the getting stated guide which walks through creating a Nitrous.IO host and sets up an web blogging service using a existing template/image. _(Concepts: Nitro CLI; Hosts; Containers; Port Mapping; Data Volumes)_

### Step 2

Now, let us set up a brand new rails environment connect it to a backing store and share it with a colleague. 
_(Concepts: DockerFile; Private Registry; Tiered Architecture; Linking Containers; Sharing)_

### Step 3

Finally, this tutorial will walk you through how to migrate your existing environment on to Nitrous.IO.


If you run into any issue or have suggestions we're available at: [support@nitrous.io](mailto:support@nitrous.io)
