### Build Job in Nexus

Build Nexus Job

- Build the Artifact from Source Code using Maven. Prerequisite include JDK8 and Maven to be installed in Jenkins to complete the job successfully.
- Install Java8 in Jenkins.

`Manage Jenkins -> Global Tool Configuration` 

- Install JDK8 manually.

```
Under JDK -> Add JDK
Name: OracleJDK8
untick Install Automatically
JAVA_HOME: < we will get after next step >
```
```
sudo apt update -y
sudo apt install openjdk-8-jdk -y
sudo -i
ls /usr/lib/jvm
### we should get both jdk-11 and jdk-8 in this path ###
java-1.11.0-openjdk-amd64  java-11-openjdk-amd64  openjdk-11
java-1.8.0-openjdk-amd64   java-8-openjdk-amd64
```

- Setup Maven.
```
Name: MAVEN3
version : keep same
```

- Add Nexus login credentials to Jenkins.

`Manage Jenkins -> Manage Credentials -> Global -> Add Credentials`

```
username: admin
password: <pwd_setup_for_nexus>
ID: nexuslogin
description: nexuslogin
```

- Create Jenkins file for Building the pipeline.

```
pipeline {
    agent any
    tools {
        maven "MAVEN3"
        jdk "OracleJDK8"
    }
```

```
    environment {
        SNAP_REPO = 'vprofile-snapshot'
        NEXUS_USER = 'admin'
        NEXUS_PASS = 'admin'
        RELEASE_REPO = 'vprofile-release'
        CENTRAL_REPO = 'vpro-maven-central'
        NEXUSIP = '172.31.10.139'
        NEXUSPORT = '8081'
        NEXUS_GRP_REPO = 'vpro-maven-group'
        NEXUS_LOGIN = 'nexuslogin'
    }    stages {
        stage('Build') {
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
        }
    }
}
```
