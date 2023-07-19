# Exercise: Autoscaling WebApp Servers
The development team in your organization has asked you to deploy a new collection of EC2 instances for a web application they're working on. You will need to create this resource in the development account, although they intend to use your CloudFormation template in several environments, with different group sizes for each one. You decide to use a Launch Template for your server parameters, as well as an AutoScaling group to keep the appropriate number of servers alive at all times.

The EC2 instances will be placed in an already existing VPC network, managed by a separate CloudFormation stack. This network template is available in the starter folder for this exercise.

# Exercise Prompt
Create a new stack for your web application resources with the following considerations:

- Create first the network stack using the template available in the starter folder for this exercise.
- Import the required networking values from the network stack using!ImportValue.
- The application will be running on port 3000. The EC2 instances must have their own security group attached, allowing access to port 3000 from 10.11.0.0/16.
- The EC2 instances must use the t2.micro instance type, a 10 GiB EBS disk, and any available Ubuntu AMI.
- The AutoScaling group should deploy the instances in the private subnets of the existing VPC.
- The AutoScaling group size goes between 1 and 6 instances depending on the environment.
- The desired capacity must be passed as a parameter. Make it default to 1.

# IMPORTANT

This exercise solution includes EC2 instances. Although t2.micro is included in the free tier plan, you might have associated hourly charges if you no longer have that plan available or keep EC2 instances running for a long time. Remember to delete your stack after completion.

