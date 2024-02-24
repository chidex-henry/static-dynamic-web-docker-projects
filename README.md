# AWS Dockerized Website Deployment Projects

## Static Website on AWS with Docker, Amazon ECR, and ECS

### Project Overview

This project focused on deploying a static website using Docker, Amazon ECR, and ECS on AWS. The containerization platform Docker is utilized for building, shipping, and running applications, providing benefits such as portability, consistency, scalability, and security.

### Deployment Process

1. **GitHub Repository Setup:**
   - Created a GitHub repository to store the Dockerfile.
   - Cloned the repository to the local machine.
   - Pushed changes from the local repository to the remote repository.
  
   ![image](https://github.com/chidex-henry/docker-projects/assets/77998377/957b2007-f89b-419e-9ec1-96cb4a78b1df)

2. **Docker Image Creation and Deployment:**
   - Created a Dockerfile for the static website.
   - Built the Docker container image.
   - Started the Docker container locally for testing.

3. **Docker Hub Repository:**
   - Created a repository on Docker Hub.
   - Pushed the Docker image to the Docker Hub repository.

4. **IAM User Creation:**
   - Created an IAM user with programmatic access (access and secret access keys).
   - Attached the AdministratorAccess permission policy for the IAM user.

  ![image](https://github.com/chidex-henry/docker-projects/assets/77998377/02d4d0fb-0c3a-46e5-acd3-076e087bf47e)

5. **Amazon ECR Repository:**
   - Created an Amazon ECR repository to store the Docker image.
   - Pushed the Docker image to the ECR repository.
  
  ![image](https://github.com/chidex-henry/docker-projects/assets/77998377/13b9bd7f-eadc-4274-a88e-4c53e36f4604)

### AWS Core Services Setup

Configure AWS core services to support the deployment of the website.

  ![image](https://github.com/chidex-henry/docker-projects/assets/77998377/24c4c455-4dce-422a-a63d-3cf22df5d264)

1. **Virtual Private Cloud (VPC):**
   - Configured a VPC with public and private subnets across two availability zones.
   - Deployed an Internet Gateway for connectivity to the wider internet.

2. **Security Groups:**
   - Established security groups as a network firewall mechanism.

3. **Availability Zones:**
   - Leveraged two availability zones for enhanced reliability and fault tolerance.

4. **Public Subnets:**
   - Used public subnets for infrastructure components like NAT Gateway and Application Load Balancer.

5. **ECS Task Execution Role:**
   - Configured a task execution role in ECS for container environment setup, image pulling from ECR, and log management.

6. **ECS Setup:**
   - Implemented an ECS Cluster, Task Definition, and Service for application deployment and scaling.

7. **Application Load Balancer (ALB):**
   - Employed an ALB and a target group to distribute web traffic to an Auto Scaling Group.

8. **Auto Scaling Group:**
   - Utilize an Auto Scaling Group for managing EC2 instances, ensuring availability, scalability, fault tolerance, and elasticity.

9. **Version Control and Collaboration:**
   - Stored web files on GitHub for version control and collaboration.

10. **Security Measures:**
    - Secured application communication using AWS Certificate Manager.

11. **Notification Setup:**
    - Configured Simple Notification Service (SNS) to receive alerts about Auto Scaling Group activities.

12. **Domain Registration and DNS Setup:**
    - Registered the domain name.
    - Set up DNS records using Route 53.

### Conclusion

This project demonstrated the end-to-end process of deploying a static website using Docker, Amazon ECR, and ECS on AWS. The combination of containerization and AWS services provides a scalable, secure, and reliable environment for hosting web applications.

 ![image](https://github.com/chidex-henry/docker-projects/assets/77998377/0de28b44-bdfe-4f68-bc68-9bec9b0b65f1)







## Dynamic Website on AWS with Docker, Amazon ECR, and ECS

### Overview
This project sets up a dynamic website infrastructure on Amazon Web Services (AWS) using Docker containers, Amazon Elastic Container Registry (ECR), and Amazon Elastic Container Service (ECS). The infrastructure is designed for high availability, fault tolerance, and scalability.

### AWS Core Services Setup

1. **Virtual Private Cloud (VPC):**
   - Configured a VPC with public and private subnets across two availability zones for enhanced reliability and fault tolerance.

2. **Internet Gateway (IGW):**
   - Deployed an IGW to facilitate connectivity between VPC instances and the wider Internet.

3. **Security Groups:**
   - Established Security Groups as a network firewall mechanism to control traffic to the instances.

4. **Availability Zones (AZs):**
   - Leveraged two AZs to enhance system reliability and fault tolerance.

5. **Public Subnets:**
   - Utilized Public Subnets for infrastructure components like the NAT Gateway and Application Load Balancer.

6. **ECS Task Execution Role:**
   - Configured a task execution role in ECS to set up the environment for a container, pull images from Amazon ECR, and manage logging with CloudWatch.

7. **ECS Cluster, Task Definition, and Service:**
   - Implemented an ECS Cluster, Task Definition, and Service to deploy, manage, and scale the application in containers.

8. **Application Load Balancer (ALB):**
   - Employed an ALB and a target group for evenly distributing web traffic to an Auto Scaling Group of EC2 instances across multiple AZs.

9. **Auto Scaling Group (ASG):**
   - Utilized an ASG to automatically manage EC2 instances, ensuring website availability, scalability, fault tolerance, and elasticity.

10. **GitHub for Version Control:**
    - Stored web files on GitHub for version control and collaboration.

11. **Certificate Manager:**
    - Secured application communication using a Certificate Manager.

12. **Simple Notification Service (SNS):**
    - Configured SNS to alert about activities within the Auto Scaling Group.

13. **Route 53:**
    - Registered the domain name and set up a DNS record using Route 53.

### Docker Implementation Setup

1. **GitHub Repository:**
   - Created a GitHub repository to store the application codes and Dockerfile, cloned to the local environment, and pushed changes to the remote repository.
  
   ![image](https://github.com/chidex-henry/docker-projects/assets/77998377/e57328af-a140-422a-a29c-61c83f5177d9)

2. **Dockerfile:**
   - Created a Dockerfile to build the Docker Image.
  
    ![image](https://github.com/chidex-henry/docker-projects/assets/77998377/9b270382-3d17-4eab-bf31-724b14324bcf)

3. **Built and Pushed Docker Image to ECR:**
   - Built and pushed the Docker image from an AWS EC2 Instance to AWS ECR using the following steps:

    - **Pre-requisites:**
            Created a personal token; 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 

    - **Created a new repository and added a `Dockerfile` and ‘AppServiceProvider.php file’. Cloned the Repository**
            git clone https://<personal access token>@github.com/<github-user-name>/<repository-name>.git

    -  **AWS configuration:**
	      Created an IAM Role: Use the “AmazonEC2ContainerRegistryFullAccess” policy
	      Launched an Amazon EC2 instance in the private subnet and an EC2 instance connect endpoint.
              This EC2 Instance connect endpoint was used to SSH into theAmazon EC2 instance in the private subnet
	      SSH into the EC2 instance:  aws ec2-instance-connect ssh --instance-id i-0739dee0c2d494619

	 - **Installation of Docker on EC2: Installed Docker on the EC2 instance** 
   	      sudo amazon-linux-extras install docker
   	      sudo service docker start
   	      sudo usermod -a -G docker ec2-user

	 -  **Installed Git:**
	         sudo yum install git -y

	 -  **Cloned the repository on the EC2 Instance:**
	         git clone https://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@github.com/chidex-henry/docker-projects.git

         -  **Built the Docker Image**
  
       ![image](https://github.com/chidex-henry/docker-projects/assets/77998377/00e8d2b9-d291-4be1-80d7-4da4f451f279)
   

         -  **Created an AWS ECR repository:** 
	         aws ecr create-repository --repository-name <repository-name> --region <region>

	 -   **Tagged and Pushed Docker image to ECR:**
	         docker tag <image-tag> <repository-uri>
    		 aws ecr get-login-password | docker login --username AWS --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com
           	 docker push <repository-uri>

4. **Database Migration with Flyway:**
   - Migrated SQL script into RDS database with Flyway. Installed and extracted Flyway on the EC2 Instance, downloaded the SQL script from S3, and migrated the SQL into RDS.

### Flyway Migration Script
```bash
#!/bin/bash

S3_URI=s3://chidex-data-migration-sql/V1__rentzone-db.sql
RDS_ENDPOINT=dev-rds-db.cu2idoemakwo.us-east-1.rds.amazonaws.com
RDS_DB_NAME=applicationdb
RDS_DB_USERNAME=chidexhenry
RDS_DB_PASSWORD=Chidexhenrytee

# Update all packages
sudo yum update -y

# Download and extract Flyway
sudo wget -qO- https://repo1.maven.org/maven2/org/flywaydb/flyway-commandline/9.20.0/flyway-commandline-9.20.0-linux-x64.tar.gz | tar -xvz

# Create a symbolic link to make Flyway accessible globally
sudo ln -s $(pwd)/flyway-9.20.0/flyway /usr/local/bin

# Create the SQL directory for migrations
sudo mkdir sql

# Download the migration SQL script from AWS S3
sudo aws s3 cp "$S3_URI" sql/

# Run Flyway migration
sudo flyway -url=jdbc:mysql://"$RDS_ENDPOINT":3306/"$RDS_DB_NAME" \
  -user="$RDS_DB_USERNAME" \
  -password="$RDS_DB_PASSWORD" \
  -locations=filesystem:sql \
  migrate
```

### Conclusion
This project demonstrates the setup of a dynamic website infrastructure on AWS using Docker containers, Amazon ECR, and ECS. It ensures reliability, scalability, and security while leveraging various AWS services for seamless deployment and management. 

<img width="1268" alt="Screen Shot 2023-11-04 at 3 34 21 AM" src="https://github.com/chidex-henry/docker-projects/assets/77998377/960addf1-82db-4c6f-a601-c98f8c3e1c21">

