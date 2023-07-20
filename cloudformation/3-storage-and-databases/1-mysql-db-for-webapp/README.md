# Exercise: MySQL Database for MyWebAPP

You are tasked with creating a MySQL database for the MyWebApp application. The database must be RDS managed, and all resources are handled with CloudFormation. Important information will be stored in this database, so it must be protected against accidental deletion or data loss. Also, the development team has given you specific properties to set for the engine.

# Exercise Prompt

Create a CloudFormation template with the required RDS resources, considering:

- Create the network stack using the starter template provided for this exercise.
- The network stack exports VPC and subnet parameters. Import them in your solution template.
- The database engine must be MySQL 8.0.32 or newer.
- Use a db.t3.micro instance class.
- Allocate 20 GiB to the instance.
- Protect your database against accidental data loss.
- Place your database in the private subnets.
- Pass your master username and password as parameters. The values must be specified only in a JSON parameters file.
- The database security group should allow access on port 3306 for the CIDR block 10.10.0.0/24
- The engine must be configured with the following parameters:

    innodb_buffer_pool_instances: 1
    innodb_buffer_pool_size: 134217728
    max_connections: 1000
    IMPORTANT

This exercise solution includes RDS instances. Although db.t3.micro instances are included in the free tier plan, if you no longer have that plan available or kept RDS instances running for a long time, you might have associated hourly charges. Remember to delete your stack after completion.