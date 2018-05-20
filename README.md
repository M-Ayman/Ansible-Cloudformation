#  Ansible-CloudFormation

![alt text](img/Ansible-CloudFormation.png "Add Architecture")

# CloudFormation template Create:

- A VPC from scratch with 1 Public and 1 private Subnet.

- Attach this VPC to InternetGateway.

- Create Public & Private Route Table for each subnet

- Create 2 security group "the first allow access on port 80 & 22 which used for a web server, the other allows only ssh on port 22"

- Launch an EC2 with apache2 in the public subnet and attach it to SG "allow 80 & 22"

-Launch an EC2 with MySQL in the private subnet.


# How to run it?
# you need to modify the values of vars under vpc/vars/ directory based on your region

 #AWS Credentials
 
aws_access_key: "AKIAIV22

aws_secret_key: "JN1bLQDd22N"

aws_region:     "us-west-2"

 #Cloudformation Parameters
StackName: "ansible-clouformation"

EnvironmentName: "dev"

ImageId: "ami-e251209a"

InstanceType: "t2.micro"

PrivateSubnet1CIDR: "10.192.20.0/24"

PublicSubnet1CIDR: "10.192.10.0/24"

VpcCIDR: "10.192.0.0/16"


# pip install boto boto3 botocore
# pip install ansible==2.4.2
# ansible-playbook vpc.yml 

