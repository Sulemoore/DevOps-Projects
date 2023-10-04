### Create Slack Notification

- Login to slack and create a workspace.
- Add Jenkins app to slack.
- Choose the channel you created.
- Go to Jenkins dashboard and Configure system -> Slack

```
Workspace:  example (in the workspace url example.slack.com)
credential: slacktoken 
default channel: #jenkins-slack-cicd
```

- Add our sonar token to global credentials.

```
Kind: secret text
Secret: <paste_token>
name: slacktoken
description: slacktoken
```

- Add below part to our Jenkins file in the same level with stages and push our changes.

```
post{
        always {
            echo 'Slack Notifications'
            slackSend channel: '#jenkinscicd',
                color: COLOR_MAP[currentBuild.currentResult],
                message: "*${currentBuild.currentResult}:* Job ${env.JOB_NAME} build ${env.BUILD_NUMBER} \n More info at: ${env.BUILD_URL}"
        }
    }
```
