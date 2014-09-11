---
layout: overview
mitem: overview
---

## About the Beta

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

## Install

The Nitrous Toolkit is currently supported for OSX and Debian/Ubuntu. 

[Download the right client for you OS]({{site.baseurl}}/download/) for installation instructions.

## Overview

If you're familiar with containerization you can skip this next section and go directly to the getting started guide and tutorial in the next section. Otherwise here are a few basic concepts that will help you get started easily. 

### Host

A host is a virtual machine that runs containers. A host runs one or more Containers that can be linked together.

### Container

A container is a portable, lightweight runtime that enables apps to be quickly assembled. You can create a container within a running host. Containers can be built from existing images that are stored in your registry and be made accessible on a private network within the host or a public network. To learn more simply type `nitro create` in the terminal. 

### Image

An image is a template for creating and sharing containers. Images are stored in a Repository and pulled to your host where it can be used to replicate containers. You can also create images with the `nitro commit` command. 
Learn more about images with by typing `nitro images` into the terminal  or [learn how to create your images and share them with your team.]({{site.baseurl}}/sharing)

### Registry

Registries are where Images are stored so that they can be shared. Nitrous.IO supports Docker Hub and Quay.Io registries out of the box but you can also use your own private registry if you have one setup. 

### Volume

A data volume is persistant store on you host where you can store the data needed by your containers. Isolating your data from your container allows you to make changes to your application without affecting your data.


## Tutorials

### Getting Started

First, let us get familiar with the Nitrous.IO service with [the Getting Started tutorial]({{site.baseurl}}/getting-started) which walks through creating a Nitrous.IO host and sets up a web blogging service using an existing template/Image.

_(Concepts: Nitro CLI; Hosts; Containers; Port Mapping; Data Volumes)_

### Creating a Rails App

Now, let us [set up a brand new rails environment connect it to a backing store.]({{site.baseurl}}/rails-app/)

_(Concepts: Private Registry; Tiered Architecture; Linking Containers; Sharing)_

### Sharing Environments

Follow this guide on sharing your environment with another collegue.

### Migrating to Nitrous _(Coming Soon)_

Finally, this tutorial will walk you through how to migrate your existing environment on to Nitrous.IO.

_(Concepts: Dockerfile, Migration, Vagrant to Docker, Tiered Application)_

---

If you run into any issue or have suggestions, we're available at: [support@nitrous.io](mailto:support@nitrous.io)
