---
title: "Siem Lab  2"
datePublished: Mon Mar 25 2024 05:00:39 GMT+0000 (Coordinated Universal Time)
cuid: clu6hc9nn00020ajwar4qc8bh
slug: siem-lab-2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1711062656283/4563e9ba-09d7-4717-a117-055c695fc8d7.png
tags: security, splunk, cybersecurity-1, homelab, cybersec, siem, labs

---

For this SIEM lab, I will be using a popular SIEM tool called Splunk, if you haven't checked out my previous [article](https://afukamwrites.hashnode.dev/siem-lab-1) as it starts from the basics, you can also check out the [series](https://afukamwrites.hashnode.dev/series/siem-homelabs) , and if at any point you get lost, no need to fret, just check out my [SIEM](https://github.com/Afukam/SIEM-lab-series.git)

repo on GitHub, it has all the images taken during the labs, and the folders correlate with the articles. Now let's get into it.

Splunk is a powerful tool used for security, observability, business management, and so many other things. Now since this is a Security Information Event, we would be focusing on the security function of Splunk, now I'm going to assume that we've set up our distro and our virtual machines, so I'm just going to get right into it.

## STEP 1

The first step would be to get a [Splunk account](https://www.splunk.com/en_us/download/splunk-cloud.html). To do so, you can simply click on the profile menu, sign up and it will take you to your dashboard. Once logged in, you would be introduced to a variety of options. Because we are dealing with security, we would want a package that is for security, so head over to the products menu and click on Security. Under products you are going to see a wide range of products available. Now this description is just to provide you with a basic overview of the function of each product.

Splunk Enterprise Security is so helpful for detection

Splunk SOAR is helpful for incident response

Splunk User Analytics is helpful for detecting anomalies in user behaviour.

Splunk Attack is helpful for analyzing and responding to malware.

For this lab, I would be using Splunk Enterprise, so go ahead and select Splunk Enterprise on Splunk Enterprise, you get a 60-day trial period.

Click on get my free trial, now select the Linux option, there you would see three different options

.deb: is for Linux that are from a Debian distribution

.rpm: is for Linux from Red Hat distribution

.tgz: is a zip for all Linux distribution

Since we are using Kali Linux, which is a Debian linux distribution, you can go ahead and select .deb4

## STEP 2

Once your package has been installed you can find it in the home under downloads, `home/downloads`

To install, right click the package and select the open terminal here, then input command `ls`

Now you'd also input `sudo dpkg -i ./splunk package` and then once the unpacking is done, you should also do `ls /opt` and if you notice, you'll see your Splunk right there now `sudo /opt/splunk/bin/splunk start`

Now at this point just scroll down and you'd have to agree with the license and then after which, you will create an admin username and password. So it's going to be opened on port 8000, so you'd want to get you Ip address : 8000 and paste it in your browser that is if you aren't using the same network, or alternately you can just copy it from your terminal, and paste it into your browser and you'll be shown Splunk where you just enter your password and login.

## STEP 3

Now we'd want to add data from a source, with Splunk Enterprise, you can add data from 3 sources:

Your computer, in form of file upload

Monitor, in terms of files and ports on your Splunk interface platform

So we are going to go back to Splunk and Install Universal forwarder because we need to add data from our System( as at the time this article was published I was using a windows), however you can use whatever system you have, so go ahead and select your OS from the drop down and I will be installing the 64bit for my system as that is more convenient for me.

So as with Splunk, you'd want to accept the terms and conditions and then proceed to install it

Once your installation is complete, Splunk universal forwarder has an md5 of <mark>11d0550baca9ebcc882d4800f6471d72</mark> so you can check to be sure you've downloaded the right Splunk Universal Forwarder, once you've checked and you are sure that you've downloaded the right size, you can then proceed to initialize it.

At some point you'd have to set up your forwarding ip address and port and receiving ip address and port.

Simply run `ifconfig` on your kali linux and `ipconfig` on your Powershell, now once you've gotten your ip addresses, your kali linux is your **receiving index.** It collects, indexes, and correlates real-time data in a searchable repository, while your local pc is your **forwarder**. It forwards logs, network events, and other machine data to Splunk Enterprise for indexing. Then proceed to finish installation.

Using `windows + r` , type in this command s`ervices.msc` to check if splunk is running.

Then using Powershell type in the command Test-NetConnection -Computername Splunk\_IP -port 9997

Alternatively, you can decide to install it on your Kali Linux(For some reason after installing it on my windows, I decided that I only wanted to work with my Kali) so for that, simply download the Linux option, from the list select the .deb option then proceed to install it. As always, verify your md5, and once that is correct, simply go back to your desktop, select home, downloads, and on the splunk universal terminal, right-click and select the open terminal here option then you'd want to `sudo dpkg -i splunkforwarder-version.deb` this is cause by default the `dpkg` will install the universal forwarder in the /opt folder next you'd want to accept the license using `sudo /opt/splunkforwarder/bin/splunk start --accept-license` here you would be prompted to create a user name and a password. After which because we want our universal forwarder to start on boot just simply `sudo /opt/splunkforwarder/bin/splunk enable boot-start -systemd-managed 0`

So now that we've installed Universal forwarder, you'd also want to connect it to the instance using `sudo /opt/splunkforwarder/bin/splunk set deploy-poll (the depolyment server)` your version of Splunk is running on. Once done, we must restart the forwarder using `sudo /opt/splunkforwarder/bin/splunk restart`

Once this is done, you can just go back to your Splunk instance and log in

On the dashboard, you can see the logs there, from your system. Alternatively, you can upload your logs. For this I would be using [LetsDefend Log](https://app.letsdefend.io/training/lesson_detail/add-data-to-splunk) . So, download the zip file in your kali Linux and unzip it. Afterwards go to Add data on Splunk and select the upload the log you want to analyze.

## STEP 4

Now using queries you can search for data in logs, (I was rushing at this point so I skipped the images), and you can also view reports which are saved searches and send an email to yourself when you are done.

With Splunk you can also generate dashboards, manage users, and view health status.

I highly recommend practicing with

[LetsDefend room](https://app.letsdefend.io/training/lesson_detail/introduction-to-splunk)

TryhackMe

And viewing the series on GitHub.