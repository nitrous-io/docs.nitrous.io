---
layout: default
title: Getting Started with Nitrous
---

## Getting Started

*

## Creating Your First App

[Login](https://pro.nitrous.io/#/login) to your Nitrous account and select **New > Application** from the menu.

Give your application a name, and select a size (for this example you can select Nano). Check the Starter Template **Ruby on Rails with Postgres** and click **Create**. This will create a new Rails site with a preconfigured PostgreSQL database.

![Starter Template]({{site.baseurl}}/images/articles/getting-started/starter-template.png)

## Developing

To develop on your new Rails app you will want to sync your code locally using [Nitrous Sync]({{site.baseurl}}/nitrous-sync). Once Nitrous Sync has been installed on your local machine, login and you should see your new Rails app.

![Nitrous Desktop Rails App]({{site.baseurl}}/images/articles/getting-started/nitrous-sync-rails-app.png)

Click on your Rails container and enable file sync. From there you can open the folder to view your code, and you can use which ever editor you are comfortable with to edit your code.

![Nitrous Desktop Folder]({{site.baseurl}}/images/articles/getting-started/nitrous-sync-folder.png)

## Previewing

The starter template has everything configured for you, so you will simply need to start your Rails app. Within the desktop app, click on the Rails container followed by clicking the **Shell** link. This will open up your local terminal and will shell directly into your box.

Cd into `~/workspace/app/` and run `rails s` to start the app.

![Terminal]({{site.baseurl}}/images/articles/getting-started/terminal.png)

Once the app is running, you can preview the app by clicking **Preview** within Nitrous Desktop.

![Nitrous Desktop Folder]({{site.baseurl}}/images/articles/getting-started/nitrous-sync-preview.png)

You will notice that you are taken to a public URL which you can share for staging and development purposes.

