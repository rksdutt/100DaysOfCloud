---
title: "AWS S3 : The Complete Solution for Hosting a Static Websites"
datePublished: Mon Sep 09 2024 15:58:18 GMT+0000 (Coordinated Universal Time)
cuid: cm0v6t4h4000x09l7bkf5h8he
slug: aws-s3-the-complete-solution-for-hosting-static-websites
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1725910871145/35773637-3cef-4376-9aed-a5c831986e62.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1725903497128/b56232e2-28e9-4d9b-ae37-10b1d1142366.webp
tags: s3, static-website, aws-s3, aws-s3-for-beginners

---

Amazon S3, or Amazon Simple Storage Service, is a scalable, highly available, secure and cost-effective with enhanced performance cloud-centric service provided by Amazon Web Services (AWS). It lets us store and retrieve any kind and volume of data from anywhere on the web.

S3 allows us for static website hosting but if your app is developed using Angular, React or HTML then you can do that here. However, you cannot host sites written in such languages as Python, PHP, Node.js or Next.js which involve server side rendering or server side data processing. All you need to do is create an application build package and upload the same to the S3 bucket.

**Prerequisites of this Project are :** First, Having an S3 bucket in your appropriate region or we can create it together.

Second, Make sure to have a local Index.html file and an image you want to place on S3 both in the same location.

Step 1 : So just search for S3 in the AWS console. Click to create a bucket. A trick here is that the bucket name should be globally unique.

Step 2 : If you want to access other people on this bucket if you have policies then allow ACLs or Enable it. If not then click on ACLs disabled.

Step 3 : Untick the Block Public Access and acknowledge that. After all that step just hit create Bucket.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725895014557/7a65e55f-5ee6-4951-9d62-0c2a5c72ed62.png align="center")

Step 4 : Move inside of the bucket and upload object just hitting by Upload from local.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725895240710/416d459f-b706-421a-9911-f05aae92cd74.png align="center")

Step 5 : After uploading of these object we will try to access or host our website through object URL.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725897018915/d24a47c3-4e48-402a-b805-63f3a7d45fb2.png align="center")

Step 6 : Here after trying with URL we found that our URL is not accessible. So, weneed to make accessable first. Here above go to the Permission we are going to edit the Bucket Policy by just clicking on Edit & hit Policy generator. Then follow the steps like that,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725896082804/1a7ddcb2-0095-48ec-bc06-d8bb2962338d.png align="center")

Select Policy type : S3 Bucket Policy

Principle : \*/all

Action : Get Obeject

ARN : arn:aws:s3:::&lt;your-bucket-name&gt;

Then hit Add Statement and put copy the JSON file and put policy script in S3 Bucket Policy then hit save changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725897146167/fdfae144-6202-49f4-8a89-cbcd0e7b456c.png align="center")

Step 7 : After the save changes we need to enable Static website hosting. Go to the Bucket Properties and hit edit static website hosting click enable, put index document and hit save changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725897078040/18b08a28-5fbc-4295-a13e-c67b90438a4d.png align="center")

Step 8 : After all these steps we got the static website link and if we head to this link. And here we can successfully see our website. And Remember to waive off all the services you have created.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725897044332/f1407c9f-a55e-4b2d-a8af-e53871dc2c65.png align="center")

Static Websites can be effectively hosted using AWS S3 since it is not only the most cost-effective but also user-friendly. Therefore, cloud computing environments can have consistent performance regardless of how many users are accessing them. Great for both developers and companies aiming to ease deployment processes as well as increasing their visibility on the web.

Thank yu !!