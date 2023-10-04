### Create Jenkins Server

```
Server Name:    jenkins-server
AMI:            Ubuntu 20.04
Security Group: jenkins-SG
InstanceType:   t2.small
KeyPair:        "select your key-pair"
Additional Details: copy and paste user data
```

- Userdata

```
#!/bin/bash
sudo apt update
sudo apt install openjdk-11-jdk -y
sudo apt install maven -y
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
  
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt-get update
sudo apt-get install jenkins -y
###
```

### Post Installation Configuration

- Copy the public IP of the Jenkins server and ssh into the server to check the status. Run the below commands.

```
sudo -i
system status jenkins
```
- The server should be running at this time
- Paste the Public IP of the Jenkins server in the url and append the port number (e.g 172.23.6.137:8080).
- This should take you to the Jenkins page.
- Copy the path and to to the terminal and run the below to get the password to login.

`cat /var/lib/jenkins/secrets/initialAdminPassword`

- Install suggested plugins and then sign up on the next page.
- Add the following plugins:
  ```
  Maven Integration
  Github Integration
  Nexus Artifact uploader
  Sonarqube Scanner
  Slack notification
  Build timestamp
  ```
