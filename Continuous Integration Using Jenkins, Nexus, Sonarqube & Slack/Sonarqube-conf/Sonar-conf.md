### Configure Code Analysis with Sonarqube

- Analyzing Code with SonarQube. 
We need:

- SonarScanner tool in Jenkins to scan the code
- SonarQube information in Jenkins
- To configure SonarScanner Go to:

`Manage Jenkins -> Global Tool Configuration`


```
Add sonar scanner
name: sonarscanner
tick install automatically
```

- Next we need to go to Configure System, and find SonarQube servers section

'''
tick environment variables
Add sonarqube
Name: sonarserver
Server URL: http://<private_ip_of_sonar_server>
Server authentication token: we need to create token from sonar website
'''

- Add our sonar token to global credentials.

'''
Kind: secret text
Secret: <paste_token>
name: sonartoken
description: sonartoken
'''

- Add sonarQube code for our pipeline and commit/push changes to GitHub.

```
##new environment variables to be added to environment##
SONARSERVER = 'sonarserver'
SONARSCANNER = 'sonarscanner'
```

```
##new stages to be added##
 stage('CODE ANALYSIS with SONARQUBE') {
          
          environment {
             scannerHome = tool "${SONARSCANNER}"
          }          steps {
            withSonarQubeEnv("${SONARSERVER}") {
               sh '''${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=vprofile \
                   -Dsonar.projectName=vprofile-repo \
                   -Dsonar.projectVersion=1.0 \
                   -Dsonar.sources=src/ \
                   -Dsonar.java.binaries=target/test-classes/com/visualpathit/account/controllerTest/ \
                   -Dsonar.junit.reportsPath=target/surefire-reports/ \
                   -Dsonar.jacoco.reportsPath=target/jacoco.exec \
                   -Dsonar.java.checkstyle.reportPaths=target/checkstyle-result.xml'''
            }
          }
```


- We can see quality gate results in SonarQube server.
- To Create a custom Quality Gates and add to our project go to:

```
Quality gate -> Create. add Condition.
Note: You can give Bug is greater than 80 then Save it. 
Click on projectname it will have a dropdown.
Click Quality Gate and choose the new Quality gate you have created.
```

- Create a Webhook in SonarQube to send the analyzed results to Jenkins.

`http://<private_ip_of_jenkins>:8080/sonarqube-webhook`

- Add another stage to our pipeline and commit changes to Github.

```
stage('QUALITY GATE') {
            steps {
                timeout(time: 10, unit: 'MINUTES') {
               waitForQualityGate abortPipeline: true
            }
            }
}
```

- At this time BUILD should be successful.
