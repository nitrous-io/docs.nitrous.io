---
layout: docs
title: Getting Started with Your Nitrous.IO Environment
published: true
mitem: getting-started
---

### Getting Started with Your Nitrous.IO Environment by Setting Up a Ghost Blog.

#### Overview

This will quickly walk you through setting up a Ghost Blog on the new Nitrous.IO. There are a lot more parameters than those covered in the commands below. You can type any of the commands in the CLI without parameters to get detailed information about the various options.

#### Step 1: Download and run the Nitrous.IO Command Line Interface (CLI) Installer Package for your operating system.


#### Step 2: Authenticate with your Nitrous.IO credentials.

    nitro login

#### Step 2b: Optional - for Staging Only.

Set the `NITRO_API_URL` environment variable.

    export NITRO_API_URL=https://pro.nitrous.io


#### Step 3: Create a new Host. Specify size, region and slug (a unique name). 

    nitro hosts:create 512mb -r sfo -s hello


Or issue the command without parameters to see all the options.

```
nitro hosts:create
  Usage: nitro hosts:create <size>

create a new host

Options:

size
-r, --region=""       Region in which you want to create the host
-s, --slug=""         A unique slug for the host
```

#### Step 4: Pull an Existing Image onto the Host (Host is ‘hello’ in this instance).

    nitro images:pull hello dockerfile/ghost


Step 4b: Alternately, you can also build your own DockerFile if you have an existing copy. 

    nitro images:build hello ./Dockerfile


#### Step 5: Setup a Data Volume.

This is where your Data will be stored - isolating your Data from Compute. You can then make changes to your application without affecting your Data.

    nitro volumes:create hello data


#### Step 6: Create a Container using the Data Volume and with Port Forwarding.

Now we can create a new Container, connect the Data Volume we created to the Container and link the appropriate port from the Container out to the host. Container linking also allows you to connect various microservices in your application stack to one another. 

    nitro create hello -s ghost -i dockerfile/ghost -p 80:2368 -v data:/ghost-overide


Using the command above, a Container named ‘ghost’ will be created using the Image dockerfile/ghost with Ports forwarded 80:2368 and Data Volume mounted. 


#### Step 7: Connect to the Container via shell.

We can ensure that the Container came up properly by accessing it.

    nitro shell ghost


Now we can access the Ghost Blog locally within the Container:

    curl localhost:2368


#### Step 8: Access the Service on Web.

Find the URL to your host and point your browser to your new Ghost Blog.

    nitro hosts:inspect hello


You have now successfully set up a Ghost Blog. 
