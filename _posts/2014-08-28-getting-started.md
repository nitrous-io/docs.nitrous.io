---
layout: getting_started
title: Getting Started with Your Nitrous.IO Environment
published: true
mitem: getting-started
---

### Getting Started with Your Nitrous.IO Environment by Setting Up a Ghost Blog.

#### Overview

This will quickly walk you through setting up a Ghost Blog on the new Nitrous.IO. There are a lot more parameters than those covered in the commands below. You can type any of the commands in the CLI without parameters to get detailed information about the various options.

#### Step 1: Download and run the Nitrous.IO Command Line Interface (CLI) Installer Package for your operating system.


#### Step 2: Authenticate with your Nitrous.IO credentials.

{% highlight bash %}
nitro login
{% endhighlight %}

#### Step 2b: Optional - for Staging Only.

Set the `NITRO_API_URL` environment variable.

{% highlight bash %}
    export NITRO_API_URL=https://pro.nitrous.io
{% endhighlight %}

#### Step 3: Create a new Host. Specify size, region and slug (a unique name).

{% highlight bash %}
    nitro hosts:create 512mb -r sfo -s hello
{% endhighlight %}


Or issue the command without parameters to see all the options.

{% highlight bash %}
nitro hosts:create
  Usage: nitro hosts:create <size>

create a new host

Options:

size
-r, --region=""       Region in which you want to create the host
-s, --slug=""         A unique slug for the host
{% endhighlight %}

#### Step 4: Pull an Existing Image onto the Host (Host is ‘hello’ in this instance).

{% highlight bash %}
    nitro images:pull hello dockerfile/ghost
{% endhighlight %}


Step 4b: Alternately, you can also build your own DockerFile if you have an existing copy.

{% highlight bash %}
    nitro images:build hello ./Dockerfile
{% endhighlight %}


#### Step 5: Setup a Data Volume.

This is where your Data will be stored - isolating your Data from Compute. You can then make changes to your application without affecting your Data.

{% highlight bash %}
    nitro volumes:create hello data
{% endhighlight %}


#### Step 6: Create a Container using the Data Volume and with Port Forwarding.

Now we can create a new Container, connect the Data Volume we created to the Container and link the appropriate port from the Container out to the host. Container linking also allows you to connect various microservices in your application stack to one another.

{% highlight bash %}
    nitro create hello -s CONTAINER_NAME -i dockerfile/ghost -p 80:2368 -v data:/ghost-overide
{% endhighlight %}


Using the command above, a Container will be created using the Image dockerfile/ghost with Ports forwarded 80:2368 and Data Volume mounted.


#### Step 7: Connect to the Container via shell.

We can ensure that the Container came up properly by accessing it.

{% highlight bash %}
    nitro shell CONTAINER_NAME
{% endhighlight %}

Now we can access the Ghost Blog locally within the Container:

{% highlight bash %}
    curl localhost:2368
{% endhighlight %}

#### Step 8: Access the Service on Web.

Find the URL to your host and point your browser to your new Ghost Blog.

{% highlight bash %}
    nitro hosts:inspect hello
{% endhighlight %}

You have now successfully set up a Ghost Blog.
