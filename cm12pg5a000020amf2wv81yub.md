---
title: "Deployed a Voting App & Set up a KinD & Argo CD with Kubernetes cluster on AWS EC2."
datePublished: Sat Sep 14 2024 22:14:28 GMT+0000 (Coordinated Universal Time)
cuid: cm12pg5a000020amf2wv81yub
slug: deployed-a-voting-app-set-up-a-kind-argo-cd-with-kubernetes-cluster-on-aws-ec2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1726431133092/89cd014d-2279-46ce-bc88-7dd31ce491a3.jpeg
tags: kubernetes, kind, argocd, polling-app

---

In this article, we’ll guide you through deploying the Voting App from the kubernetes-kind-voting-app GitHub project on an AWS EC2 instance. First, we’ll briefly introduce Kubernetes and Kind, the tool we'll use for local Kubernetes clusters.

**Prerequisites are of this Project.**

Having an AWS account and launch an ubuntu instance with type of t2.xlarge.

Then we’ll go through with basics of Linux and Docker commands.

Step 1 : On the AWS Console need to launch an ubuntu instance with type of t2.xlarge( where we expect the space is 16GB and 4 cpu ) with the name of kubernetes cluster and configure the storage of this instance is 15GB then click on launch instance.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351775322/7a987a21-d0d5-400d-b5cb-3ebc0d7ff076.png align="center")

Step 2 : After a while when instance is up and running then ssh into it and install docker on it with this commad. First thing is to update your terminal through this command.

```typescript
$ sudo apt-get update
$ sudo newgrp docker
$ sudo apt-get install docker.io
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351781300/e37d707f-1a89-4f27-8803-f7e8a3da1f37.png align="center")

Step 3 : Start the Docker service and ensure it runs on boot. And to verify that Docker is installed and running or not.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351827036/2201d89a-b4e4-43fc-8c71-0ddd71c7705f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351792767/edccd5ce-46df-42e7-a71a-760342d91884.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351816305/611a1231-2798-42de-bfed-dafc325d3e20.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351822039/5864a7a5-c34c-4d57-ae06-8d6ae57ca2c0.png align="center")

```typescript

$ sudo usermod -aG docker $USER
$ sudo reboot
$ docker --version
$ docker ps
```

Step 4 : Download and install kind here we will write a bash script to install kind and give it a permission for execute.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351832165/95df5b0d-b43e-4fc5-8e80-778fb509aba9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351836432/3300abaa-90f6-4a45-ae6b-e8668fd4ed78.png align="center")

```typescript
$ vim install_kind.sh
#!/bin/bash
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.20.0/kind-linux-amd64
chmod 421 ./kind
sudo mv ./kind /usr/local/bin/kind
```

Step 5 : After installation we will run this command on terminal.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351859646/0ad2c2f8-2add-4c41-8d56-723a330a2036.png align="center")

```typescript
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.20.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind
```

Step : 6 Here we will install kubectl on our vm.

```typescript
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/kubectl
```

Step 7 : Verify the installation.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351840478/a163e91a-0978-4460-806c-578c82f0948c.png align="center")

```typescript
$ kind --version
$ kubectl version --client
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351873338/f1b3b4ed-5cd4-44f1-920a-a8a40e93f277.png align="center")

Step 8 : Create a Kubernetes Cluster with kind.

We will create a 3-node Kubernetes cluster using **kind**. This will include one control plane node and two worker nodes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351878604/fbf602f6-e2a7-425e-96aa-3ea795ccebd5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351878604/fbf602f6-e2a7-425e-96aa-3ea795ccebd5.png align="center")

```typescript
$ vim cinfig.yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4

nodes:
- role: control-plane
  image: kindest/node:v1.31.0  # Match this with kubectl version
- role: worker
  image: kindest/node:v1.31.0  # Match this with kubectl version
- role: worker
  image: kindest/node:v1.31.0  # Match this with kubectl version
```

Step 9 : Create the Cluster

Now, use this configuration file to create a 3-node cluster with kind

```typescript
$ kind create cluster —config=config.yaml.yaml —name=<cluster1>
```

Step 10 : Verify the cluster.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351883305/0cacc84f-8bef-4271-805c-10b3f7de25a0.png align="center")

```typescript
$ kubectl cluster-info
$ kubectl get nodes
```

Step 11 : Installing and Configuring Argo CD & Create an ArgoCD Namespace

In this step, we will install **Argo CD**, a declarative GitOps continuous delivery tool for Kubernetes.

Step 12 : First, create a dedicated namespace for ArgoCD.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351888996/19b99a08-2151-4777-9492-2a57f0efe75c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351895244/dc416ee4-d4bb-48bc-b8be-6c1275a03eaf.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351898972/4ea392b6-6aa0-482a-9cc4-18f5c4a84884.png align="center")

```typescript
$ kubectl create namespace argocd
$ dockr ps
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351902028/200a0e1b-d63e-4f19-a382-86b174a12302.png align="center")

Step 13 : Install ArgoCD Now, install ArgoCD by applying the installation YAML file.

```typescript
$ kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Step 14 : This command will download and install all the necessary resources for Argo CD in your Kubernetes cluster.

Step 15 : Check Argo CD Services. Verify that the services for Argo CD have been created and are running.

```typescript
$ kubectl get svc -n argocd
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351913080/0cf50f00-c462-43bf-b0f0-b7cc04a9cd10.png align="center")

The output will show the services created by Argo CD, including the `argocd-server`. By default, the `argocd-server` service will be of type **ClusterIP**, meaning it is accessible only within the Kubernetes cluster.

To make the `argocd-server` accessible from outside the cluster, we need to change the service type from `ClusterIP` to `NodePort`. This will expose the Argo CD server on a port accessible via the external IP of any node in the cluster. We will do this in the next step.

Step 16 : **Expose the Argo CD Server using NodePort** Expose the Argo CD server to allow access via a `NodePort`.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351910216/f81821e2-19a8-4531-a840-15b80f83620f.png align="center")

```typescript
$ kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "NodePort"}}'
```

Step 17 : Access the Argo CD Server. Forward the Argo CD server port to your local machine to access the Argo CD UI

```typescript
$ kubectl port-forward --address 0.0.0.0 -n argocd service/argocd-server 8443:443 &
$ https://<EC2_PUBLIC_IP>:8443 (on your search engine)
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351930163/5132fc2d-89bf-4a38-ab7d-90edfd108a6c.png align="center")

Step 18 : **Login to ArgoCD.** Retrieve the initial ArgoCD admin password.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351934398/749d4f8e-c096-4935-847f-e011d867435f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351938756/ca06afbd-7aeb-4478-82ef-13d20da9e494.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351946477/64f66d09-3d5a-4db7-9940-71e30e166df3.png align="center")

```typescript
$ kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d
```

Step 19 : You will get this type of reply as -

```typescript
$ kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d
  && echo a3ls9GRXpSrhq9Xv
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351957495/ccaf8874-2fed-4cd7-978e-2bb2a97a7af9.png align="center")

Step 20 : Deploy the Poling App & Create an Argo CD Application

Next, you’ll create an Argo CD application to deploy the Polling App.

In the Argo CD UI, go to **Applications** and click **Create Application**.

Fill in the following fields :

Application Name: `polling-app`

Project: `default`

Sync Policy: You can either choose manual or automated sync as needed.

Step 21 : Access the Voting App. Now that the Voting App is deployed and the pods are running, you can access the application by exposing the services.

Step 22 : Verify Services & First, check that the services for the app have been created.

```typescript
$ kubectl get pods
$ kubectl get svc
```

Step 23 : Port Forward to Access Services. To access the application locally, forward the ports for both the `vote` and `result` services. Use the `--address=0.0.0.0` flag to allow connections from outside [localhost](http://localhost):

Forward port for the `vote` service

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351954148/0a42cfd2-0d11-4c36-8f5b-199c0327e9a3.png align="center")

```typescript
$ kubectl port-forward svc/vote 5000:5000 --address=0.0.0.0 &
$ kubectl port-forward svc/result 5001:5001 --address=0.0.0.0 &
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351973857/727c1904-11bc-4dda-82bb-0383a098e912.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351981964/ae49f28a-9172-4960-8e81-5fa967988c7f.png align="center")

Step 24 : Configure Security Group & Ensure that your EC2 security group allows inbound traffic on ports `5000` and `5001`. You can do this by expose on the aws instance security inbound rule 5000 & 5001.

Step 25 : Installing Kubernetes Dashboard. To manage your Kubernetes cluster more effectively, you can install the Kubernetes Dashboard. Follow these steps to deploy the dashboard and set up access.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351961059/30a3b0e3-0d23-4214-999b-ebd41df60737.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351967756/958906da-b93f-475d-9cb5-2b50440f29fa.png align="center")

```typescript
$ kubectl create namespace kubernetes-dashboard namespace/kubernetes-dashboard created
$ kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml
```

Step 26 : To create dash first we need this

```typescript
$ vim dashboards.yaml
apiVersion: v1
kind: ServiceAccount
metadata:
  name: admin-user
  namespace: kubernetes-dashboard
---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: admin-user
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: cluster-admin
subjects:
- kind: ServiceAccount
  name: admin-user
  namespace: kubernetes-dashboard
```

Step 27 : Deploy Kubernetes Dashboard & Install the Kubernetes Dashboard by applying the recommended manifest…

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351978456/bc3e78a0-58b7-461e-ae23-9249dd52fe0a.png align="center")

```typescript
$ kubectl apply f dashboard.yaml 
serviceaccount/admin-user created clusterrolebinding.rbac.authorization.k8s.io/admin-user created (output will came out)
```

Step 28 : After applying the Service Account and RBAC configuration, create a token for the `admin-user`

```typescript
$ kubectl -n kubernetes-dashboard create token admin-user
eyJhbGciOiJSUzI1NiIsImtpZCI6Ii1JSTFpWHBMaXhQc1NMM0Vmdy1LR3FVbnNPczN6RGQ5dGowRUExRGV6S2cifQ.eyJhdWQiOlsiaHR0cHM6Ly9rdWJlcm5ldGVzLmRlZmF1bHQuc3ZjLmNsdXN0ZXIubG9jYWwiXSwiZXhwIjoxNzI2MzQ1NTk3LCJpYXQiOjE3MjYzNDE5OTcsImlzcyI6Imh0dHBzOi8va3ViZXJuZXRlcy5kZWZhdWx0LnN2Yy5jbHVzdGVyLmxvY2FsIiwianRpIjoiM2M1ODQ5MTgtNjNkMi00M2JlLWEzMTUtN2FkNWM2MWI4OWU3Iiwia3ViZXJuZXRlcy5pbyI6eyJuYW1lc3BhY2UiOiJrdWJlcm5ldGVzLWRhc2hib2FyZCIsInNlcnZpY2VhY2NvdW50Ijp7Im5hbWUiOiJhZG1pbi11c2VyIiwidWlkIjoiZDg4NmQxYmUtYzgxYS00MmU2LTllNjctOWJmZmQ1MzI2MTE2In19LCJuYmYiOjE3MjYzNDE5OTcsInN1YiI6InN5c3RlbTpzZXJ2aWNlYWNjb3VudDprdWJlcm5ldGVzLWRhc2hib2FyZDphZG1pbi11c2VyIn0.MBD0WKLphctpx9pSG6TwQUfsGQ8gfGRhXqpEVXcIaDYdge9LPs3gvrSCQb6_b9mPmiJ-BsXnrz1ynT_Ozp8ZzPUt7XX7y8xp0lzfrzeCRLVeJG7htXc3AIerTtUz5zZ7n18mnsxqPjTNFEjCD6EkZYwv4Z0oudNxpuxuXr7v_2Uj_cZfuWvQYsx6zbo7l-wKTsMJP8EM9bbawLi45Q3ttUkW2QO5OqKmiZGFOo5hTSmVFeI0dQARZWE5ZdexEKp4aH68iyXKNB3QnMmYq4Eh5aTybSmSuhm0nvMQm9eq94DFdPNeuuLNreRENgquCmLbK95RGHMrPmN8Gd4065lY2Q
(the token)
```

Step 29 : Access the Kubernetes Dashboard & to access the dashboard locally, forward the port for the Kubernetes Dashboard service.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726352014206/45d4651b-2a4d-41c2-9090-d5f61e4e04ab.png align="center")

```typescript
$ kubectl port-forward -n kubernetes-dashboard svc/kubernetes-dashboard 8080:443 --address=0.0.0.0 &
$ https://98.80.212.3:8080/ (on your search engine)
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726351998907/8f263a74-3ed4-4ad6-941e-962e0f248f7d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726352004377/b83fea41-3598-4814-9684-209caf4500f6.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726352020882/c7c05d45-c9e9-42f9-88f5-46a4e7785595.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726352007747/ab336931-52ce-4727-afb8-2f093e226a78.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726352028092/244a37ce-d1c0-4b13-9d8e-f6858258a537.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726352057472/b2799f37-a4f4-4b34-a5df-ae041cf7a8d1.png align="center")

**Introduction to Kind and ArgoCD** : We introduced Kubernetes in Docker (Kind) for creating local clusters and ArgoCD for continuous deployment.

**Prerequisites** : We ensured that we had an AWS account, basic Linux, and Docker knowledge, and outlined the steps to set up an EC2 instance with Ubuntu.

**Setting Up EC2** : We created an EC2 instance, configured security groups, and installed Docker and Kind.

**Creating a Kubernetes Cluster with Kind** : We created a 3-node Kubernetes cluster using Kind with the appropriate Kubernetes version.

**Installing ArgoCD** We deployed ArgoCD, exposed its service, and configured port forwarding. We also set up the necessary security group rules for external access.

**Deploying the Voting App** : We created an ArgoCD application to deploy the Voting App from a GitHub repository, synced the application, and verified that the pods were running correctly.

**Accessing the Application** : We configured port forwarding for the `vote` and `result` services and updated the EC2 security group to allow traffic on the necessary ports.

**Installing Kubernetes Dashboard** : We deployed the Kubernetes Dashboard, set up a Service Account and RBAC, created a token for access, and configured port forwarding for the dashboard.

In this blog post, we successfully deployed a Kubernetes-based Voting App on AWS EC2, utilizing Kind for local Kubernetes clusters and ArgoCD for continuous deployment. We also set up the Kubernetes Dashboard for enhanced cluster management.

thank yu !!