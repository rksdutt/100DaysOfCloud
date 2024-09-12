---
title: "Deploying a Simple Django-Notes-app on Local Server through the Shell Script with handling errors  & pushed it to the docker.hub🚀✅"
datePublished: Mon Aug 19 2024 20:46:27 GMT+0000 (Coordinated Universal Time)
cuid: cm01guswu000308k0cbb7c7w0
slug: deploying-a-simple-django-notes-app-on-local-server-through-the-shell-script-with-handling-errors
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1724100665501/fe58030a-3fdc-49a6-b971-c64a9e0304c0.jpeg
tags: django-notes-app, simpleproject

---

In this blog, we'll see how to deploy a Django Notes app using Nginx and Docker. This guide will cover everything from setting up to launching our app so it's live on the local.

**Here's what to expect :**

**Setup :** We'll start by preparing everything we need.

**Containerization :** How to use Docker to build, create and manage containers for our app.

In the end of the simple project we'll know how to effectively deploy our Django app using these tools. Whether you're experienced or beginner, we'll make sure you have the knowledge to succeed.

Let's Start,,,

We will covering this projects through Shell Scripting. So, we need to create a file like this

```typescript
$ vim django-app-deployment.sh 
or 
$ touch django-app-deployment.sh
```

To set up our development environment for the django-notes-app going thrugh the blog...

**Step 1 : Clone the Repository**

First, we need to get the source code for the django-notes-app from GitHub repo. We are going to get into that file we created and put following commands on the script.

```typescript
git clone https://github.com/rksdutt/django-notes-app.git
```

**Step 2 : Install dependencies**

After that we need install the required packages listed in the requirements.txt file through the script.

```typescript
install_requirements()
        echo "Installing dependencies"
        sudo apt-get update && install docker.io nginx -y
```

**Step 3 : Required restart**

After giving the permission to the docker.sock we need restart the system through our script.

```typescript
required_restart()
        sudo chown $USER /var/run/docker.sock
        sudo systemctl enable docker
        sudo systemctl enable nginx
        sudo systemctl restart docker
```

**Step 4 : Deployment**

After that we need to build that image for docker and run it like this on the script.

```typescript
deploy() 
        docker build -t notes-app .
        docker run -d -p 8000:8000 notes-app:latest
```

**Step 5 : Handling Errors code cloning**

Our Job is not done here, we will handling all errors through the runtime of this application on each steps with condition statements.

```typescript
if code_clone; then
        echo "the code dir already exists"
        cd django-notes-app
fi
```

**Step 6 : Handling Errors Installing dependencies**

If there is any problem in installaton on dependencies or the code ran earliar or the object already exists.

```typescript
if ! install_requirements; then
        echo "Installation failed"
        exit 1
fi
```

**Step 7 : Handling Errors Installing dependencies**

If there is a problem on local server on restart dependencies then this conditions will helps to take the problem away.

```typescript
if ! required_restart; then
        echo "System fault identified"
        exit 1
fi
```

**Step 8 : Docker login**

First of all we need to log in to the repo...

```typescript
$ docker login
Username : asdfghjkl
Password : lkjhg@212
```

**Step 9 : Docker tag to Pushed image to the docker hub**

First we need to tag that build image with username like that

```typescript
$ docker image tag asdfghjkl/notes-app:latest notes-app:latest
```

**Step 10 : Docker push**

**Here we can push the image to the docker hub like this..**

```typescript
$ docker push sdfghjkl/notes-app:latest
```

**Step 11 : Here all things in one script and errors will be handled by the script itself.**

```typescript
#!/bin/bash

<< task
Deploy a Django app
and Handling the errors
task


code_clone() {
        echo "Cloning the django app..."
        git clone https://github.com/rksdutt/django-notes-app.git

}


install_requirements() {
        echo "Installing dependencies"
        sudo apt-get install docker.io nginx -y
}


required_restart() {
        sudo chown $USER /var/run/docker.sock
        sudo systemctl enable docker
        sudo systemctl enable nginx
        sudo systemctl restart docker
}

deploy() {
        docker build -t notes-app .
        docker run -d -p 8000:8000 notes-app:latest
}
push_to_docker_repo() {
        echo "Logging in to Docker Hub..."
        docker login -u $asdfghjkl -p $lkjhg@212

        echo "Tagging Docker image..."
        docker tag notes-app:latest $asdfghjkl/notes-app:latest

        echo "Pushing Docker image to Docker Hub..."
        docker push $asdfghjkl/notes-app:latest
}

echo "********** DEPLOYMENT STARTED ************"

if code_clone; then
        echo "the code dir already exists"
        cd django-notes-app
fi

if ! install_requirements; then
        echo "Installation failed"
        exit 1
fi
if ! required_restart; then
        echo "System fault identified"
        exit 1
fi
deploy

echo "********** DEPLOYMENT FINISH ************"
```

We have reached an important milestone in our deployment journey. Here's what we've done so far and recall the steps again.

Set up local server : We have prepared our server.

Repository cloned: We downloaded the Note app code from GitHub.

Installed Dependencies: We have installed all the required packages for the app.

Restarted everything : After fixing some permission issues, we restarted everything to make sure it works smoothly with Nginx and Docker.

Everything should now be in place and ready for further testing and improvement and here our django-notes-app running successfully.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724100302983/633d9b18-a268-4e7d-8c31-a8ace0426754.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724103016361/7921ddfa-3a77-4430-aa00-a43c91eda072.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724100310366/87928a72-ab82-4263-a7bf-6734c0597579.png align="center")

Thank yu !!🙂