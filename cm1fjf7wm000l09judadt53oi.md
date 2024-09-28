---
title: "Elevate Your Infrastructure : Harnessing Cross-Region Replication for Global Efficiency"
datePublished: Mon Sep 23 2024 21:46:47 GMT+0000 (Coordinated Universal Time)
cuid: cm1fjf7wm000l09judadt53oi
slug: amazon-rds-databasewith-mysql-and-make-it-cross-region-replica
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1727518664946/cf098d7a-c08b-460f-9bad-40ee640b843f.jpeg
tags: rds, crossregionreplication, rdscrr

---

Cross-region replication in Amazon Relational Database Service (Amazon RDS) allows us to create a read-only database instance in a different AWS region than your primary database instance. RDS Cross-Region Read Replicas Process RDS creates an automated DB snapshot of the source DB instance in the source AWS Region. **RDS begins a cross-Region snapshot copy for the initial data transfer**. RDS then uses the copied DB snapshot for the initial data load on the read replica.

**Disaster recovery :** If your primary region experiences a disruption, you can promote a replica to a master to keep your business running. 

**Data proximity :** You can place replicas closer to your application users to reduce read latency. 

**Database migration :** You can quickly migrate your database to a different AWS region. 

**Read workload scaling :** Cross-region replication allows you to scale out read workloads over a farm of up to five read replicas.

**Read workload offloading :** You can offload read workload from your primary database instance.

Amazon RDS uses the replication functionality integrated into the MariaDB, MySQL, Oracle, PostgreSQL & Microsoft SQL Server database engines to create a special type of DB instance called a Read Replica from a source DB instance. Cross-region replication is a feature that automatically replicates data across regions to provide disaster recovery protection.

**Step 1 :** On the RDS database hit to create database choose a database engine.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127840207/9bb3f54e-d1b6-46a2-87d8-97a15a69fb3c.png align="center")

**Step 2 :** Then choose a template according to your potentials. And choose single DB instance, give a identifier to your database and fill the credentials as asked.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127914350/67d88d9a-309a-4dcc-bb31-2990e3855cbd.png align="center")

**Step 3 :** Then come on Instance configuration choose Burstable classes(Includes t classes)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127917160/d510f3cf-acf3-4973-b8f1-65f296d216c6.png align="center")

**Step 4 :** On storage whatever allocated storage given by default go as along with it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127918746/e31de8f3-9185-499c-bdad-bba8d12bd585.png align="center")

**Step 5 :** On connectivity give access to the public choose a security group.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127920692/c5c18d31-2c62-45d7-b13c-2e8d7c44b27c.png align="center")

Step 6 : Leave everything as default then hit the create database button.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127923124/f08c22c7-b92b-4488-941b-7fa8e6cb094e.png align="center")

Step 7 : Here we can see our database is created successfully.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127924503/c59445d3-beb1-4d4e-9039-3acf82cdde3b.png align="center")

Step 8 : Let’s try to connect with database endpoint.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127927533/05e7446b-6f19-49d5-8f21-6f232e4571a0.png align="center")

Step 9 : Here we connected successfully to the databases. Here we will create a database with terminal.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127929971/c183c553-8c40-45f0-b995-f5aa92bd1053.png align="center")

Step 10 : After all that things we remember thta we’ve to do one important thing to create that one is Read-Replica.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127931992/8a9d8184-23bc-43c5-815d-6685f95c1caf.png align="center")

Step 11 : Creating the Read Replica within the region where the database created and we want to create this read replica on another region. Here Everything most probably remain same and on AWS Region we have to choose our destination region. In Our’s end we chose Ohio(US-EAST).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127933495/026d0065-a344-4fbc-88e1-591731e62a4c.png align="center")

Step 12 : On AZ we can go with single db instance for practice purpose.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127935485/5ca7474a-8234-4344-9ee2-d35cfd031c24.png align="center")

Step 13 : Leave everything as default and hit the button Create read replica.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127939421/bc575dfb-3d4d-42a3-8a38-f3faae233650.png align="center")

Step 14 : Here our primary database available is in N.Virginia.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127954163/9f882247-a3c2-486d-9a90-a6b7b1eec611.png align="center")

Step 15 : From here we’ll go to the Ohio.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127943798/78f36ccf-d34b-4a9a-9b6d-69131f990055.png align="center")

Step 16 : Hola !! Here is our Read replica which we have created on N.Virginia.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127974822/8d7574a1-1c8e-4b3c-a45a-fe8acaa8715f.png align="center")

Step 17 : Not only read replica even its all about Subnet-Groups we’ve created a subnet groups from N.Virginia the Subnets groups also are here.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127977900/c5ecb8a2-1b5f-424c-a921-9a0ba52ecd18.png align="center")

Stepp 18 : Here We will try to connect with read replica’s endpoints and we’ll try to see that the database we’ve created the database through terminal on mysql -h are they’ll visible here.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127979365/e81ef7c3-eb16-49fc-854e-a85b6c3f7fde.png align="center")

Step 19 : Edit the Security groups attached with our primary database and add MYSQL /AURORA.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127983055/8a169ffc-477a-42b3-a813-326685d8f03b.png align="center")

Step 20 : Here we’ve connected with our mysql host from Ohio Region and when se didi show databases. And we can see that the databse we have cretaed through terminal on which was created on N.Virginia Region.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727129138415/f5f2e9da-7e4b-4f17-813b-88720c2482ca.jpeg align="center")

Step 21 : Here after our practice we’ve to remove our instance or AWS resources.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727127987577/89722b97-34e2-4f4c-bb6f-04c1592d3966.png align="center")

thank Yu !!