# Automatic Provisioning of the Multi-Tier Web Application

- This is a continuation of the VProfile Project where we manually deployed the web application on our local machine.
- This time, using Bash scripts we are able to automatically provision the servers making it more scalable and repeatable.

## Architectural Diagram
![vprofile projectsetup Automate](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/a5ba69d9-c925-44cc-8fb6-b15d88044c7c)


### Prerequisite
- [VProfile Project](https://github.com/Sulemoore/DevOps-Projects/tree/main/VProfile-Project)
- From the already cloned repository in the last project, open the scripts.
  
### Steps

- Open your terminal and get into the source code, vagrant directory/automated provisioning.
- Run `vagrant up` to automatically provision the servers (this may take up to 30 min)

### Web Verification
  - Once the servers have been configured, get the IP address of the web page and paste in the browser.
  - You can also use the host name `web01`.

#### Web page

![Screenshot 2023-09-11 230812](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/ce401eb8-4bd1-4ef3-93d0-ec3471363d90)


![Screenshot 2023-09-11 230927](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/2c4c38b3-4185-48bd-904a-78e8d3e84218)

#### RabbitMQ 
![Screenshot 2023-09-11 230955](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/fc18b343-bc33-4156-a70f-063917085f69)

#### Memcache 
![Screenshot 2023-09-11 231024](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/2771cb87-b84b-46cf-8b53-42a9bd61568f)

![Screenshot 2023-09-11 231043](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/cc64d506-cc3e-42f5-b078-d88dd8ae47c7)

## CONGRATULATIONS, YOU HAVE JUST AUTOMATED THE DEPLOYMENT

