---
title: "Let's Deploy a reddit-replica on kubernetes with ingress & push that replicate image of reddit to the dockerhub."
datePublished: Mon Sep 02 2024 07:06:27 GMT+0000 (Coordinated Universal Time)
cuid: cm0knq72000000ajth8iifvas
slug: lets-deploy-a-reddit-replica-on-kubernetes-with-ingress-push-that-replicate-image-of-reddit-to-the-dockerhub
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1725205629189/a60f9139-3f11-47f4-8dbc-3ef446198de4.jpeg
tags: docker, aws, kubernetes, reddit, minikube, devopsproject, reddit-clone-on-kubernetes-with-ingress

---

In this reddit-replicate project we are going to see how to pick code from github and build a docker image then how and push that image on dockerhub from CI server which is running on AWS console with t2.micro type of instance and pull that image from dockerhub on Deployment Server which also running on AWS console with t2.xlarge type of instance and how to create our deployment.

Here is the architecture of this reddit-replica application runing on kubernetes with ingress.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725249701807/1e9fa56a-7158-4a77-a51a-28b311675682.png align="center")

### **Here are some prerequisites that we need to get through this deployment.**

An AWS account and where are successfully running two different instances one on t2.micro for CI server and another on t2.xlarge for deployment server.

Installed Docker on both.

Installed Minikube.

Installed Kubectl.

Installed Git.

If they are not installed already on our AWS then lets begin the process.

**Step 1 :** Here we start with launching two different types of server based on AMI Ubuntu one is on t2.micro and other one is on t2.xlarge. And expose the port 3000 to anywhere.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725250325320/b8f2f185-29f1-46be-b4db-f6f16a8845d9.jpeg align="center")

**Step 2 :** Let's install Docker and setup our CI server.

```typescript
# Docker Installation
sudo apt-get update
sudo apt-get install docker.io -y
sudo usermod -aG docker $USER && newgrp docker
```

**Step 3 :** Clone this source code for reddit-clone from Github and enter to this reddit-clone directory.

```typescript
# Cloning from Github
git clone https://github.com/rksdutt/reddit-clone-k8s-ingress.git
cd reddit-clone-k8s-ingress
```

**Step 4 :** Here we are going to create Dockerfile to containerize the application.

```typescript
# Write a Dockerfile

FROM node:19-alpine3.15

WORKDIR /reddit-clone

COPY . /reddit-clone

RUN npm install

EXPOSE 3000

CMD ["npm", "run", "dev"]
```

**Step 5 :** Here are going to build Docker image through this Dockerfile and push this image to the dockerhub.

```typescript
# Build Image & Push it on DockerHub
docker build . -t rakeshdutt/reddit-clone
docker images
docker login
docker push rakeshdutt/reddit-clone
```

**Step 6 :** Here we can see our Docker image pushed on Dockerhub successfully.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725252354483/7c08e735-1ff1-465c-a829-221bef470ebd.png align="center")

**Step 7 :** Now its time to setup our Deployment Server

```typescript
# Docker Installation
sudo apt-get update
sudo apt-get install docker.io -y
sudo usermod -aG docker $USER && newgrp docker
```

**Step 8 :** Here we are going to install Kubectl and Minikube and set up our Deployment server.

```typescript
# Minikube Installation
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube 
# Installation of Kubectl
sudo snap install kubectl --classic
# Start Minikube
minikube start --driver=docker
```

**Step 9 :** Here we are going to check if minikube is installed correctly.

```typescript
# Check Minikube status
minikube status
```

**Step 10 :** Here we can see everything goes well till now..

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725255306187/bdd16b36-469f-451e-b0f6-d5c16d6285e2.png align="center")

**Step 11 :** So lets write the manifest files to to deploy the applicatiion. Lets make a folder and write the deployment.yml and service.yml & ingress.yml manifest files.

```typescript
# Making a Folder
mkdir k8s
cd k8s/
```

**Step 12 :** Let's write the deployment.yml

```typescript
# Write deployment.yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: reddit-clone-deployment
  labels:
    app: reddit-clone
spec:
  replicas: 2
  selector:
    matchLabels:
      app: reddit-clone
  template:
    metadata:
      labels:
        app: reddit-clone
    spec:
      containers:
      - name: reddit-clone
        image: rakeshdutt/reddit-clone
        ports:
        - containerPort: 3000
```

**Step 13 :** Lets write the service.yml

```typescript
# Write service.yml
apiVersion: v1
kind: Service
metadata:
  name: reddit-clone-service
  labels:
    app: reddit-clone
spec:
  type: NodePort
  ports:
  - port: 3000
    targetPort: 3000
    nodePort: 31000
  selector:
    app: reddit-clone
```

**Step 14 :** Here we are going to deploy the application and service on kubernetes cluster.

```typescript
# Deployment and Verify
kubectl apply -f deployment.yml
kubectl get deployment
kubectl apply -f service.yml
kubectl get services
```

**Step 15 :** Here we can see our application running successfully.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725256565661/42b5b360-3a27-4e7c-922a-e36804498499.png align="center")

**Step 16 :** Here we are going to verify both our services are running or not.

```typescript
# Verify the Deployment
minikube service reddit-clone-service --url
```

**Step 17 :** Here we can see everything going well as we expected.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725257133825/7117bd41-9985-43c6-b6d9-8774d3d96081.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725259092169/c78a0494-e753-4c89-88d2-ea58abb93c32.png align="center")

**Step 18 :** Let see our application deployed or not with this command

```typescript
# Verify the Apllication
curl -L http://192.168.49.2:31000
```

**Step 19 :** Here we are going apply ingress to route outside traffic to the application.

```typescript
minikube addons enable ingress
```

**Step 20 :** Its time to write ingress.yml

```typescript
# Write ingress.yml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: ingress-reddit-app
spec:
  rules:
  - host: "domain.com"
    http:
      paths:
      - pathType: Prefix
        path: "/test"
        backend:
          service:
            name: reddit-clone-service
            port:
              number: 3000
  - host: "*.domain.com"
    http:
      paths:
      - pathType: Prefix
        path: "/test"
        backend:
          service:
            name: reddit-clone-service
            port:
              number: 3000
```

**Step 21 :** Lets do the deployment and verify everything going well or not..

```typescript
# Deployment and Verify and Expose the Application and Map the Expposed Port
kubectl apply -f ingress.yml
kubectl get ingress ingress-reddit-app
kubectl expose deployment reddit-clone-deployment --type=NodePort
kubectl port-forward svc/reddit-clone-service 3000:3000 --address 0.0.0.0
# If we Wanna keep the our Application Running just add & end of this
kubectl port-forward svc/reddit-clone-service 3000:3000 --address 0.0.0.0 &
# Test the deplyment through ingress
curl -L domain.com/test
```

**Step 22 :** Here we can see our applicstion is deployed & running successfully.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725259209563/9cee449e-5473-4d09-8526-e277337eae00.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725259618996/98f2d704-92df-47b7-82d6-753d70cf59de.jpeg align="center")

We have successfully deployed a Reddit replicaton on a Kubernetes cluster with Ingress enabled. By following these steps we have containerized the application, deployed it to Kubernetes and exposed it via Ingress for outiside world.