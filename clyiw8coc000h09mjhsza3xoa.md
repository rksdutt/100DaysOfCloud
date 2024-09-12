---
title: "Brief on AWS Load Balancer 🌥️ ⚖️ !!"
datePublished: Fri Jul 12 2024 16:09:33 GMT+0000 (Coordinated Universal Time)
cuid: clyiw8coc000h09mjhsza3xoa
slug: brief-on-aws-load-balancer
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1720800403554/e2e41460-b0ee-48f8-a384-9a71a1d9179a.png
tags: alb, 2articles1week, nlb, awselb, gwlb

---

Load balancers prevent servers from getting overloaded by managing their workload. This speeds up cloud services, improves response times, and ensures stability. They analyze why workloads might become uneven and use methods like physical or virtual setups and application delivery controllers (ADCs) to optimize web and microservices applications for better performance and security.

Overall, A load balancer is like a traffic manager for servers. Load balancers improve application performance by increasing response time and reducing network latency. They perform several important functions like, distribute load equally among servers to improve application performance. Redirect client requests to geographically closer servers to reduce latency and ensures our website or app stays online even if one server has a problem.

AWS offers a variety of load balancers to match the unique needs of different applications and services, so customers can choose the best-fit option based on performance, cost, and specific application requirements.

**Let's see different types of Load Balancing :**

**Static Load Balancing :** Static load balancing uses specific algorithms to distribute the workload between servers. These algorithms follow a fixed schedule like Round Robin(who dirtributes traffic to the list of servers in rotation using DomainNameSystem), where each server receives requests equally regardless of current load or capacity. This is easy to implement but may not equal resource utilization if servers have different capacities or different workloads.

**Dynamic load balancing :** Dynamic load balancing adjusts in real-time based on server state and workload variations. Algorithms like minimum connection or minimum response time distribute incoming requests to servers with fewer active connections or faster response times means low latency like a ping response in 40 to 60MS. This flexibility optimizes resource allocation and increases performance by adapting to changing traffic patterns and server capacity.

### Let's check out the key features and benefits of Elastic Load Balancing (ELB)

**High Availability :** ELB makes sure our app always checks if Amazon's servers are running before sending visitors there. It can also use Amazon Route 53 to switch to backup servers if needed, making our app more reliable.

**Auto Scaling :** AWS uses Auto Scaling to manage how many EC2 instances are working with ELB. It changes how many are running based on how many people are visiting your site or using your app. This keeps things running fast and smooth, even if a lot of people start using it.

**Security :** It helps secure applications using Amazon's private network known as Virtual Private Cloud (VPC). We can choose whether your load balancer is internet facing or internal, directing traffic using private IP addresses for added security.

**Traffic distribution :** It spreads incoming visitors or users across many servers or containers, such as EC2 instances. This prevents any one server from getting too much work, ensuring that all servers are used efficiently.

**Availability and Fault Tolerance :** This helps our application run smoothly by noticing when the servers are not working properly and sending traffic to them. That way, problems don't affect our application much because it stops sending traffic to bad servers until it's fixed.

**Health Check :** We can set up checks that regularly check how well your servers are working. ELB only sends traffic to servers that pass these checks, which keeps your application running smoothly.

### **let's check out there are three types of Load Balancer in AWS**

**Classic Load Balancer (CLB) :** Classic load balancer is an older type of load balancer in AWS. They are still around for applications that have not yet switched to the new load balancer options from AWS.*(Not Much handy with modern infrastructure and environment.)*

**Application Load Balancer(ALB) :** Application Load Balancer (ALB) is great for managing web traffic like websites and apps that use HTTP or HTTPS. They can also do more advanced things like direct traffic based on specific content.

AWS Elastic Load Balancing spreads incoming traffic across multiple targets like EC2 instances, containers, and IP addresses in different Availability Zones. There is Application Load Balancers (ALB) stands out, which handles advanced routing and content-based traffic management at the application layer.

ALB in AWS directs traffic to specific target groups based on content. It is designed for advanced routing and traffic management at the application layer, supporting a variety of applications such as Web Sockets, HTTP, HTTPS, microservices, and containers with seamless integration with EC2 services. ALB handles routing requests from multiple applications to a single EC2 instance and supports features such as cross-zone load balancing and sticky sessions using load balancer-generated cookies.

**How ALB Works --**

**Traffic Routing :** ALB directs incoming requests to specific backend servers or services based on the content of the request, such as URL path or domain name.

**Application Layer Features :** Operating at Layer 7, ALB understands HTTP, HTTPS, and other application-layer protocols. It supports advanced routing features such as path-based and host-based routing for efficient traffic management across EC2 instances or applications hosted in containers.

**Network Load Balancer (NLB) :** It is designed to handle internet traffic very quickly and with low latency. They are great for apps that require high performance for things like online games or video streaming.

AWS Elastic Load Balancing spreads incoming traffic across different targets like EC2 instances, containers, and IP addresses in different Availability Zones. Network load balancers (NLB) are particularly good at handling this traffic quickly and efficiently at a deeper level of network processing.

NLB handles large traffic spikes across EC2 instances to keep everything running smoothly. It uses the TCP protocol to manage connections and ensure data is delivered reliably. NLB adapts to different workloads and can handle a large number of requests per second. We can use Static IP or Elastic IP with NLB for different network setup. Cross-zone load balancing is not enabled by default in NLB. It sends the client IP address to applications using the instance ID as the target. NLB allows clients to connect from VPCs in different AWS regions, AWS VPNs, and third-party VPNs.

**How NLB Works --**

**Listeners :** Listeners in NLB wait for incoming connection requests from clients. They are set up with specific protocols and ports to manage how traffic enters.

**Target Groups :** These groups direct incoming requests to selected targets such as EC2 instances or IP addresses. You can configure target groups to support different protocols (TCP, UDP, TCP\_UDP, TLS), providing flexibility decide how traffic is handled.

**Gateway Load Balancer (GWLB) :** Used to deploy and manage third-party network security tools such as firewalls and intrusion detection systems. They ensure that network traffic is filtered and monitored effectively to protect against unauthorized access and potential threats.

AWS Elastic Load Balancing spreads incoming network traffic across multiple targets like EC2 instances, containers, and IP addresses while checking their health. A notable type is the Gateway Load Balancers (GWLB), which is designed to deploy and manage virtual appliances.

GWLB makes it easy to scale, install and manage third-party virtual appliances. It uses a single gateway to distribute traffic across multiple virtual appliances, adjusting their capacity as needed. GWLB increases network reliability by reducing the risk of breakdown. Users can easily find, test, and purchase virtual appliances from third-party vendors through the AWS Marketplace, speeding up deployment for faster results.

**How GWLB Works --**

**Traffic Distribution :** The GWLB acts as a central hub that receives incoming traffic and directs it to multiple virtual appliances based on predefined rules. This ensures that traffic is evenly distributed across these appliances for efficient processing.

**Application Layer Features :** Operating at Layer 7, ALB understands HTTP, HTTPS, and other application-layer protocols. It supports advanced routing features such as path-based and host-based routing for efficient traffic management across EC2 instances or applications hosted in containers.

Overall, AWS ELB simplifies load balancing operations, improves application scalability and availability, enhances security, and seamlessly integrates with other AWS services to provide a robust and reliable solution for managing traffic across applications and services.