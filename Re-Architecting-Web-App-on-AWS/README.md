# Re-Architecting (Refactoring) Web App on AWS

In this project we will rearchitect our on premises stack on AWS. This approach is used to boost agility or to improve business continuity. So we can add new features, scale effectively and easily have very good performance for our application workload.

Refactoring/Re-architecting is simply re-imagining how the application is architected and developed by typically using cloud-native features. It could also mean migrating from a monolithic architecture to a service-oriented or fully managed architecture to boost agility and/or improvee business continuity.

For this project we will be using PAAS (platform as a service) and SAAS (software as a service) services, by taking advantage of cloud fully managed services on AWS.

### Architecture Diagram

- #### On-Premise Architecture
  
![Vprofile projectsetup Manual](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/f3fb4a5e-eb31-41a1-af94-6bd5eddef18f)


- #### Refactored Architecture
![Refactoring drawio](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/0cfeb2b7-f933-4a80-9204-1a650e0fc15e)



### AWS Services

- Elastic Beanstalk
- RDS
- Amazon ActiveMQ
- Route53
- Cloudfront
- S3
- Amazon Elasticache
- EC2
  

### Flow of Execution

- Login to AWS Account
- Create Key-pair for Beanstalk Instance login
- Create Security Group for Elasticache, RDS and ActiveMQ
- Create RDS
- Create Amazon Elasticache
- Create ActiveMQ
- Create Elastic Beanstalk Environment
- Update SG of backend to allow traffic from Beanstalk SG
- Update SG of backend to allow internal traffic
- Launch EC2 Instances for DB
- Login to the Instance and Initialize RDS DB
- Change healthcheck on Beanstalk to /login
- Add port 443-HTTPS listener to ELB
- Build Artifact
- Create CDN with ssl certificate
- Test URL



