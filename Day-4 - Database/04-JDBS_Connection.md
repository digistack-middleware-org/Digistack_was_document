# PostgreSQL JDBC Driver

Download the PostgreSQL JDBC driver.
```
wget https://jdbc.postgresql.org/download/postgresql-42.5.4.jar

```
Create Directory for postgresql driver 

```
sudo mkdir -p /apps/IBM/SharedLibs/postgresql
```

Copy to

```
sudo mv postgresql-42.2.29.jar postgresql.jar
sudo mv postgresql.jar /apps/IBM/SharedLibs/postgresql/
sudo chown wasadmin:wasadmin /apps/IBM/SharedLibs/postgresql/postgresql.jar
```

# Create JDBC Provider and DataSource

## Admin Console

Navigate to

```text
Resources
    ↓
JDBC
    ↓
JDBC Providers
```
<img width="991" height="472" alt="image" src="https://github.com/user-attachments/assets/e60f69c8-7ff3-446a-b466-bb3b678c538d" />
<img width="1134" height="402" alt="image" src="https://github.com/user-attachments/assets/9473c377-7e6f-49eb-adb4-6df829758060" />


Create a PostgreSQL JDBC Provider.

Create a DataSource with:

| Property  | Value              |
| --------- | ------------------ |
| Name      | DigiStackBankDS     |
| JNDI Name | jdbc/digistackbankDS |
| Database  | nextgenbank        |
| Host      | localhost          |
| Port      | 5432               |
| Username  | nextgenbank_app    |
| Password  | wasadmin@951           |
<img width="1120" height="373" alt="image" src="https://github.com/user-attachments/assets/6d5421b4-cd21-4f74-9b96-56e4dcd27b01" />
<img width="1135" height="364" alt="image" src="https://github.com/user-attachments/assets/fa6fb11b-a500-4ec8-acff-849ee57e2264" />
<img width="1120" height="358" alt="image" src="https://github.com/user-attachments/assets/b2841c69-7a2c-413b-8c40-a90ecb54de09" />
<img width="1126" height="439" alt="image" src="https://github.com/user-attachments/assets/12238aeb-0372-4e0d-8c4b-a32fbe9d1c22" />
<img width="1011" height="297" alt="image" src="https://github.com/user-attachments/assets/f5837b7d-df82-45be-b9eb-42db929ac7fe" />
<img width="529" height="375" alt="image" src="https://github.com/user-attachments/assets/6334e3f4-85a1-4747-aa95-27b29d355397" />
<img width="1116" height="438" alt="image" src="https://github.com/user-attachments/assets/0e24bd9b-4bab-4fc1-8db2-8d64ebbe1de3" />
<img width="1129" height="432" alt="image" src="https://github.com/user-attachments/assets/1a2bca9f-2d01-4357-bd02-a9fd0e6456f1" />

<img width="1141" height="523" alt="image" src="https://github.com/user-attachments/assets/0376db22-8e73-4fc6-94ac-63269689d935" />
<img width="1096" height="838" alt="image" src="https://github.com/user-attachments/assets/b5733fd8-3600-4fc5-a745-13a652e18eb6" />
<img width="976" height="496" alt="image" src="https://github.com/user-attachments/assets/86565f37-0686-48fd-9f39-5b537e47490d" />


Click **Test Connection**.

Expected result

```text
Succeeded
```

---
