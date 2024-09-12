---
title: "What Is CFT ⛈ 🏗 !!"
datePublished: Thu Jul 04 2024 05:47:49 GMT+0000 (Coordinated Universal Time)
cuid: cly6uhz4j00000ak1gcgke5id
slug: what-is-cft
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1720000502883/593d24d8-eb76-41fc-9d78-ecac012afe53.png
tags: cloudformation, 2articles1week, aws-cloudformation, cloudformationtemplate

---

CFT is basically stands for Cloud Formation Template that helps in cloud formation for creating resources,managing and updating on AWS. Aws CFT implements the principle of IAC where CLI doesn't.

AWS CloudFormation is a tool that helps us to design and set up our entire cloud system using straightforward configuration files. It's part of Infrastructure as Code (IAC), making it easier for developers and admins to handle AWS resources like creating, updating, and deleting infrastructure automatically.

CloudFormation lets organizations use one language to model and set up their entire system across different regions and accounts. This automation cuts down on mistakes, boosts how efficiently resources are used, enhances system reliability, and speeds up setting up new environments.

Basically here users writes a template in YAML or JSON format or anything that is declarative and versioned in nature, submitted by users on CFT, and the tool has to do just convert the template in to a specificc language which can understandable by cloud providers. Usually the language are API calls.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720037880637/6fd01a9a-8909-4a43-8d09-94a929ddc359.png align="center")

## **Benefits of CloudFormation**

The benefits of using CloudFormation for infrastructure management are numerous. Let’s discuss the most obvious ones.

**Improved Efficiency :** AWS CloudFormation is a powerful tool that makes it easy to quickly create complex sets of resources without manual setup. It speeds up the launch of new services and apps, allowing developers and IT teams to focus on core tasks.

Using JSON or YAML files, CloudFormation templates can be versioned in Git or AWS CodeCommit. This allows for tracking changes over time and reviewing deployments in detail.

**Reduced Costs :** By automatically creating bulk resources, CloudFormation significantly lowers costs and reduces the labor associated with manual setup. AWS charges only for resources used during deployment, avoiding upfront costs and increasing reliability by eliminating human error.

**Improved Scalability :** CloudFormation templates enable rapid scaling services without managing each resource individually. This flexibility helps to adjust to changing demands, ensure optimal performance and avoid additional costs and complexities of manual scaling.

**Resource Management :** Managing related AWS resources ensures streamlined and automated, consistent configuration across the stack with CloudFormation. This makes it easy to add or modify resources across multiple stacks simultaneously with minimal effort.

**Easy and Quick Deployment :** CloudFormation offers an intuitive interface to monitor deployment progress, view previous deployment changes, and tag resources for organization and tracking. It supports rollback capabilities for quick recovery from deployment issues.

**Infrastructure as code :** Infrastructure as code (IAC) means we manage our infrastructure using code. This makes it simple to create entire environments from development to production. With IaC, we can easily adjust resources based on demand, whether we need to scale up or scale down quickly.

**Security :** We may use security policies and rules to ensure that all AWS resources are configured securely.

**When to Use :**

When should we use CLI when we need some in short and quick action. Like when we need to write a simple script or we need to write code related to AWS and going into details then CLI is the preffered.

When we need to create actual resources like two or three aws resources similarly if we create huge tags in such cases we use CFT.

Example, someone says quickly list down S3 buckets . So instead of writing a template in yaml or json format and then submitted to the CFT or other IAC tool and it will converted it to API calls and give us results or Opening a web browser and then login into AWS console and then go to S3 console and finally list down the buckets. Too boring huh just open terminal which is already have aws\_cli installed in it and search for "$ aws s3 ls" that's all we need to do.

## **Features of CloudFormation :**

**Template Creation :** It supports both YAML & JSON format. As newbie here we choose YAML . Reason behind to use it is easy to use and widely used in DevOps and it allows us to put comments to the code JSON doesn't allow commenting. As a Devops engineer we working as a team and it is very important to add comments on our code so anyone who look at our code they can easily understand what exactly it is and YAML is more readable and less complex. It basically depends on indentation JSON depends on Curly braces and hard to read. This website [https://docs.aws.amazon.com/](https://docs.aws.amazon.com/) helps me to where to put Resources(Important), also need Version,Description,Metadata,Parameter,Rules,Mappings,Conditions(Those are optional) through i can create any aws service by cloudformation in YAML language.

**Drift Detection :** CFT is not just for creating infrastructure also it known to create new features in infrastructure. When we create resources through CFT there is a function call detect drift using that function we can se actual difference between template and UI. Inside the aws there is option called stack by importing the stack we can run the template from our local machine. For example, in AWS CloudFormation, we can detect whether a stack's current configuration differs from its defined template.

**Sensor Drift :** Whether the sensor data is drifting from a baseline, which should remain stable within pre-defined limits. For example, a factory equipment technician may analyze historical sensor data trends to assess for drift.

**CFT Structure :** When we write a file for CFT in YAML or JSON the basic components are Version,Description,Metadata Information,Parametres,Rules,Mappings,Conditions,Resources these are the components we use when we write a CFT.

Terraform and CloudFormation are both infrastructure-as-code (IaC) tools that interact with infrastructure differently:

**Terraform :** Terraform, created by HashiCorp, is a tool that can work across different cloud services like AWS, Azure, and Google Cloud. It uses a simple way to describe what we want our cloud infrastructure to look like, without needing to detail every step. Unlike CloudFormation, Terraform allows for more flexibility with how we organize and use our infrastructure components.

**CloudFormation :** CloudFormation build by AWS it is a tool for setting up and managing AWS resources. It follows a step-by-step procedure to ensure that resources are created or updated correctly. It can run these steps repeatedly without causing problems and supports using custom functions for more advanced tasks.

Using AWS CloudFormation we automates the deployment of cloud infrastructure and run applications securely without exposing sensitive information. Organizations benefit from accelerating their digital transformation with improved scalability and efficiency.

...thank you !!