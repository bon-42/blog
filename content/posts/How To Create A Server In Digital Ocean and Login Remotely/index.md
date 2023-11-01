---
title: "How To Create A Server In Digital Ocean and Login Remotely"
date: 2021-08-03T10:59:15-04:00
---

Digital Ocean is a cloud service provider that is gaining a lot of attention from developers in recent years. When I was doing my research in hosting a remote server for one of my project, It frequently came as a recommendation. And, despite being my first time setting up the remote server all on my own, it turned out to be a very easy process. And, if I can do it, you can too. I will show you how easy the process is and in no time you will have your own remote server where you can host your application. I will be creating a linux based server in this tutorial. So, let’s dive in:

Step 1. Create An Account
Go to Digital Ocean and create your account.
Once your account is created, login with your credentials
You can skip this process if you already have an account
Step 2. Create A Project
On the left side of the home page, you will see + New Project option under Projects
Fill in the Create New Project form with the name for your project, description, and purpose
Click Create Project
That should create a new project which you will be able to see it now under your Projects section on the left of your home page
Click on your project name you created earlier. In my case it’s TestProject
Step 3. Create A Linux Droplet
Click on the Get Started with a Droplet
You will be shown with choices of different linux images. I am going to create an “Ubuntu” one but if you prefer something else, that should be fine.
Click Standard plan under Choose a plan section. I suggest starting with the lowest plan and scaling up as your project gets bigger. This is one of the very nice thing about cloud computing. You don’t have to put aside big chunk of money for the resources which may go unused. You can easily scale up when the time comes for your project to have more resources.
Next, you can go directly to Choose a datacenter region and pick a datacenter closest to your web traffic. In my case, I’m picking New York
We will now have to create SSH keys so that we can remotely login to our linux server once it is created.

Click on New SSH Key
Go to your terminal and type ssh-keygen
It will ask you to pick a location where you want to save this key. I usually just select the default location
Next it will ask you to pick and confirm the passphrase. This is an extra security measure. If you are just trying out, you can leave it empty
It should look something like this

bon@MacBook-Pro  ~  ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/bon/.ssh/id_rsa):
/Users/bon/.ssh/id_rsa already exists.
Overwrite (y/n)? y
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /Users/bon/.ssh/id_rsa.
Your public key has been saved in /Users/bon/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:rd6CpZVyiUalphaNumericsf9KPSj387G+9La0pf bon@MacBook-Pro.local
The key's randomart image is:
+---[RSA 2048]----+
|   o . ..        |
|. * o o+         |
|o=.= ++ o        |
|++. ==++ .       |
|o ooooO.S        |
| o.. O . .       |
|  ..ooo.o .      |
|    ..=o.o .     |
|     o==o E      |
+----[SHA256]-----+
Type cat ~/.ssh/id_rsa.pub
Copy the key and paste it in the Add Public SSH Key box

Give a name to your ssh key. I am calling mine Test Key

Click Add SSH Key

Click Create Droplet

It will take few sconds and you should be able to see a new linux server

Next, we will login to this new server from our local computer -PUT IMAGE HERE

Step 4. Log In To Your Remote Server
Click on the newly created linux droplet within your project. Since, we didn’t give any name to it, it’s name should star with something like ubuntu-s-4scpu-8gb-sfo-103
Now on your left side you will see different options. Click on Networking
Under Public Address, copy the IP Address of your server.
Next go to your local terminal and type ssh root@YOUR_IP_ADDRESS
It will give a prompt of Are you sure you want to continue connecting (yes/no)? and just hit enter
Next, it will ask you to enter the password. If you didn’t created one during the ssh key creation, just hit enter again.
If everything worked fine, it will log you into the remote server and display a message like this:

Welcome to Ubuntu 18.04.2 LTS (GNU/Linux 4.15.0-52-generic x86_64)
* Documentation:  https://help.ubuntu.com
* Management:     https://landscape.canonical.com
* Support:        https://ubuntu.com/advantage

System information as of Sun Jul 14 02:10:57 UTC 2019

System load:  0.0                Processes:           107
Usage of /:   0.6% of 154.90GB   Users logged in:     0
Memory usage: 1%                 IP address for eth0: 168.77.4.202
Swap usage:   0%

0 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

root@ubuntu-s-4scpu-8gb-sfo-103:~#
Congratulations, you just created a cloud server and remotely accessed it. Please let me know if you find any errors in this article. Happy Coding!
