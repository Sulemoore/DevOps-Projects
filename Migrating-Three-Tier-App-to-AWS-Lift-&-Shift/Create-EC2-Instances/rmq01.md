#### Create the RabbitMQ Instance

-Name: VProfile-rmq01

![Screenshot 2023-09-15 000526](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/05ddaac7-2e46-4b5d-836c-f6fe6505cc9b)

- AMI: Choose CentOS 9
  
![Screenshot 2023-09-14 234106](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/4144357d-66d2-47b8-926a-84adb749108c)

- Pick keypair and Backend SG

![Screenshot 2023-09-15 000556](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/47c15527-44f1-4bd5-bc4b-4299a7a9fa0c)

- Add user data
- 
![Screenshot 2023-09-15 000607](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/060de9dc-f96e-44e9-8845-7f8508d856f2)

```
#!/bin/bash
sudo yum install epel-release -y
sudo yum update -y
sudo yum install wget -y
cd /tmp/
dnf -y install centos-release-rabbitmq-38
 dnf --enablerepo=centos-rabbitmq-38 -y install rabbitmq-server
 systemctl enable --now rabbitmq-server
 firewall-cmd --add-port=5672/tcp
 firewall-cmd --runtime-to-permanent
sudo systemctl start rabbitmq-server
sudo systemctl enable rabbitmq-server
sudo systemctl status rabbitmq-server
sudo sh -c 'echo "[{rabbit, [{loopback_users, []}]}]." > /etc/rabbitmq/rabbitmq.config'
sudo rabbitmqctl add_user test test
sudo rabbitmqctl set_user_tags test administrator
sudo systemctl restart rabbitmq-server
```
