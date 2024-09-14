---
title: "Creating AWS Resources through Aws cli > EC2 instance"
datePublished: Thu Jul 18 2024 12:53:00 GMT+0000 (Coordinated Universal Time)
cuid: clyr9uomg000f09l7d89n0t22
slug: project-1-aws-cli-ec2-instance
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1722033456072/5cefa738-6296-4bdc-ab23-be97b8cb3691.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1722033607890/9af2809b-410a-4a49-a428-f5e827c80a31.png
tags: 2articles1week, aws-cli, ec2-instance, project-devops

---

**Creating EC2 instance by using AWS CLI.**

In this DevOps projects we are efficiently build and manage a simple cloud infrastructure service. Amazon Web Services (AWS) provides a powerful command-line interface (CLI) that allows us to automatically create resources like EC2 instances. Lets walk through the steps to create an EC2 instance using the AWS CLI.

Assuring that we have successfully installed aws cli.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721302779252/15891fbc-839e-4e1b-91ad-e6b7c101e6b9.png align="center")

Also giving assurance our AWS is configured successfully.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721303878599/7ead8ded-adde-4ca5-b909-c7834241c685.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721304093740/6afc1e3a-baaa-4a6c-b1de-97a897dde32b.png align="center")

Fisrt we have decide which **AMI** we want to use for our EC2 instance.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721305074751/88e89cd5-9210-48bc-b524-a665428c9d8f.png align="center")

Second Select an **instance type** based on our application’s requirements.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721305129898/c620e1af-a107-42c4-a7bd-1437862fe180.png align="center")

Third We have to select **security groups** act as virtual firewalls for our EC2 instances.

Fourth We have specify an existing or create a key pair to securely connect to your EC2 instance.

Then we have to give all these thing in this format below :

`$ aws ec2 run-instances --image-id ami-xxxxxxxx --count 2 --instance-type t2.micro --key-name MyKeyPair --security-group-ids sg-903004f8 --region=us-east-1`

This is a very basic project that's why we need to go with few simple things.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721306402048/3ade0de3-8be7-4509-b4e3-ccef2d9571fd.png align="center")

Here **bang** !!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721306452723/1e26338b-9633-4cf1-b1a8-adadbdc9b5f7.png align="center")

Make sure **deleting** aws resources after use is a skill count on cost-optimization.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1721317654168/bd0402ff-ebf4-43aa-98ca-9169750de203.png align="center")

Again this is a very basic project to be mentioned on profile. Creating EC2 instances using the AWS CLI makes the process smoother and more consistent in DevOps. This will helps us efficiently to deploy and manage EC2 instances for our applications on AWS. For more advanced settings and tips go through the [docs.aws.amazon.com](https://docs.aws.amazon.com/) for best practices.