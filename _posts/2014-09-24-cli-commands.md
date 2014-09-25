---
layout: cli-commands
title: Nitrous CLI Commands
published: true
---

# Nitrous CLI Commands

This is an overview of all the commands available through the Nitro Command Line Interface (CLI).

Type ‘nitro’ in your command shell without parameters to display a list of available commands.

To view the specific options of each command, simply type the command without inserting any variable.

## Attach

The `attach` command will allow you to view or interact with any running container, detached (`-d`) or interactive (`-i`). You
can attach to the same container at the same time - screen sharing style, or quickly view the progress of your
daemonized process.

    nitro attach <container slug>

    Attach to a running container

## Commit

    Usage: nitro commit <container slug>

    Commit a container to an image.

    Options:

      -t, --tag=""    give image a name after committing (automatically generated if omitted)

**Examples:**

Save your custom container by creating a new Image on the Host:

    nitro commit CONTAINER_NAME -t mysnapshot

## Create

    Usage: nitro create <host> [options]

      create a new container

    Options:

      -s, --slug=""           A unique slug for the container
      -i, --image=""          Specify an image to use to create the container
      -e, --env=[]            Set environment variables for the container in the format <key>=<value>. Can be specified multiple times.
      -v, --volume=[]         Add data volume so other containers can mount given <path>. Can be specified multiple times.
      -p, --port-forward=[]   Forward ports from container to host.  Use one of: 'public:hostPort:containerPort', 'private:hostPort:containerPort', 'public::containerPort', or 'private::containerPort' specifications. Publicly forwarded ports will be accessible via the host. Can be specified multiple times.
      -P, --port-forward-all  Forward all ports specified by EXPOSE command in Dockerfile

**Examples:**

Run the following command to create a container with port 80 forwarded, on a Host and Image which you have already created:

    nitro create HOST_NAME -i IMAGE_NAME -s CONTAINER_NAME -p 0.0.0.0:80:2368

## Destroy

    Usage: nitro destroy <container slug>

      destroy a container

    Options:

      -f, --force=""    Skip confirmation

## Hosts

A Host is a virtual machine that runs containers. A Host runs one or more Containers that can be linked together through port forwarding or data volumes. You need to specify the geographic region, Host size and a name for the Host.

    Usage: nitro hosts

      list all hosts

**Examples:**

    nitro hosts:create 512mb -r sfo -s HOST_NAME

### hosts:create

    Usage: nitro hosts:create <size> <region>

      create a new host

    Options:

      size                  Size of the host (use `nitro plans` to see available sizes)
      region                A region to create the host (use `nitro regions` to see available regions)
      -s, --slug=""         A unique slug for the host

### hosts:destroy

    Usage: nitro hosts:destroy <slug>

      destroy host with the given slug

    Options:

      -f, --force=""    %s

### hosts:inspect

    Usage: nitro inspect <host>

      inspect a host

    Options:

      -j, --json    Display output in JSON format

### hosts:restart

    Usage: nitro restart <slug>

      restart a host

    Options:

      -f, --force=""    Skip confirmation

### hosts:start

    Usage: nitro start <slug>

      start a host

### hosts:stop

    Usage: nitro stop <slug>

      stop a host

    Options:

      -f, --force=""    Skip confirmation

## Images

A Docker Image is a template for creating new containers and is stored in a Registry.

    Usage: nitro images <host>

      list images on a given host

**Examples:**

You need to pull an image from a registry onto a host before you can create a container from it. Here is an example of pulling the Ghost Blog Image from Docker Hub to a Host:

    nitro images:pull HOST_NAME dockerfile/ghost

To build an Image from an existing Dockerfile, run the following command:

    nitro images:build HOST_NAME ./Dockerfile

To share an Image, you “push” it onto a Registry with the following command:

    nitro images:push HOST_NAME IMAGE_NAME USERNAME/REPOSITORY_NAME

### images:build

    Usage: nitro images:build <host> <path to Dockerfile or tarball with Dockerfile>

      Build image on host. If a tarball is provided, it must have a Dockerfile in the archive root.

    Options:

      -s, --slug=""   A slug for the image (automatically generated if omitted)

### images:pull

    Usage: nitro images:pull <host> [registry_host/][username/]<repo_name:tag>

      pull image onto a given host

### images:push

    Usage: nitro images:push <host> <image id or repo url tag> [registry_host/]username/<repo_name:tag>

      Push image to a registry. If registry host is not specified, defaults to Docker Hub registry.

### images:remove

    Usage: nitro images:remove <host> <image id or name[:tag]>

      remove image on a given host

    Options:

      -f, --force=""    Skip confirmation

### images:tag

    Usage: nitro images:tag <host> <image id or slug[:tag]> <new image slug[:tag]>

      Tag an existing image with a different slug and optional tag.

    Options:

      -f, --force=""    overwrites an existing image with the new slug:tag even if it exists

## Inspect

    Usage: nitro inspect <container slug>

      inspect a container

## Keys

SSH Keys are secure means to identify trusted computers without involving passwords, allowing you to control access to your Containers.

    Usage: nitro keys <container>

      list public keys in the container

**Examples:**

Save your SSH Key into a text file (my_public_key) and add it to your container:

    nitro keys:add CONTAINER_NAME ./my_public_key

Your container is now secured, you can verify by running the following command to display a list of the added keys:

    nitro keys CONTAINER_NAME

### keys:add

    Usage: nitro keys:add <container> <path to public key file>

      add a public key to a container

### keys:clear

    Usage: nitro keys:clear <container>

      remove all public keys from container

    Options:

      -f, --force=""    %s

### keys:remove

    Usage: nitro keys:remove <container> <md5_fingerprint>

      remove a public key

    Options:

      -f, --force=""    Skip confirmation

## List

    Usage: nitro list [host]

      list containers

## Login

Create a [Nitrous.IO account](https://www.nitrous.io/join) and use the following commands to authenticate with the Nitrous.IO Service.

    Usage: nitro login [options]

      log in to your Nitrous.IO account.

    Options:

      -u, --username=""    Nitrous.IO username
      -p, --password=""    Nitrous.IO password

## Logout

    Usage: nitro logout

      log out from Nitrous.IO.

## Logs

    Usage: nitro logs <container slug>

      Fetch the logs of the container with specified slug.

    Options:

      -f, --follow=""         Follow log output.
      -t, --timestamps=""     Show timestamps.
      -T, --tail=""           Output specified number of lines at the end of logs: `all` or `<number>`. Default all.

## Plans

    Usage: nitro plans

      list available plans

## Regions

    Usage: nitro regions

      list available regions

## Registry

Registries allow you to store your working environment as an Image in a private or public repository.

    Usage: nitro registry <host>

      List currently logged in Docker registries.

**Examples:**

Run the following command to login to your Docker Hub, Quay.IO or other private Registry (only 1 registry at a time):

    nitro registry:login HOST_NAME -u USERNAME -p PASSWORD -e EMAIL -r REGISTRY_URL

You can now push or pull images from this repository:

    nitro images:push HOST_NAME IMAGE_NAME USERNAME/REPO_NAME

### registry:login

    Usage: nitro registry:login [options] <host>

      log in to a Docker registry on a Nitrous.IO host.

    Options:
      -u, --username=""   Docker registry's username
      -p, --password=""   Docker registry's password
      -e, --email=""      Docker registry's email
      -r, --registry=""   Docker registry's server. Defaults to Docker Hub registry

### registry:logout

    Usage: nitro registry:logout [options] <host>

      log out from a Docker registry on a Nitrous.IO host.

    Options:

      -r, --registry=""  Docker registry's server. Defaults to Docker Hub registry

## Restart

    Usage: nitro restart <container slug>

      restart a container

    Options:

      -f, --force=""    Skip confirmation

## Run

    Usage: nitro run [OPTIONS] [container] [cmd]

      run a command on a container

    Options:
      --notty="" do not allocate an interactive TTY for the command.

## Shell

    Usage: nitro shell <slug>

      open a shell on a container

    Options:

      -u, --username=""    Run as this user.

**Examples:**

To start a shell session in a running container, run the following command:

    nitro shell CONTAINER_NAME

You can customize your container from within the shell including installing any additional tools and dependencies.

## Start

    Usage: nitro start <container slug>

      start a container

## Stop

    Usage: nitro stop <container slug>

      stop a container

    Options:

      -f, --force=""    Skip confirmation

## Volumes

A data volume is persistent store on your host where you can store the data needed by our Containers. Isolating your data from your Container allows you to make changes to your application without affecting your data.

    Usage: nitro volumes <host>

      list data volumes on host

**Examples:**

Run the following command to create a new volume:

    nitro volumes:create HOST_NAME VOLUME_NAME


Data volumes can be mounted onto containers when they are created with -v --volume flag on `nitro create` command:

    nitro create HOST_NAME -i IMAGE_NAME -s CONTAINER_NAME -v VOLUME_NAME:/data

### volumes:create

    Usage: nitro volumes:create <host_slug> <volume_slug>

      create a new data volume on host

### volumes:inspect

    Usage: nitro volumes:inspect <host_slug> <volume_slug>

      inspect data volume on host

    Options:

      -h, --human-readable     print sizes in human readable format (e.g., 1K 234M 5G)

### volumes:remove

    Usage: nitro volumes:remove <host> <volume_slug>

      remove a data volume from a host

    Options:

      -f, --force=""    Skip confirmation

