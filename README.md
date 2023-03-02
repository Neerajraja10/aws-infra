# aws-infra

Prerequisites
Before starting this project, you will need to have the following installed:

Visual Studio Code or any other IDE
POSTMAN
MySQL or any other database management system
Node.js
AWS account

Terraform

Steps
Create a Node.js and MYSQL2 Webapp with RESTful APIs to perform CRUD operations on users and products.
Create a .sh file with the necessary dependencies, including Node.js and Mariadb. The commands in the .sh file should include unzipping the Webapp.zip file, installing nginx, and enabling and starting webapp and nginx services.
Configure your MySQL database and connect it to your Webapp.
Test your Webapp locally to make sure it is functioning correctly.
Create a Packer file to build the new AMI, including the source AMI to build from, a provisioner section to run the shell script file created in step 2, and a builders section to create the new AMI.
Run the Packer build command to create the new AMI.
Use Terraform to create a new EC2 instance from the AMI created in step 6.
Obtain the public IP address of the EC2 instance and test the APIs using POSTMAN.
After testing, create a pull request with a detailed description of changes.
Store the Image details in the RDS and meta data in S3 for future use.
API Endpoints
The Webapp includes the following endpoints for performing operations on users and products:

GET
POST
PUT
PATCH
DELETE
HTTP messages that can be received include:

"200 OK"
"201 Created"
"204 No Content"
"400 Bad Request"
"401 Unauthenticated"
"403 Forbidden"
"500 Internal Server Error"

Conclusion
By following these steps, you can create an AMI for a Node.js and MYSQL2 Webapp and use it to run API tests with POSTMAN. With Terraform, you can easily create an EC2 instance from the AMI, and store the Image details in RDS and meta data in S3 for future use.

USAGE

$ terraform init
$ terraform plan
$ terraform apply
$ terraform destroy

REQUIREMENTS    

terraform      >= 0.12.26
aws            >= 3.15

PROVIDERS

aws            >= 3.15


MODULES

vpc_cidr_block
vpc_instance_tenancy
vpc_name
vpc_internet_gateway_name
vpc_public_subnet_name
vpc_public_rt_name


RESOURCES 

aws_vpc
aws_internet_gateway
aws_subnet
aws_route_table
aws_route_table_association


AWS Custom VPC Creation steps 

1. Select the region: Choose the geographical location where the VPC will be hosted.

2. Create VPC: Create a virtual network environment that closely resembles a traditional network infrastructure, complete with subnets and routing tables.

3. Enable the DNS HOST name in the VPC: Enable DNS resolution for instances in the VPC so that they can be accessed using a fully qualified domain name (FQDN).

4. Create Internet Gateway: Create an internet gateway to provide internet connectivity to the VPC.

5. Attach Internet gateway to the VPC: Attach the internet gateway to the VPC so that instances in the VPC can access the internet.

6. Create Public Subnets: Create subnets in the VPC that are publicly accessible and have a route to the internet.

7. Enable Auto Assign Public IP settings: Enable the automatic assignment of public IP addresses to instances launched in the public subnets.

8. Create Public route table: Create a routing table for the public subnets.

9. Add public route to the public route table: Add a route to the internet gateway in the public route table.

10. Associate the Public subnets with the Public Route table: Associate the public subnets with the public route table so that they can route traffic to the internet.

11. Create the Private subnets: Create subnets in the VPC that are not publicly accessible and do not have a route to the internet.

12. Create Private Route table: Create a routing table for the private subnets.

13. Add public route to the Private route table: Add a route to the internet gateway in the private route table.

14. Associate the Private Subnets with the Private Route table: Associate the private subnets with the private route table so that they can route traffic to the internet via the internet gateway.



For query reach out to raja.n@northeastern.edu

