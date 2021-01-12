---
layout:     post
title:      concepts in MPC literatures
subtitle:   some key words in MPC protocol
date:       2020-09-14
author:     Faxing Wang
header-img: img/kisspng-hedge-maze-labyrinth-puzzle-mural-5adfcb35c56c91.7130978515246159898087.png
catalog: true
tags:
    - Cryptography
    - Paper 
    - Multi-party computation
---
# Some Unfriendly Terms

It's pretty clear that in recent years TOP Crypto and Security conferences have accepted many papers in discussing a variety of topics of multi-party computation. For someone who are not follow this field continuously may felt confused by the some of the term used in the paper
  - Honest Majority for Malicious Adversaries(Crypto18)
  - Adaptive, Static, Proactive  
  - Information-theoretic security, statistical security 
  
If you are new to this field and lack of strong background in the theory of computing YOU might get stuck from reading the very beginning of a paper. In this blog, I will try to clarify as many key concepts as I know in understanding MPC papers.
First of all, let's review some of the components of an MPC protocol, which are functionality, security model, adversarial model, and communication model. I will then present all the terms used in cryptographic research or to be more specific in MPC research according to the categories listed above.
### Functionality
SFE(Secure Function Evaluation) and PFE(Private Function Evaluation) are two common terms when considering the functionality of an MPC protocol. Basically, SFE means a group of parties participating in a collective computation with their private input while guaranteeing the privacy of their input. In contrast to SFE, when parties in PFE getting into a computation, the input of the protocol not only can be their data but also the functionality of the protocol which is the function f that will be computed together. More specifically, the difference between the SFE and the PFE is that in PFE the protocol function f is among the inputs. But one thing to keep in mind is that essentially PFE equals SFE in theory.
### Security Model
For Security Model, I mean what kind of adversary to defend against in considering an MPC protocol, which means the power of the adversary that we assume when discussing the security of the protocol. Roughly we usually see three different adversaries. First is computational security, which means we consider a PPT(probabilistic polynomial-time) adversary. Well, for A PPT adversary what the author trying to say is that the adversary is able to run any polynomial-time algorithm while preserving the ability to produce randomness. It's easy to tell we constrain(bound) the ability(power) of an adversary to define security.
Besides, when relaxing the constraint we can get statistical security, now an adversary has unlimited power of computation while he still can only distinguish the real/ideal world with statistical close advantage( negligible ). In this model, we still allow the posterior probability of guessing of the adversary to be slightly larger than the a-priori.
It's natural that we can relax the concept further by bounding the advantage of guessing without the negligible possibility, which we call perfect security-- a protocol is still secure even with unlimited power adversaries no matter how hard they try.
### Adversarial Model
> Behavior

In the secure model, we discussed the abilities of one adversary. The further topic is that what is the behavior of an adversary might presenting in an MPC protocol. Basically, there are three kinds of adversaries, semi-honest(passive), malicious(active) and convert. A semi-honest adversary is an adversary who follows the protocol honestly while the malicious one can behave arbitrarily even abort the protocol. The covert one is a little subtle which indicates that there is a possibility that catches the adversary attempting to break the protocol which is not assumed in the active model.
> Corruption Pattern

Except for the behavior of the adversary, the security of a protocol can be different according to the adversary behavior pattern, which means they are static or dynamic. In a static model, all the corrupted parties in the protocol are fixed even before the protocol starts. Oppositely, the behavior of the adversary can be very different in the context of a dynamic environment. There can be an adaptive adversary who is able to corrupt parties during the execution rather than corrupts a set of fixed parties from the very beginning. He can choose whom to be his target and when to corrupt arbitrarily or based on the view of the execution. To note that once a party is corrupted, it remains corrupted ever since. So another kind of dynamic adversary is to corrupt a party for a certain amount of time. Thus in the proactive model, the honest and the dishonest parties can transfer into each other during the execution. Sometimes we also call this mobile adversary since the adversary is not stable.
> Number of Adversaries

What we discussed above we mentioned the corrupted parties, as it is clear that we overlooked a key factor when describing adversary which is the amount of the adversary. It's a vital parameter that not only impacts the security achieved in the protocol but also the whole performance of the MPC system.  Usually, when designing a protocol against malicious participants we care about the bound of adversaries that a protocol tolerates.
Let t denotes the number of adversaries and n is the total number of parties

* Honest majority means t<n/2
* Dishonest majority usually means t>=n/2, sometimes up to n-1
* In special case(two-party computation), No majority

### Communication Model
    * point-to-point channel: there are secure/private channels between each pair of parties.
    * broadcast channel: an authenticate channel which can be used as a broadcast by every party.
    * synchronous: all messages sent by any party will be received by others with an upper bound delay.
    * asynchronous: messages send by parties can be delayed without bound.


