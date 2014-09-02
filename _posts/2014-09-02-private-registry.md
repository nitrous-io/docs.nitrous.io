---
layout: private-registry
title: Pulling an existing Docker Image from your Private Repository
published: true
mitem: private-registry
---

### Pulling an existing Image from your Private Registry


#### Overview

This document will walk you through how to set up a a Container from an existing Docker image in your private registry. 
This guide assumes that you have the Nitro CLI installed and a Host created on Nitrous.IO.


#### Step 1: Log in to your Docker Private Registry or any Private Registry you may use through the Nitro CLI.

{% highlight bash %}
nitro registry:login HOST_NAME
{% endhighlight %}

You will be prompted for your Username, Password, Email and Registry.


#### Step 2: Now that you are logged in, you can pull an existing Image from your Private Registry.  

{% highlight bash %}
nitro images:pull HOST_NAME USERNAME/REPO_NAME
{% endhighlight %}


#### Step 3: Create a Container using the Image you have just pulled.

{% highlight bash %}
nitro create HOST_NAME -i USERNAME/REPO_NAME -s CONTAINER_NAME -p 4000:4000
{% endhighlight %}


#### Step 4: Connect to the Container via shell.

{% highlight bash %}
nitro shell CONTAINER_NAME
{% endhighlight %}

Now you can access the contents of the Container to ensure that it is running properly.

{% highlight bash %}
curl localhost:4000
{% endhighlight %}


#### Step 5: Access the Service on Web.

Find the URL to your host and point your browser to your application.

{% highlight bash %}
    nitro hosts:inspect HOST_NAME
{% endhighlight %}

You have now successfully created a Container using an existing Image pulled from a Private Registry. 
