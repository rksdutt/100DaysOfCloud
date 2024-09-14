---
title: "What is the VPC is 🛡️ !"
datePublished: Wed Jun 26 2024 22:20:57 GMT+0000 (Coordinated Universal Time)
cuid: clxwegc0t000509jwa7m6fh7b
slug: what-is-the-vpc-is
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1719440369069/2ce73095-3fb1-477d-8fe6-6cf8ce230201.png
tags: 2articles1week, aws-vpc

---

VPC stands for Virtual Private Cloud (VPC) is a private cloud computing environment inside a public cloud which is dedicated to our AWS account. It allows us or an enterprise to deploy its own private cloud-like computing environment on a shared public cloud infrastructure. With a VPC we can run codes, stores data, hosting websites, and do anything else we could do in an ordinary private cloud. VPCs can also provide networking functionality for cloud-based resources and services, such as Compute Engine virtual machine (VM) instances, Google Kubernetes Engine (GKE) clusters, and serverless workloads. It offers a certain level of isolation between different organizations using same the resources.

**Components of VPCs:**

**InternetGateway :** IGW allows us to extend its network to multiple locations through their connections. The IGW provides connectivity between different networks. In one word if someone from outside tries to access the application then first he/she have to deal with Internet Gateway of the application.

**Subnets :** VPC can be used to visualize and divide subnets in same size, which can helps us when we are working with same size of networks. The entire the vpc have a ip address range and inside of it for each project have to divide the ip addresses among them from the vpc ip address range.

**Route table :** In AWS VPC, route tables is the sets of rules, which are used to indicates where to direct the network traffic. The route table specifies the destination where to send the traffic through ip address. So the traffic which comes from the outside after accessing the IGW there is a load balancer who sends traffic through the route there is route table comes to play. Target can be internet gateway(IGW), Network Address Translator NAT gateway, virtual private gateway, VPC peering connection etc.

**Load balancer :** Incoming and outgoing traffic goes through the load balancer, which provides data traffic based on configured VPC policies and rules and it attached with the private subnet. When incoming requests matches the rules and policy, that policy defines how the load balancer provide its traffic through route.

**Security Group :** A security group acts as a virtual firewall for instances (EC2 instances or other resources) within a VPC. It controls inbound and outbound traffic at the instance level. Security groups allow us to define rules that permit or restrict traffic based on protocols, ports, and IP addresses.

**NatGateway :** Network Address Translation (NAT) gateways are used when high bandwidth, availability with low administrative effort is required. It stays always inside the public subnet of an availability zone. A NAT gateway can use to get access a private subnet using a public subnet. It updates the private subnet's route table so that it sends traffic to the NAT gateway.

**Network Access Control List (NACL) :** A Network Access Control List is a stateless firewall that controls inbound and outbound traffic at the subnet level. It operates at the IP address level and can allow or deny traffic based on rules that you define. NACLs provide an additional layer of network security for your VPC.

**InternetGateway :** IGW allows us to extend its network to multiple locations through their connections. The IGW provides connectivity between different networks.