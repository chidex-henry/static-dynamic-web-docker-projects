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
