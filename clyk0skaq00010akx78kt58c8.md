---
title: "What is EBS  🌐 🗄!!"
datePublished: Sat Jul 13 2024 11:05:01 GMT+0000 (Coordinated Universal Time)
cuid: clyk0skaq00010akx78kt58c8
slug: what-is-ebs
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1720865886165/057a7c8e-2ed2-435c-8618-bbab8b7ac4fa.png
tags: ebs, 2articles1week, aws-ebs, ebs-vol

---

Amazon Elastic Block Store (AWS EBS) is a storage service built for Amazon EC2 instances, providing raw block-level storage. After attached with an EC2 instance EBS volumes act like traditional hard drives & supporting different file systems and applications. You can create snapshots and clones from EBS volumes. Each EBS volume is automatically duplicated within the same AWS Availability Zone also ensuring data abundance and high availability with a 99.999% uptime guarantee. AWS offers encryption for data at rest using Amazon-managed keys or customer-managed keys through Amazon Key Management Service (KMS).

Overall, AWS EBS enables reliable and secure storage for EC2 instances, critical to maintaining data integrity and availability in cloud environments.

### There are two types of EBS volume popular in AWS

**There are two Amazon EBS volume type categories :** Solid state drive (SSD) volumes & second is Hard disk drive (HDD) volumes.

**There are also sub-types of SSD :** General Purpose SSD(GP2 & GP3) and the second one is Provisioned I/OPS SSD.

**Solid State Drive (SSD) :** SSD volumes are designed for workloads that demand fast access to data and perform frequent operations. General purpose SSDs offer versatile and balanced performance, suitable for a wide range of applications.

**Provisioned I/OPS SSD :**

Provisioned IOPS SSDs are tailored for applications needing consistent high-speed and low-latency storage, such as databases and critical business applications. These volumes ensure that applications can handle demanding workloads efficiently while maintaining fast response times.

**General Purpose SSD(gp-2) :** General purpose SSD volumes offers a good balance between cost and performabce, making them suitable for various applications. They are recommended for boot volumes, development, testing environments and low latency production applications that do not demand high IOPS. The performance of these volumes increases with their size, as users get three IOPS per gigabyte of volume size.

Amazon EBS volumes have I/O credits that determine how much bandwidth they can use to burst at higher IOPS levels for a given period of time. These credits accumulate over time, with larger volumes earning more credits up to a maximum of 3,000 IOPS.

Once the credit is used-up the volume returns to its baseline performance. GP2 volumes range in size from 1 GiB to 16 TiB with a maximum throughput of 160 MiB/s.

**General Purpose SSD(gp-3) :** GP3 volumes are also a type of SSD storage like GP2 offered by EBS which is designed for a wide range of workloads requiring balanced performance and cost efficiency. They offer flexible performance and pricing options which making them suitable for a variety of applications, from development environments to production workloads.

GP3 volumes automatically adjust performance levels to meet workload demands. Users can add provisioned IOPS for consistent high-speed data access and optimizing costs while ensuring smooth application performance.

GP3 volumes do not use I/O credits like GP2. Instead of that they provide a baseline performabce that scales with volume size, starting at 3,000 IOPS and 125 MiB/s throughput. Additional performance can be provisioned as per requirement & ensuring predictable performance upon varying workloads.

**Provisioned I/OPS SSD :** Provisioned IOPS SSD (IO1) volumes are designed for applicationa that require high-performance storage in Amazon EBS. Unlike general purpose SSD (gp2) volumes IO1 volumes allow us to specify the exact number of IOPS we need, making them ideal for databases and critical production environments where consistent performance is essential.

AWS guarantees IO1 volumes will provide 99.9% uptime and maintain performance within 10% of the annual IOPS rate. It is recommended to maintain a 2:1 ratio between provisioned IOPS and volume size for optimal performance and cost efficiency.

With sizes ranging from 4 GiB to 16 TiB and throughput up to 500 MiB/s IO1 volumes provide the flexibility to scale performance and capacity based on application needs & ensuring reliable and predictable performance for workloads on AWS.

**Hard disk drive (HDD) :** HDD volumes in AWS are designed for tasks requiring fast data processing and high throughput, measured in MiB/s. There are two types: throughput optimized HDDs (st1) for fast access to large datasets, and cold HDDs (sc1) for storing infrequently accessed data such as backups. They provide cost-effective options for handling large amounts of data with varying speed and access requirements.

These HDD volumes provide a cost-effective option for storing large amounts of data with different access patterns that meet different workload requirements based on throughput and performance demands.

**There are also sub-types of HDD :** Throughput Optimized HDD (st1) and other one is Cold HDD (sc1).

**Throughput Optimized HDD (st1) :** ST1 volumes or throughput optimized HDDs are ideal for applications that prioritize large storage and high throughput over high IOPS. They provide a baseline throughput based on volume size and accumulate credits over time for bursts of up to 500 MiB/s. With sizes ranging from 500 GiB to 16 TiB, ST1 volumes ensure consistebt and fast data access, suitable for data warehousing and big data analytics.

These volumes prioritize sustained, fast data throughput over frequent IOPS demands, making them cost-effective for applications that require efficient data processing and high-speed data transfer without requiring extremely low latency access. Which is ideal for handling large datasets in situations like data warehousing and big data analytics.

**Cold HDD (sc1) :** It is a cost-effective storage option is ideal for prioritizing low-cost data storage. It supports sizes from 500 GiB to 16 TiB with throughput up to 250 MiB/s. Similar to st1 volumes, sc1 also uses a burst model, but credits accumulate at a slower rate (12 MiB/s compared to 40 MiB/s for st1 volumes). Cannot use st1 or sc1 volume as boot volume; gp2 volume is recommended for boot purposes instead.

These volumes are budget-friendly for scenarios requiring consistent, efficient data management focused on constant, fast data transfers rather than frequent IOPS demands. which is suitable for applications handling large datasets that require reliable, high-speed data movement without the need for extremely fast access times.

Amazon Elastic Block Store (EBS) provides durable and highly available block-level storage for Amazon EC2 instances. It is ideal for file systems, databases, and applications that require direct, granular access to storage at the block level within Availability Zone (AZ). EBS volumes ensure data replication and reliability within the same AZ where they are created, supporting critical workloads with consistent performance and resiliency.

### So here we will get knowledge about AWS Snapshot

EBS snapshots are essential for long-term data protection and durability of data stored on EBS volumes. They allow us to replicating data across AWS regions and through it we can easily create a new EBS volumes. Snapshots capture incremental(Incremental back-up means suppose yesterday we've taken a snapshot of our EBS volume it was 6GB and today if we take a snapshot of EBS of 2GB it will take snapshot of 2GB not direct 8GB ) changes and metadata in a single snapshot, ensuring comprehensive backups.

**Use cases of Snapshots :**

**Data backup :** Amazon EBS snapshots are ideal for backing up Amazon EC2 instances and their data volumes off-site, across different Availability Zones (AZs), or even across different AWS Regions. Snapshots capture the entire state of a running EC2 instance and its data, which is then stored in Amazon S3 for long-term retention.

**Replication & Disaster recovery :** Amazon EBS allows data to be replicated across different AWS regions using snapshots, increasing disaster recovery capabilities for EC2 instances. Snapshots enable rapid recovery of instances using copied snapshots stored in alternate regions.

**Dev/Test Environments :** Amazon EBS snapshots make it easy to create dev/test environments by simplifying cloning of production EC2 instances. Developers can create copies of volumes from snapshots, ensuring consistency and efficiency in the testing and development process.

**Automated process :** When we create an EBS snapshot AWS automatically sends the snapshot data to Amazon S3 with timestamp in the background. EBS snapshots are stored in Amazon S3, S3 buckets that we cannot access directly. We can create and manage your snapshots using the Amazon EC2 console or the Amazon EC2 API. We cannot access our snapshots using the Amazon S3 console or the Amazon S3 API. It securely stores your data off-instance for long-term retention. This automated process makes EBS snapshots a reliable backup solution, protecting your data and enabling easy recovery without manual effort. This is critical to maintaining data consistency and availability across AWS services.

Overall, Elastic Block Store (EBS) provides persistent storage volumes for Amazon EC2 instances. It includes options like General Purpose SSD (gp2) for balanced performance, Provisioned IOPS SSD (io1) for high-performance needs, and Throughput Optimized HDD (st1) and Cold HDD (sc1) for cost-effective large-scale data storage.