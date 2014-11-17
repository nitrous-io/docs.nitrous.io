---
layout: docs
title: How to Install Nitrous Sync
published: true
category: tutorials
---

# Using Nitrous Sync

*Nitrous Sync is an app which can be installed on your desktop or laptop. This adds more functionality to your Nitrous account, including File Sync, Shell access, and quick access to previewing your app.*

## Download

Download Nitrous Sync for desktop here.

* [Mac OS X](http://nitrous-pro-app.s3.amazonaws.com/mac/Nitrous.app-0.1.4.zip)
* [Windows](http://nitrous-pro-app.s3.amazonaws.com/windows/nitrous-0.1.4.zip)
* [Linux](http://nitrous-pro-app.s3.amazonaws.com/linux/nitrous-0.1.4.zip)

## Install

### Mac OS X

To install, [download](http://nitrous-pro-app.s3.amazonaws.com/mac/Nitrous.app-0.1.4.zip) the archived app and extract it to your Applications folder.

### Windows

To install, [download](http://nitrous-pro-app.s3.amazonaws.com/windows/nitrous-0.1.4.zip) the archived app and extract it to your Program Files directory.

You should now have access to `C:\Program Files\Nitrous\nitrous.exe`. Create a desktop shortcut of this if you wish and run the executable.

### Linux

To install, [download](http://nitrous-pro-app.s3.amazonaws.com/linux/nitrous-0.1.4.zip) the archived app and extract it
to the directory of your choice. Run the app by navigating into the Nitrous directory through your terminal, and run
`./nitrous`.

## Usage

When the Nitrous Sync app is first opened, you will be prompted to provide your login credentials. From there you will see the following options:

**File Sync**: When file sync is enabled, a folder titled `Nitrous/` is created within your local home folder (~/Nitrous for Mac/Linux, C:\Users\User_Name\Nitrous for Windows). Any application you have created within Nitrous will display here, and if the Application contains a directory `~/workspace` you will have the option to sync the data within that folder. All Nitrous Base images are configured to sync instantly.

Click on the File Sync button to begin syncing. This will continue to monitor and sync any future changes.

![Nitrous Sync Folder]({{site.baseurl}}/images/articles/getting-started/nitrous-sync-folder.png)

**Open Folder**: This will open Finder to the location of your `Nitrous/` folder. You can use the editor of your choice to edit the files and they will instantly sync to the app on Nitrous.

**Shell**: The shell option will automatically open up your terminal and will SSH into your Application.

![Shell]({{site.baseurl}}/images/articles/getting-started/shell.png)

**Preview**: This link will open up your app's public URL within your default web browser.
