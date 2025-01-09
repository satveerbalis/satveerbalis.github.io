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
- Enable a single network interface on the ubuntu desktop and configure it with a static ip address and attach it to the 192.168.8.1 (enp0s8) surface of the gateway router. Set up the DNS IP address as 1.1.1.1 and 8.8.8.8.
- Enable three interfaces on the Ubuntu Gateway router (enp0s3, enp0s8, enp0s9 in this case). 
- Configure the the first two with a static ip and the third one as nat to allow internet access.
    - use this for the configuration ***sudo nano /etc/netplan/00-installer-config.yaml***
- Enable IP forwarding and create a routing table to allow routing of traffic between the gateway router interfaces
    
    -Use this to achieve it
    - sudo iptables -A FORWARD -i enp0s8 -o enp0s9 -j ACCEPT
    - sudo iptables -A FORWARD -i enp0s9 -o enp0s8 -j ACCEPT
    - sudo iptables -A FORWARD -i enp0s3 -o enp0s8 -j ACCEPT
    - sudo iptables -A FORWARD -i enp0s8 -o enp0s3 -j ACCEPT
    - sudo iptables -A FORWARD -i enp0s3 -o enp0s9 -j ACCEPT
    - sudo iptables -A FORWARD -i enp0s9 -o enp0s3 -j ACCEPT
    - sudo iptables -t nat -A POSTROUTING -o enp0s3 -j MASQUERADE

    SAVE THE SETTINGS WITH
    - sudo apt install iptables-persistent
    - sudo netfilter-persistent save
    - sudo netfilter-persistent reload

-configure the application server with a static ip address and attach it to the 192.168.108.1 (enp0s9) surface of the gateway router

TEST CONNECTIVITY
- ping the application server from the ubuntu desktop
- ping the ubuntu desktop from the application server
- access the internet fom the ubuntu desktop.

PROBLEM AND SOLUTION
Unable to access the internet.
This was solved by varifying the 
