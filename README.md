# Setup VM Ubuntu 20.4 LTS in GG Cloud with Compute Engine

![Alt text](image.png)

# Config SSH by password

## Create new password

```bash
sudo passwd
```

## Update SSHD Config (need root user)

```bash
vi /etc/ssh/sshd_config
```

Change

* PermitLogin: yes
* PasswordAuthentication: yes

![Alt text](image-1.png)

## Restart SSHD

```bash
service restart sshd.service
```

# Setup CI/CD Github Actions

## Create github flow
![Alt text](image-2.png)

## Configure in VM
![Alt text](image-3.png)

# Config Nginx, Setup DNS and SSL Certificate by Certbot

## Congig Nginx

```bash
sudo apt install nginx
```

![Alt text](image-4.png)

Change config file nginx

* root /var/www/build (need create folder first)

* update server_name by domain

![Alt text](image-5.png)

## Setup DNS in Network Service GG and Tenten for domain

![Alt text](image-6.png)

![Alt text](image-7.png)

## Setup SSL by Certbot

```bash
sudo certbot --nginx -d testfrontend.click -d www.testfrontend.click
```

Link: https://www.testfrontend.click/
