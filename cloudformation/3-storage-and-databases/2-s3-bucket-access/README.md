# Exercise: Granting Access to S3 buckets
You now understand how to add S3 buckets to your CloudFormation. But do you remember how to grant access to those buckets from your EC2 instances?

In this exercise, you will adjust the provided CloudFormation template to grant access to an S3 bucket from a group of EC2 servers. Of course, you will need to create the bucket itself.

# Exercise Prompt
A starter CloudFormation template is provided in the GitHub repository folder. Make the following adjustments:

- Add an S3 bucket to the template. Name it as you like.
- Make sure that all content in the bucket is and remains private.
- Enable Versioning for the bucket.
- Enable S3 AES256 encryption for the bucket.
- Create the required IAM resources for granting s3:GetObject and s3:PutObject permissions to the S3 bucket (IAM InstanceProfile and IAM Role).
- Modify the Launch Template so the instances can assume the created role.
- Remember to use the proper CloudFormation capabilities when creating the IAM resources using the CLI.

# IMPORTANT

This exercise solution includes EC2 instances. Although t2.micro is included in the free tier plan, you might have associated hourly charges if you no longer have that plan available or keep EC2 instances running for a long time. Remember to delete your stack after completion.