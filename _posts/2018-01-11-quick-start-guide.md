---
layout: post
title:  "A SANDBOX NETWORK"
author: sal
categories: [ Jekyll, tutorial ]
image: assets/images/12.jpg
featured: true
hidden: true
---
**CREATING A SANDBOX NETWORK**

REQUIREMENTS 

- An Application Server
- A gateway router
- An ubuntu desktop vm

AIM

To have a network that permits the following 
- Communication between the ubuntu desktop and the gateway router on subnet 1
- Communication between the Application server and the gateway router on subnet 2
- Routing of traffic between the interfaces of the gateway router
- Internet access through the NAT interface of the gateway router.

PROCEDURE 

VIRTUAL MACHINE SETUP
- Download and install an Ubuntu Desktop VM, An ubuntu server (Acting as the gateway router) and an Application server (Wordpress server used in this case).

VIRTUAL MACHINE CONFIGURATION
- Enable a single network interface on the ubuntu desktop and configure it with a static ip address. Set up the DNS IP address as 1.1.1.1 and 8.8.8.8.
- Enable three interfaces on the Ubuntu Gateway router (enp0s3, enp0s8, enp0s9 in this case). 
- Configure the 

"When You Don't Have a Memory, How Can You Remember Who to Trust?"

The mind-warping film opened with a hospital patient Simon Cable (Ryan Phillippe) awakening in a <span class="spoiler"> hospital with little knowledge (amnesia perhaps?) of what had happened, and why he was there, etc. He was told by attending Dr. Jeremy Newman (Stephen Rea) that it was July 29, 2002 (Simon thought it was the year 2000 - he was confused - he heard a doctor say 20:00 hours!) and that he had died for two minutes from cardiac arrest following the near-fatal accident -- but he had been revived ("You're as good as new").</span> Dr. Newman: "Simon, this is the 29th of July. The year is 2002. And your wife, whose name is Anna, is waiting outside." 

(The doctor left off four crucial additional words, revealed in the film's ending.) (Spoiler: Simon had died and was not resuscitated!).

A major clue to everything that truly happened was the scene that played next under the credits - hospital staff failed to bring a patient back to life with a defibrillator after a car accident. Chest compressions failed and there was no pulse. A second major clue was provided by hospital orderly Travis (Stephen Graham): <span class="spoiler">Everybody dies. No mystery there. But why and how everyone dies. Now, there's a mystery worth solving. Probably the biggest mystery there is.</span>

#### So how do we do spoilers?

```html
<span class="spoiler">My hidden paragraph here.</span>
```
