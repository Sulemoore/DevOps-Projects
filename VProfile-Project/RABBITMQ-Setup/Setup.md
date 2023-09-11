## RABBITMQ SETUP - rmq01
- #### Login to the RabbitMQ vm

`$ vagrant ssh rmq01`

- #### Verify Hosts entry, if entries missing update the it with IP and hostnames

`# cat /etc/hosts`

- #### Update OS with latest patches

`# yum update -y`

- #### Set EPEL Repository

`# yum install epel-release -y`

- #### Install Dependencies
```
# sudo yum install wget -y
# cd /tmp/
# dnf -y install centos-release-rabbitmq-38
# dnf --enablerepo=centos-rabbitmq-38 -y install rabbitmq-server
# systemctl enable --now rabbitmq-server
# sudo systemctl start rabbitmq-server
# sudo systemctl enable rabbitmq-server
# sudo systemctl status rabbitmq-server
# sudo sh -c 'echo "[{rabbit, [{loopback_users, []}]}]." > /etc/rabbitmq/rabbitmq.config'
# sudo rabbitmqctl add_user test test
# sudo rabbitmqctl set_user_tags test administrator
# sudo systemctl restart rabbitmq-server
```
