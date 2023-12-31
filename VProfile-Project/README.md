# VPROFILE PROJECT (MANUAL) OVERVIEW
This projects implements a Multi-Tier Web Application from your local machine. This is a precursor to other projects where we will be migrating the stack to AWS Cloud.

## Flow of Execution
- Setup prerequisites (check below)
- [Clone source code](https://github.com/hkhcoder/vprofile-project.git)(save localy on your computer)
- `cd` into the vagrant dir
- Bring up the VM's `vagrant up`
- Validate
- Setup All the services

### Services
- 1. Nginx: Is going to be used for Web Service
- 2. Tomcat: Will be used for Application Server
- 3. RabbitMQ: Will be the Broker/Queuing Agent
- 4. Memcache: DB Caching
- 5. ElasticSearch: Indexing/Search service
- 6. MySQL: SQL Database


## Architecture Diagram

![Vprofile projectsetup Manual](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/03c4824b-6d97-42ba-a6bd-dc41a6d8b706)

## Prerequisite

- [Install Oracle VM Virtualbox](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwj2_qL-k5-BAxULl2oFHWgeD-AQFnoECBIQAQ&url=https%3A%2F%2Fwww.virtualbox.org%2Fwiki%2FDownloads&usg=AOvVaw2aIAdQV7iMGmQmEtwhZCT0&opi=89978449)
- [Install Vagrant](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwi5z8-UlJ-BAxWslWoFHXuIC4UQFnoECBgQAQ&url=https%3A%2F%2Fdeveloper.hashicorp.com%2Fvagrant%2Fdocs%2Finstallation&usg=AOvVaw22zitKutSvAXkC3V3RmGOJ&opi=89978449) (Install vagrant plugin - vagrant-hostmanager)
- Git bash or equivalent editor

## Set Up (Should be completed in the below order)

### Step 1 - [MYSQL Setup](https://github.com/Sulemoore/DevOps-Projects/blob/main/VProfile-Project/MYSQL%20Setup/Setup.md)
### Step 2 - [MEMCACHE Setup](https://github.com/Sulemoore/DevOps-Projects/blob/main/VProfile-Project/MEMCACHE-Setup/Setup.md)
### Step 3 - [RABBITMQ Setup](https://github.com/Sulemoore/DevOps-Projects/blob/main/VProfile-Project/RABBITMQ-Setup/Setup.md)
### Step 4 - [TOMCAT Setup](https://github.com/Sulemoore/DevOps-Projects/blob/main/VProfile-Project/TOMCAT-Setup/Setup.md)
### Step 5 - [CODE BUILD & DEPLOY](https://github.com/Sulemoore/DevOps-Projects/blob/main/VProfile-Project/CODE-BUILD-and-DEPLOY/Setup.md) (app01)
### Step 6 - [NGINX Setup](https://github.com/Sulemoore/DevOps-Projects/blob/main/VProfile-Project/NGINX-Setup/Setup.md)

## [Verify Website](https://github.com/Sulemoore/DevOps-Projects/blob/main/VProfile-Project/Verify-Website.md)

### CLEAN UP
- To clean up run `vagrant destroy` to destroy all the servers.
- If you want to come back and continue the next project, you can run `vagrant halt` to halt all servers .
