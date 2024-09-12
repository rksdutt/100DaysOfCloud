---
title: "What is Security Group 🛅!!"
datePublished: Fri Jun 28 2024 04:42:54 GMT+0000 (Coordinated Universal Time)
cuid: clxy7jd8s00030amcdp72hdh3
slug: what-is-security-group
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1719549685892/cd84ea09-e506-4bfd-8cf5-e35d41c4e421.jpeg
tags: aws-securitygrooup

---

A security group in Amazon Web Services (AWS) is a virtual firewall that controls traffic to and from basis. Amazon Ec2 instances and the other AWS resources. Security groups filter incoming and outgoing traffic at the IP and TCP layers based on specific ports and source and destination of the IP addresses. They are similar to network access control lists (NACLs), but security groups control traffic at the instance level, while NACLs control traffic at the subnet level. As a security group it can manage both inbound and outbound traffic.

**What is Inbound Traffic and Outbound Traffc in Security Group !!**

**Inbound Traffic :** Basically when we deploy our application inside the Ec2 instance, users will try to access our application. If we want to allows anything we can add a specific port in the traffic rule. The security firewall rules helps it to define which types of traffic are allowed to pass through the secured ports and access to the application. This traffic can be directed from a web browser, or an email client or application requesting for a service like FTP, SSH, API, web server to our network. The traffic that doesn't originate from within our network but wants to enter the area of our network is inbound traffic. So in one word this traffic which is flowing into our application call inbound traffic.

**Outbound Traffic :** Traffic which is flows from our applicaton to outside that is outbound traffic or traffic leaving the instances associated with the security group. The outbound firewall rules are that define the traffic allowed to leave your network through secured ports to reach valid destination. In one word when our application tries access a trird party tool that comes under outbound rules it can prevent potentially malicious software from sending data out, and stop requests sent to malicious websites and untrusted domains. The traffic which is flowing from our application to the secured destination call outbound traffic.