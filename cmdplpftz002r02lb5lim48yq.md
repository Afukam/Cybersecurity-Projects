---
title: "Phishers Of People"
datePublished: Mon Jan 30 2023 13:42:45 GMT+0000 (Coordinated Universal Time)
cuid: cmdplpftz002r02lb5lim48yq
slug: phishers-of-people-19e7bbd601bd
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1753857892586/43b790d7-cdb2-4c68-ab87-6a87078bee42.jpeg

---

Recently I started having a weird obsession with emails, phishing and the likes, I don’t know how it happened but it did. Feel free to check out my article [https://link.medium.com/7HHEDylaZwb](https://link.medium.com/7HHEDylaZwb) on phishing as it can come in handy.

After a hectic search for case study samples, I finally got some.

Let’s get into it shall we?

My friend — I’ll call him X — got a wonderful opportunity some days ago, I mean what’s more awesome than getting a full-time remote job, company car and an above 5 figure salary, sounds like a dream come true, cause come on, I’ll gladly trade hopping buses for this.

The perks are just so appetising right?

So I started my usual game of spot the oddities from the mail, just by checking the header.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857880553/9b92ec1a-112c-4d97-aafd-5f3a1c416dc3.jpeg)

Employment offer, mail header.

The first question, why will you send me an employment offer with a personal email address, they keep saying GenZs are woke, but what sort of... anyways

My first red flag was the email address, but I decided to push it by doing some email header analysis.

### Steps involved:

If you’re using your desktop, you can just;

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857881660/c9e2f944-0117-4d32-b1c2-645d6a102b46.jpeg)

*   Click on the toogle
*   Scroll down to View entire message
*   Alternatively, you can choose to download the mail, and open it using any word text editor.
*   Copy the header of the mail and paste it in any email header analyser, I use mailheader.org

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857882961/f5c0771b-b8f8-459e-92c9-0b46c9ad515a.jpeg)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857884202/f51d5e5b-6800-46db-96d9-6c6f316a0510.jpeg)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857885511/7e13df9d-f351-400f-9526-252afc971431.jpeg)

Header details

*   The first thing to observe is the Return-path ( ie who does the answer or the response of my mail go back to)
*   Then I checked the company used as a case study and while there is a company called COLEXA HEALTHCARE LTD, it is a Nigerian company which has no branch in the US, so that was another dead giveaway
*   Then I also decided to get the location of the scammer

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857886372/4d8ce61c-7410-421e-9c60-7acad1f32501.jpeg)

### The body of the mail

#### After I was done with the header, I decided to check the body.

Body of mail

At first glance, you may still decide to go ahead and click the link, just to pull some sleeves buttttt...... I don't advise that cause some links are, let me use the word poisonous, but any way.

I didn't find any typographical error, so I decided to jump right into into it

*   The first thing was using an email body analyser cause I wanted to get the file hash. I used virustotal.com for this

### NOTE IF YOU JUST INPUT THE WHOLE MESSAGE, THERE IS A HIGH CHANCE THAT IT WILL BYPASS THE MALICIOUS LINK

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857887327/ec7ed10e-3980-4541-86ac-09cb86d114f6.jpeg)

This is what I got when I just put in the whole file

So it's safer for you to just copy the link and search link. And when I did, these were the results

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857888409/51bfa6f4-eb52-45b4-ad83-e944de61e0dc.jpeg)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857889906/d242c4d4-6235-4eb6-88d4-a962b3216c82.jpeg)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753857891191/c7942f27-c6bd-4f21-853d-c5b53bfb2ea4.jpeg)

So yeah, I’ll just stop it there, I could further look for some things but I think I can just leave it as it is .

However, the question as to if these tools are sufficient still lingers in the minds of some.

I hope you enjoyed reading it as I enjoyed writing it, please feel free to reach out to me if you have any queries.