---
layout: docs
title: How to Setup SSH Keys on Windows
published: true
category: ssh
---

# How to Setup SSH Keys on Windows

<p class="intro">SSH keys enable you to manage your Nitrous boxes directly from your computer via your favorite SSH client.</p>

On Windows, we recommend that you use [PuttyGen](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html). Visit this link and look for the PuttyGen download:

[http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)

![PuTTYgen]({{site.baseurl}}/images/articles/ssh/puttygen.png)

Click the **PuTTYgen.exe** link to download the application.

Open PuTTYgen and select the **SSH-2 RSA** within the parameter settings. The "Number of bits in a generated key" field should be **2048**. Once these settings are selected, click the **Generate** button next to "Generate a public/private keypair".

![keygen button]({{site.baseurl}}/images/articles/ssh/putty-keygen.png)

You'll be asked to move your mouse around to help PuTTY generate a random keypair for you.

![keygen random]({{site.baseurl}}/images/articles/ssh/putty-random.png)

Once your keys are generated, you'll want to save them someplace private. Click the "Save Public Key" and "Save Private Key" buttons to save the files.

![putty save keys]({{site.baseurl}}/images/articles/ssh/putty-key.png)

PuTTY will automatically save the private key as a .ppk file, which is a putty private key file that contains some additional encoded information about your key. Keep the .ppk extension for this file.

Name the public key **public_key.pub** and the private key **private_key.ppk** and save them someplace safe.

<p class="note">You want to save these keys someplace safe because if someone were to find your private key, they could authenticate with any services where you utilize public key authentication.</p>

Okay, so now we have our keypairs set up, let's go ahead and add our public keys to Nitrous. 

Within your Nitrous Dashboard, select **SSH Keys** within the App settings and paste your public key in the text area. Click **Register Key** once the key has been added.

>Note: The Putty Key Generator may add a line similar to 'the comment: "rsa-key-20130101"' to your public RSA key. You will need to remove this line before pasting it into the text area within your Nitrous account.

![Nitrous key]({{site.baseurl}}/images/articles/ssh/public-key-form.png)

Now let's connect to one of our development boxes. For this, we're going to use the [PuTTY SSH client](http://www.chiark.greenend.org.uk/~sgtatham/putty/).

![putty download]({{site.baseurl}}/images/articles/ssh/putty-dl.png)

Once you've downloaded, open up the application. On the left pane, you'll need to navigate down to **Connection > SSH > Auth**

![putty auth]({{site.baseurl}}/images/articles/ssh/putty-auth.png)

Now we're going to tell PuTTY where to find our private key. Click on the **Browse** button, and navigate to the safe folder where you saved your public key above.

![putty key]({{site.baseurl}}/images/articles/ssh/putty-privatekey.png)

Select your private key, and click **Open**

Back on the PuTTY pane, click **Session** at the top. You'll see all of the required connection information. You'll need to type in your hostname, port, and make sure the connection type is set to SSH. You can find the hostname and port information within your app information on the Nitrous Dashboard.

![box details]({{site.baseurl}}/images/articles/ssh/box-details.png)

Your hostname will look similar to `your_workspace.nitrouspro.com`, and your port will be be found just after the colon `:`.

Once you have everything setup with Putty you can save the session within the **Saved Sessions** tab.

Now, let's try out the connection. With your profile loaded, click the **Open** link at the bottom of the window. An SSH terminal should appear. When it asks you who to login as, just type "nitrous". This is the common user for free boxes.

    login as: nitrous

Then hit enter, and you should see the message:

    Authenticating with public key "rsa-key-[date]"

And we'll see that we're successfully connected to our box!

![connected]({{site.baseurl}}/images/articles/ssh/putty-term.png)

