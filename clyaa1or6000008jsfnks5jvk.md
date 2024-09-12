---
title: "What is AWS Cloud Watch 🧐👀 ! !"
datePublished: Sat Jul 06 2024 15:26:22 GMT+0000 (Coordinated Universal Time)
cuid: clyaa1or6000008jsfnks5jvk
slug: what-is-aws-cloud-watch
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1720415025496/f00bb655-e46b-4ec9-b407-9f3a8a2a2312.jpeg
tags: cloud-computing, monitoring, 2articles1week, cloudwatch, cost-optimisation

---

Amazon CloudWatch is a service that monitors and manages our Amazon Web Services (AWS) resources. Which helps us to understanding and implementing the monitoring, alerting, reporting & logging using this features of cloudwatch we can track those activity which are happening on AWS account.

Suppose Cloudwatch basically a service(gatekeeper) on AWS Cloud which is observes that which service get in touch with whom. When anyone creating or interacting with any kind of AWS resources.

Amazon CloudWatch makes it easy to collect metrics from over 70 AWS services like EC2, DynamoDB, S3, ECS, Lambda, and API Gateway without requiring any user set-up. For example, EC2 instances automatically share metrics such as CPU usage, data transfer, and disk usage, which helps you track changes in their status. Built-in metrics for API Gateway can detect latency, while for AWS Lambda can detect errors or throttling issues. This capability helps monitor performance, troubleshoot problems, and identify patterns over time. We can send these metrics to CloudWatch using the CloudWatch agent or with the PutMetricData API service call. Overall, CloudWatch allows us to collect application metrics (such as user activity, error rate, or memory usage) from our own applications.

**Features of AWS CloudWatch :**

**Monitoring :** Monitoring is one of the primary thing which AWS is doing. Monitoring is the biggest advantage of AWS CloudWatch and it is a very important activity for DevOps Engineer. Wheather its kubernates architechture monitoring or infrastructure monitoring CloudWatch basically plays a critical role in infrastructure monitoring or application monitoring.

**Real-Life Metrics :** AWS CloudWatch allow us to see the metrics which is reaching on our services. Metrics meaning in simple word suppose, there ec2 instance in my account and how many api request did this instance received and metrics gives us reports about how was the CPU utilization and memory consumption in last 1 hour. Metrics is a service which is helps us to get the understanding on utilization and details of AWS services.

**CloudWatch Alarms :** Metrics & alarm are very closely associated. AWS CloudWatch alarms let us set thresholds on metrics and trigger actions when those thresholds are crossed. For example, we can monitor EC2 metrics, get alerts, and automatically manage instances to minimize downtime and business impact. Suppose we have collected metrics upon CPU utilization if there is 80% then it goes on 100% consumption of CPU then it will be not useable further. So our resposibilities to not only take metrics information but also take action on metrics outcome. So we will set-up an alarm for when CPU utilization is above the 60 or 80% we will get a notification on mentioned email address.

**Log Inshights :** CloudWatch Logs Insights in Amazon CloudWatch allows us to search and analyze log data. It helps us to find and fix issues, diagnose problems, and improve application performance. Log records all of our activity if someone or this specific service trying to access to an Instance or S3 bucket with timestamp. CloudWatch is capable of doing lot of activities out of the box of our cloud. CloudWatch has default capabilities of all these things but we can additionally enhance this as well. For example kubernates has lots of capabilities if we feels something is missing then we can enhance the capabilities. Likewise, we can use custom metrics concept on AWS CloudWatch. So logging is basically a capability provide us the inshights that which service is accessing the other service.

**Custom Metrics :** We mentioned earliar about the CPU utilization it is a default metrics if we need to see memory utilization with CPU utilization then we have to enhance CloudWatch it means to send this custom metrics to the CloudWatch. Because cloudwatch is not tracking this metrics someone need to send this metrics to the CloudWatch. Using Custom metrics we can track our own application or memory of our instance.

**Cost-Optimization :** People are moving to the cloud to reduce maintenance and increase security, which is their main goal. Cloudwatch is crucial in this shift. Although CloudWatch does not handle scaling directly, it collaborates with other services for tasks such as cost optimization. As a gatekeeper, CloudWatch monitors interactions with cloud services. This integration enables serverless functions like Lambda to act based on cloud activity, improving what they can do. Lambda functions cannot see cloud operations directly, but CloudWatch gives them this data, helping to reduce costs.

**Few features of Cost-optimization :**

**Right-Sizing** : Match your resource provision to your needs, like CPU, storage, and memory.

**Increase elasticity** : Turn off resources not in use to save costs, a benefit of cloud computing.

**Choose the right pricing** : AWS offers various models; pick one that suits your workload, such as Reserved Instances for steady workloads.

**Optimize storage** : Use AWS storage tiers for cost-effective performance matching.

**Measure, Monitor, Improve** : Continuously monitor costs and performance, use tags for cost allocation, and assign optimization roles to teams.

**Scaling :** CloudWatch doesn't direct performing on scaling or cost optimization. But it can integrate with other services like cost-optimization because cloudwatch is a gatekeeper therefore it records all over activities happening on AWS cloud. If CPU utilization is over 90% and clcoudwatch invoke the auto scaling group to launch one more to reach at next level.

Overall, CloudWatch simplifies monitoring and managing our AWS resources, providing insights into performance, operational health, and cost optimization through automated alerts and integrations with other AWS services.

..thank you !!