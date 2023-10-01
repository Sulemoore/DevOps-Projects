### Create SG for the instances.

- Jenkins SG
```
Name: jenkins-SG
Allow: SSH from MyIP
Allow: 8080 from Anywhere IPv4 and IPv6 
```

- Nexus SG
```
Name: nexus-SG
Allow: SSH from MyIP
Allow: 8081 from MyIP and Jenkins-SG
```

![Screenshot 2023-09-30 at 11 28 08 PM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/9629ec96-b901-4676-9046-67b3212c7d4d)

- Sonar SG
```
Name: sonar-SG
Allow: SSH from MyIP
Allow: 80 from MyIP and Jenkins-SG
```
![Screenshot 2023-09-30 at 11 29 21 PM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/210a6d11-8361-49c8-846e-dfe8158fc759)

![Screenshot 2023-09-30 at 11 28 44 PM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/76fad18b-2636-426e-b142-627f3f74ca3c)
