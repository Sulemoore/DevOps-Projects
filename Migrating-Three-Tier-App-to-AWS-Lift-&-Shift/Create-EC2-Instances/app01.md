#### Create the App Instance

- Name: VProfile-app01

  ![Screenshot 2023-09-16 225322](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/5fb002f4-8bd4-44c6-8350-8a75995d124e)

- AMI: Choose Ubuntu for the AMI

![Screenshot 2023-09-16 225336](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/89e9dc9b-ed0c-4786-ac1e-c31d9f02984f)

- T2 micro for instance type

![Screenshot 2023-09-16 225350](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/91f7ca52-0ef6-43a8-84d0-b287aa4ed270)

- Security Group: Select the APP Security Group

![Screenshot 2023-09-16 225421](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/06b4ee0b-dd03-420d-9e32-7db4959c3160)

- User data: Add the below user data to install open JDK and tomcat9

```
#!/bin/bash
sudo apt update
sudo apt upgrade -y
sudo apt install openjdk-11-jdk -y
sudo apt install tomcat9 tomcat9-admin tomcat9-docs tomcat9-common git -y
```
