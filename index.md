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

The Nitrous Toolkit is currently only supported for OSX and Debian/Ubuntu. Head on over to the [Download page]({{site.baseurl}}/download/) for installation instructions.

## Overview

### Host

A host is a virtual machine that runs containers. A host runs one or more Containers that can be linked together.

Create a new container with the following command:

{% highlight bash %}
$ nitro hosts:create 512mb -r sfo -s HOST_NAME
{% endhighlight %}

### Container

A container is a portable, lightweight runtime that enables apps to be quickly assembled.

You can create a container within a running host. Run the following command to create a container, specifying a host which you have already created:

{% highlight bash %}
$ nitro create HOST_NAME -s CONTAINER_NAME
{% endhighlight %}

You can also include an image from your registry, enable port forwarding, and also specify if the container should be publicly acessible or not.

{% highlight bash %}
$ nitro create HOST_NAME -s CONTAINER_NAME -i nitrousio/ruby -p public:3000:3000
{% endhighlight %}

### Image

A Docker image that is stored in Repository that is used as a template for new containers.

When pulling an image you will need to specify the host. Here is an example of pulling the ghost image from Docker Hub to a host:

{% highlight bash %}
$ nitro images:pull HOST_NAME dockerfile/ghost
{% endhighlight %}

### Registry

You can connect your host to public or private registries.

Run the following command to login to the Docker Hub registry:

{% highlight bash %}
$ nitro registry:login HOST_NAME
{% endhighlight %}

### Volume

A data volume is where your data will be stored - isolating your data from your computer. You can then make changes to your application without affecting your data.

Run the following command to create a new volume:

{% highlight bash %}
$ nitro volumes:create HOST_NAME VOLUME_NAME
{% endhighlight %}

### DockerFile

A DockerFile is a set of instructions to build an image.

## Tutorials

### Getting Started

First, let us get familiar with the Nitrous.IO service with [the Getting Started tutorial]({{site.baseurl}}/getting-started) which walks through creating a Nitrous.IO host and sets up a web blogging service using an existing template/Image.

_(Concepts: Nitro CLI; Hosts; Containers; Port Mapping; Data Volumes)_

### Creating a Rails App

Now, let us [set up a brand new rails environment connect it to a backing store.]({{site.baseurl}}/rails-app/)

_(Concepts: Private Registry; Tiered Architecture; Linking Containers; Sharing)_

### Sharing Environments

Follow this guide on sharing your environment with another collegue.

### Migrating to Nitrous

Finally, this tutorial will walk you through how to migrate your existing environment on to Nitrous.IO.

_(Concepts: Dockerfile, Migration, Vagrant to Docker, Tiered Application)_

If you run into any issue or have suggestions, we're available at: [support@nitrous.io](mailto:support@nitrous.io)
