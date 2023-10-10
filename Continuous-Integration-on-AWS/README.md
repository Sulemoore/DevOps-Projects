# Continuous Integration (CI) on AWS.

### Scenario

You have a product development and Agile SDLC with developers regularly making multiple code changes every day. And all these codes need to be regularly built and tested because this is what actually is building our product.

In a typical enterprise there will be a separate build and release team who bears this responsibility of building, testing and releasing the code.

### Problem

Because of the regular commits and/or pull requests, their will be dependency of teams on one another to complete their jobs.

- Developers will be dependent on build and release team, usually to test the code and move it to the next level in the release cycle.
- The code will be tested for any bugs or error which may be discovered late after a tone have accumulated.
- Developers would need to work extra to fix these bugs and errors, which is a time consuming process and teams would be already approaching the deadline.

### Solution
- Regular build and test for every commit. Instead of waiting to complete the code before discovering bugs, regular commits are made during the code writing to discover and fix bugs if any.
- Automated build and release process instead of manual process.
- Developer should get notified automatically if their is any code error or test failure.

### Architecture

### AWS Services Utilized

- Code Commit for version control
- Code Artifact for Maven Repository for Dependencies
- Code Build to run our build process and also code analysis
- Code Deploy to deploy our artifact stored in S3.
- SonarCloud
- CheckStyle for code analysis
- Code Pipiline to integrate all jobs together 

### Flow of Execution

- Login to AWS Account

- Code Commit

      . Create code commit repo
      
      . Create IAM user with code commit policy
      
      . Generate ssh keys locally
      
      . Exchange keys with IAM user
      
      . Put source code from Github repo to Code Commit repository and push

- Code Artifact

        . Create an IAM user with code artifact access
        
        . Install AWS CLI and configure
        
        . Export Auth token
        
        . Update settings.xml file in source code top level directory with details
        
        . Update pom.xml file with repo details

- Sonar cloud

        . Create sonar cloud account
        
        . Generate token
        
        . Create SSM parameters with sonar details
        
        . create Build project
        
        . Update code build role to access SSM parameter store

- Create notifications for SNS or Slack

- Build Project

        . Update pom.xml with artifact version with timestamp
        
        . Create variables in SSm => parameter store
        
        . Create Build Project
        
        . Update code build role to access SSm parameter store

- Create Pipeline

        . Codecommit
        
        . Test Code
        
        . Build
        
        . Deploy to S3 Bucket

- Test Pipeline
