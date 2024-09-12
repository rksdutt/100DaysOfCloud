---
title: "Basic of AWS RDS 🛢️ 🚀 !!"
datePublished: Sun Jul 14 2024 21:37:16 GMT+0000 (Coordinated Universal Time)
cuid: clym2thgt000509kz78se4o1i
slug: explore-aws-rds
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1720995534177/8c6ce5ef-6651-4f8a-a307-2cdce46b7266.jpeg
tags: rds, aws-rds, relational-database

---

AWS RDS(Relational Database Service) is a fully managed open-source cloud database service by AWS that allows us to easily simplifies the process of managing relational databases in the cloud. Instead of manually setting up and maintaining databases RDS automates the complex tasks of managing databases, so we can focus on our applications. This allows us to quickly build databases and adjust their size as our needs change, ensuring we have enough storage and processing power. RDS supports various popular database engines like MySQL, PostgreSQL, Oracle and SQL Server which gives us the flexibility to use the one that best which fill our requirements. This means we can focus more on developing our applications and less on managing the underlying database infrastructure.

### Use Cases of RDS

There are many use cases of RDS few of them are here :

**Web Application :** Web applications often rely on AWS RDS because it can handle large amounts of data smoothly and reliably and ensuring that apps work well even when many people use them. It is a popular choice for developers who need robust support for managing data and making their apps run smoothly.

**Mobile Application and Online Games :** Amazon RDS is often used to make mobile and online games run smoothly by efficiently managing their database requirements. It simplifies tasks like setting up, resizing, and monitoring databases by ensuring that games perform well and are always available. This not only improves gameplay but also saves money and increases security for arcade, social and mobile games.

**E-commerce Applications :** Amazon RDS ensures a reliable and secure method for processing and storing user data, typically relied on by e-commerce websites. It offers scalable database engines that quickly adapt to meet increased user needs, enabling companies to increase performance, lower costs, strengthen security measures, and ensure greater availability for their operations.

### Benefits of AWS RDS

**High Availability & Durability :** RDS ensures high availability and stability by automatically backing up and restoring essential databases. It supports multi-AZ deployments, distributing databases across different Availability Zones to maintain access and protect against data loss during failures. These features make RDS reliable for ensuring data integrity and accessibility in cloud environments, providing peace of mind to efficiently manage critical databases.

**Cost-Effectiveness :** RDS is cost-effective because it works on a pay-as-you-go model which allowing us to pay only for the resources we use. Once our database or other resources are exhausted we should delete them to avoid charges. There is no mandatory minimum fee, and our monthly bill is determined by the type of database engine and our usage. Free tier accounts offer specific configuration and as long as all resources are deleted before logging out, we don't accept any charges, making it a flexible and economical choice for managing databases in the cloud.

**Security :** When we create a new database on Amazon RDS, we choose a personal password known only to us and are automatically granted the "Administration Role" with full control. For added security, Amazon RDS allows us to encrypt our database using AWS KMS(Key Management Service). KMS helps us by generating encryption keys that act like digital locks, ensuring that only authorized users can access our data. This additional layer of security protects our information from unauthorized access, ensuring our database remains safe and secure.

**Scalability :** RDS allows us to easily adjust our infrastructure based on the number of transactions our database handles per minute.

**There are two types of Scaling: Horizontal Scaling and Vertical Scaling.**

**Horizontal Scaling :** Horizontal Scaling is when we make more copies of our hardware and software in the cloud to handle sudden increases in traffic on our database. Then the workload gets spread out and everything runs smoothly even when there's a lot more activity happening.

**Vertical Scaling :** Vertical scaling is when our current hardware and software setup is not powerful enough to handle our requirements even if the traffic does not even increase very much. With vertical scaling we can increase our resources by adding more storage or processors. This improves our system's ability to handle the workload smoothly.

**Reduced Administrator Burden :** By using RDS we can set up our database from start to finish without needing to install any database software or manage the infrastructure ourselves. AWS takes care of everything, including installing the latest software updates and patches for our created RDS instances. This makes it easy to manage and secure our database without having to worry about the technical details.

### AWS RDS Database Engines

There are six database engines which RDS provides, and they are :

**Amazon Aurora (Compatible with MySQL and PostgreSQL)**

**PostgreSQL**

**MySQL**

**MariaDB**

**Oracle Database**

**Microsoft SQL Server**

Overall, RDS is a useful service that manages databases for various industries. It simplifies tasks likes set up, size adjustments, and database monitoring, ensuring that they are running smoothly and reliably. Whether for e-commerce, mobile apps, or online games. RDS helps improve efficiency, reduce costs, enhance security, and ensure applications run smoothly.