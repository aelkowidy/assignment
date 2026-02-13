# Webapp Assignment - Directory Permissions Setup

## Objective
Set up `/opt/webapp/` directory structure with proper users, groups, and permissions.

## Users and Groups
- **User:** `webapp_user`  
- **Group:** `webapp_support`  

## Directory Structure
/opt/webapp/
├── bin/
├── config/
└── logs/


## Permissions Setup

1. Create user and group:
```bash
sudo useradd -r -s /usr/sbin/nologin webapp_user
sudo groupadd -r webapp_support
Create support user for testing group:

sudo useradd -m -s /bin/bash support1
sudo usermod -aG webapp_support support1
Create directory structure:

sudo mkdir -p /opt/webapp/{bin,config,logs}
Set ownership:

sudo chown -R webapp_user:webapp_support /opt/webapp
Set permissions:

sudo chmod -R 700 /opt/webapp
sudo chmod -R 750 /opt/webapp/config /opt/webapp/logs
sudo chmod -R 700 /opt/webapp/bin
Verify users, groups, and permissions:

id webapp_user
groups support1
ls -l /opt/webapp
Notes
Others (everyone else) have no access to any part of /opt/webapp/.

Commands were executed on Ubuntu VM via SSH.

These are the whole Assignment's commands:
sudo useradd -r -s /usr/sbin/nologin webapp_user
grep webapp_user /etc/passwd
ls /home
su -webapp_user
sudo groupadd -r webapp_support
grep webapp_support /etc/group
sudo useradd -m -s /bin/bash support1
sudo usermod -aG webapp_support support1
groups support1
sudo mkdir -p /opt/webapp/{bin,config,logs}
ls -l/opt/webapp
ls -l /opt/webapp
sudo chown -R webapp_user:webapp_support /opt/webapp
ls -ld /opt/webapp
ls -l /opt/webapp
sudo chown -R webapp_user:web_support /opt/webapp/
sudo chown -R webapp_user:webapp_support /opt/webapp/
sudo chmod -R 700 /opt/webapp/
sudo chgrp -R webapp_support /optwebapp/config opt/webapp/logs
sudo chgrp -R webapp_support /opt/webapp/config opt/webapp/logs
sudo chgrp -R webapp_support /opt/webapp/config /opt/webapp/logs
sudo chmod -R 750 /opt/webapp/config /opt/webapp/logs
sudochgrp -R webapp_support /opt/webapp/bin
sudo chgrp -R webapp_support /opt/webapp/bin
sudo chmod -R 700 /opt/webapp/bin
ls -lR /opt/webapp > verfication.txt
sudo ls -lR /opt/webapp > verfication.txt
id webapp_user >> verfication.txt
groups support1 >> verfication.txt
