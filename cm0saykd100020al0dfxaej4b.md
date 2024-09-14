---
title: "Deploying a Website on Amazon EC2 with the Amazon Linux Operating System, AWS Service Project."
datePublished: Sat Sep 07 2024 15:31:11 GMT+0000 (Coordinated Universal Time)
cuid: cm0saykd100020al0dfxaej4b
slug: deploying-a-website-on-amazon-ec2-with-the-amazon-linux-operating-system-aws-service-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1725716585836/e1a2384e-62ae-4b76-8dcd-ae559d2efb75.jpeg
tags: website, cloud, devops, httpd, ec2-instance

---

This entire guide helps you through each step necessary for a successful Amazon EC2 instance hosting using the Amazon Linux AMI. Starting from how to set up your EC2 instance in the beginning and in the end where you deploy your website. Launch an EC2 instance, establish secure connection with it, install and configure web server and make sure that everything is working.  
  
In a nutshell, this blog purpose is to provides guidelines on how to configure webserver and Host it. For those new to AWS or looking for a systematic approach to website hosting, this guide provides clarity and guidance.

**Prerequisites are :- 1. Having a AWS Console Account.**

To register for an AWS account you need go to [aws.amazon.com](http://aws.amazon.com) and click on “Create your AWS Account” after which you will be asked to fill in your email, password and account name. After providing personal information including payment methods you will need to verify your identity and select a support plan. Last but not least one needs to accept the Terms of Service to start using the AWS Management Console along with completing the creation steps.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725722466099/6d76324a-8847-44fd-aa0e-aff46fb59071.png align="center")

**2\. Having a Insatnce which are running on Amazon Linux -ami.**

To launch an EC2 instance on Amazon Linux you need to log in to the AWS Management Console. Choose a region that suits you. On navigation bar search for EC2 and click "Launch Instance". Choose Amazon Linux 2 AMI, then select instance type `t2.micro` configure details and security settings and then select a key-pair click "Launch" . After the instance state on running then connect it with ssh or amzon ec2 connect.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725722587418/04094978-e841-4b82-8b52-0636b4a86f03.png align="center")

**Step 1 :** Log into your console and connect to the launched Ec2 instance through Amazon Ec2 Linux Connect.

**Step 2 :** After getting connected with Ec2 instance we have to update our server.

```typescript
Update Your System
sudo yum update
```

Step 3 : After sytem got updated then simply go to the root or act as a root user.

```typescript
To Act as A root User
sudo su -
```

Step 4 : Now as a root user install httpd on your server through this command.

```typescript
Install the apache Server
yum install httpd -y
```

Step 5 : Check the installation through this command.

```typescript
Check Services
systemctl status httpd
```

Step 6 : Then you have to make a directory call temp/ through this command.

```typescript
Make a Directory & Move into this or change diretory :
mkdir temp/
cd temp/
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725722488707/943aa35f-67cc-4957-a18e-814468b3d578.png align="center")

Step 7 : Here we will going to download a zip file through hosting website link through this command.

```typescript
Download the Website link thourgh wget Command
wget https://www.free-css.com/assets/files/free-css-templates/download/page296/neogym.zip
or you can use your desired directory by expolring by your own like this :
wget https://www.toolplate.com/zip-templates/2135_mini_finance.zip
```

Step 8 : After downloaded the zip file we need to unzip this file through this command.

```typescript
Unzip the file according to your Download.
unzip <file.name.zip>
```

Step 9 : After the unzipping the file we need to move into this unzip directory.

```typescript
Move into unzip Folder & see What inside of it
cd <directory name>
ls -ltr
```

Step 10 : Whatever in this directory we need to move it to a default root folder of the webserver through this command.

```typescript
Move everything from Unzip Folder to default root Folder and Check Everything is Available you Want to Move.
mv * /var/www/html/
cd /var/www/html/
ls -ltr
```

Step 11 : After doing all this setup now we need to enable our httpd server which we downloded earliar through this command.

```typescript
Check status of the Server and Enable the Server and Start the Server.
systemctl status httpd
systemctl enable httpd
systemctl start httpd
systemctl status httpd
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725722551277/1f434ca1-99c8-4ed8-8aaf-c7b89202f03f.png align="center")

Step 12 : Now after all this step go back to your AWS Console and take the public IP and put it on your search engine.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725722369144/ca769794-2437-4c92-ad72-92c20f8bb8f8.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725722404750/2d887cd3-b0ec-4bd3-91db-aee1af876266.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725722419085/38daaf8b-0a5f-4062-8c74-d2f2a5c06356.png align="center")

Well done! You have hosted your static website successfully on a AWS EC2 instance. Don't forget to terminate the instance, remove all services you've created for the project tidy up Everything. By using cloud computing resources to deploy and manage a static website we gained insight into the process of such a project.

Thank Yu !!