### Build Jenkins job

- Create a New Job in Jenkins with below properties:

```
Pipeline from SCM 
Git
URL: <url_from_project> I will use SSH link
Crdentials: we will create github login credentials
#### add Jenkins credentials for github ####
Kind: SSH Username with private key
ID: githublogin
Description: githublogin
Username: git
Private key file: paste your private key here
#####
Branch: */ci-jenkins
path: Jenkinsfile
```

- Error is not gone, we need to login jenkins server via SSH and complete host-key checking step. After below command, our host-key will be stored in .ssh/known_hosts file.Then error will be gone.

```
sudo -i
sudo su - jenkins
git ls-remote -h -- git@github.com:rumeysakdogan/vprociproject.git HEAD
```
