---
layout: docs
title: Nitrous Sync - Ignoring Files
published: true
category: tutorials
---

## Create a .syncignore file

You can configure Nitrous Sync to ignore files and folders when syncing. To determine which files you want to ignore you can either add a `.syncignore` file within your container's `~/workspace/` folder **OR** within your local project folder which syncs to Nitrous.

Follow these steps to create a `.syncignore` file within the container:

1. Connect to the terminal of your Nitrous container and cd into the `~/workspace` folder.
2. Enter `touch .syncignore` to create a `.syncignore` file.
3. To edit the file within the terminal, run `nano .syncignore`.

Files matching the rules entered into the `.syncignore` file will no longer sync between the container and your local machine.

## Examples

Here are some examples of rules you can add to `.syncignore`:

    # File extensions
    -----------------
    *.dll
    *.exe
    *.so
    *.7z
    *.dmg
    *.gz
    *.iso
    *.jar
    *.rar
    *.tar
    *.zip
    *.log
    *.sql
    *.sqlite

    # Folders
    ----------------
    /tmp         # ignores /tmp in root directory of project folder (~/workspace)
    .meteor/   # ignores all folders/subfolders matching name

    # OS generated files
    ----------------
    .DS_Store
    .DS_Store?
    ._*
    .Spotlight-V100
    .Trashes
    ehthumbs.db
    Thumbs.db

