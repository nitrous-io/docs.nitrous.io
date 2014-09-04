---
layout: docs
title: Pulling an existing Docker Image from your Private Registry
published: true
mitem: private-registry
---

# Pulling an existing Docker Image from your Private Registry


## Overview

This document will walk you through how to pull an existing Docker image from your Private Registry to your Nitrous.IO Host. This guide assumes that you have the [Nitro CLI installed](/docs/toolbelt/) and a [Host created on Nitrous.IO](/docs/getting-started/).

## Step 1: Log in to your Private Registry via the Nitro CLI

You will be prompted for your Username, Password, Email and Registry URL, enter your credentials accordingly.

{% highlight bash %}
$ nitro registry:login HOST_NAME

Username: 
Password (will not be echoed):
Email: 
Registry (press enter for index.docker.io):
Successfully logged in to Docker registry on HOST_NAME
{% endhighlight %}

Note: Currently, Nitrous.IO supports [Docker Hub](hub.docker.com) and [Quay.io](quay.io) registries. 

## Step 2: Pull an existing Image from your Private Registry

Now that you are logged in, you can simply pull in any private or public Image from your registry via the `nitro images:pull` command.

{% highlight bash %}
$ nitro images:pull HOST_NAME USERNAME/REPO_NAME

Pulling image 'USERNAME/REPO' to 'HOST_NAME'...
  ID                   Slug                Tag       Name   Created                                 Size   Virtual Size
  aad91b0a4e8311738f   USERNAME/REPO       latest           2014-09-03 00:08:20.995835 +0000 UTC    0      602771479

{% endhighlight %}

## Step 3: Verify

You can run `nitro images HOST_NAME` to verify that your Image is now available on the host.

<br>

You have now successfully pulled your existing Image from a Private Registry. If you need help creating a container from this Image, please follow Step 6 to 8 of the [Getting Started Tutorial](/docs/getting-started/).
