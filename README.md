# -Migrating-a-Database-to-Amazon-RDS
In this project, I migrated a café’s application database from a MariaDB instance running on Amazon EC2 to Amazon RDS, without breaking the application or losing data.
The objective was to understand why databases are better managed as separate, fully managed services rather than running directly on application servers. This lab demonstrated how to decouple application and database layers to improve scalability, reliability, maintainability, and cost efficiency.
By completing this migration successfully, I gained hands-on experience with real-world database migration workflows and learned how managed services simplify operations while improving system design.

**Steps Taken**

1️⃣**Created an Amazon RDS Database Instance**
Provisioned an Amazon RDS instance running MariaDB.
Prepared the RDS environment to receive migrated data.
Ensured the database was accessible from the application environment.

2️⃣ **Exported Data from EC2-Based MariaDB**
Used mysqldump to export data from the MariaDB database running on the EC2 instance.
Verified the integrity of the exported data before migration.

3️⃣ **Migrated Data to Amazon RDS**
Connected a SQL client to the Amazon RDS instance.
Imported the exported data into the RDS database.
Confirmed that all tables and records were successfully migrated.

4️⃣ **Updated Database Connection Using AWS Secrets Manager**
Instead of modifying the application’s PHP code, updated database connection details stored in AWS Secrets Manager.
Changed values such as the database endpoint to point to the new RDS instance.
Allowed the application to automatically connect to RDS without redeployment.

5️⃣ **Decommissioned the Old Database and Tested the Application**
Stopped the MariaDB service running on the EC2 instance.
Tested the application by placing new orders.
Verified that all existing orders were still available, confirming a successful migration with no data loss.

 **Cost Optimization Insight**
With the database removed from the EC2 instance:
The EC2 instance can be downsized.
Unused storage can be reduced.
This results in lower operational costs and a more efficient architecture.

 **Key Skills Demonstrated**
Database migration from EC2 to Amazon RDS
Using mysqldump for data export and import
Secure configuration management with AWS Secrets Manager
Decoupling application and database layers
Cost optimization through managed AWS services
