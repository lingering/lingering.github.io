---
layout:     post
title:      Security Summary of the Zoom
subtitle:   
date:       2020-07-14
author:     Faxing Wang
header-img: img/kisspng-zoom.png
catalog: true
tags:
    - Cryptography
    - News 
    - Zoom
---
zoom was a minority commercial video meeting software until COVID-19 has became worldwide pandemic. Employees from a variety of companies have been working from home for the last couple of months. It is exactly the time that zoom has become popular due to the following three points:

easy to use, simply click mouse and share a link you can arrange a meeting.
easy to set up, zoom will set you up and prepare everything you need to hold a meeting
Free to start a meeting(under 100 people). THAT is the core competitiveness of this product. Public organizations such as civil service, universities, and NGOs use zoom to hold a meeting. Meanwhile, so many people use it for personal purposes. Because at that time there are no other products with good quality and free in the market.
Surprisingly and being expected, a software suddenly being used explosively can be a disaster, not only for the software user but also for the software vendor. The critical problem for this situation is that the small vendor doesn't prepare well and compare to functionalities of the software they don't usually take security and privacy at all, even give not shit about security. As Bruce Scheider concluded:

bad privacy practice: zoom collects it's users' data for profit in a sneak way and seems to clean that up before someone started noticing it. Dr. Searls noticed that on the web page of zoom there are astonishing amounts of third-party trackers on this website. Furthermore, zoom on iPhones were caught to send personal data to Facebook even the user didn't have a Facebook account.
bad security practice. It's not fair to criticize that zoom did not take security at all. zoom desktop version utilizes AES-ECB to encrypt traffic link which means that everything on servers of zoom is in plaintext. lack of end-to-end encryption and use CBC mode indicates that there is no one in this company understands cryptography.
bad configuration: zoom provides many options for its users, but the default configuration is terrible. The default length of meeting IDs is short and predictable, everyone can beak into a random meeting by simply random trial and surprisingly there is NONE access control of entering a meeting.
But to be fair we cannot blame on zoom otherwise it's too harsh for a startup company, their primary goal is undoubtedly to realize video conference service in high quality. Still, it's a bloody demonstration that severe security flaws could be the grave of a product. when bells ring, Thomas Gray begins to sing the song of ALL the research efforts of crypto and privacy-preserving.

Once again, it's hard to deny that Real-world crypto could be a disaster which for an illusional sense of security.
