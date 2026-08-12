# DMGR Profile creation

```
/apps/IBM/WebSphere/AppServer/bin/manageprofiles.sh -create \
  -profileName devdsbindmgr01 \
  -profilePath /apps/IBM/WebSphere/AppServer/profiles/devdsbindmgr01 \
  -templatePath /apps/IBM/WebSphere/AppServer/profileTemplates/dmgr \
  -cellName devdsbincell01 \
  -nodeName devdsbindmgrnode01 \
  -adminUserName wasadmin \
  -adminPassword <your-admin-password> \
  -enableAdminSecurity true
```
