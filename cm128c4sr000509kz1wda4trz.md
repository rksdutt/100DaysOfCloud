---
title: "Same Region Replication(SRR) Amazon S3-Replication."
datePublished: Sat Sep 14 2024 14:15:27 GMT+0000 (Coordinated Universal Time)
cuid: cm128c4sr000509kz1wda4trz
slug: same-region-replicationsrr-amazon-s3-replication
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1726322888861/feb94778-00d7-4969-bbc2-baa9749b6226.jpeg
tags: ssr, aws-s3-versioning, aws-s3-replication

---

Replication helps us store our data with rules and regulations and where or how it will be managed by region replication. Replication helps us keep a copy of our data across different AWS accounts but in the same region. Replication helps us choose or switch ownership of data through backups and protect against accidental deletion.

**Data complience and supremacy of Replication :** Replication helps us with data compilance and data supremacy through keeping a replica of our data in a different AWS account in the same region like the original.

**Aggregated logs of Replication :** Replication helps us with merging logs from another s3 bucket into one bucket for processing the same region.

**Replication in different accounts :** Replication helps us to replicate object and metadata between different accounts, like testers and developers accounts.

**Variable account ownership :** Replication helps us to change ownership for the replicated object or metadata to protect it from accidental deletation.

**Critical data recovery :** Replication helps us with backing-up of critical data when compilance does’nt allow to move tha data within region.

In a nutshell Replication is responsible for keeping our data safe within a same region and also in different accounts.

**Step 1 :** On the AWS console we heading towards S3 bucket and hit create bucket with the name along ‘buck-origin’ and another one is ‘buck-demo’ with enabling bucket versioning.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726314573548/ee6ee30a-0877-4461-9c86-870d3cc0e11a.png align="center")

**Step 2 :** Put some object or data on bucks-origin with enabling versioning.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726314890600/ad37ac0c-56f6-4822-94e1-afc315d0f8ea.png align="center")

**Step 3 :** Here we can see the our origin bucket have the both original data and version data also.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726314640355/0fb94b31-abce-4bb5-9b39-a1e5c59cb632.png align="center")

**Step 4 :** Here we are going to allow replication on bucks-demo which is our replication bucket of buks-origin. So on the management after the scroll we can see replication rule, we’ll set it up for our replication. Here we’ll also add the the delete marker replication also. Here is those steps to create replication rule for replication bucket.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726320788895/457b5526-b78e-483c-8209-80fbe4054ef1.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726316277332/5a70206c-1e11-467a-9567-efa996ec7729.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726316366375/f862f38d-64a4-4b02-ab1d-245806de2666.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726316346208/d08d822a-6807-4776-8685-deaed9cffb11.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726316331295/2a0ed079-96a3-42af-b86f-0bc18663ba78.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726316150592/55ec8bf0-fc8c-4e67-b177-332bd7c2ee7e.png align="center")

Here is our replication rule for bucket which defing the source of the bucket where

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726315248129/b6fbb38c-8b40-4536-af2d-9bdfbfcc85ad.png align="center")

**Step 5 :** Here on the bucks-origin we wll erase the data which we uploaded from local to bucket earliar. Here we can see we delete the data.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726316235647/fbf6d290-5683-4500-9428-6ed073d2ae61.png align="center")

**Step 6 :** After enebling the replication for buck-demo which is our replication bucket there our uploaded object will be present and if we delete this data or object with agreee or by accidentally.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726320847095/1da8ed5b-fda4-4830-85e7-5237847088b3.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726319846834/512e1cf4-2d24-4cd8-a2e2-11fe6ea2d239.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726319877373/781d6d6e-8608-4f55-8fa1-1d81f90235d5.png align="center")

**Step 7 :** If we waive off the data which is stored on our bucks-origin S3 bucket and replicated on bucks-demo bucket we can we there data will be still present cause we tick delete marker replication when we creating replica set for bucks-demo.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726320544069/30b35365-6168-462c-b327-20437fcda987.png align="center")

Here we can see how to can retrive our data or object which kept on our s3 bucket here we can easily save our data or retrive our data by doing s3 SRR same region replicaton.

thank Yu !!