---
title: "Siem 101"
datePublished: Tue Jun 13 2023 18:08:49 GMT+0000 (Coordinated Universal Time)
cuid: cliulk8ou000309jy535efjof
slug: siem-101
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686679684839/59abc303-d251-46e2-a476-80712ed73cd2.png
tags: logs, cybersecurity-1, siem

---

SIEM is a technology solution that supports threat detection, compliance, and security management through the collection of analysis of security events. Now, you may be wondering, if there's a technology that helps in doing all these things, or what relevance is my role as an SOC analyst...well trust me, you get to work with SIEM products.

The thing is there are different SIEM tools from different companies, and while each product Is unique, it doesn't make the others less.

## HOW DOES SIEM WORK?

Now you know SIEM is used for threat detection, but the thing is how does it actually work, how do we detect threats? In fact, what does threat detection even mean?

**Threat Detection vs Threat Intelligence**

Threat detection is a proactive process used for detecting unauthorized access to network data and resources by both internal and external sources while Threat intelligence is a way of looking at signature data from previously seen attacks and comparing it to enterprise data to identify threats.

So how does one even detect threats or even know what threats are?

Well, the answer to that question is data, threats come in different forms, in order not to pass off the wrong thing as a threat or to even skip a threat you'll need a collection of data known as logs, this step is known as log collection.

## LOG COLLECTION

We know the process of collecting the data is called log collection, but what does a log even mean? In computing, a log file is a file that records either events that occur in an operating system or other software runs, or messages between different users of a communication software. But the thing about this log collection business is that there are 2 ways to go about it;

**AGENT**

Logagent is a modern, open-source, light-weight data shipper with out-of-the-box and extensible log parsing, on-disk buffering, secure transport and bulk indexing, what this means is that in this method, you make use of software

**AGENTLESS**

The agentless log-sending process is sometimes preferred as there is no installation and update cost. Think of this as a DIY

Okay now you have collected the log, the next step would be to put it together

## LOG AGGREGATION

This step is basically you combing the connected log together, doing the whole modification, filtering, enrichment, parsing

Once you've done that you'd want to keep the logs in a safe place

## LOG STORING

This is where the SIEM storage comes in, you'd want to store your logs in SIEM products based on speed, price storage etc

Wow, you have successfully inputted data into your SIEM product, this would then be used to set up alerts for you.

SOME SIEM PRODUCTS INCLUDE:

SPLUNK

Qradar

Sentinel... just to mention a few

I hope this was a nice read for you, as much as I enjoyed writing it, feel free to eave your queries, share and like the article.

Thank you