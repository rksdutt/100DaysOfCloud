---
title: "Just playing with loops 𖦹.."
datePublished: Sun Aug 18 2024 22:41:28 GMT+0000 (Coordinated Universal Time)
cuid: cm005ivdk000009kxhcg9fy59
slug: just-playing-with-loops
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1724019550950/a7598d9d-c66e-4f74-bb95-2d1d0eacd831.png
tags: loops, shell-script, loopsinshellscript

---

A loop is a programming tool that repeats a set of instructions until a condition is true. They help avoid writing the same code multiple times. There are Three statements in loop on scripting. Used in programming to execute statements iterately during the period of a running program.

While : A while loop is used when the number of iterations is unknown. This loop runs as long as the condition is true the commands inside the loop are executed until the condition is no longer met.

Step 1 : We are going to create a file for while loops.

```typescript
$ touch demo-while.sh
or
$ vim demo-while.sh
```

Step 2 : Lets write the while loop script and we want to this while statement meet only odd number till 20.

```typescript
#!/bin/bash


num=0

while [[ $((num%2))==0 && $num -le 20  ]]
do
        echo $num
        num=$((num+3))
done
                       
```

Step 3 : Lets execute the file with this command

```typescript
$ ./demo-while.sh
or
bash demo-while.sh
```

Step 4 : Check the output of this file and see exact it matches the conditions..

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724075613770/989d08d0-d3fd-4d81-84bf-b8b4977e4ffa.png align="center")

For : A for loop is used when you know how many times you need to repeat something. We'll set a start and end point and the loop runs through a certain number of iterations.

Step 1 : Lets make a file to write the for loops script.

```typescript
$ vim demo-for-loops.sh
```

Step 2 : Here we gonna write the loop file and take arguments from user

```typescript
#!/bin/bash

# Here we going to mentioned and applying them in script


<< task
The For loops operates on the list of items it continiously iterates the 
commands until it matches the end
task 



for (( num=$2 ; num<=$3; num++ ))
do
        mkdir "$1$num"
done
```

Step 3 : After writting the script we need to save it and giving this file a partcular permission so who can do what to execute.

```typescript
$ chmod 770 demo-for-loops.sh
```

Step 4 : To execute this particlar file we need to run this command. Here is the part to take a arguments from users.

```typescript
$ bash demo-for-loops.sh Roll-Number 1 100
or 
$ ./ demo-for-loops.sh Roll-Number 1 100
```

Step 5 : Do ls to see the output whatever we did till now.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724066823419/0cfa77cc-8cce-430c-859a-07954079bdf5.png align="center")

Until : A loop is used when you want to loop until a condition is true. The loop continues to execute the commands inside it until the condition returns false. For example We can keep trying to start a service and check if it's running repeating until the service is running.

Step 1 : First of all create a file in the name of until.sh like this with this command.

```typescript
$ touch demo-until.sh
or 
$ vim demo-until.sh
```

Step 2 : Write a script for until loop it will run from 0 to till the given statement.

```typescript
#!/bin/bash

num=0

until [[ ! $num -lt 21  ]]

do
        echo $num

        num=$((num+1))

done
~              
```

Step 3 : Giving permission to the file so who can do what with the file depends on permission.

```typescript
$ chmod 770 demo-until.sh
```

Step 4 : Lets execute the file with this command.

```typescript
$ ./demo-until.sh
or 
bash demo-until.sh
```

Step 5 : Here let's see the output of the written file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724078849142/23395a55-581f-48bb-a9c2-c36f1d87c06c.png align="center")

Here we tried to demonstrate three types among the loops uses in shell script.