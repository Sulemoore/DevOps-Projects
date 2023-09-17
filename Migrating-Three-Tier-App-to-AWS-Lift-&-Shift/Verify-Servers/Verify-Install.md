### Verify Installation of scripts on servers

#### App01
- ssh into the instance ( example: `ssh -i "lift&shift-key.pem" ubuntu@ec2-35-175-205-115.compute-1.amazonaws.com`)
- If you do not have permission run `chmod 400 lift&shift-key.pem` to change permission.
- Verify system status:

`systemctl status tomcat9`

#### rmq01
- ssh into the instance ( example: `ssh -i "lift&shift-key.pem" ec2-user@ec2-35-175-205-115.compute-1.amazonaws.com`)
- If you do not have permission run `chmod 400 lift&shift-key.pem` to change permission.
- Verify system status:

`systemctl status rabbitmq-server`

#### mc01
- ssh into the instance ( example: `ssh -i "lift&shift-key.pem" ec2-user@ec2-35-175-205-115.compute-1.amazonaws.com`)
- If you do not have permission run `chmod 400 lift&shift-key.pem` to change permission.
- Verify system status:

`systemctl status memcache-server`

#### dbp01
- ssh into the db instance ( example: `ssh -i "lift&shift-key.pem" ec2-user@ec2-35-175-205-115.compute-1.amazonaws.com`)
- If you do not have permission run `chmod 400 lift&shift-key.pem` to change permission.

- Login to db:

`mysql -u admin -padmin123 accounts`
`show tables`

