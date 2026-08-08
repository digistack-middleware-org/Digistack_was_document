# Create Database and Tables

### Run on dsb-db, as the postgres OS user
```
sudo -u postgres psql
```
### Create Database and "digistack_app" user and give permissions
```
CREATE DATABASE digistack_bank;
CREATE USER digistack_app WITH PASSWORD 'Wasadmin@951951';
GRANT ALL PRIVILEGES ON DATABASE digistack_bank TO digistack_app;
```
### Quit Db
```
\q
```
