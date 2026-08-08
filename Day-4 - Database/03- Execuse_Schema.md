# Deploy Schema

### Deploy in Localhost
```
psql -h localhost -U digistack_app -d digistack_bank -f V1__create_app_config.sql
```
#### Verification
```
psql -h localhost -U digistack_app -d digistack_bank -c "SELECT * FROM app_config;"
```

### Deploy from Deploy server

#### Install PostgreSQL Clint 

```

sudo dnf -qy module disable postgresql
sudo dnf install -y https://download.postgresql.org/pub/repos/yum/reporpms/EL-8-x86_64/pgdg-redhat-repo-latest.noarch.rpm

sudo dnf install -y postgresql16-server postgresql16-contrib

sudo /usr/pgsql-15/bin/postgresql-15-setup initdb

sudo systemctl enable postgresql-16
sudo systemctl start postgresql-16
```
```
psql -h 192.168.10.30 -U digistack_app -d digistack_bank -f V1__create_app_config.sql
```
#### Verification
```
psql -h 192.168.10.30 -U digistack_app -d digistack_bank -c "SELECT * FROM app_config;"
```
