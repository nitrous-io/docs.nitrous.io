---
layout: docs
title: Pulling an existing Docker Image from your Private Repository
published: true
mitem: private-registry
---

# Pulling an existing Docker Image from your Private Registry


## Overview

This document will walk you through how to pull an existing Docker image from your private registry to your Nitrous.IO Host. This guide assumes that you have the [Nitro CLI installed]({{site.url}}docs/toolbelt/) and a [Host created on Nitrous.IO]({{site.url}}docs/getting-started/).

## Step 1: Log in to your Private Registry via the Nitro CLI

{% highlight bash %}
$ nitro registry:login HOST_NAME
{% endhighlight %}

You will be prompted for your Username, Password, Email and Registry URL.

Note: Currently, Nitrous.IO supports [Docker Hub](hub.docker.com) and [Quay.io](quay.io).

## Step 2: Pull an existing Image from your Private Registry.

Now that you are logged in, you can simply pull in any private or public image from your repository via the `nitro images:pull` command.

{% highlight bash %}
$ nitro images:pull HOST_NAME USERNAME/REPO_NAME
{% endhighlight %}

## Step 3: Verify

You can run `nitro images HOST_NAME` to verify that your image is now available on the host.

You have now successfully pulled your existing Image from a Private Registry. If you need help creating a container from this Image, please follow Step 6 to 8 of the [Getting Started Guide](/docs/getting-started/).
