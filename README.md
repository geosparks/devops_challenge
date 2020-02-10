# Devops Challenge - AWS Automation

Automate the following tasks with your own choice of scripting language (Ansible preferred).

### Task 1

Automate the EC2 instance creation under load balancer.

1. Create a VPC with should have a public and private subnet
2. Create a role with s3 access.
3. Launch an ec2 instance with the role created in step 1, inside the private subnet of VPC, and install apache through bootstrapping. ( You need to have your NAT gateway attached to your private subnet )
4. Create a load balancer in public subnet.
5. Add the ec2 instance, under the load balancer

### Task 2

Automate the process of stop ( For cost saving )

Automate the process of stop to a group of EC2 instances (based on tags). Ensure that there is no user
logged into the servers, and CPU usage is idle ( less than 10% ) for the particular period of time before stopping. The idle period and tag will be passed as arguments.
**usage:** autostop <Tag name> < idle period>

For example:

```
 autostop <development> 30
```

If the current time is 7 PM, the script needs to check the idle development instances in the last 30
minutes ( 6.30 PM to 7 PM ) and make sure no users are logged into those instances before stopping them. Don’t set up permanent cloudwatch alarm to stop the instances. The script needs to run on-demand for stopping the instances.

### **Bonus Task**

Once you have the basic functionality implemented, try to do the following bonus exercises in Task 1:

1. Create an auto scaling group with minimum size of 1 and maximum size of 3 with load balancer
   created in step 3 of Task 1 .

1. Add the created instance under the auto scaling group. ( You need to have an AMI created out of previously created instance in Task 1 which has apache installed in it)

1. Write a life cycle policy with the following parameters:

   scale in : CPU utilization > 80%

   scale out : CPU Utilization < 60%


 
