---
layout: docs
title: Sharing and Replicating Environments for Teams
published: true
mitem: docs
---

# Sharing and Replication Environments for Teams

## Overview

* NitrousIO allows you to setup your environment once and replicate that as often as needed.
In this tutorial you will learn how to take an existing container, snapshot it and share that image
with your team so that they can replicate the same environment. This requires you to have a specific
container that you have cusotmized by installing specific software and a Docker Registry Account.

## Step 1: Ensure that you have a customized Container on an Nitrous.IO Host

{% highlight bash %}
$ nitro list
{% endhighlight %}


## Step 2: Snapshot Your Container to Image on the Host

After making the customizations to your container, from the snapshot thechanges so that you can share or restore this image later.

{% highlight bash %}
$ nitro commit CONTAINER_NAME -t mysnapshot
{% endhighlight %}

This will snapshost your container into a new image on the host.


## Step 3: Login in to you registry

If you haven't already this is a good time to log into the registry you will be using.

{% highlight bash %}
$ nitro registry:login REGISTRY_HOST_NAME
{% endhighlight %}


## Step 4: Push to Your Registry

Now you can push your custom snapshot into a public or private repo on your registry. By default Nitrous.IO uses the Docker Hub Registry.

{% highlight bash %}
$ nitro images:push IMAGE_NAME
{% endhighlight %}

## Step 5: Pull the Image to a New Host

Your team can now pull that image from the registry on to their own host. Since the image is already on your own host this command is not needed if you are replicating on the host where the image was created.

On a new host run the following command:

{% highlight bash %}
$ nitro images:pull HOST_NAME REGISTRY_HOST_NAME/REPO_NAME/IMAGE_NAME
{% endhighlight %}

## Step 6: Replicate the Container.

Now you can replicate the container using the appropriate port and volume mounting options to suit your needs.
If you're replicating on an existing host be sure to use different ports from any that are being used by existing containers.

{% highlight bash %}
$ nitro create HOST_NAME -s clone2 -i IMAGE_NAME -p public:80 -p private:8080
{% endhighlight %}



## Recommended Articles

Check out the [Private Repository Tutorial]({{site.url}}docs/private-registry/) to pull an existing Docker Image from your Private Repository.
