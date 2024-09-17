---
title: "Boosting Performance and Cutting Costs with Simplified S3 Lifecycle Rules"
datePublished: Mon Sep 16 2024 20:03:13 GMT+0000 (Coordinated Universal Time)
cuid: cm15fn20n000k09jwhvse82p0
slug: boosting-performance-and-cutting-costs-with-simplified-s3-lifecycle-rules
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1726513228858/a37bcace-33fe-4e3a-a81b-a3a316e75821.jpeg
tags: s3, s3-bucket, s3lifecyclerule

---

### What is Amazon S3 !!

Amazon Simple Storage Service (S3) is an AWS object storage service that is secure and scalable. It enables us to store and access data across the world using what is known as buckets. Every object in S3 has a unique identifier and metadata, as well as a version ID that ensures the maintenance of data integrity within time limits. Objects can be anything from bytes to terabytes in size.  
  
These policies automatically manage data on S3 with different lifecycle stages intended at cost management and performance optimization. This means for example, how we can use a simple rule to move objects from one storage class into another or even remove them notwithstanding their predefined criteria hence making storage cheaper.

### What is S3 LifeCycle Policy !!

A set of rules that outlines the actions to be taken on objects in an S3 bucket is what is called an S3 lifecycle policy. These policies allow for automated transitions of objects between different storage classes (i.e., from standard storage class to infrequent access) or deleting them after a given retention period. The highly customizable nature of these lifecycle policies enables organizations to align data management strategies with their unique requirements.  
  
Lifecycle policies operate on the basis of predetermined rules specified by the user. The user can specify certain conditions that an object must satisfy in order for it to trigger a specific action. For example, we’ll establish a rule & demonstrate, that will transfer files older than 30 days then 60 days then 150 days to a less expensive type of storage such as Glacier which fits well for archival purposes. Likewise, one may establish rules that will permanently delete files which are no longer useful after certain time elapses.

### Benefits of establishing the S3 LifeCycle Policy !!

Implementing S3 lifecycle policies offers several benefits to businesses

**Cost Optimization :** Unsupervised data transfer from frequent to rare storage classes significantly lowers storage costs, hence reducing human effort.  
**Efficient Data Management :** It makes automatic transitions between storage classes for objects or their delete, thereby relieving IT staff members from stress.  
**Compliance and Security :** It implements data retention policies to adhere to relevant legislation and automatically deletes sensitive information after expiration thus preventing possible leaks.  
**Improved Performance :** By keeping only the necessary information, it helps with quicker access to files.

### Amazon S3 LifeCycle Transition

Objects are automatically transitioned between storage classes based on predefined rules in S3 lifecycle transitions to optimize storage costs as per data access patterns.  
  
**Advantages :** Minimizing expenditure: The data is transferred to cheaper storage classes once it becomes less accessed thus cutting down all costs  
**Example of Transition rule :** First Transition: The S3 Standard storage class will have its contents moved into S3 Intelligent-Tiering within 30 days of inactivity.  
**Second Transition :** If there is no need for access after another sixty days then there will be one zone-s3 (as noted) which costs less.

### How to Create an S3 Lifecycle Policy

To create an S3 lifecycle policy, we need to create an S3 bucket. 

To create an S3 bucket :

**Step 1 :** Log in to your AWS console and enter S3 in the search bar. Search for S3 and hit that then again hit on Create Bucket & remember the bucket name should be unique globally. Decide on object ownership. If you want to keep object ownership leave is as default for now. If you want to give ownership to the account that uploads the files to your S3 bucket then enable ACLs.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514240013/4f47af36-ba34-4477-8b85-d31bec323290.png align="center")

Step 2 : Choose if you want to enable bucket versioning.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514252752/38d218ef-2edc-42ba-8987-0f5715fa67a5.png align="center")

Step 3 : Congratulation !! In only three steps once you see the following you learn to create S3 Bucket you’ve created your bucket.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514277936/e5322f80-39b0-43b9-85e7-78fc77251b6c.png align="center")

Step 4 : Select your bucket go inside of it hit upload and put some object from your local to your bucket.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514286488/1c0cbcf8-60ec-471b-b308-7c39b76272d5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514386258/aa30e4ef-a9b2-4e9c-a7af-d2a8b3b3bcf9.png align="center")

Step 5 : Here we will write access policy for hosting it publicly. You dont need to do this for creating LifeCycle Policy.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514296014/c0340f08-4646-4d3a-a87c-fb369877b73d.png align="center")

Step 6 : Here we will hit policy generator and give the instructions as required like that then put bucket ARN then add statement and copy that policy and paste it on policy here below.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726515535872/be8ff434-7898-4386-a715-db908ca83100.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514308444/017b12f2-e61f-4d26-ae78-ae496c8c3a47.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514371118/bdcb662c-7a87-4e3c-99fe-4ea8047e319f.png align="center")

Step 7 : Here we can see our two different website hosted properly and smoothly through S3.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514318027/1e08cdda-eca1-430e-8aee-66ea8f8d0878.png align="center")

Step 8 : Back to the point lets create LifeCycle Rule for our bucket hit Create LifeCycle Rule and then choose a name for it and then choose scope ✅ as “Limit this scope of this rule using one or more filters”.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514391521/c5411fcf-0518-4548-a30c-d4f12189b17d.png align="center")

Step 9 : Then choose LifeCycle rule action and specify the transition for each option according to your choice.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514399572/50882e14-18f0-4924-804d-e09fb40eaae2.png align="center")

Step 10 : Then select the transition of according to your choice current, noncurrent, expire of noncurrent, permanently delete of noncurrent version and also delete the expire object as delete markers fill them according to your choice.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514435163/23e5d135-62af-41d0-98d7-e8ee6193e45d.png align="center")

Step 11 : Here I only chose Standard-IA then fill them according to requirement.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514440246/8839cc06-4898-45b8-b2d0-ec9934c5dac3.png align="center")

Step 12 : Congratulation !! In 12 you’ll be able to create LifeCycle Rule for our S3 Bucket.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514446398/169d1e60-a15b-4b7f-bef2-6a9ae7b123eb.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514451822/ad7b616d-35ad-4aee-a121-f3849861deec.png align="center")

Step 13 : Here we can see our S3 Bucket LifeCycle rule review and details.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514463339/945af2d5-e743-4680-b89b-ed8dfd77c8b8.png align="center")

<mark>Step 14 : Important steps whatever resources you created and uploaded it with versions even with delete marker waive them off right now.</mark>

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514468189/4040abf7-c64d-4869-a530-b1c0c4c710d2.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514472901/9c7da785-b6b4-4941-9ac3-d82c766e0b42.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514477497/cf3e7d18-225b-4d55-af01-9bbeafa204f4.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726514489990/58eded29-6111-487e-956b-4b46577f5bf1.png align="center")

Overall, The automated management of data is made possible by the use of S3 lifecycle regulations that take care of moving information to low-cost storage classes depending on its access patterns which reduce expenses. They facilitate transitions and deletions, support adherence to data retention policies and improve performance through reducing storage devices and removing obsolete information.

Happy Learning 😄 !!

Thank Yu 😄