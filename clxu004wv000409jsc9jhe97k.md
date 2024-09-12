---
title: "What is  AWS IAM (Identity Access Management)🔑 !"
datePublished: Tue Jun 25 2024 06:00:54 GMT+0000 (Coordinated Universal Time)
cuid: clxu004wv000409jsc9jhe97k
slug: what-is-amazon-web-services-aws-iam
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1719295353401/3b659b67-9b6b-46c7-8bdc-f179a0ad830c.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1719295376343/31eda3df-dfab-4636-81ff-54063cce7aea.png
tags: 2articles1week, aws-iam

---

Amazon Web Services (AWS) IAM stands for Identity Access Management. It is a service of Amazon Web Services (AWS) through it we can decide who can access and what can access of aws services and resources with the user, groups & policies. It is a lenthy process to create a IAM services for each user and give them access of particular service, it can reduce our productivity by go through it everyday and creating a user without attaching them to the groups and policies that would be waste of user creation, That's why we attach group and policies while creating a user.

So, IAM policies define a permission for the right users by which they are given access to aws resources. There are over a hundred policies in the portal.

Now comes to the groups there is people in the team in a company as a DevOps Engineer who join very frequently. So as a DevOps Engineer to automate the all process at once we created groups and attached policies so when a new DevOps Engineer come to the company we just need to create a IAM user and attach it to the group.

**Now its time to talks about Roles :** It is a service that provide access to conversation between two different aws account based on their permissions they have which makes them similar as a aws account user. Roles comes with temporary security credentials to whomever has ability to access to the Role.

**Role can use for:** One aws user from same account. Second a user from different account. Third aws service and fedarated identity.