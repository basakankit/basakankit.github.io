---

layout: post
title:  "Overview of Magma Architecture on Local Deployment Point of View."
date: 2026-03-03 
tags: [Jekyll, GitHub, 4G, Mobile Cellular Networking,Evolved PAcket Core, EPC, Magma Core, Blog, Website]
---

This is a collection of notes for better understanding of architecture of magam. I am still in progress to complete the blog.

Magma adopts many principles from cloud native application architecture and modern data center design to achieve a scalable and resilient architecture for implementing a mobile core network.   

![Magma-Overall-Diagram](/assets/magma-arch/magma-overall.png)
Magma is mainly divided in 3 different compononets for minimalised deployment point of view:  

**Acess Gateway(AGW)**: Implemnts the components of EPC which include SWG, PGW (data plane/data plane)and some aspects of MME (control plane). It manages the dynamic nature of UE like starting, ending, hand-over of new connection, metering etc. Provides the configuration interface for Magma via REST APIs.  



**Orchestrator (orc8r)**: 
 The orchestrator is the central point for configuration input, remote device management, and monitoring of a Magma deployment. It implements centralized management plane and aspects of control plane. For example, a new user can be added to the network via the API to the Orchestrator. A single orchestrator connects to multiple Magma access gateways.  
 It Collectively constitute FCAPS - fault management, configuration management, accounting management, performance management, and security management.
Implemented through docker on host OS to emulate the cloud enviroment.

![Planes
](/assets/magma-arch/orc8r.png)

The Orchestrator supports the following functionality:

    Network entity configuration (networks, access gateways, federation gateways, subscribers, policies, etc.)
    Metrics querying (via integration with Prometheus and Grafana)
    Event and log aggregation (via integration with Fluentd and Elasticsearch Kibana)
    Device state reporting (metrics and status)



The AGW reports runtime state to the orchestrator, while the orchestrator pushes configuration commands to the AGW. For example, the AGW is responsible for generating encryption keys (runtime state) so that a UE can securely communicate with the mobile core. At the same time, the Orchestrator is responsible for configuring the policy (config state) that allows a UE to connect to the network in the first place.

**Network Management System(NMS)**: 
Cloud based web UI for configuring and managing wireless network. It communicates to the rest of magma via api to orchestrator. 


![Planes
](/assets/magma-arch/planes.png)

---
Credits: [Introduction to Magma: Cloud Native Wireless Networking (LFS166)][LFS1666], [Private 5G: A Systems Approach][5G-book-link] 

[LFS1666]: https://trainingportal.linuxfoundation.org/courses/introduction-to-magma-cloud-native-wireless-networking-lfs166
[5G-book-link]: https://5g.systemsapproach.org/
