### Create Nexus Server

```
Server Name:    Nexus-server
AMI:            Amazon Linus 2
Security Group: nexus-SG
InstanceType:   t2.medium
KeyPair:        "select your key-pair"
Additional Details: copy and paste user data
```

- Nexus userdata

```
#!/bin/bash
yum install java-1.8.0-openjdk.x86_64 wget -y   
mkdir -p /opt/nexus/   
mkdir -p /tmp/nexus/                           
cd /tmp/nexus/
NEXUSURL="https://download.sonatype.com/nexus/3/latest-unix.tar.gz"
wget $NEXUSURL -O nexus.tar.gz
sleep 10
EXTOUT=`tar xzvf nexus.tar.gz`
NEXUSDIR=`echo $EXTOUT | cut -d '/' -f1`
sleep 5
rm -rf /tmp/nexus/nexus.tar.gz
cp -r /tmp/nexus/* /opt/nexus/
sleep 5
useradd nexus
chown -R nexus.nexus /opt/nexus 
cat <<EOT>> /etc/systemd/system/nexus.service
[Unit]                                                                          
Description=nexus service                                                       
After=network.target                                                            
                                                                  
[Service]                                                                       
Type=forking                                                                    
LimitNOFILE=65536                                                               
ExecStart=/opt/nexus/$NEXUSDIR/bin/nexus start                                  
ExecStop=/opt/nexus/$NEXUSDIR/bin/nexus stop                                    
User=nexus                                                                      
Restart=on-abort                                                                
                                                                  
[Install]                                                                       
WantedBy=multi-user.target                                                      

EOT

echo 'run_as_user="nexus"' > /opt/nexus/$NEXUSDIR/bin/nexus.rc
systemctl daemon-reload
systemctl start nexus
systemctl enable nexus
```

### Post Installation Configuration
- ssh into the nexus server

```
sudo -i
system status nexus
```

- Paste the Public IP of the Nexus server in the url and append the port number (e.g 172.23.6.137:8081).
- click sign-in. Go to terminal and get the password from: `/opt/nexus/sonatype-work/nexus3/admin.password`

`cat /opt/nexus/sonatype-work/nexus3/admin.password`

- Login with:

```
Username = admin

Add the password copied.
** setup our new password and select `Disable Anonymous Access`
 **
```
![nexus](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/f165dae7-a946-4483-ae20-ee96fe7feff7)

- Select gear symbol and create repository to help store our release artifacts.

```
maven2 hosted
Name: vprofile-release
Version policy: Release
```
- Next we will create a maven2 proxy repository to store the dependencies in this repository.
```
maven2 proxy
Name: vpro-maven-central
remote storage: https://repo1.maven.org/maven2/
```

- This repo will be used to store our snapshot artifacts with -SNAPSHOT extension in this repository.

```
maven2 hosted
Name: vprofile-snapshot
Version policy: Snapshot
```

- Last repo, will be maven2 group type used this repo to group all maven repositories.

```
maven2 group
Name: vpro-maven-group
Member repositories: 
 - vpro-maven-central
 - vprofile-release
 - vprofile-snapshot
```
