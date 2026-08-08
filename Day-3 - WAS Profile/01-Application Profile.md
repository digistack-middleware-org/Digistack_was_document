# Application Server Profile
## Step:1 ==> Profile creation
### Give permissions to the wasadmin user
```
chown -R wasadmin:wasgrp /apps/IBM
chown -R wasadmin:wasgrp /opt/software/IBM
chown -R wasadmin:wasgrp /var/log/IBM
```
```
chmod -R 774 /apps/IBM
chmod -R 774 /opt/software/IBM
chmod 775 /home/wasadmin
```

### Switch to wasadmin User
```
su - wasadmin
```
### Goto the PATH
```
cd /apps/IBM/WebSphere/AppServer/bin/
```
### Create Application Profile
```
/apps/IBM/WebSphere/AppServer/bin/manageprofiles.sh -create \
  -templatePath /apps/IBM/WebSphere/AppServer/profileTemplates/default \
  -profileName devdsbinappserver01 \
  -profilePath /apps/IBM/WebSphere/AppServer/profiles/devdsbinappserver01 \
  -nodeName devdsbinnode01 \
  -cellName devdsbincell01 \
  -hostName dsb-dmgr.digistack.cloud \
  -adminUserName wasadmin \
  -adminPassword 'Wasadmin@951951' \
  -enableAdminSecurity true
```
## Step:2 ==> Verification
#### Confirm the profile is registered
```
/apps/IBM/WebSphere/AppServer/bin/manageprofiles.sh -listProfiles
```
#### Confirm the profile's folder structure was actually built
```
ls /apps/IBM/WebSphere/AppServer/profiles/devdsbinappserver01
```
## Step:3 ==> Start the Application server to access admin console
```
/apps/IBM/WebSphere/AppServer/profiles/devdsbinappserver01/bin/startServer.sh server1
```
#### Open Mozilla Firefox and navigate to the following URL:
```
https://dsb-dmgr.digistack.cloud:9043/ibm/console
```
