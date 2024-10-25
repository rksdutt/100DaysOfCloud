---
title: "🚀 My Jenkins Setup Journey: A Step-by-Step Guide 🚀"
datePublished: Fri Oct 25 2024 19:43:59 GMT+0000 (Coordinated Universal Time)
cuid: cm2p54jyl000309ld9fxq5ito
slug: my-jenkins-setup-journey-a-step-by-step-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1729885495515/85e3fccb-6fab-4e24-b5a9-3abab71564bd.jpeg
tags: chrishtmas-project, secret-santa

---

## Introduction

Embarking on the journey of setting up Jenkins has been an enlightening experience, especially in the context of modern software development. Jenkins serves as a cornerstone for continuous integration and continuous deployment (CI/CD), allowing teams to automate and streamline their workflows. In this blog, I’ll share the detailed steps I took to set up Jenkins on an AWS virtual machine, along with insights and best practices that can benefit anyone looking to enhance their development process.

## Why Jenkins?

Jenkins is an open-source automation server that facilitates the automation of building, testing, and deploying applications. Its extensibility through plugins and its vibrant community make it a popular choice among developers and DevOps teams alike. By setting up Jenkins, I aimed to:

* Automate repetitive tasks to reduce manual errors.
    
* Streamline the build and deployment process.
    
* Enhance collaboration within the development team.
    

## Step 1: Create a Virtual Machine on AWS

To begin my Jenkins setup, I needed a dedicated environment where Jenkins could run without interference from other applications.

1. **Log into the AWS Management Console**: After logging in, I navigated to the EC2 dashboard.
    
2. **Launch an Instance**:
    
    * I selected an **Amazon Machine Image (AMI)**, choosing Ubuntu Server for its lightweight nature and community support.
        
    * I opted for the **t2.micro instance type**, suitable for testing and small projects.
        
3. **Configure Security Groups**:
    
    * I ensured that my security group allowed inbound traffic on port **8080** (the default port for Jenkins) to facilitate web access.
        
4. **Launch the Instance**: After reviewing the configuration, I launched the instance and generated a key pair for secure SSH access.
    

## Step 2: SSH into the VM

After launching the instance, I needed to access it securely.

* **Open Terminal (Linux/Mac) or Command Prompt (Windows)**:
    
    * Using the following command, I SSH-ed into my instance:
        
    
    ```typescript
    bashCopy codessh -i "your-key.pem" ubuntu@your-ec2-public-dns
    ```
    
* **Verify Connection**: Successfully logging in indicated that I could manage the VM remotely.
    

## Step 3: Install Jenkins

With access secured, I proceeded to install Jenkins.

1. **Update Packages**:
    
    * To ensure all dependencies were up to date, I ran:
        
    
    ```typescript
    bashCopy codesudo apt update && sudo apt upgrade -y
    ```
    
2. **Install Java (JDK)**:
    
    * Jenkins requires Java to run, so I installed it with:
        
    
    ```typescript
    bashCopy codesudo apt install openjdk-11-jdk -y
    ```
    
3. **Add Jenkins Repository**:
    
    * I followed these commands to add the Jenkins repository to my system:
        
    
    ```typescript
    bashCopy codewget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key.asc | sudo apt-key add -
    echo deb http://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list
    ```
    
4. **Install Jenkins**:
    
    * After updating the package list, I installed Jenkins with:
        
    
    ```typescript
    bashCopy codesudo apt update
    sudo apt install jenkins -y
    ```
    
5. **Start Jenkins**:
    
    * Finally, I started the Jenkins service:
        
    
    ```typescript
    bashCopy codesudo systemctl start jenkins
    ```
    

## Step 4: Access the Jenkins Dashboard

With Jenkins installed, it was time to explore the interface.

1. **Open a Web Browser**:
    
    * I navigated to `http://your-ec2-public-dns:8080`.
        
2. **Unlock Jenkins**:
    
    * To access the dashboard, I needed to retrieve the initial admin password using the following command:
        
    
    ```typescript
    bashCopy codesudo cat /var/lib/jenkins/secrets/initialAdminPassword
    ```
    
3. **Log In**:
    
    * Using the password, I logged into Jenkins for the first time, greeted by a setup wizard guiding me through the initial configuration.
        

## Step 5: Configure Jenkins

Customizing Jenkins to suit my project’s needs was a crucial step.

1. **Set Up Administrator User**:
    
    * The setup wizard prompted me to create an admin user, enhancing security.
        
2. **Configure Security Settings**:
    
    * I enabled security features and set up user roles for better access control, ensuring that sensitive operations were protected.
        

## Step 6: Install Plugins

One of Jenkins' strengths is its extensive plugin ecosystem, allowing for enhanced functionality.

1. **Plugin Manager**:
    
    * I navigated to **Manage Jenkins &gt; Manage Plugins**.
        
2. **Essential Plugins**:
    
    * I searched for and installed key plugins, including:
        
        * **Git Plugin**: For version control integration.
            
        * **Pipeline Plugin**: To facilitate the creation of complex CI/CD pipelines.
            
        * **Blue Ocean**: For a modern user interface that simplifies pipeline visualization.
            

## Step 7: Set Up Global Tool Configuration

Consistency across build environments is essential.

1. **Manage Global Tools**:
    
    * I navigated to **Manage Jenkins &gt; Global Tool Configuration**.
        
    * I configured tools such as:
        
        * **JDK**: Specifying the version of Java needed for builds.
            
        * **Maven**: Setting up Maven for managing dependencies and building projects.
            

## Step 8: Configure System Settings

Optimizing Jenkins for performance and resource management is critical.

1. **Executor Settings**:
    
    * I adjusted the number of executors based on my instance’s available resources, allowing multiple builds to run concurrently.
        
2. **Environment Variables**:
    
    * I defined environment variables necessary for my builds, ensuring that all jobs had access to the right configurations.
        

## Step 9: Manage Nodes

To distribute build tasks efficiently, I managed Jenkins nodes.

1. **Add Agent Nodes**:
    
    * If needed, I could add additional agent nodes for distributed builds by going to **Manage Jenkins &gt; Manage Nodes and Clouds**.
        

## Step 10: Create Freestyle Jobs

Setting up my first job was an exciting milestone.

1. **New Item**:
    
    * From the Jenkins dashboard, I clicked on **New Item**.
        
    * I entered a name and selected **Freestyle project**.
        
2. **Job Configuration**:
    
    * Under **Source Code Management**, I selected Git and entered my repository URL.
        
    * I configured build triggers, such as polling the SCM for changes.
        
3. **Build Steps**:
    
    * I defined the build steps, using shell commands to compile and package my application.
        
4. **Save and Build**:
    
    * After saving the configuration, I initiated a build by clicking **Build Now**, and I was thrilled to see my first automated job in action!
        

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729885364024/1db02547-bec5-44ec-9bf0-d4510b4e917b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729885357485/24a2badc-8c0f-43e9-9635-ff8557546195.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729885355181/eb0b8812-8315-4509-87f9-8066f798b33d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729885353270/e830d39e-c302-4c76-ad19-495fba1b4f01.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729885350068/c8dc1c32-509f-48cf-89b6-03caacaa2d02.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729885347005/2ff0f1d5-6aa0-4a82-9c5f-e9fe7dbfc70b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729885344188/91b3690c-ecde-49b6-b7e0-5516df0a94b3.png align="center")

## Conclusion

Setting up Jenkins on an AWS VM has been a rewarding experience, significantly improving my development workflow. By automating tasks, I’ve reduced manual errors and enhanced collaboration within my team. The user-friendly interface, combined with extensive plugin support, makes Jenkins an invaluable tool in any developer’s arsenal.

## Future Enhancements

1. **Transition to Pipeline as Code**: I plan to implement Jenkins Pipeline (Jenkinsfile) for a more robust CI/CD workflow.
    
2. **Integrate Automated Testing**: Adding automated testing tools like Selenium and JUnit will further enhance my pipeline.
    
3. **Configure Notifications**: Setting up notifications through email or Slack will keep the team informed about build statuses.
    
4. **Implement Backups**: A strategy for backing up Jenkins configurations and job data will safeguard against data loss.
    
5. **Monitoring Solutions**: Integrating tools like Prometheus will help monitor Jenkins performance and health.
    

## Resources

* Jenkins Official Documentation
    
* [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/index.html)
    
* Jenkins Plugins
    
* Continuous Integration Best Practices
    

Thank yu !!