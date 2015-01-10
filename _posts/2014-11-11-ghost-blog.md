---
layout: docs
title: Create a Ghost Blog
published: true
category: [ghost, node.js, tutorials]
---

# Create a Ghost Blog

<p class="intro">This tutorial introduces you to key Nitrous.IO concepts by walking you through the process of setting up the blogging platform, Ghost, on Nitrous.IO.</p>

## Create the Ghost Application

>Before creating a new application, enable Advanced Options for your account. Navigate in the menu to **Account > Account
Settings** and enable **Show Advanced Options**.

[Login](https://pro.nitrous.io/#/login) to your Nitrous account and select **New > Application** from the menu. 

Title your app "Ghost", and select the **Vanilla** template.

![Specify Image Reposity]({{site.baseurl}}/images/articles/ghost/vanilla-template.png)

Click next to go to step 2. Within this step we will need to add port bindings. Within the Port Bindings section, add the following public port:

* Host Port: 80
* Container Port: 2368

![Specify Image Reposity]({{site.baseurl}}/images/articles/ghost/port-binding.png)

Click **Create** and a new Ubuntu installation will be built with some development tools pre-installed.

## Install Node.JS

After the box is created, open the Web IDE. The first thing you will want to do is to install Node.JS. Run this command within the console to install Node.JS:

$ sudo apt-get install -y nodejs

## Install and Configure Ghost

Next, run the following commands to download and extract Ghost:

    $ cd workspace/
    $ wget https://ghost.org/zip/ghost-latest.zip && unzip ghost-latest.zip -d ~/workspace/app && rm -f ghost-latest.zip

Next, cd into the app folder which the project files were extracted to and run npm install.

    $ cd app/
    $ npm install

Next, modify the host in the configuration to `0.0.0.0` and add the user `ghost`.

    $ sudo sed 's/127.0.0.1/0.0.0.0/' ~/workspace/app/config.example.js > ~/workspace/app/config.js
    $ sudo useradd ghost --home ~/workspace/app

Your Ghost blog should be ready to go at this point. Run your app with npm start.

    $ npm start

## Preview the Blog

To preview your app, navigate to **Preview > Port 80** within the menu bar. A new tab will open at this point with your new Ghost blog.

![ghost-settings]({{site.baseurl}}/images/articles/ghost/ghost-preview.png)

