---
title: "What is NACL ♾️ 🚫 in AWS !!"
datePublished: Fri Jun 28 2024 11:40:24 GMT+0000 (Coordinated Universal Time)
cuid: clxymg9xl00080akzba9z8g27
slug: what-is-nacl-in-aws
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1719574404464/10360a52-78e6-4366-93d5-9424fa065207.png
tags: 2articles1week, aws-nacl

---

Whoa! Whoa! Whoa! Wait !! Not a Sodium Chloride, NACL stands for Network Access Control List where security group is working at instance level and it is a optional layer of firewall that control traffic in or out in subnet level for our VPC. It is a additional security layer that act as a firewall to control traffic in and out of one or more subnets. NACL rule are allow or deny access to a subnet level. The rules are applied differently depending upon the scenario, such as when EC2 instances are in the same subnet or in different subnets. Multiple subnets can be associated with a single NACL, but a subnet can only be associated with one NACL at a time.

Suppose there are 22 or more ec2 instances in one subnet and all of them security ports open for all traffic, instead of applying security config or assigning rule for each instance just add NACL for automation. And security group cant deny traffic it only have one feature call allow If NACL configured like only access specific port there our organization will deny all the traffic which are flowing in and only allows the NACL defines traffic. So instead of applying security config for each instance just add NACL for automation.

**Types of NACL :** NACL comes in with two types First one is **Default NACL** and the Second one is **Customized NACL Or Non-default NACL**.

**Default NACL :** This default NACL have one "allow-all" and one "deny-all" rule for both traffic flow. The allow-all rules are processed first. A default NACL also comes with a specific rule that's associated with a rule number and that can't be modified or deleted. When a request doesn't match with the associated rule number, it can simply deny.

**Customized NACL :** A customized network access control list (NACL) in the cloud is a user-defined access control list that allows us to customize network security policies. This is also known as a non-default NACL. When we create a custom NACL, it contains a deny-all rule for both traffic. The deny-all rule contains an asterisk(star) instead of giving a number.

...thank you !!