---
title: "SOC282 — LetsDefend"
datePublished: Wed Jan 29 2025 20:40:30 GMT+0000 (Coordinated Universal Time)
cuid: cmdplo440000y02icb4jihngf
slug: soc282-letsdefend-da067a70167f
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1753857830467/e97489be-3439-4a30-853a-d5a4e8ba0de1.png

---

Hey I took a long break from everything cybersecurity and writing for personal reasons, maybe I would write about it one day, maybe anxiety won’t let me, but anyways I guess I am back.

I would be writing an investigation for SOC282 in LetsDefend, LFG.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857804052/5c010753-fe4e-4a26-a8d7-ed4e0496c1dc.png)

Event Details

I highly recommend making notes of what ever information you have before actually working on any Alert.

Click on the <<< button to Create a case, you should be prompted to see something like this.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857805351/41baf297-412f-4f57-87de-e3b1de3dd4c8.png)

EventID

Once you click on start Playbook, you would see these questions :

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857806463/7545119f-5537-4af4-b8a3-f8afcc8c560f.png)

SOC ANALYSIS COMMON QUESTIONS

#### TRUE POSITIVE, FALSE POSITIVE, FALSE NEGATIVE, TRUE NEGATIVE

Now questions like this are actually so important to ask, as even tho we have Alerts and Triggers set in place, it doesn’t mean that all alerts are True positives, as sometimes we may have alerts that aren’t necessarily true or alerts that should be a cause for concern. Think of it this way, you have a group of employees, and they were randomly sent emails containing gift cards, and because of the triggers set in place, your system creates alerts for them.

Employee John ( received a gift card for participating in a psychology survey , and after our investigation, we actually saw that it was a legitimate link, there were no malicious attachments, that would be a **FALSE POSITIVE**).

Employee John II ( received a gift card, clicked the link and we were notified, after our investigation, we found out that it was actually a malicious link, that would be a **TRUE POSITIVE** ).

Employee John III ( receives a gift card, we weren’t alerted but maybe after a while we noticed some suspicious activities which we investigated, after which we discovered it was actually a malicious link, that would be a **FALSE NEGATIVE).**

Employee John IV ( receives a gift card, when investigating John III, we decided to check all links employees have received in 24 hours, after we investigated, we found the link to not be malicious that would be a **TRUE NEGATIVE)**

All these are important as not only do they help us detect possible compromise, they actually help SOC analysis update their Alert triggers.

Back to our investigation.

Head over to Email Security and paste the the source email address in the search bar.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857807493/3e9bd509-6666-437d-9736-12f7da13bfbf.png)

Email overview

Email details

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857808806/5570da4e-dd91-4d3a-ab80-8da70859c525.png)

Email continuation

This helps us answer our first question:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857809847/fd5e5b4e-7b5a-4146-b0d1-ee7260318cd5.png)

Question I

After which we would then have to do some Malware Analysis.

Personally I try to use at least 3 sandboxes just to be sure

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857811202/551d367f-9273-4d26-84f8-428bb2a2635a.png)

Question II

I would be analyzing the URL, as it actually contains the same link to download the attachment

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857812556/e4fc3e01-7075-44de-97fa-57a3fb21fd17.png)

Virus Total

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857813878/a08bfa15-4164-490b-819d-22b1535ea50e.png)

Hybrid Analysis

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857815387/ea2c6b86-76d1-4cb4-b91d-845b7446ab29.png)

AnyRun

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857816757/6309b44e-e3a6-4afa-91a8-c4b9bdb2339f.png)

Question III

From the Device action we see it was allowed, which shows it was delivered to the user.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857818018/b9a32c4a-1c35-4715-af7a-34690501d6bc.png)

QUESTION IV

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857819131/3cd11b77-3d3b-4ccf-98fb-68e4bf7abada.png)

QUESTION V

I decided to do a SIEM query for Felix

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857820385/d247e4d8-9bc4-4808-a2c5-9df1862c2be8.png)

SIEM query

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857821853/2d2a80f3-4582-4f4b-b545-e139bdd28ee4.png)

Raw Log

From here we see that there is an exchange with the source address , over at End Point Security, we get to see some interesting information :

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857823063/fbd2f162-caf4-48aa-9518-7d7d51c2e65c.png)

EndPoint Security

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857824218/035bbb85-73d0-47e4-bff5-a0fd531ce08a.png)

We see that there was some interaction, and a lot of processes that show us it was run.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857825660/6a2683c2-d5ed-4273-9a3b-fa171c3ce727.png)

Question VI

So we go ahead to contain it

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857826979/9245dacb-df79-4722-a0a5-baf48cf47f5b.png)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857828016/b48713d1-fba1-4ddc-98b2-fded39a77a3f.png)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857829225/c783acc7-23fc-4cc8-96a5-9e62cb46c3f5.png)

So go ahead to leave any comments or notes and you are done

The results of my sandboxes are attached below, thanks for dropping by.

Anyrun : [Analysis](https://app.any.run/tasks/6883e734-565e-4487-950a-f9e015455aa3)

VirusTotal : [Analysis](https://www.virustotal.com/gui/url/bb6460ae86e964854fcb2c379bb937f63611e6be3a25ded254e5ad4e9498b278/details)

[Hybrid Analysis](https://tinyurl.com/2782mhvl)