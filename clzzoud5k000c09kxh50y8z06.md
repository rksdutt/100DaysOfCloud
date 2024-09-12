---
title: "It's the time to write first Shell Script  📋 ."
datePublished: Sun Aug 18 2024 14:54:31 GMT+0000 (Coordinated Universal Time)
cuid: clzzoud5k000c09kxh50y8z06
slug: its-the-time-to-write-first-shell-script
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1724018539602/ef01a23c-927a-4e91-be04-166ddf31c483.webp
tags: shell, shell-scripting, shellscripting-devops

---

How about let's write the First Script in Bash .

Step 1 : Prerequisites are we need a debian model ubuntu linux lts : latest version

As soon as we log into it we can write a script for our hands-on.

Make a separated dir for these scripts

And last one to create a shell file with this command

```typescript
$ touch hello.sh 
or 
$ vim hello.sh
```

Step 2 Let's write the script,,,

```typescript
#!/bin/bash
<< Comment 
First Script 
Comment

echo "Me : Hello World !! What do you want to be when you grow up !!"

echo "Folks : A Shell Writer <)) A Globe known Key-Word"

echo "Me : Work On it now Or Regret for it Later"
```

step 3 : Yup We will write it like this. And save it with :wq ↩

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723990844740/fadf54fe-3c5f-4cd0-9e4c-f34707aa3a14.png align="center")

Step : 4 After we back on the terminal again here are the multiple way to print but there is a hook.

```typescript
$ cat hello.sh
```

Through this we can easily only print out the script like this.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723991992911/6b87e779-6a18-4e05-8c98-f57149046bcd.png align="center")

Steps : 5 To execute this script or make executable we need to give permissions about who mean users, groups, others can access what by this command.

```typescript
$ chmod 755 hello.sh
```

```typescript
$ bash hello.sh
or 
$ ./hello.sh
```

Steps 6 : Shell Here we how execute a shell file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723992052110/1b9cd8e2-6ca0-439f-b86f-11e56ebd3a44.png align="center")

This is way through which we can write a Script and then execute them .