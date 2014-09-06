---
layout: overview
mitem: overview
---

##Nitrous.IO Beta


Nitrous.IO has always been about making it easier for developers to easily work collaboratively without having to fight with their environment. In this Beta - We are extending our existing environment in a few important ways: 

> ####Privileged Mode: Sudo when you need to
>
> First, many customers like you asked for the ability to be able to run in privileged mode. Now you can. Install any packages that > you need to do - imagemagick, PHP tools or even specific visualization and data-science libraries.
> 
> ####Snapshots: Create and Share Entire Environments
> Second, this upgrade allows teams to snapshot the entire set of installed tools and configured environment. This means that anyone on the team can create and share their templates and not just the four available from Nitrous.IO. 
>
> ####Docker Support: Leverage the Ecosystem
> And finally, we are leveraging a technology called Docker to implement our containers. If you already have a DockerFile or Image > you can use it with Nitrous.IO. If you don't already use Docker - no problem you can still enjoy all the benefits of  Nitrous.IO's easy to use environments without having to learn yet another set of tools. 


We will be continuously improving this experience over the next few weeks as we add easier ways to update the snapshots, connect to your local filesystem.  The documents below walk you through the process for getting started on Nitrous.IO. We would love to hear what you think - Please email us with your thoughts and questions: [support@nitrous.io](mailto:support@nitrous.io)



## Getting Started: New Concepts

Nitrous.IO uses a few new terms to describe an application consisting of containers:

**Container:** A portable, lightweight runtime that enables apps to be quickly assembled.

**Host:**  A virtual machine that runs containers. A Host runs one or more Containers that can be linked together.

**Image:** A Docker Image that is stored in Repository that is used as a template for new containers.

**DockerFile:**A set of instructions to build an Image.


## Getting Started: A 3 Step Tutorial 

### Step 1

First, let us get familiar with the Nitrous.IO service with [the Getting Started tutorial](/docs/getting-started) which walks through creating a Nitrous.IO host and sets up a web blogging service using an existing template/Image. 

_(Concepts: Nitro CLI; Hosts; Containers; Port Mapping; Data Volumes)_

### Step 2

Now, let us set up a brand new rails environment connect it to a backing store and share it with a colleague. 

_(Concepts: DockerFile; Private Registry; Tiered Architecture; Linking Containers; Sharing)_

### Step 3

Finally, this tutorial will walk you through how to migrate your existing environment on to Nitrous.IO.

_(Concepts: Migration, Vagrant to Docker, Tiered Application)_

If you run into any issue or have suggestions, we're available at: [support@nitrous.io](mailto:support@nitrous.io)
