---
layout: docs
title: Create a Ghost Blog
published: true
category: tutorials
---

## Overview

*This tutorial introduces you to key Nitrous.IO concepts by walking you through the process of setting up the blogging platform, Ghost, on Nitrous.IO.*

## Prerequisites

* A Nitrous Pro account
* [Nitrous Sync]({{site.baseurl}}/nitrous-sync)

## Create the Ghost Application

[Login](https://pro.nitrous.io/#/login) to your Nitrous account and select **New > Application** from the menu. For this example a nano sized host will work.

![New Host]({{site.baseurl}}/images/articles/ghost/ghost-host.png)

After configuring your host, select **Create** and your new host will be available in a moment.

## Create a Container

*Within a Host you can create multiple containers. A container could be your development environment, a database service, or any repository found within the [Docker Hub Registry](https://registry.hub.docker.com/).*

Navigate to **New > Container** within the menu. Give your container a name such as "Ghost", and under the **Image** field enter `dockerfile/ghost:latest` within the "Specify Image Repository" field.

![Specify Image Reposity]({{site.baseurl}}/images/articles/ghost/specify-image.png)

Click next to go to step 2. Within this step we will need to add port bindings. Within the Port Bindings section, add the following public port:

* Host Port: 80
* Container Port: 2368

![Specify Image Reposity]({{site.baseurl}}/images/articles/ghost/port-binding.png)

Click **Create** and Nitrous will pull the latest Ghost image with your configurations.

## Previewing

Navigate to your Ghost application within the Dashboard to see the configurations. You will find the publicly available URL of your app under **Hostname**.

![ghost-settings]({{site.baseurl}}/images/articles/ghost/ghost-settings.png)

In this example the **Hostname** is `ghost-2682.nitrouspro.com`. Paste this URL into the browser to view your new Ghost blog.

![ghost-settings]({{site.baseurl}}/images/articles/ghost/ghost-settings.png)

