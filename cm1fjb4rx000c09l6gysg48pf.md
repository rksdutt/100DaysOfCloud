---
title: "Streamline Your Data Operations : Setting Up Amazon Aurora with Reader/Writer Endpoints."
datePublished: Mon Sep 23 2024 21:43:37 GMT+0000 (Coordinated Universal Time)
cuid: cm1fjb4rx000c09l6gysg48pf
slug: streamline-your-data-operations-setting-up-amazon-aurora-with-readerwriter-endpoints
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1727383130193/eb9c5cc5-4a49-45a3-988f-0cd1916ebf7a.jpeg
tags: aws-aurora, awsauroradb, readerwriter

---

Reasons to Use Amazon Aurora with Reader/Writer Endpoints :

High Availability : Amazon Aurora automatically replicates your data across multiple availability zones, ensuring your databases are always accessible and reducing downtime.

Scalability : With Reader/Writer endpoints, you can easily scale your database workloads. The writer endpoint handles all write operations, while reader endpoints distribute read traffic, allowing you to scale read capacity as needed.

Improved Performance : Aurora is designed for high throughput and low latency. By separating read and write operations, you can optimize performance for both types of requests, enhancing overall application responsiveness.

Cost Efficiency : With the ability to scale read replicas, you can optimize resource usage and reduce costs. Pay only for the resources you need, especially during peak traffic times.

Simplified Management : Using Amazon RDS for Aurora simplifies database management tasks such as backups, patching, and monitoring, allowing you to focus on your applications rather than infrastructure.

MySQL Compatibility : If you’re already using MySQL, migrating to Aurora is straightforward due to its compatibility. This minimizes the learning curve and allows for quick adoption.

Data Security : Amazon Aurora provides built-in security features, including encryption at rest and in transit, as well as network isolation options to protect your data.

The primary reason to create separate Aurora DB reader and writer instances is to enable efficient scaling for read-heavy workloads by allowing you to independently add more read replicas (readers) to handle high volumes of read requests without impacting the performance of the primary write instance (writer).

Step 1 : Select Standard create then choose the Engine type we are going with Aurora(MySql Compatible)Amazon aurora compatibility with mysql with different versions.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127765524/fe706104-c261-4ccb-8896-b2046cb594da.png align="center")

Step 2 : Select Dev/Test as a Template. Give a database identifier then fill the credentials with self managed.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127767615/715ecd6c-5dfc-4567-9b59-bca9b7b37265.png align="center")

Step 3 : Select Aurora I/O-Optimized( It offers improved performance, increasing throughput and reducing latency to support your most demanding workloads ). Select burstable includes t classes (benefits of t classes can handle sudden spikes in workload without compromising overall performance )

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127769757/892726f1-ba47-4dd9-b7bc-601c8272ccee.png align="center")

Step 4 : On connectivity select the default vpc as given then choose public access Yes. Then choose the security group create a new one.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127771033/fe96833d-6230-41e8-afca-b1dd345fedaf.png align="center")

Step 5 : Leave everything as default and hit the create database to create one.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127773256/d88e1caf-e1db-47f2-9d69-fac48a000fbd.png align="center")

step 6 : Edit the insbound rules of the created database security group.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127775266/a10eb534-dc9a-4b99-8d4e-a35f27035720.png align="center")

Step 7 : Here we can see our database is successfully created withreader and writer instance.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127780504/6cc22b2c-8311-4ea8-8b1d-56783db9e065.png align="center")

Step 8 : Here we are gonna see a trick if we copy the endpoint URL of Writer instance then we can do create or erase database from the terminal. On the other hand if we copy the endpoint URL of Reader instance we can’t create from it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127782698/67906879-12ac-4bbe-b9de-4623b848e2ee.png align="center")

Step 9 : Copy the writer endpoint and try something new to create. Then we create one database from writer instance.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127786708/cdd50ecc-cd65-4b75-9994-a54a2122c79d.png align="center")

Step 10 : Copy the reader instance endpoint URL then connect with it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127790293/4e316c97-065b-4f04-b73b-9863feee9db7.png align="center")

Step 11 : Sorry we can not create and databse for us the reason is that dispalys on the terminal “*Running-read-only-mode“*

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127791497/cb69ae6d-2496-4c77-b20b-8b44dabec789.png align="center")

Step 12 : After all that practice demo stauff allow me to waive off my database which we’ve createted for our practice purpose.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127794319/fdbd49d9-6216-4551-8c9c-02ba9a4af405.png align="center")

thank Yu !!