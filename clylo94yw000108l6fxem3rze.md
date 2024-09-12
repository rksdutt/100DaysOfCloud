---
title: "What is EKS 🚀 🧊!!"
datePublished: Sun Jul 14 2024 14:49:32 GMT+0000 (Coordinated Universal Time)
cuid: clylo94yw000108l6fxem3rze
slug: what-is-eks
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1720963867847/1bd6df8d-f331-4c7f-b20a-8a830022f9a6.jpeg
tags: eks, 2articles1week, eks-cluster, eks-project

---

Amazon Elastic Kubernetes Service (EKS) is a managed service that allows us to run Kubernetes on AWS without having to set up or manage our own Kubernetes control plane or nodes. It automates important tasks like updating, setting up new nodes and adjusting size as needed. EKS is reliable and connects well with AWS tools such as IAM, CloudWatch and VPC. The Kubernetes management infrastructure of EKS runs across multiple Availability Zones (AZ). It supports both EC2 and Fargate to run Kubernetes pods. In short, EKS makes it easy to deploy, manage, and extend containerized applications using Kubernetes on AWS.

### Components of EKS -

There are three components in EKS cluster here they are EKS Control Plane,Worker Nodes & Networking.

**EKS Control Plane :** The control plane is like the central command center of a Kubernetes cluster. It has three main nodes spread across different AWS Availability Zones to ensure reliability. It runs on a dedicated set of EC2 instances in an AWS managed account and provides an API endpoint that can be accessed by our applications. It works by itself and takes care of important parts of Kubernetes like API server and etcd. This ensures that everything runs smoothly and keeps data safe. Also, it manages how applications connect to the Kubernetes system. The role of the control plane is to ensure that the cluster can expand, handle heavy workloads, and remain available for operations.

**EKS Worker Nodes :** EKS nodes are where Kubernetes worker nodes run on EC2 instances in your AWS account. They connect to the control plane using an API endpoint and a special certificate made just for each cluster. In EKS we can have up to 1000 of these nodes. They are grouped together each group has a maximum of 100 nodes and we can create up to 10 groups per cluster. These nodes manage the day-to-day operations of the applications running within the cluster.

**EKS Networking :** AWS EKS cluster operates in a VPC a secure private network within a data center. EKS deploys all resources to an existing subnet in a VPC of our choice in a AWS region. EKS control plane runs in VPC. Which creates and manages network interfaces in our account attached with each EKS cluster we create. Each EC2 instance in the EKS cluster is placed in subnet to keep things organized and easy to handle.

### **Features & Benefits of EKS Cluster -**

Amazon Elastic Container Service for Kubernetes (Amazon EKS) clusters has many features few of them are following below.

**Managed EKS Control Plane :** EKS takes care core of the Kubernetes Control Plane. This includes automatically managing updates and patches.This ensures that Kubernetes operates smoothly without requiring manual input from users.

**Cluster Management :** EKS offers tools and APIs to effortlessly create, upgrade and manage Kubernetes clusters, including setup, upgrade, scaling and monitoring through a user-friendly interface and automation.

**Cluster Autoscaler :** Cluster AutoScaler automatically adjusts the number of pods based on workload in our Kubernetes cluster, adding pods as needed for increased resource demand and removing them during low-demand periods to optimize efficiency and cost.

**Network Management :** EKS support IPv6 for extended IP addresses, service discovery for easy communication between cluster components and IAM authentication for secure resource access. It making sure that organizations follow all the rules and regulations that apply to them.

**Integration with AWS services :** Integrate with AWS services EKS works together with Amazon Web Services networking and security tools like application load balancers, IAM and VPC.

**Security :** EKS integrates IAM for user authentication and access control & VPC to create secure network boundaries and encryption to protect sensitive data from unauthorized access, uses encryption to keep data secure, ensuring everything on AWS is well-protected.

Overall, EKS makes it easy to deploy, manage, and scale containerized applications using Kubernetes on AWS. It automates routine tasks and provides a stable platform to run container workloads, freeing users to focus on their core tasks rather than managing infrastructure. With simple setup, seamless AWS integration, and robust scalability features. EKS helps organizations modernize their application infrastructure efficiently in the cloud.