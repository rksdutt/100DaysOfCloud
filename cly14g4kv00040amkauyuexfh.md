---
title: "What is Route53 ⛙ !!"
datePublished: Sun Jun 30 2024 05:39:42 GMT+0000 (Coordinated Universal Time)
cuid: cly14g4kv00040amkauyuexfh
slug: what-is-route53
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1719725863969/d5143b77-5208-41d1-8202-af8b381d6a0d.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1719725935709/dbbf88fe-a8e9-437b-875b-7531f00fc0a2.png
tags: 2articles1week, route53, aws-routing, route53policies

---

Amazon Web Service provide us Route53 Domain Name System(DNS) as a service. It is designed so that users can access websites such as [amazon.com](http://amazon.com) and other Internet applications such as [LinkedIn](http://linkedin.com) by translating domain names into IP addresses that computers can easily connect through Internet.

Before comes to the Route we have to gain proper knowledge about **DNS**.

## **What is DNS !!**

DNS who resolves domain name to the ip address. In one word DNS is like saved number in phonebook by name whenever we need call our Mother instead of write the 10-digit on dial-pad simply type ''**Ma**" or "**Aai**" and call her that's like instead of write or memorize the ip addresses we simply type the domain name cause dns server also take cache request which allow multiple user at same time in the same website. Thats what all from my side !!

Now comming back to the Route53 again...

Route 53 uses a network which is globally distributed server which maintain global servers traffic, sending requests to the AWS region closest to the user's location. The service automatically scales to handle upon workloads and gave us better performance. Route 53 can route users to various AWS services, including EC2, as well as non-AWS infrastructure.

Here are few routing policies that can be used in **Route53:**

**1\. Simple routing policy:** The Amazon Route 53's general routing policy is a simple round-robin policy that allows us to configure standard DNS records without using special routing, such as latency. This is typically used when routing traffic to a single resource such as a web server on our site.

**2\. Weighted routing policy:** The Amazon Route 53's weighted routing policy distributes traffic to different resources based on percentage of total traffic flow. Weighted routing allows us to support multiple resources with a single domain name [Amazon.com](http://Amazon.com) or subdomain [www.amazon.com](http://www.amazon.com) and choose the amount of traffic to route to each resource.

**3\. Latency routing policy:** The Amazon route 53 latency routing policy is used when resources are located in multiple AWS regions and traffic needs to be routed to the region that provides the best latency. This routing policy helps response DNS queries by routing traffic to the data center with the lowest network latency.

**4\. Geo-proximity routing policy:** The Amazon Route 53's geo-proximity policy is used to route traffic to resources based on users' geographic locations and resources. To use geo proximity routing traffic flow must be used. A bias function is used to expand or shrink the size of the geographic region from which traffic is sent to a resource. For bias we need to specify a positive or negative integer from 1 to 99/-1 to -99.

**5\. Multi-value response routing policy:** The Amazon Route 53's multi-value response routing policy is called as a simple routing policy but in response to DNS queries it returns multiple values like IP addresses for web servers. Route 53 will be used to response DNS queries with upto eight randomly selected healthy records.

**6\. Failover routing policy:** The Amazon Route 53's failover routing policy is used to create an active/passive set-up. One site is active and serving all traffic at a time while the other disaster recovery (DR) site is in standby mode. Primary site health is maintained by route 53 using health checks.

...thank you !!