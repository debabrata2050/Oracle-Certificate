# Skill Check
## MySQL 8.4: Essentials

## Enterprise Edition

#### What does the Oracle commercial licensing option allow businesses to do?
- [ ] Allows businesses to use MySQL Enterprise Edition for free
- [x] Allows businesses to use MySQL code in their products and keep their code private ✅
- [ ] Allows businesses to use MySQL in their products with other third-party commercial products
- [ ] Allows businesses to pay a reduced price for MySQL Community Edition

#### For which language does MySQL Shell offer support?
- [ ] Java
- [ ] GO
- [ ] PHP
- [x] Python ✅

#### Which statement is true about MySQL Workbench Enterprise?
- [ ] It backs up MySQL instances.
- [ ] It installs MySQL server.
- [x] It simplifies MySQL database migrations. ✅
- [ ] It adds security features to the MySQL system.

#### How many major editions does MySQL offer?
- [ ] Five
- [x] Two ✅
- [ ] Three
- [ ] One

#### Which service does MySQL HeatWave offer?
- [ ] Automatic replication to the Oracle Database
- [ ] Migration to AWS Aurora
- [x] A fully managed MySQL service ✅
- [ ] Backup to GitHub

#### When is MySQL Enterprise Support available?
- [ ] 8 hours a day, 7 days a week
- [x] 24 hours a day, 7 days a week ✅
- [ ] 8 hours a day, 5 days a week
- [ ] 24 hours a day, 5 days a week

***

## Installation and Architecture

#### 1. Which statement is true about the data directory?
- [ ] It is empty until you create a user database.
- [x] It is a mandatory setting in the my.cnf file. ✅
- [ ] It contains the my.cnf and temporary files.
- [ ] It is configured automatically when you install MySQL from binary archive.

> The data directory setting datadir specifies the default location of system and user databases, and is one of the settings for file locations. Other settings include locations for temporary files and configuration files.

#### 2. How often are MySQL Innovation versions released?
- [x] Every quarter ✅
- [ ] Every two years
- [ ] Every year
- [ ] Every month

> MySQL long-term support versions are released every two years. Innovation versions are released quarterly.

#### 3. Which installation method requires that you manually configure the service user?
- [ ] yum packages
- [ ] MySQL Installer
- [ ] RPM packages
- [x] binary archive ✅

> The yum and RPM package installers install and configure MySQL on Linux. The MySQL Installer installs and configures MySQL on Windows. The binary archive only contains the necessary files but does not perform any configuration.

#### 4. Which permissions are required for the MySQL service user?
- [ ] Shell privileges
- [ ] System privileges
- [ ] Root privileges
- [x] Data directory privileges ✅

> The MySQL service user needs only privileges to run the process and access the network and relevant directories in the file system. You should not grant permissions beyond that, so that the service cannot be exploited by malicious users.

#### 5. Which statement is true about upgrades?
- [ ] You must reinstall MySQL completely and restore from backup when upgrading from Community Edition to Enterprise Edition.
- [ ] The Upgrade Checker utility is only available in Enterprise Edition.
- [x] You can upgrade MySQL while the server is offline by replacing the binaries with new versions. ✅
- [ ] You can upgrade MySQL while the server is running.

> Upgrading is an offline operation, performed in-place by replacing existing binaries with the new version. This process also works when upgrading to Enterprise Edition. The Upgrade Checker utility is available in MySQL Shell, and can be used on any MySQL version and edition up to and including the version of MySQL Shell.

***

## Database Design

#### 1. What is performed by the JOIN clause in SQL?
- [ ] Concatenates two or more column values to a single output column
- [x] Connects rows from two or more tables on some condition ✅
- [ ] Jumps to the next row if a value is null (Jump Only If Null)
- [ ] Generates a Venn diagram of table row associations

#### 2. Which is the default MySQL storage engine?
- [ ] NDB Cluster
- [ ] Memory
- [ ] MylSAM
- [x] InnoDB ✅

#### 3. What can you accomplish using MySQL Partitioning?
- [ ] Specify the storage engine for a particular database.
- [ ] Specify how big each column can be based on how many partitions are there.
- [ ] Specify how big each table can be based on where it is stored
- [x] Specify a physical file for each row based on a rule. ✅

#### 4. Which data type stores string values?
- [ ] DOUBLE
- [x] ENUM ✅
- [ ] DECIMAL
- [ ] BIT

> The ENUM (short for enumeration) stores multiple indexed string values.

#### 5. Which statement is true about PRIMARY indexes?
- [ ] You can have multiple rows with the same value in the PRIMARY index.
- [x] PRIMARY index values are replicated to every secondary index. ✅
- [ ] They speed up insert operations.
- [ ] You can have multiple PRIMARY indexes on a table.

> The PRIMARY index manages the primary key of a table. Its values must be unique and are used as a lookup value for all secondary indexes.

***

## Database Security

#### 1. Which statement about dynamic privileges is true?
- [x] They are assigned by the server, a plugin, or a component at load time. ✅
- [ ] They are assigned implicitly when a transaction requires them.
- [ ] They are assigned in the mysqld-auto.cnf configuration file.
- [ ] They are assigned in the my.cnf configuration file.

> Dynamic privileges are granted by the server at run time, either during the startup process or by plugins and components as they are loaded. They may also be granted explicitly with GRANT statements. They are not specified in configuration files.

#### 2. Which MySQL Enterprise feature supports Kerberos, PAM, and FIDO?
- [x] Authentication ✅
- [ ] Auditing
- [ ] Manager
- [ ] Firewall

> MySQL Enterprise Authentication brings together a set of plugins that support authentication with external infrastructure based on LDAP, Kerberos, or using the Pluggable Authentication Module (PAM) framework in Linux.

#### 3. What is the default MySQL authentication plugin used to encrypt passwords?
- [ ] caching_sha256_password
- [ ] plaintext
- [ ] mysql_native_password
- [x] caching_sha2_password ✅

> MySQL encrypts passwords before storing them in the database. The caching_sha2_password plugin uses a secure one-way encryption algorithm to create passwords that cannot easily be decrypted, even if the database is compromised.

#### 4. Which product can mitigate the risk of SQL Injection attacks?
- [ ] MySQL Shell
- [ ] MySQL Enterprise Audit
- [x] MySQL Enterprise Firewall ✅
- [ ] Oracle Enterprise Manager

> MySQL Enterprise Firewall enables you to create an allow list of statements, and it blocks statements that do not match that allow list. SQL injection attacks attempt to insert SQL statements within user interfaces, and if those statements are not in the allow list then they are prevented from executing.

#### 5. Which type of compliance do GDPR, HIPAA, FERPA, and GLBA impose that MySQL can implement?
- [ ] Performance
- [x] Regulatory ✅
- [ ] Administrative
- [ ] Financial

***

## MySQL Enterprise Security Tools

#### 1. What file can you encrypt using MySQL Enterprise Transparent Data Encryption (TDE)?
- [x] Tablespace File ✅
- [ ] SSL Key File
- [ ] Configuration File (my.cnf or my.ini)
- [ ] General Query, Slow Query, and Error Log File

> MySQL stores table data in a tablespace file. Using MySQL Enterprise Transparent Data Encryption (TDE), you can encrypt these files to protect the privacy of your information, prevent data breaches and help meet regulatory requirements. TDE can also encrypt log files such as binary, relay, undo, and redo logs, but it cannot encrypt general query, slow query, and error log file.

#### 2. Against what does MySQL Enterprise Firewall provide real-time protection?
- [ ] Virus
- [ ] Denial of Service (DoS) Attack
- [x] SQL Injection ✅
- [ ] Brute Force Attack

#### 3. Which two formatting options are supported by MySQL Enterprise Audit?
- [x] XML ✅
- [ ] SQL
- [ ] Text
- [ ] YAML
- [x] JSON ✅

> The supported audit log file formats are XML and JSON. The default is XML. However, this can be changed at server startup by setting the audit_log_format variable.

#### 4. When using MySQL Enterprise Transparent Data Encryption (TDE), which key must be stored outside the database?
- [ ] Primary
- [ ] Public
- [x] Master ✅
- [ ] Private
- [ ] Tablespace

> InnoDB uses a two-tier encryption key architecture, consisting of a master key and tablespace keys. When a tablespace is encrypted, a tablespace key is encrypted and stored in the tablespace header. InnoDB uses a master encryption key to decrypt the tablespace key when accessing encrypted data. It is the master key that must be stored outside the database (in a key vault) and should be rotated periodically or whenever you suspect that the key has been compromised and this key.

#### 5. In which two ways can you install the MySQL Enterprise Masking and De-Identification feature?
- [ ] Configuration File
- [x] Plugin ✅
- [ ] Tablespace
- [x] Component ✅
- [ ] Stored Procedure

> MySQL Enterprise Masking and De-Identification feature can be implemented through either a plugin or a component. Plugins are a *set of loadable functions* that provide a SQL-level API for performing operations such as masking and de-identification. Components are *self-contained code containers* that interact with other code exclusively by implementing and consuming services via the registry. However, enabling both at the same time is unsupported and results may not be as anticipated.

***

## MySQL Backup

#### 1. What must you do to restore from a backup using MySQL Enterprise Backup?
- [ ] Shut down the MySQL database system.
- [ ] Review the SQL script generated script to make sure it is valid.
- [ ] Unzip the MySQL Enterprise Backup file.
- [x] Remove any previous files from the MySQL data directory. ✅

> To restore from a backup using MySQL Enterprise Backup, you must first remove any previous files from the data directory. The restore process will fail if you attempt to restore over an existing system or backup.

#### 2. How does MySQL Enterprise Backup support optimistic backup?
- [x] It records all data including data from busy tables. ✅
- [ ] It puts the database server in read-only mode.
- [ ] It locks up tables during the backup process.
- [ ] It ignores data from busy tables.

> MySQL Enterprise Backup supports optimistic backup. This process deals with busy tables separately from the rest of the database. It can record changes that happen in the database during the backup, for consistency. In a large dataset, this can make a huge difference in performance.

#### 3. What makes a database backup effective?
- [x] Being able to restore the backup data ✅
- [ ] Monitoring the backup for consistency
- [ ] Not exceeding limitations for the backup resources
- [ ] Scheduling the backup

> No backup is effective unless you can use it to restore your data. It is important to not just create backups, but to also regularly test the restoration process to ensure it works effectively.

#### 4. Which statement is true about the mysqldump utility?
- [ ] mysqldump is excellent for backing up large databases.
- [x] The mysqldump output is a human-readable text file with SQL statements. ✅
- [ ] mysqldump is fast and does not require locking tables.
- [ ] mysqldump is a standard way to create physical backups.

#### 5. What is the MySQL Enterprise Backup utility designed for?
- [ ] Create a snapshot of the MySQL storage medium
- [ ] Perform upgrades of MySQL systems
- [ ] Create Logical backup of MySQL systems
- [x] Create Physical backup of MySQL systems ✅

***

## MySQL Replication

#### 1. What is one requirement on the source to enable source-replica replication?
- [x] Source must have binary logging enabled. ✅
- [ ] Source must have its binary log format set to statement based.
- [ ] Source must have all tables use InnoDB storage engine only.
- [ ] Source must have the sql_require_primary_key variable set to on.

> The binary log contains "events" that describe database changes such as table creation operations or changes to table data. Binary logging must be enabled on a replication source so the record of data changes can be sent to the replicas.

#### 2. Which thread maintains an open connection to the source when the replica connects and is used to send the binary log contents from the source to a replica?
- [ ] SQL thread
- [x] I/0 binlog dump thread ✅
- [ ] Connection thread
- [ ] I/0 thread

> The source creates an I/O binlog dump thread to send the binary log contents to a replica when the replica connects. This thread can be identified in the output of SHOW PROCESSLIST on the source as the binlog dump thread.

#### 3. What uses the Relay Log?
- [x] Replica ✅
- [ ] Source
- [ ] Both Source and Replica
- [ ] Neither

> The relay log is written by the I/O thread and contains the transactions read from the replication source server's binary log. The relay log is stored on the replica and used by the replica. The transactions in the relay log are applied on the replica by the SQL thread.

#### 4. Which thread reads the relay log and executes the transactions that it contains on the replica?
- [ ] I/0 thread
- [ ] Connection thread
- [ ] I/0 binlog dump thread
- [x] SQL thread ✅

> The replica creates a SQL thread to read the relay log that is written by the replication I/O thread and execute the transactions contained in it.

#### 5. Which thread is responsible for taking a copy of the binary log events from the source and writing those to a relay log?
- [ ] SQL thread
- [ ] Connection thread
- [x] I/0 thread ✅
- [ ] I/0 binlog dump thread

***

## Enabling High Availability in MySQL

#### 1. Which two are NOT used when setting up MySQL InnoDB ReplicaSet?
- [x] MySQL Workbench ✅
- [ ] MySQL Router
- [x] MySQL Group Replication ✅
- [ ] MySQL Read Replica
- [ ] MySQL Shell

> When setting up a MySQL InnoDB ReplicaSet, MySQL Router and MySQL Shell are used. MySQL Shell provides the AdminAPI which allows you to easily deploy, configure, and administer the ReplicaSet, whereas MySQL Router provides transparent routing between your application and InnoDB ReplicaSet. MySQL Workbench and Group Replication are not used.

#### 2. Which MySQL component provides automatic failover when using InnoDB Cluster?
- [ ] MySQL Shell
- [x] MySQL Group Replication ✅
- [ ] MySQL Router
- [ ] MySQL Workbench

#### 3. Which MySQL component redirects application queries to available nodes in an InnoDB Cluster?
- [ ] MySQL Group Replication
- [x] MySQL Router ✅
- [ ] MySQL Shell
- [ ] MySQL Workbench

#### 4. What is the Recovery Point Objective (RPO) or data loss tolerance within a region when using MySQL InnoDB Cluster?
- [ ] Seconds to minutes
- [ ] Minutes to hours
- [x] Zero ✅
- [ ] Minutes

> MySQL InnoDB Cluster is made up of three MySQL instances: a primary instance, and two secondary instances. All data that you write to the primary instance is copied to the secondary instances using Group Replication. InnoDB Cluster guarantees if one instance fails, another takes over, with zero data loss and minimal downtime.

#### 5. Which MySQL component automates InnoDB Cluster creation and makes managing the Cluster easy?
- [ ] MySQL Workbench
- [x] MySQL Shell ✅
- [ ] MySQL Group Replication
- [ ] MySQL Router

> MySQL Shell uses AdminAPI which allows you to easily deploy, configure, and administer InnoDB Cluster, InnoDB ClusterSet, and InnoDB ReplicaSet.

***

## Monitoring MySQL

#### 1. What does the MySQL Performance Schema do?
- [ ] It creates indexes for the SQL code.
- [ ] It compresses the database for better underlying hardware management.
- [ ] It scales the MySQL database for better performance.
- [x] It provides statistics about your MySQL instance. ✅

> One important monitoring feature in MySQL is the Performance Schema. It’s a system database that provides statistics of how MySQL executes at a low level. The performance information belongs only to the specific instance, so it isn’t replicated to other systems.

#### 2. What can you do with MySQL in Oracle Enterprise Manager?
- [ ] Back up a MySQL database instance.
- [x] Monitor MySQL Performance. ✅
- [ ] Add extra security to the MySQL database.
- [ ] Create a MySQL InnoDB ReplicaSet.

> The Oracle Enterprise Manager tool is used to monitor the following MySQL activities: Performance, System availability, replication topology, InnoDB performance characteristics and locking, bad queries caught by the MySQL Enterprise firewall, and events that are raised by MySQL Enterprise Audit.

#### 3. Slow query log is used to capture long-running SQL statements. Which is NOT logged by default?
- [ ] Queries that use an index
- [x] Administrative statements ✅
- [ ] Queries that use a join operation
- [ ] SELECT statements

> By default, administrative statements are not logged, nor are queries that do not use indexes for lookups. This behavior can be changed using log_slow_admin_statements and log_queries_not_using_indexes.

#### 4. Which part of the database is the highest source of Database Performance Problems?
- [ ] The overall size of retained data in the active dataset
- [ ] The underlying hardware
- [x] The SQL, index, and Schema group ✅
- [ ] The database structure

> 90% of Performance Problems come from the SQL, index, and Schema group. Poor SQL query design or incorrect use of indexes can significantly impact database performance.

#### 5. Which MySQL schema has its own dedicated storage engine?
- [ ] mysal schema
- [ ] sakila Schema
- [ ] world schema
- [x] Performance schema ✅

> It is the Performance schema that has its own dedicated engine called PERFORMANCE_SCHEMA to store performance data, whereas mysql, world, and sakila schemas use the default InnoDB storage engine.

***

## HeatWave

#### 1. Which machine learning technique is NOT supported by HeatWave ML?
- [ ] Recommendation Systems
- [ ] Forecasting
- [ ] Anomaly Detection
- [x] Clustering ✅

> HeatWave ML currently supports Anomaly Detection, Classification, Forecasting, Recommendation Systems, and Regression techniques. Clustering is a technique that looks for similar data points and groups them together based on certain features. Clustering is not supported by HeatWave ML.

#### 2. Which action can you perform using the HeatWave service web-based console?
- [ ] Connect to MySQL Workbench.
- [ ] Write SQL code.
- [x] Deploy your instances and manage their backups. ✅
- [ ] Install MySQL Shell.

> The HeatWave service is a fully-managed MySQL. Through the web-based console, you can deploy your instances and manage their backups, enable high availability, resize your instances, create read replicas and perform many common administration tasks without writing a line of SQL.

#### 3. From which cloud service can you use HeatWave?
- [ ] Google Cloud Platform (GCP)
- [ ] Salesforce Cloud
- [x] Amazon Web Services (AWS) ✅
- [ ] IBM Cloud

> HeatWave is not just available in Oracle Cloud Infrastructure. You can use HeatWave from your applications in Amazon Web Services and Microsoft Azure too, and at a great price.

#### 4. Which HeatWave feature allows you to query data from Object Storage?
- [ ] Read Replicas
- [ ] High Availability
- [x] Lakehouse ✅
- [ ] Autopilot

> HeatWave Lakehouse enables query processing on data resident in Object Storage. The file formats supported by this feature are Avro, CSV, JSON, and Parquet.

#### 5. Which database platform does HeatWave use to store OLTP data?
- [x] MySQL ✅
- [ ] TimesTen In-Memory Database
- [ ] Berkley DB
- [ ] Oracle Database

***
