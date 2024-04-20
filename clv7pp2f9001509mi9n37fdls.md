---
title: "Malware 101"
datePublished: Sat Apr 20 2024 06:22:01 GMT+0000 (Coordinated Universal Time)
cuid: clv7pp2f9001509mi9n37fdls
slug: malware-101
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713594050179/ea588a45-6014-4bb1-845f-c119d24c654a.jpeg
tags: security, malware, trojan, cybersecurity-1, valyria

---

I just realized that I have been up all night an even though I never expected to write any article this month as I have been trying to catch up with school and life, you can say that well the article caught me. So let us get into it shall we?

## HOW IT STARTED

*This would typically be getting your setup ready, however i didn't need any set up for mine initially, as my malware was on my local host <mark>( crazy I know but please see this as a lesson to keep your pc away from other people, no matter who they are to you, as even though they may not mean any harm, they can visit a site that can mean harm for you, anyways I figured out that I may as well share the story)</mark> So here I am at 10pm reading for my exams, when I remembered that I had a private repo on GitHub, which was also my final projects in one of my courses this semester, and I needed to edit the read me file to be something wayyy understandable, so I remember a flowchart I had created about the website I made, and in looking for it, I stumbled upon a very weird looking zip folder, and some bells go off in my head. So here is where the story began*

## STEP 1

So I started with first ensuring I wasn't using the same network for my VM and my host machine, to do that I simply isolated the network of my VM from my host, next you'd want to also start a new snapshot for that purpose so after you're done you can just use a new Snapshots, and of course used a VPN, if you don't know how to set up a VPN on you machine, I highly recommend this [Article](https://protonvpn.com/support/official-linux-vpn-kali/), and following the steps.

Once this is done, I highly recommend using 2 temp mails to send the malware from your host to you VM, and then installing it on you VM ( please only do this once you've followed the steps above)

## STEP 2

Since this was a dynamic Analysis, it was wayy easier, so what I did was to head over to VirusTotal, and there I got my reports. I like to do a Rerun of what ever I am dealing with, so I also went to AnyRun and Hybrid Analysis, and as suspected I had a malware, to be more specific it was a RAT ( Remote Access Trojan)

### RATs

Remote Access Trojan is a type of malware that give attackers full control of a desktop or mobile device so that they can silently browse applications and files and bypass common security such as firewalls, intrusion detection systems, and authentication controls. Now to attackers this is so helpful because they get information to what you are doing because they practically have surveillance or the ability to gain unauthorized access to a victim PC. Remote Access Trojans often mimic similar behaviors of keylogger applications by allowing the automated collection of keystrokes, usernames, passwords, screenshots, browser history, emails, chat lots, etc.

The name of the RAT that was installed on my device is Valyria and I the earliest articles I saw about it dated back to 2019, so I promptly followed the detections and luckily my anti malware was enabled so I don't have any RAT running any backdoors on me -yet-

You can check out my reports :

* For my report on [Hybrid Analysis](https://hybrid-analysis.com/sample/b8070e7657dd1b5bccb4a8016b9dfd81bc7459087527b9adf8e50b9cdc820803)
    
* To learn more about [Valyria](https://success.trendmicro.com/dcx/s/solution/1117788-emerging-threat-on-valyria?language=en_US)
    
* To see the [screenshots](https://github.com/Afukam/Malware-Analysis.git) I got during my mini lab session
    
* To preview my [AnyRun](https://app.any.run/tasks/35520356-fdb0-4322-ac1c-4f59c3a0d006/) report