### Connect Github to Jenkins through webhooks

- Connect Github and Jenkins for monitoring commits and trigger automatically by setting up GitHub Web-hook. In your Github repository, go to:
```
Settings -> Webhooks
Note: Copy and add JenkinsURL with /github-webhook/ at the end.
```

- Add below configuration to your Jenkins pipeline:

`Build Trigger: GitHub hook trigger for GITScm polling`

- We can add a post action to our pipeline script and commit/push changes to GitHub.

```
stage('Build') {
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
            post {
                success {
                    echo "Now Archiving."
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
```

```
stage('Test') {
           steps {
            sh 'mvn test'
           }
        }
        
        stage('Checkstyle Analysis'){
            steps {
                sh 'mvn -s settings.xml checkstyle:checkstyle'
            }
        }
```

- With the above setting, every code commit in the repository should trigger our job automatically.
