---
title: "SOC114 — Malicious Attachment Detected (LetsDefend)"
datePublished: Sat Aug 24 2024 22:37:37 GMT+0000 (Coordinated Universal Time)
cuid: cmdploqky002m02lbhgznh9kb
slug: soc114-malicious-attachment-detected-letsdefend-3ccf7268a49d
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1753857859712/e95f776b-648e-4c23-af99-c73af50d089d.png

---

Hello, so I will be working on LetsDefend SOC114: EventID 45 so let’s get into it

The first thing you’d want to do is familiarizing yourself with LetsDefend practise page and all the menu options seen-Feel free to check out this blog- as we would be going through different tools on there.

Event ID 45

Select EventID 45, click on the profile button to claim the event, before claiming the profile I love to take note of things like emails, IP addresses and device as it helps me get a final outcome of the event.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857838550/df16d838-8500-4e04-b893-82f970d4eaa2.png)

Incident Details

Click on Start Playbook but beware, shits about to get real from there.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857840020/3ef625f8-a27d-476f-a0bd-d0a0d8d2d269.png)

Shit just got real

The first question is if there are any attachments or URLs. Remember when I said to take notes of the email, that knowledge comes in handy here. So, head over to the Email Security menu, on there you’d want to put in the email we’ve saved in the search bar, and you should get a log that shows the email history containing all emails with that address.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857841485/79881b2a-228e-47ed-aeec-6cf45a52d598.png)

Email Log

Click on the log and you’d get the email sample

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857842846/a0672a9a-a114-4b9c-804e-aecd0ec13383.png)

Email body

Notice here that there is a md5 showing that there is an attachment and a password to access that attachment, you can copy the hash value you are seeing as it would help in our investigation.

Now the next prompt would be you analyzing the hash value you got from the email sample.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857844275/9b0ee8b6-2a5c-40fc-b72f-95b5186da84f.png)

You can go ahead to any sandbox, for this walkthrough I would be using VirusTotal, HybridAnalysis and AnyRun.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857845619/ef7e75a2-5eea-4118-b6e4-a57a863a529b.png)

Virus Total

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857847200/4c49aaff-e40f-490f-9b3e-c8bb093810cf.png)

HybridAnalysis

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857848505/9423212b-d2c1-4865-a3d6-1a5e1525d2ef.png)

AnyRun

Feel free to check out the reports on here, [AnyRun](https://app.any.run/tasks/66c81867-239a-45c3-b9bb-4d3e80364962/), [HybridAnalysis](https://www.hybrid-analysis.com/sample/44e65a641fb970031c5efed324676b5018803e0a768608d3e186152102615795), [VirusTotal](https://www.virustotal.com/gui/file/44e65a641fb970031c5efed324676b5018803e0a768608d3e186152102615795/details). Since it’s malicious we are going to go ahead and check Malicious, and it would take us to the next prompt

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857850256/af7602ae-d02f-4fa4-befe-d378c7269563.png)

Mail Delivery

Now if you look back at the device action at the beginning of the event, it shows Allowed, meaning that the email was delivered.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857851385/0c1c177a-fd8c-4cf4-8424-40231d3e0961.png)

Delete Email

Next we’d want to delete the email so click on the delete button, to delete.

We’d also want to know if someone opened the Malware, so go back to the report on VirusTotal, in the relations you’d see a list of Indicators of Compromise (Think of IoC as artifacts left behind that show intrusion)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857852816/29be01c1-0479-4308-a6ff-d3ef5bc2c17a.png)

IOCs

From here we can get the contacted domains, Contacted Ip addresses and bundled files, so to know the indicator comprise we would want to check on our end point (While working on the event, I check all IP addresses and contacted domains on the endpoint security, but for this walkthrough, I would only work with the contacted endpoint)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857854143/d54dcc5a-04ba-4c94-825b-743e84d65681.png)

Endpoint

On here we can see that Richard PRD interacted with one of the IoCs, so we can also go ahead and click yes.

We’d also want to contain the user machine on the EDR, so click on the containment toggle then select next.

We’d also want to save all the artifacts (I'd like to think of this as data gotten during an event)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857855649/b1877fc5-73c7-42e7-a834-cdf516767473.png)

Also, you’d want to leave comments, on there.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857856717/df681f7f-a086-4f02-9410-1405e5499639.png)

Then you’d want to finish the playbook

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857858271/2a698491-2bc6-4af5-be2c-671d23c2a16a.png)

Finish playbook

Then we’d also want to close the Alert, and here we are given 2 options, a true positive and a false positive.

A true positive is a successful identification of a threat/ attack

A false positive is a false identification of a threat or alert.

So, from our incident, we’ve seen that we have a True positive