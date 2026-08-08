# RHEL 8.0 Installation

### Step:1 ==> Install VMWare

### Step:2 ==> Install RedHat Linux 8 

### Step:3 ==> Register the Subscription Manager

Once RHEL 8 installation is finished we need to register to official RedHat repositories for Package Management

#### Step:1 ===> Switch to Root User
```
su -
```
validate your dnf or YUM repo are working or Not
```
dnf update -y
```

#### Step:2 ===> Register to RedHat Account
```
subscription-manager register
```
It is asking RedHat account Username and Password and Organization gave that Information

or

```
subscription-manager register --username <your-username> --password <your-password>
```

### In real Organizations, follow use these command
```
subscription-manager register --org=<ORG_ID> --activationkey=<ACTIVATION_KEY>
```

#### Step:3 ===> Attach the free subscription
```
subscription-manager attach --auto
```

#### Step:4 ===> Enable the Repos 

For RHEL 7
```
subscription-manager repos --enable=rhel-7-server-rpms
```

For RHEL 8
```
subscription-manager repos --enable=rhel-8-for-x86_64-baseos-rpms --enable=rhel-8-for-x86_64-appstream-rpms
```
#### Step:5 ===> Refresh the Subscription
```
subscription-manager refresh
```

#### Step:6 ===> Verify the Subscription status
```
subscription-manager status
```

validate your dnf or YUM repo are working or Not
```
dnf update -y
```
