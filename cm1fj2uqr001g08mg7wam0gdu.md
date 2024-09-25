---
title: "Set Up Your First Database on RDS and Connect MySQL to Create Database through Terminal."
datePublished: Mon Sep 23 2024 21:37:10 GMT+0000 (Coordinated Universal Time)
cuid: cm1fj2uqr001g08mg7wam0gdu
slug: how-to-make-rds
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1727130595891/6fb35933-e776-470b-ab34-27297c8e2d5c.jpeg
tags: mariadb, mysqldb, rds-instance, relationaldatabases

---

Amazon Relational Database Service (RDS) is a web service that helps you set up, manage, and scale a relational database in the AWS cloud. It automates many database management tasks, such as backups, patching, and provisioning, so you can focus on your applications and business.

### Here are some benefits of using Amazon RDS

**Cost-efficient :** You only pay for the resources you use.

**Easy to use :** You can use the same tools and applications you already use with your existing databases.

**Scalable :** You can scale the compute resources or storage capacity of your database instance.

**Replication :** You can use replication to improve data durability and availability.

**Database engines :** You can use a variety of database engines, including open source and commercial options.

To create your first RDS instance with MariaDB on AWS and connect to it using the MySQL command line interface (CLI) to create a new database, you need to first set up the RDS instance in the AWS console, then use the MySQL client to connect and execute SQL commands to create the database.

Prerequisites are : Having an account of AWS Console.

Step 1 : On the search option just search for RDS & hit Enter. On the navigation click on database to create one.

Select 2 : Tick Standard create then tick on MariaDB.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127323023/419ed11a-5a88-44af-9e1a-ecc7941527d4.png align="center")

Step 3 : On templates tick Free tier. On the settings fill the creadentials as asked. On Instance configuration tick Burstable class.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127326174/f9936f55-e5bb-4bb9-9959-212cfb448560.png align="center")

Step 4 : Check all configuration before create the database.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127329009/84158de8-e02e-4f72-aa30-25be64803a45.png align="center")

Step 5 : Here we can see our database is in creating stage.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127332524/4947b000-7207-4dbd-87ba-42501e23e073.png align="center")

Step 6 : Here we go our database is in available state.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127335136/53e19077-790e-4a26-bd8e-58f6e7b39de0.png align="center")

Step 7 : Here we on search bar search for EC2 and hit that and create one with simple configuration.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127351715/77b52351-5ab1-4fb9-ac5e-89d229a949e7.png align="center")

Step 8 : After the instance on running state just ssh into it. Update the instance, Install the mysql-client in it, check the —version of mysql.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127356433/a413216b-b980-4f15-a85d-8c2702431ee4.png align="center")

Steo 9 : Then try to connect the database through terminal.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127358907/81989496-9dbd-40d8-b729-b07735af521f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127364264/b2f7df48-b72f-4d11-b055-7740352d713c.png align="center")

Step 10 : Go to the vpc security group and modify or allow the rule of mysql from anywhere.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127368308/5771645f-b371-47b9-a7cf-b903459ab637.png align="center")

Step 11 : Again try to ssh into it.

Step 12 : After successfully connected into the instance. copy the endpoint of Database and run it with mysql host and login into it with username and password.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127371896/5961ac4c-4d1f-47c8-b14c-1a038f3e1393.png align="center")

Step 13 : Here we can see after log in into mysql , how many databases are here.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127375587/6776f5d6-676b-480c-a142-c5c8b5152be4.png align="center")

Step 14 : Here we will create new datsbase through CLI

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127387107/6c7b01bb-c0db-4b4b-9e2c-a04019ade30c.png align="center")

Step 15 : Here we go our database are created successfully.

Overall, We’ve successfully set up an Amazon RDS instance for MySQL and connected to it, allowing for a managed database environment. Using the MySQL command-line interface, you created a new database, demonstrating your ability to interact with the database effectively. This foundational knowledge prepares you for efficient data management and future database tasks.