# OS Check
### Switch to Root User
```
su -
```
### Step 1 — Confirm OS Version and Baseline
```
cat /etc/os-release
uname -r
```
### Step:2 ==> Install the Required packages for Websphere
```
sudo dnf install -y glibc libstdc++ ncurses
```

### Step:3 ==> Confirm Hostname, FQDN, and DNS Resolution
```
hostname -f
```
##### Step:1 ==> Configure hostname
```
hostnamectl set-hostname dsb-dmgr.digistack.cloud
```
##### Step:2 ==> Configure hostname
```
vi /etc/hosts
```
```
192.168.10.11 dsb-dmgr.digistack.cloud dsb-dmgr
```
##### Step:3 ==> Check the Connection
```
hostname -f

getent hosts $(hostname -f) 

nslookup $(hostname -f)
```
### Step:4 ==> Stop the Firewall {for LAB Purpose}
```
systemctl stop firewalld
systemctl disable firewalld
```

### Step:5 ==> Create WebSphere Service User

##### Step:1 ==> Create group for Websphere
```
groupadd -g 1500 wasgrp
```
##### Step:2 ==> create WebSphere service user "wasadmin"
```
	useradd -u 1500 \
	        -g wasgrp \
	        -G wasgrp \
	        -d /home/wasadmin \
	        -m \
	        -s /bin/bash \
	        -c "WAS Middleware Service Account" \
        wasadmin
```
##### Step:3 ==> Change password for "wasadmin" user
```
passwd wasadmin
```
##### Step:4 ==> Validation
```
id wasadmin
getent passwd wasadmin
getent group wasgrp
```

### Step:6 ==> Create Directories for Websphere
##### Step:1 ==> Create the full IBM directory layout
```
mkdir -p /apps/IBM/InstallationManager
mkdir -p /apps/IBM/IMShared
mkdir -p /apps/IBM/IMData
	
mkdir -p /apps/IBM/WebSphere/AppServer
mkdir -p /var/log/IBM/websphere
```
##### Step:2 ==> Create staging area for binaries
```
mkdir -p /opt/software/IBM/IM
mkdir -p /opt/software/IBM/WAS
```
##### Step:3 ==> Hand ownership to "wasadmin" user
```
chown -R wasadmin:wasgrp /apps/IBM
chown -R wasadmin:wasgrp /opt/software/IBM
chown -R wasadmin:wasgrp /var/log/IBM
```
##### Step:4 ==> Set Permissions
```
chmod -R 774 /apps/IBM
chmod -R 774 /opt/software/IBM
chmod 775 /home/wasadmin
```
