---
title: "Email Analysis 101"
datePublished: Sun Jun 04 2023 00:29:07 GMT+0000 (Coordinated Universal Time)
cuid: cligoqsc7000409ji2ub3g35v
slug: email-analysis-101
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/LPZy4da9aRo/upload/6ba760e0aa46d8f10a1c93b21df8d70b.jpeg
tags: email, phishing, cybersecurity-1, technical-writing-1

---

From time to time, we all get phishing emails–if you don't, I'll like to believe that you are doing some magic–sometimes they made us wonder if they think we are stupid, but sometimes, we just have to give it to cybercriminals. Whether it is legit mail, or phishing mail a little email analysis 101 never hurts right?

**BEFORE YOU CLICK THAT LINK/OPEN THAT FILE**

According to recent research carried out, 91% of cybercrime begins with successful phishing to an unsuspecting victim, and 96% of that came from emails-this does not mean that there are no blockers there are many steps, filters and security for your email providers(i honestly don't know what they are called) put in place just to prevent you from receiving these emails, however, some emails still manage to pass through these filters, hence still receiving some of these phishing emails. So before you click that link claiming you have won some money, or open that "bank statement" file even when we both know that your bank doesn't issue you one you might one to read this article.

## **THE BEGINNING**

Once upon a time, I received a mail for an employment opportunity which had its perks attached to it- quite a decent sum, with decent conditions- but I decided to do a mail analysis on it, I mean what could go wrong right? Well, I was about to find out.

### STEP 1

Download the email, before you can even start your analysis, you'd want to make sure that you have a sample file of the email you plan on analyzing, so go ahead and download that mail.

### STEP2

An email header analysis would let you know: who the mail is from, their IP address, the return path and so many other things. To do this open the downloaded email in a text editor-if your mail has a file, please do not open it as it may be malware-copy the content and paste it into a mail header analyzer, I use [mailheader.org](http://mailheader.org) . This will help you know who the mail is from.

**STEP2a**

You can take it a step further by analyzing the IP address, visiting ipinfo.io or urlscan.io from there you can get the whois of the sender.

### STEP3

By now, you have gotten a hint from the header, so it's time to go to the body of the email to analyze that as the malicious content is usually in the body of the mail.

**STEP3a**

If it is a link, you can view the source code of this link, using a URL extractor, extract the URL.

*OR*

You can copy the URL and visit services that analyze malicious files to get the hash and report such as virus total, Talos intelligence etc.

**STEP3b**

If it is a link, you'd want to visit a malware analysis sandbox such as Anyrun, hybrid-analysis, joesecurity etc, to run an analysis on the file.

## THE ENDING

I hope you have as much fun following this step as I have writing it I wrote a sample piece on [Here](https://link.medium.com/0hDI2wVhlAb).

Feel free to like, share and even leave any comment if you have.

Thank you