---

layout: post
title:  "Understanding Mobile Cellular Networking"
date:   2026-03-03 
tags: [Jekyll, GitHub, 4G, Mobile Cellular Networking,Evolved PAcket Core, EPC, Magma Core, Blog, Website]
---

In this blog, I have compiled a list of fundamental concepts to better understand an EPC in this case [magma core][magma-website]. 

One of the main reason I have compiled these information is to better understand magma components and help me debug miscongurations in local magma deployment and succesfully simulate a network, during my mentorship in magma project. And if you are reading it hopefully it will help you too.

The cellular network consists of:  
1. Radio Access Network (RAN)
2. Mobile Core (EPC in 4G)
3. UE (User Equipment) i.e device for eg. mobile phone, router with cellular interface connecting to network.

![High-level cellular network architecture](/assets/understanding-magma-images/highLevelOverviewNw.png)

#### Mobile Core is partitioned into:   
**User Plane** is responsible for managing all the actual data that you use, like streaming videos, browsing, or sending files. It’s responsible for transmitting user data, such as internet browsing, streaming, and voice calls, between your device and the network.

**Control plane** is responsible for functions such as identifying subscribers, determining what services they are entitled to, and tracking usage for billing purposes. 

#### Radio Access Network (RAN) Functions
A useful way to understand the RAN is to look at how a single base station reacts to the arrival of a new UE (user equipment such as a mobile phone).   

First, a base station establishes the wireless channel for a subscriber’s UE upon power-up or upon handover from another station.

Second, the base station establishes Control Plane connectivity between the UE and the Mobile Core and forwards signaling traffic between the two. This signaling traffic enables UE authentication, registration, and mobility tracking.

Third, for each active UE, the base station establishes one or more tunnels to the Mobile Core User Plane component.

#### Mobile Core Overview - 4G

Mobile core functions include both user plane components (SGW and PGW) and control plane components (HSS, MME, PCRF). 

![Mobile-Core functional blocks](/assets/understanding-magma-images/functionalBlocksMobileCore.png)

##### Control Plane (CP) Components:

MME (Mobility Management Entity) - Tracks and manages the movement of UEs throughout the RAN. This includes recording when the UE is not active.

HSS (Home Subscriber Server) - A database that contains all subscriber-related information.

PCRF (Policy & Charging Rules Function) - Tracks and manages policy rules and records billing data on subscriber traffic.

##### User Plane (UP) Components:

SGW (Serving Gateway) - Forwards IP packets to and from the RAN. Anchors the Mobile Core end of the bearer service to a (potentially mobile) UE, and so is involved in handovers from one base station to another.

PGW (Packet Gateway) - Essentially an IP router connecting the Mobile Core to the external Internet. Supports additional access-related functions, including policy enforcement, traffic shaping, and charging.

##### Mobile Core Authentication

![Mobile-Core Authentication](/assets/understanding-magma-images/mobileCoreAuth.png)

1. The UE contains a sim-card containing secret code which intializes communication with base station as a suscriber. 
2. The base station forwards it to contol plane i.e MME which initiates authentication protocol with UE.  
3. (a) Further contol plane instucts SGW(Serving Gateway) i.e user plane (is initialized) to assign ip to UE and other parameters. 
(b)(c) And initalizing encrypted channel between base station and UE.
4. Enabling UE for access to encrypted channel with user plane.  

Signalling: Process (1 to 3) before connection between UE and user plane is established.

##### Mobility

This is the process when a UE moves form affinity of one base station to another. In between the process where a UE reconnects with another base station, going through the above process, a downtime is encounterred between the sessions.

  

In the next blog I will go in depth of architecture magma centric to understand what is happening when simluating a telecom network with softwares like UERANSIM, srsRAN, Packetrusher.

---

Credits: [Introduction to Magma: Cloud Native Wireless Networking (LFS166)][LFS1666], [Roadmap to LTE - Protocol Stacks][Rodmap-LTE], [Private 5G: A Systems Approach][5G-book-link] 


[magma-website]: https://magmacore.org/
[LFS1666]: https://trainingportal.linuxfoundation.org/courses/introduction-to-magma-cloud-native-wireless-networking-lfs166
[Rodmap-LTE]: https://www.telecomhall.net/t/roadmap-to-lte-protocol-stacks/30327
[5G-book-link]: https://5g.systemsapproach.org/
