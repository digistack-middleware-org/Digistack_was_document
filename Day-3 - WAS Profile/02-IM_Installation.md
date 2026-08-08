# Installation Manager Installation

### Step:1 ==> Extract the Package 
```
unzip agent.installer.linux.gtk.x86_64_1.10.1004.20260506_0701.zip -d /opt/software/IBM/IM
```
```
cd /opt/software/IBM/IM
```
### Step:2 ==> Install the IBM installation Manager

```
./installc\
-acceptLicense \
-installationDirectory /apps/IBM/InstallationManager \
-dataLocation /apps/IBM/IMData \
-log /var/log/IBM/was/IM_install_$(date +%Y%m%d_%H%M%S).log \
-showProgress
```

### Step:3 ==> Verify IBM installation Manager Installation
```
cd /apps/IBM/InstallationManager/eclipse/tools/
```
```
./imcl version
./imcl listInstalledPackages 
```
