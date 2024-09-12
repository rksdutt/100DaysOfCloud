---
title: "Deployed🚀 a two-tier flask & mysqldb applicaton with advanced Shell Script commands integration call MAKEFILE📂."
datePublished: Fri Aug 23 2024 16:41:59 GMT+0000 (Coordinated Universal Time)
cuid: cm06xvtx1001309jyhn6j2f7b
slug: deployed-a-two-tier-flask-mysqldb-applicaton-with-advanced-shell-script-commands-integration-call-makefile
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1724443409352/981ed833-a05d-4f1f-b9c5-c32f7a8d8f10.jpeg
tags: makefile, command-compilance, two-tier-flask-application, makefilefortwotierapp

---

A makefile is a text file that works with the Unix make utility to automate the process of compiling and linking source code to create an executable. It lists source files, compiler options and recompilation rules, making it easy to manage complex builds and dependencies. While Makefiles are specifically designed for efficient project builds, such as compiling code, shell scripts are more general tools for various automation tasks. Makefiles can use shell scripts but focus on streamlining the build process.

### Let's begin the deployment ,,,

**Prerequisite are,,,**

**1\. Update the Terminal or System.**

```typescript
$ sudo apt-get update
```

**2\. Installation of docker && docker-compose.**

```typescript
$ sudo apt-get install docker.io
$ sudo apt-get install docker-compose
```

**3\. Give correct permission to the docker daemon socket.**

```typescript
$ sudo chown $USER /var/run/docker.sock
```

**4\. Cloning from remote repository.**

```typescript
$ git clone https://github.com/rksdutt/two-tier-flask-app.git
```

**5\. Installation of Make.**

```typescript
$ sudo apt-get install make
```

Here are our prerequisite gone on terminal. From here we will write a make file and try to execute it and solve the errors we facing step by step.

**Step 1 :** First we'll create a file Makefile inside of out cloned directory.

```typescript
$ touch Makefile
or 
$ vim makefile
```

**Step 2 :** Second here we can find similarities what commands we ran on our terminal for docker build, up, down and also free our system from it after the task completion. Here we will put some **key : value** pairs format in variable and commands in this file like like as below. Here we can mention about only on which OS this compile commands can run.

```typescript
DOCKER_COMPOSE := docker-compose

OS:= $(shell uname)

build:
ifeq ($(OS), Linux)
        @echo "Running in $(OS)"
        $(DOCKER_COMPOSE) build
endif

up(start):
        $(DOCKER_COMPOSE) up -d

down(stop):
        $(DOCKER_COMPOSE) down

prune(wipeoff):
        docker system prune
```

**Step 3 :** After writing this compile commands in a file this we dont need to give it permission for execution like shell script. We just need to save the file and run this command. According to the compile commands what we want to run this if we want to build then we will run this, to run the docker compose command make up, to stop make down and to free the system after completion of our task docker prune.

```typescript
make build
make up
```

Step 4 : After completing this we need to check our application deployed or not. Let's see that by this command

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724431224172/479c18fe-dd10-4759-8832-0bad82494d6e.png align="center")

```typescript
docker ps
```

**Step 5 :** If both of the container frontend and database application running successfully then we need to open it and see on the web with mentiioned port number by exposing it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724431213307/c80b9bb0-5a9e-4c87-8264-64f1e7c40363.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724431237684/d0f6a2c2-44bf-41d6-9744-20987b800c4d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724431252752/1eae9dad-b876-48b9-881d-379072a46328.png align="center")

After all these step we have successfully deployed our two-tier flask-application with makefile compile commands on our local. After the two tier application deployed the local server we need to stop when it's not longer needed and free our system from running services with these command...

```typescript
make down 
make prune
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724431261573/533096f9-a820-430d-a5be-bd8771901d89.png align="center")

Here we tried and successfully deployed a two-tier flask-application with makefile command compilance and after that deployment we cut them off the both frontend and mysqldb and free our system space. Last one is how any one can write a makefile and learn more about makefile just click on this link [https://makefiletutorial.com/](https://makefiletutorial.com/).

Thanks and I leave my gratitude here for Shubham Londhe.