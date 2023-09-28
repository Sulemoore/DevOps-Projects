# Continuous Integration Using Jenkins, Nexus, Sonarqube & Slack

## Architecture

### Prerequisite

- AWS Account
- GitHub account
- Jenkins
- Nexus
- SonarQube
- Slack

### Continuous Integration Flow
![Continuous Integration Using Jenkins,Nexus,Sonarqube  Slack](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/ac99a77c-bb12-495a-9383-b7f05f6b19eb)


### Flow of Execution

- Login to AWS Account.
- Create Your Key Pair.
- Create Security Group for Jenkins, Nexus and Sonarqube.
- Create EC2 Instances with User-data for Jenkins, Nexus and Sonarqube
- Post Installation.
Jenkins setup and Plugin
Nexus Setup and repository setup
Sonarqube login test
- Git.
.Create a github repository and migration code
. integrate github repo with Vs-code and test it
- Build Job with Nexus integration.
- Github Webhooks.
- Sonarqube Server integration stage.
- Nexus Artifact upload stage.
- Slack Notification.
