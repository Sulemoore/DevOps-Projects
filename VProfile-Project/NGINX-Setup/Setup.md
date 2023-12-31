## NGINX SETUP - Web01
- #### Login to the Nginx vm

`$ vagrant ssh web01`

- #### Verify Hosts entry, if entries missing update the it with IP and hostnames

`# cat /etc/hosts`

- #### Update OS with latest patches
```
# apt update
# apt upgrade
```

- #### Install nginx

`# apt install nginx -y`

- #### Create Nginx conf file with below content

`# vi /etc/nginx/sites-available/vproapp`
```
upstream vproapp {
server app01:8080;
}
server {
listen 80;
location / {
proxy_pass http://vproapp;
}
}
```

- #### Remove default nginx conf

`# rm -rf /etc/nginx/sites-enabled/default`

- #### Create link to activate website

`# ln -s /etc/nginx/sites-available/vproapp /etc/nginx/sites-enabled/vproapp`

- #### Restart Nginx

`# systemctl restart nginx`

![Screenshot 2023-09-11 005220](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/b24c0dbb-7a66-498b-a396-48c5696a2d30)
