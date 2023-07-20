# Exercise: Load Balancing WebApp Servers
In the previous exercise, you've already created the launch template for your development team request. However, you know that for the staging and production environments, you will need up to 6 instances running at the same time. It's time to add a Load Balancer in front of your servers, to properly distribute traffic across them.

# Exercise Prompt
Using the same stack from the previous exercise, add all the required resources to load balance the website requests. Remember to deploy the starter network stack also, for network imports.

Your requirements are:

- You must use an Application Load Balancer, deployed to the VPC public subnets.
- This ALB must have its own security group created and attached, allowing access to port 80 from 0.0.0.0/0.
- Instances should only allow access on port 3000 from the load balancer's security group.
- The ALB listener must use port 80, as this will be the port used to access the load balancer.
- A single ALB listener rule should forward traffic to the instances target group, for any path.
- The target group must include a health check on port 3000. Choose the parameters you find suitable.

# IMPORTANT

This exercise solution includes EC2 instances. Although t2.micro instances are included in the free tier plan, you might have associated hourly charges if you no longer have that plan available or kept EC2 instances running for a long time. Remember to delete your stack after completion.

