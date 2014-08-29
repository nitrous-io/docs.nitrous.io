---
layout: overview
mitem: overview
---

We use a containerization technology called Docker which is supported by Google, Microsoft and host of other technology stalwarts to make this happen so you get access to existing full set of pre-built images ranging from Language runtimes to Databases and

If you're app is like a typical app you probably have a language run time which runs a web component, that interacts with one or more databases and other services. With the new Nitrous.IO you create and isolate these components. This gives you a couple of benefits:

1) You can update any component independently and without affecting the others.

2) Your development environment becomes similar to production environment.

We will show a few example applications that show you how to get started and how to start separating your application to gain these benefits.


### New Concepts

Nitrous.IO uses a variety of terms to describe an application consisting of containers. Some of the most frequent include:

Container: A portable, lightweight runtime that enables apps to be quickly assembled.
Host:  A virtual machine that runs Docker containers and your workloads. A Host will run one or more Containers.
Image: A Docker Image that is stored in Repository.
DockerFile: A set of instructions to build an Image.

### Getting Started.

_Step 1:_

First let us get familiar with the Nitrous.IO service by using some existing resources to setup and running the popular Ghost Blog on Nitrous.IO.
(Concepts: Nitro CLI; Hosts; Containers; Port Mapping; Data Volumes)

_Step 2:_

Now let us set up a brand new rails environment to suit our needs and share it with a colleague. (Concepts: DockerFile; Registry; Tiered Architecture; Linking Containers; Sharing)

_Step 3:_

Finally, this tutorial will walk you through how to migrate your existing environment on to Nitrous.IO.

We would love to hear from you - Please email us with your thoughts and question: [support@nitrous.io](mailto:support@nitrous.io)

