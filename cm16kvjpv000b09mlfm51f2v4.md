---
title: "Temporary Access Made Easy : Secure S3 Object Management with Presigned URLs"
datePublished: Tue Sep 17 2024 15:17:33 GMT+0000 (Coordinated Universal Time)
cuid: cm16kvjpv000b09mlfm51f2v4
slug: temporary-access-made-easy-secure-s3-object-management-with-presigned-urls
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1726593597736/acdfc81d-d3ab-4faf-b7ab-c71f20a84f9b.jpeg
tags: s3, presignedurl, getobjectaccessthroughpresignedurl

---

A presigned URL in Amazon S3 is a temporary URL that allows users without direct access to your S3 bucket to download or upload files for a limited time, essentially granting temporary access to a specific object within your bucket without exposing your full AWS credentials.

### Benefits of using presigned URLs

**Security :** Since the URL is only valid for a limited time, it reduces the risk of unauthorized access to your S3 objects.

**Controlled access :** You can specify which users or applications can access specific objects by setting appropriate IAM permissions.

**Flexibility :** You can use presigned URLs to enable features like file sharing, image previews, or user-initiated uploads without exposing your full AWS credentials.

**Integration with third-party applications :** Easily integrate presigned URLs into your application to allow users to interact with your S3 data.

**Expiration time :** Always set an appropriate expiration time for your presigned URLs to prevent prolonged unauthorized access.

### How to create a presigned URL

**Access your AWS console**

Step 1 : Log in to your AWS account and navigate to the S3 service and hit create bucket name should be unique globally.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726584389853/28e89f41-9bde-4de3-ad96-b743b39ea7a5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726584336955/b1a07b6f-9f74-40d1-99cd-1e9a7fe47a75.png align="center")

**Step 2 : Select the object from your local and hit** upload or choose the specific object within your bucket that you want to generate a presigned URL for.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726584429163/dd6de065-6bf1-41cc-8ffa-de97b784350e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726584438874/2d41779b-2f33-4246-96ac-5657a712be9c.png align="center")

Step 3 : Generate the presigned URL at the top right corner hit the Open box dropdown click on Share with Presigned URL that allows temporary access.

* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726584513552/0a298354-ac58-4506-927f-45922a3b518b.png align="left")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726584470982/7e4e563c-87f4-411a-b235-0fae586c4c85.png align="left")
    
    Step 4 : How to use a presigned URL Share the URL with anyone you wants to give access of this URL .
    
    * ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726584756861/c00d8a76-22b9-4b88-9114-acf82cae0010.png align="center")
        
        Step 5 : Important part is how longer you will give access for this presigned URL.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726584772546/9c63147b-f72f-432d-b2f1-c7500620051b.png align="center")
        
        Step 6 : Simply copy and paste the presigned URL into a web browser or provide it to a user through your application.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726584818865/36559e3e-9847-4bc9-a104-d6ad5873282d.png align="center")
        
        * **Step 7 :** Access the object with the URL when the user clicks the URL, they will be able to download or upload the object depending on the HTTP method used to generate the presigned URL, without needing their own AWS credentials.
            
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726585025656/b61b3f1f-69f5-43cb-b81b-373b331e31f5.png align="center")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726584857094/376a24b7-9dbb-4802-823a-86a2699b132b.png align="center")
        
        Step 8 : Here we can see our presigned URL worked properly and accessed to the person with whom we wanted to share this file.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726585009604/00845bb8-c8aa-4c3a-a874-b4ddfd0ab10f.png align="center")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726584837928/39028d8d-9e1c-41e9-a631-265a9040c66b.png align="center")
        
        Step 9 : Fun part !! Handover and Monthly Cost.csv to them.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726584862846/bdf71548-1e39-4135-88a5-82c9093b4895.png align="center")
        
    
    **Step 10 : Consider security best practices :** Use a unique identifier or nonce when generating presigned URLs to further enhance security.
    
    Overall, Presigned URLs are used to access S3 objects securely and temporarily without exposing AWS credentials. They allow users to download or upload files with a time-limited URL, providing controlled access to specific S3 objects. This approach enhances security by avoiding the need for direct AWS credentials. It’s ideal for sharing files or integrating third-party services while maintaining fine-grained access control. Presigned URLs streamline access management in various applications and workflows.
    
    Thank Yu !!