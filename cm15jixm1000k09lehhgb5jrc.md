---
title: "AWS Intelligent Tiering for S3: Efficient Cost Management and Performance Optimization"
datePublished: Mon Sep 16 2024 21:51:59 GMT+0000 (Coordinated Universal Time)
cuid: cm15jixm1000k09lehhgb5jrc
slug: aws-intelligent-tiering-for-s3-efficient-cost-management-and-performance-optimization
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1726520554328/012b6be0-0bac-4292-ac97-8f3ac8556940.jpeg
tags: s3, cost-optimisation, s3-configuration

---

Amazon Simple Storage Service (affectionately (otherwise) called **AWS S3**) is AWS’s object-based file storage service. As we deep dive into the AWS S3 major storage classes in today’s blog entry, let us also focus on S3 updates released over the years, the various reasons for designing and optimizing these storage classes, as well as how easy-to-configure S3 lifecycle policies can be set up to leverage S3 automation and enjoy substantial discounts on cloud storage.

It stands out as one of the most commonly used file storing services from Amazon; it includes data lakes, issues with big data as well as logs hosting, static web site hosting among others like server less applications or CI/CD artifacts. However, due to its simplicity in installation and usage an individual can encounter problems of cost optimization because of its scalable storage. The data is distributed across storage classes often not intended for it leading to huge financial surges.

AWS Pricing : To comprehend the optimization of costs aimed at S3, one has to thus comprehend the pricing structure of S3 buckets.  
  
AWS S3 pricing has some major components.  
  
Storage Capacity: This is the primary component of your S3 expenses and it represents all the sizes of documents, objects and files in your AWS S3 bucket.

Data Transfer : You only charge for AWS S3-useful resources stay within the same region as their S3 buckets since data transfer through S3 to the internet or another Region.

Request : In addition to the size of the S3 bucket, you are charged on all API calls made to the S3 bucket. These include PUT, Copy, Post, List, Get, Select, lifecycle transitions and data retrievals. Deletion and Cancelation requests do not incur any charges. It is only Upload API Requests that you are charged for in Glacier while all other requests such as LISTVAULTS, GETJOBOUTPUT, DELETE† are exempt from payment. Additionally, 90 days is the least time a file should stay in Glacier since deleting it before then incurs an additional fee.

All in all, it is vital for cost optimization that resources utilizing or consuming AWS S3 be placed within the same region as the S3 bucket.  
  
With regard to pricing, we can now move on to AWS’ various options in terms of S3 storage classes.

**S3 Standard :** It is the most commonly used and configured S3 storage option. Provides quick and easy access with milliseconds of data retrieval times. However, in terms of cost, it is the most expensive storage option.

**S3 Intelligent-Tiering :** If you routinely work with files that are more than 128KB, S3 intelligent Tiering is the perfect instance class for you. This storage class automatically classifies your objects into the most optimized storage class depending on the usage and access patterns. Depending on how frequently files are checked out, S3 will automatically move them between infrequent access and AWS Glacier (which is the S3 long-term archive solution).

**S3 Infrequent Access :** For files and objects that are not requested or accessed frequently you can cut storage costs by moving them to S3 infrequent Access. The catch, however, is the retrieval costs, while still only offering millisecond access times, the costs are almost double compared to standard S3.

**S3 One-zone Infrequent Access :** Provides a flat 20% storage discount at the cost of redundancy, NOT ideal for any storage requirements that need reliability such as critical database backups, key logs, and documents, you would probably not be using this storage class.

However, this is a particularly useful storage option for low-utilization storage content that can be rebuilt in case of data loss.

**AWS S3 Glacier :** AWS standard archival storage option, Glacier provides a resilient storage option for a fraction of the cost of S3 Standard (**0.023$ Per GB** for S3 standard vs **0.0036$** **Per GB** for Glacier, a **145%** per cent cost difference). The catch? Data in the S3 Glacier class requires you to settle for a retrieval time of anywhere between one to 12 hours. The storage class is perfect for objects that need to be retrieved occasionally but still need to be stored securely and safely.

**AWS S3 Deep Glacier** : Providing even more storage discounts over S3 Glacier, Deep glacier provides even lower storage costs (0.00099$ per GB), and there is a retrieval time requirement of around 12 hours for object restoration. Due to the extremely low cost, this storage class is perfect for storing compliance data that is required to be stored reliably and securely for a long time yet only needs to be accessed once or twice a year.

Understanding different Storage options are important for cost optimization and utility, but the real key to cost savings is setting up Intelligent tiering archive for S3 so that the data inside the S3 buckets move from one storage type to a cheaper version based on business logic or access patterns. Here the chart need take the place.

To cost-optimize the above scenario, you will need an S3 bucket with the following Intelligent tiering archive rule.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726523436559/6e50c26f-d949-420c-b1e5-96db45ea2cb5.avif align="center")

Move objects to Infrequent Access after 90 days to Archive Access tier.

Move objects from infrequent Deep Archive Access after 180 days.

To do that, go to the S3 console and click on the bucket and head to the properties tab.

Step 1 : On your S3 create a bucket name should be unique globally like that and hit enter to create with versioning enable with enabling version there will workout nothing and put some object on it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726522374961/e8cbfdb3-9d30-4920-8890-383365b4b649.png align="center")

Step 2 : Verify the uploaded item on your S3.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726522404544/aad0aa29-bdba-4cb5-b475-fc45544fc7b2.png align="center")

Step 3 : Then select your bucket and go to the properties tab and head to the Intelligent-Tiering Archive Configuration.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726522392321/d13237e6-2d05-448f-8e60-fbd40b59bc82.png align="center")

Step 4 : Hit create configuration and choose a name for it , dont worry there is nothing to be unique globally but different from other rules. And tick the all object contains in the bucket.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726522431330/e2014bb4-31d3-49a5-b5c4-3c68b0ba5ff4.png align="center")

Step 5 : Here is the serious rule of action to take if no-one access the data till 90 days t will automatically move to the Archive Access Tier when versioning is enable if not enable so then the rule is useless. After the again the pass of 180 days your data will move to the Deep Archive Access Tier.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726522454803/b58fff21-1052-4a82-967d-1179a51e01a5.png align="center")

Step 6 : After filling the all requirements just hit the Create Configuration and be happy. Your Cost will reduced by upcoming months.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726522467698/0d8d9b0b-3250-4390-9c9b-ed50eef6c056.png align="center")

Overall, Efficient cost management and performance optimization are key to boosting profitability and effectiveness. By controlling expenses through precise budgeting and waste reduction and enhancing performance with data-driven decisions and process improvements, businesses can achieve greater operational efficiency and sustainable growth.

Happy Learning😄 !!

Thank Yu !!