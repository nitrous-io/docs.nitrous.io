---
layout: docs
title: Nitrous Sync - Ignoring Files
published: true
category: tutorials
---

# Nitrous Sync - Ignoring Files

<p class="intro">You can configure Nitrous Sync to ignore files and folders when syncing. This will allow for faster syncing if your project generates files which you don't need to edit locally.</p>

## Create a .syncignore file

To determine which files you want to ignore, add a `.syncignore` file within your Nitrous box's `~/workspace/` folder.

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

