#### Security Group 1: For Elastic Load Balancer

- Name: lift&shift-ELB-SG
- Add rules: Ports 80 and 443 from anywhere

![Screenshot 2023-09-14 223905](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/0ce4fe49-6de4-4fca-a647-f28785641af4)

#### Security Group 2: For TOMCAT Instances

- Name: lift&shift-app-SG

Add rules: 
- Allow traffic on port 8080 from ELB Security Group
- Allow SSH port 22 from My IP
- Allow Port 8080 from My IP- This is just for troubleshooting just incase you want to access the App server without using ELB.

![Screenshot 2023-09-14 224159](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/ea1e2a23-d3e2-464a-bfb6-96b624e8fb78)

#### Security Group 3: For backend services (RabbitMQ, Memcache and, MySQL Instances)

- Name: lift&shift-backend-SG

Add rules:
- Allow MySQL port 3306 from App SG
- Allow Memcache port 11211 from App SG
- Allow rabbitMQ port 5672 from App SG
- Allow all traffic from backend SG so all the services can communicate with each other
- Allow SSH from My IP

![Screenshot 2023-09-14 225307](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/cbbc09d2-1dfb-4416-88dc-9b1e4aa7f802)

#### PLEASE DO NOT EDIT OUTBOUND RULES
