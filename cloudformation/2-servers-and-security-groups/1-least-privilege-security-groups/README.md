# Exercise: Least Privilege Security Groups
A client of yours has asked you to review their security group configuration for one of their projects. He's concerned about the firewall rules not following best practices, in particular the least privilege principle. He has sent you this CloudFormation template snippet:

`Resources:
  VPC: 
    Type: AWS::EC2::VPC
    Properties:
      CidrBlock: 10.4.0.0/16
      EnableDnsHostnames: true
      Tags: 
      - Key: Name 
        Value: udacity-security-groups
  BastionsSecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      VpcId: !Ref VPC
      GroupDescription: Security group for Bastion servers
      SecurityGroupIngress:
      - IpProtocol: tcp
        FromPort: 22
        ToPort: 22
        CidrIp: 0.0.0.0/0
  ApplicationASecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      VpcId: !Ref VPC
      GroupDescription: Security group for Application A servers
      SecurityGroupIngress:
      - IpProtocol: tcp
        FromPort: 80
        ToPort: 80
        CidrIp: 0.0.0.0/0
  ApplicationBSecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      VpcId: !Ref VPC
      GroupDescription: Security group for Application B servers
      SecurityGroupIngress:
      - IpProtocol: tcp
        FromPort: 80
        ToPort: 80
        CidrIp: 0.0.0.0/0`

There are three groups of servers: bastions or SSH jump boxes, servers hosting Application A, and servers hosting Application B. Each security group is attached to the servers based on its name.

Can you help him adjust his design so it follows security best practices?

# Exercise Prompt
Adjust the provided CloudFormation template so its security groups provide only the following network permissions:

- The operations team must be able to access the bastion servers using SSH (port 22) from their internal servers only. Their IP range is 10.156.30.0/24.
- The operations team must be able access ApplicationA and ApplicationB servers using an SSH tunnel through the bastion server (port 22).
- ApplicationA must be open to the Internet on port 80.
- ApplicationB must only be open to the developers team, working from inside the IT office. The office IP range is 10.156.36.0/24.