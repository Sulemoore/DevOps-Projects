### Publish Artifact to Nexus Repo

- This step automates the process of publishing the latest artifact to Nexus repository after every successful build.
- We need to add Build-Timestamp to artifact name to get unique artifact each time.
- To Manage, go to:

`Jenkins -> Configure 
System under Build Timestamp we can update the pattern as our wish.`

`yy-MM-dd_HHmm`

- We will add below stage to our pipeline and see results.


```
stage('UPLOAD ARTIFACT') {
                steps {
                    nexusArtifactUploader(
                        nexusVersion: 'nexus3',
                        protocol: 'http',
                        nexusUrl: "${NEXUSIP}:${NEXUSPORT}",
                        groupId: 'QA',
                        version: "${env.BUILD_ID}-${env.BUILD_TIMESTAMP}",
                        repository: "${RELEASE_REPO}",
                        credentialsId: ${NEXUS_LOGIN},
                        artifacts: [
                            [artifactId: 'vproapp' ,
                            classifier: '',
                            file: 'target/vprofile-v2.war',
                            type: 'war']
                        ]
                    )
                }
        }
```

- Build is successful.
- Artifact is uploaded to Nexus repository.
