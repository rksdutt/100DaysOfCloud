---
title: "Launching an Ec2 Instance through AWS CLI with Advanced Shell Script with handling errors. </> 🚀 🟧"
datePublished: Thu Aug 22 2024 21:09:15 GMT+0000 (Coordinated Universal Time)
cuid: cm05rzoii000108l7bgj8bgms
slug: launching-an-ec2-instance-through-aws-cli-with-advanced-shell-script-with-handling-errors
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1724359599620/6631846e-f9da-4e3d-872b-ba16068d2b5f.jpeg
tags: awscli-ec2, createec2instanceawscli

---

To launch an EC2 instance using the AWS CLI with more advanced shell scripts. We can include various features such as error handling, parameter validation also dynamic input. We'll go through step-by-step examples of a shell script that demonstrates these aspects .

**Step 1 :** We will create a file on out terminal for run this script to launch an ec2 instance on our AWS console

```typescript
$ touch ec2byawscli.sh
or 
$ vim ec2byawscli.sh
```

This command tell us about the pipefail option and **ensures that the script fails if any command in a pipeline fails,** even if other commands in the pipeline succeed. It prevents silent errors from slipping through the cracks, keeping your code robust.

```typescript
set -euo pipefail
```

**Step 2 :** First step we are taking on this matter that we have to make sure that we have awscli installed on our machine. If there is no awscli on our machine or we have older version of awscli here then we have remove and we have to run a fallback script on terminal which is going to check that

```typescript
check_awscli || install_awscli
check_awscli() {                                                                
if ! command -v aws &> /dev/null; then
  echo "AWS CLI is not installed. Please install it first." >&2     
  exit 1                                                                  
fi                                                                      
}
```

then go forward to install it asap followed by this document here 🔻[https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) .

```typescript
$ sudo apt remove awscli
or 
$ rm -rf awscliv2.zip ./aws
```

**Step 3 :** After successfully uninstall or remove the older version or not properly installed awscli we have to go through this like below commands.

```typescript
$ curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
$ sudo apt-get install -y unzip &> /dev/null
$ sudo unzip -q awscliv2.zip
$ sudo ./aws/install
```

**Step 4 :** After we installed awscli successfully on our machine we have to check for it does it successfully installed or not. For this we have to run this below command on our terminal.

```typescript
$ aws --version
```

**Step 5 :** After completing those above mentioned 3 stepes we have to go forward to and give a reality check on our goal. We are going to get this concept and visualize that how to create an ec2 instance or check instance\_id on our aws console through this script, so for that how we are going to write this script here according to this catalog.

```typescript
create_ec2_instance() {
    local ami_id="$1"
    local instance_type="$2"
    local key_name="$3"
    local subnet_id="$4"
    local security_group_ids="$5"
    local instance_name="$6"

    # Run AWS CLI command to create EC2 instance
    instance_id=$(aws ec2 run-instances \
        --image-id "$ami_id" \
        --instance-type "$instance_type" \
        --key-name "$key_name" \
        --subnet-id "$subnet_id" \
        --security-group-ids "$security_group_ids" \
        --tag-specifications "ResourceType=instance,Tags=[{Key=Name,Value=$instance_name}]" \
        --query 'Instances[0].InstanceId' \
        --output text
    )
```

**Step 6 : If** after run this script there is no instance created or launched so then there will be no question about generating instance id or if instance created or launched successfully then wait for the running state of the particular instance, if it not get into the running state then put it on waiting state till it running we will discuss about this script later. Here we are having a script to run here below..

```typescript
if [[ -z "$instance_id" ]]; then
        echo "Failed to create EC2 instance." >&2
        exit 1
    fi

    echo "Instance $instance_id created successfully."

    # Wait for the instance to be in running state
    wait_for_instance "$instance_id"
```

**Step 7 :** Here we are going to see if the instance is created successfully by the script or launched and then put in a waiting state until it comes to the running state. So here we will see how the wait example works through this script. If the the instance state is not running then run the command after 10 second interval. Take a break from the loop when the instance state goes to running after executing the command of the interval.

```typescript
wait_for_instance() {
    local instance_id="$1"                                                      
echo "Waiting for instance $instance_id to be in running state..."                                                                                      
while true; do                                                                  
    state=$(aws ec2 describe-instances --instance-ids "$instance_id" --query 'Reservations[0].Instances[0].State.Name' --output text)
        if [[ "$state" == "running" ]]; then
            echo "Instance $instance_id is now running."
            break
        fi
        sleep 10
    done
}
```

**Step 8 :** After all these steps covering we need to write our full script which are accumulated of mentioned steps above and see the further what its going to asks and give that according to that. We will take help from this aws documentation [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-ec2-instance-connect-endpoints.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-ec2-instance-connect-endpoints.html) to write the script from this refference format or this one [https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-instance.html](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-instance.html) .

```typescript
#!/bin/bash                                                                 
set -euo pipefail     
sudo apt remove awscli                                                                                                                                 
 check_awscli() {                                                                
if ! command -v aws &> /dev/null; then                                          
  echo "AWS CLI is not installed. Please install it first." >&2              
  exit 1                                                                  
fi                                                                      
}                                                                                                                                                      
 install_awscli() {                                                             
 echo "Installing AWS CLI v2 on Linux..."                                                                                                              
  # Download and install AWS CLI v2                                           
curl -s "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
    sudo apt-get install -y unzip &> /dev/null
    unzip -q awscliv2.zip
    sudo ./aws/install

    # Verify installation
    aws --version

    # Clean up
    rm -rf awscliv2.zip ./aws
}

wait_for_instance() {
    local instance_id="$1"                                                      
echo "Waiting for instance $instance_id to be in running state..."                                                                                      
while true; do                                                                  
    state=$(aws ec2 describe-instances --instance-ids "$instance_id" --query 'Reservations[0].Instances[0].State.Name' --output text)
if [[ "$state" == "running" ]]; then
            echo "Instance $instance_id is now running."
            break
        fi
        sleep 10
    done
}
create_ec2_instance() {
    local ami_id="$1"
    local instance_type="$2"
    local key_name="$3"
    local subnet_id="$4"
    local security_group_ids="$5"
    local instance_name="$6"

    # Run AWS CLI command to create EC2 instance
    instance_id=$(aws ec2 run-instances \
        --image-id "$ami_id" \
        --instance-type "$instance_type" \
        --key-name "$key_name" \
        --subnet-id "$subnet_id" \
        --security-group-ids "$security_group_ids" \
        --tag-specifications "ResourceType=instance,Tags=[{Key=Name,Value=$instance_name}]" \
        --query 'Instances[0].InstanceId' \
        --output text
    )
```

**Step 9 :** We will give permission to that ec2byawscli.sh for executing it. And solving the errors came after the script run. With this command we can give permission to it.

```typescript
$ chmod 770 ec2byawscli.sh
```

**Step 10 :** After giving the permission to the file now its time to execute the file. So we can execute the file with this commands.

```typescript
#bashfollowedbythescriptname
$ bash ec2byawscli.sh
or 
/. ec2byawscli.sh
```

**Step 11 :** Hence we can see our instance got created or launched and running successfully on the place or region we mentioned on the script. We launched two different instances in a different name.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724360336923/275b3492-959d-4580-84ef-566ef2e73488.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1724360342448/84f7fe36-3f78-4036-91e5-d06bf0aa316d.png align="center")