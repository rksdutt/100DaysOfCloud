---
title: "How to create a IAM User and Users Group . So we can add to users on AWS Console"
datePublished: Mon Sep 09 2024 20:43:31 GMT+0000 (Coordinated Universal Time)
cuid: cm0vgzwzq000h09lhf2id8bky
slug: how-to-create-a-iam-user-and-users-group-so-we-can-add-to-users-on-aws-console
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1725949012385/c472c566-5fea-4ea8-aa14-288a5257fa19.png
tags: aws, devops, aws-iam-policies

---

For accessibility and identity management is an important aspect in today’s world because it gives assurance that only the right authorized users have access to systems, data and applications. One of its major functions is preventing unauthorized access to data resulting into loss of sensitive information (data breaches). This is more crucial for cloud computing and working from home managing a team.

**Why we uses IAM here are some for the resons of IAM in short:**  
**Protection against identity-based attacks :** IAM prevents identity-based attacks and data breaches facilitated by unauthorized personnel with excessive access.  
**Preservation of digital identities :** IAM protects digital identities through standards and protocols that ensure user credentials are safe and guarded against any invasion.  
**Appropriate employee access :** IAM provides that relevant employees in possession of vital information can access it as well as having security clearances matching their respective jobs.  
**Support for federated identity :** The majority of IAM frameworks incorporate federated identity which entails having one electronic identity recognized as well as stored by different systems.  
**Authentication is required :** IAM makes it compulsory for users to authenticate themselves before having the right to enter a system or software program.  
**Governance is included :** This contains a governance model where there exists creation and proper management of all the needed policies, processes, and standards that touch on IAM functionalities.  
**Regular audits are required :** This requires regular checks so that the least privilege principle holds firm.

Prerequisites are : Having a AWS Account.

Step 1 : Search for IAM on console. Create users group and then create user. On the navigation we choose Users Groups and then click on it. Then give a name of you group hit and give it the permission you wanna access here we will use AmazonS3FullAccess then we hit create user group.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725913820146/489d3d5a-8730-4ab5-821f-83627e079d42.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725913830546/f442fd07-aab8-48f6-b06d-9ff63735370f.png align="center")

Step 2 : Again on navigation hit Create user hit to create and give a name for it and give it a valueable password if the user want to change the password then tick the box User must create a new password at next sign-in.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725913987193/c36a5b3e-eefa-4870-8afd-af01c373baed.png align="center")

Step 3 : Set permission for your user and if you wanna add this user on this group and tick the below group and hit next.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725914083037/1e906002-af30-411e-87e7-b02a38872679.png align="center")

Step 4 : Here is our IAM user has been created.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725914111313/aa7b3c7f-1190-4e39-9912-62396d7b2c24.png align="center")

Step 5 : Try to login itto it with another browser.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725914179716/9efc3460-7e07-48d8-9ed1-2d31ef100611.png align="center")

Step 6 : If you successfully managed and created for your user for a particular access by this,,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725914264125/fc5bb0b3-a4c7-4058-b4df-cbbb6aff3a4c.png align="center")

Here we learn about how to create a AWS IAM Users and Groups for a particular top permissions.

Thank Yu !!