## MEMCACHE SETUP
- #### Install, start & enable memcache on port 11211
```
# sudo dnf install epel-release -y
# sudo dnf install memcached -y
# sudo systemctl start memcached
# sudo systemctl enable memcached
# sudo systemctl status memcached
# sed -i 's/127.0.0.1/0.0.0.0/g' /etc/sysconfig/memcached
# sudo systemctl restart memcached
```
![Screenshot 2023-09-10 235235](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/95512810-b00a-4141-97aa-9847d9d2b91c)



