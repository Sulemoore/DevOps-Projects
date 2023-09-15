# Lift & Shift - Migrating a 3-Tier Web App to AWS

In this project we are going to lift and shift a web application hosted locally on our machine (this could be on premise of data center) to AWS.  Instead of running our workload in our data center, we run it on a cloud computing platform that we don't pay for the upfront cost for procuring the resource. We pay as we go based on consumption of infrastructure as a service. We get flexibility, elasticity, scalability,and cost control.

### Architecture Diagram

- #### Local or On-Prem Stack
  
![Vprofile projectsetup Manual](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/a1fd71ad-2681-445e-97c0-1192abae932d)

- #### AWS Stack
  
![diagram drawio](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/e6f17381-a94d-4706-9651-4d7acec2c10f)

- #### Lift & Shift Architecture

![lift and shift](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/2ed0e316-596e-4bdc-85c2-a05386cf635a)


### AWS Services

- EC2 Instances: We will use ec2 instances as our VMs for TOMCAT, RABBITMQ, MEMCACHE, and MYSQL.
- ELB (Load balancer): ELB will replace the NGINX Load balancer
- ASG: For automatic VM scaling based on workload
- S3/EFS Storage: As a shared storage
- Route 53: Will be used for private DNS service
- IAM: For access management
- ACM: For managing certificates

### Flow of Execution
- Login to AWS Account
- [Create Key Pairs](https://github.com/Sulemoore/DevOps-Projects/blob/main/Migrating-Three-Tier-App-to-AWS-Lift-%26-Shift/Create-Key-Pairs/Key-pair-setup.md)
- [Create Security groups](https://github.com/Sulemoore/DevOps-Projects/blob/main/Migrating-Three-Tier-App-to-AWS-Lift-%26-Shift/Create-Security-Groups/security-group.md)
- [Launch Instances with user data](https://github.com/Sulemoore/DevOps-Projects/tree/main/Migrating-Three-Tier-App-to-AWS-Lift-%26-Shift/Create-EC2-Instances)
- Update IP to name mapping in route 53
- Build application from source code
- Upload artifact to S3
- Download Artifact to Tomcat EC2 Instance
- Setup ELB with HTTPS
- Map EKB Endpoint to website
- Build Autoscaling Group for Tomcate instances
