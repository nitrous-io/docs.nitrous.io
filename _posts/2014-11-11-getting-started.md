---
layout: docs
title: Getting Started with Nitrous
published: true
category: [ruby, rails, tutorials, getting-started]
---

# Getting Started

<p class="intro">Nitrous is the quickest way to build and deploy web apps. Follow these steps to get started on building your first app.</p>

## Create a Template

[Login](https://pro.nitrous.io/#/login) to your Nitrous account and select **New > Workspace** from the menu.

Name your workspace, select a region near you, and select a VM size (for this example you can select Nano).

Select the **Ruby on Rails** template and click **Create**. This will create a new Rails site with a preconfigured PostgreSQL database.

![Starter Template]({{site.baseurl}}/images/articles/getting-started/starter-template.png)

## Development

After creating a box template, click the **IDE** link found in the bottom right of your dashboard.

![Open IDE]({{site.baseurl}}/images/articles/getting-started/open-ide.png)

Within the IDE you will see a file browser, text editor, and a console. Your development environment will come with a `~/workspace` folder which you can start developing within instantly.

## Preview Your App

The Rails template comes with a app already available within `~/code/starter` which you can preview immediately on port 3000.

Within the console, navigate into `~/code/starter/` and run the app.

    $ cd ~/code/starter
    $ rails server

Once the app is running, preview the app by navigating to **Preview > Port 3000** within the IDE menu bar. Your new Rails app will open in a new window.