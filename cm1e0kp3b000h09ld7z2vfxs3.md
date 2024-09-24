---
title: "Establish two Virtual Private Clouds (VPCs) and configure peering between them so they can ping each other using their IP addresses. 0.0.0.0"
datePublished: Sun Sep 22 2024 20:11:24 GMT+0000 (Coordinated Universal Time)
cuid: cm1e0kp3b000h09ld7z2vfxs3
slug: establish-two-virtual-private-clouds-vpcs-and-configure-peering-between-them-so-they-can-ping-each-other-using-their-ip-addresses-0000
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1727022337136/22863ac8-cdca-42ac-918b-21fc74b0ac09.jpeg
tags: aws-vpc, subnet, vpc-peering, cidrblock, routertable, insternetgateway

---

### What is VPC !!

At a high level, a virtual private cloud (VPC) can be described as a subset of a larger public cloud designed specifically for private use. Users can perform similar operations like storing data, running code, and hosting websites, among others, as they do in their personal private cloud.

Network access control lists (ACLs) on a subnet-by-subnet basis. The ACLs specify who can access which resources and how they can connect to them.

User Control over Resources Users maintain control over their resources with in a VPC through AWS Identity and Access Management (IAM). This means they can determine who gets access to the VPC, as well as what rights those have once inside.

**Monitoring :** The VPC provides necessary tools for performance management via Amazon CloudWatch, which is an online application for monitoring performance of cloud applications.

**Elasticity :** A VPC gives you the ability to provision resources dynamically based on demand using AWS services such as AWS Auto Scaling and Elastic Load Balancing.

**Interconnectivity :** The region’s data centers are interconnected, which enables you to communicate with any of your resources within a single region very fast regardless of their physical location in that region.

**Security :** A VPC is more secure than traditional data centers because it provides logical separation of customer environments in terms of network traffic flow into and out of them.

### What is VPC Peering !!

VPC peering refers to how two virtual private clouds (VPCs) are connected in such a way that information can pass between them using their private IP addresses. It is a definition of a fast transfer method that does not delay its operation too much and is an efficient way to distribute things like website servers and other online storage facilities.

**How it works :** Creating VPC peering creates a direct network route between two VPCs that avoids the need for Internet, VPN, or AWS Direct Connect.

**How to set it up :** When establishing a VPC peering connection, you request a peering connection from one VPC and it is accepted by the owner of another VPC.

**What it’s used for :** One of the main uses of VPC peering is to create multi-VPC architectures and share resources across organizational boundaries.

**Common challenges :** There are several challenges associated with VPC peering such as overlapping IP ranges, misconfigured route tables, security group issues, and non-transitive peering limitations.

Let’s Begin Here ,,,

Here we’ll be Create two VPC name Demo and Prodcution and other related resources resources to build a peering connection and ping eachother with their IP.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727019865024/a6fc20ee-8878-4c90-80c6-363175f8b578.png align="center")

### Prerequisites are :

Having an account on [https://aws.amazon.com/](https://aws.amazon.com/) and a proper Internet Connection.

**Step 1 :** Log in to the console.

On the Navigation Search for VPC and hit Create VPC to create one. With a name and a valid CIDR block. Know more to the [https://cidr.xyz/](https://cidr.xyz/) here you can define how CIDR block distributed and get the limits of CIDR. Then hit on Create VPC.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727019626611/b1f32f5f-0549-4a5c-add3-069a7eddb189.png align="center")

**Step 2 :** Here we can see our VPC created successfully with available status.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018876194/ee1cb7e5-8fd4-4082-81c9-32d0b79ef692.png align="center")

**Step 3 :** Here after creating a VPC we will create a Subnet. Here on the navigation below VPC click on Subnets and hit to create one. Just choose the VPC under which you are going to creating this Subnet and give a name to your Subnet. Give a proper valid CIDR block for Subnet remember that the Subnet CIDR shouldn’t be the same otherwise CIDR will overlap. So Choose a different bits with unique IP of your Subnet.

**Step 4 :** After successfully creating a Subnet. Here its time to create Internet-Gateway for your VPC. Just give a name to your Internet-Gateway and that’s all hit Ceate Internet-Gtaway.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018880104/d8c56bf6-bb81-489e-81c1-32245c7d64ac.png align="center")

**Step 5 :** Now it’s time to Attach the Internet-Gateway with your VPC. Just go the Action and click on Attach VPC then select your VPC then hit Attach Internet-Gateway.

**Step 6 :** Here we can see our Internet-Gateway successfully attach with our VPC.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018885468/323bbb5e-ec89-4d0b-862d-78c19c226f81.png align="center")

**Step 7 :** After successfully created a VPC and Internet-Gateway and successfully attach with VPC. Now its time to create a Route table for route the traffic to the VPC. On navigation click on Route Tables then give a name to your Route Table and select your VPC and hit on Create a Route Table.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018888476/493b72e5-7a08-4d30-a9f9-b4f4cb93d7a8.png align="center")

**Step 8 :** After successfully created a Route Table then select your route table then go to edit subnet association then add your subnet and save the association.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018893264/f26a44fc-fc00-4a89-bf32-c9190b4cbd49.png align="center")

**Step 9 :** After saving subnet association. Now it’s time to edit the route and attach your Internet-Gateway with your route and save changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018898763/f8ebaaf6-1621-414e-9130-5026522045b4.png align="center")

**Step 10 :** Now its time to create another VPC for our Peering. With a name and a valid CIDR block. Know more about CIDR go to the [https://cidr.xyz/](https://cidr.xyz/) where you can define how CIDR block distributed and fixed the limits of your given CIDR. Then hit on Create VPC.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727019622540/6fd66f30-b6a7-4615-bf23-11f5b163d50d.png align="center")

**Step 11 :** Here after creating a VPC we will create a Subnet. Here on the navigation below VPC click on Subnets and hit to create one. Just choose the VPC under which you are going to creating this Subnet and give a name to your Subnet. Give a proper valid CIDR block for Subnet remember that the Subnet CIDR shouldn’t be the same otherwise CIDR will overlap. So Choose a different bits with unique IP of your Subnet.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018903088/e44f7ee8-158d-4bc8-bc7b-b1a95d73ae96.png align="center")

**Step 12 :** After successfully creating a Subnet. Here its time to create Internet-Gateway for your VPC. Just give a name to your Internet-Gateway and that’s all hit Ceate Internet-Gtaway.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018907189/609c0a66-a424-46a0-a33b-642406842dbb.png align="center")

**Step 13 :** Now it’s time to Attach the Internet-Gateway with your VPC. Just go the Action and click on Attach VPC then select your VPC then hit Attach Internet-Gateway.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018912507/c375806a-a7ab-4cc4-8c8b-afd9cf906d52.png align="center")

**Step 14 :** After successfully created a VPC and Internet-Gateway and successfully attach with VPC. Now its time to create a Route table for route the traffic to the VPC. On navigation click on Route Tables then give a name to your Route Table and select your VPC and hit on Create a Route Table.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018915895/db7b9569-301c-4411-932d-760ae6e824ad.png align="center")

**Step 15 :** After successfully created a Route Table then select your route table then go to edit subnet association then add your subnet and save the association.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018918664/62a7c1d0-a1e1-4127-9cfa-f260d51d6bec.png align="center")

**Step 16 :** After saving subnet association. Now it’s time to edit the route and attach your Internet-Gateway with your route and save changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018922763/403f8c89-82c2-475d-a4c9-c1d0cd1f6377.png align="center")

**Step 17 :** After Creating all that resources like VPC, Subnet Internet-Gateway, Route Table. Now it’s time to Create two different Instance one-by-one with editing networks when configuring the instance according VPC and subnet then hit Launch Instace.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018926503/089340dc-51a2-429b-85fd-9920588f4d9f.png align="center")

**Step 18 :** Here we came on the main chapter of our AWS VPC Project. Here on the VPC portal on navigation, below we can find VPC Peering then hit on that to create one.

**Step 19 :** Just give a name to your Peering Connection, then select the requester VPC and define the account and define the region, then select the accepter VPC then hit the Create Peering Connection.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018930402/60a69f7e-b94c-4fbc-9634-153bc8334f03.png align="center")

**Step 20 :** After successfully created the Peering Connection. Hit on Action and Accept the request of VPC Peering.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018933885/231fd415-54b3-461a-8811-fb89646c2518.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018937879/5b2be5ed-3c0b-45fe-ac69-83c94f34f4e8.png align="center")

**Step 21 :** Here we can see the Peering Connection successfully eastablished between two VPC. Demo-VPC and Prod-VPC are connected Now.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018940812/f5bbeb80-bf50-4feb-a2b2-ca9ee44a5a7b.png align="center")

**Step 22 :** After all that we simply go to the Demo Route then hit on edit route and add destination of Prod CIDR and select target peering connection.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018947761/9bf525b8-4192-4a9b-9a0d-f601514e6cac.png align="center")

**Step 23 :** Here we will do same things on Prod Route then hit on edit route and add destination of Demo CIDR and select target peering connection.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018947523/7a5f4f93-3a45-44ab-99c8-5fd7331791cf.png align="center")

**Step 24 :** After all that edit the security groups Demo-Instance and allow All ICMP rule source will be Prod-VPC CIDR and save the changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018949607/b8f455d2-beb3-4037-9422-6563fb27a22e.png align="center")

**Step 25 :** Here we will edit the sucurity group of Prod-Instance and allow All ICMP rule source will be Demo-VPC CIDR and save the changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727034779496/39302a7f-dd1b-4309-8957-4b655d69af6d.png align="center")

**Step 26 :** Here we will ssh into both of our instance and ping each other with their IP and Lets see what happens next.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018955173/a21f7f25-342c-402d-802d-424a583ec6dd.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727018958320/e48ed1e6-0320-448d-af46-b64e273bff7a.png align="center")

**Step 27 :** Here we all saw everything is working well. If they Ping with their IP they are getting Pong.

Overall, Setting up a pair of virtual private clouds (VPCs) and setting them up to peer allows for easy interaction. The ability to ping each other's IP addresses ensures that resources between two VPCs can effectively communicate with each other. This will help improve network flexibility and improve resource management in different environments.

Happy L = earning 😊

thank Yu !!