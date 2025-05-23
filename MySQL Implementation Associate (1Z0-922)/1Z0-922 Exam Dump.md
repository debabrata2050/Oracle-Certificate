# Exam 1Z0-922: MySQL Implementation Associate

#### Q. Which statement would you use to add a role in MySQL?
- [ ] SET ROLE
- [ ] MAKE ROLE
- [x] CREATE ROLE ✅
- [ ] GRANT ROLE

#### Q. Which uniquely defines each user account identity in MySQL?
- [x] Username and host ✅
- [ ] Username
- [ ] Usemame, host, and password
- [ ] Username and password

#### Q. What statement allows you to assign a password to a MySQL user account?
- [ ] GRANT PASSWORD
- [ ] ASSIGN PASSWORD
- [ ] NEW PASSWORD
- [x] SET PASSWORD ✅
- [ ] CREATE PASSWORD

#### Q. What type of backups do mysqldump and MySQL Shell take?
- [ ] Operating System
- [ ] Snapshot
- [x] Logical ✅
- [ ] Physical

#### Q. Your customer has a 75 GB MySOL database. They are using mysqldump to take a backup of their database, which is taking the five hours to complete.
#### What can your customer do to decrease the amount of time it takes to back up their database?
- [ ] Back up the database by using mysqldump to send the backup to another server
- [ ] Back up the database to a local drive
- [ ] Use MySQL Enterprise Monitor
- [x] Use MySQL Enterprise Backup ✅

#### Q. Which log file is used to perform a Point in time Recovery?
- [ ] Undo log
- [x] Binary log ✅
- [ ] Audit log
- [ ] Redo log

#### Q. Which data type would you use for a column to store large chunks of binary data such as images and audio files?
- [x] BLOB ✅
- [ ] VARCHAR
- [ ] BIT
- [ ] JSON

#### Q. When creating a table, which data type would you use for a column that contains only whole numbers (a number that is not a fraction)?
- [x] INT ✅
- [ ] DECIMAL(5, 2)
- [ ] FLOAT
- [ ] BIGNUM

#### Q. By using MySQL replication, data can be replicated from source to replica.
#### What are two advantages of MySQL replication?
- [ ] In-memory cache
- [ ] Automatic backup
- [x] Scale out ✅
- [x] Analytics ✅
- [ ] Data compression

#### Q. The replica connects to the source and asks for updated records.
#### What command was issued for this to happen?
- [ ] REPLICA RUN
- [x] START REPLICA ✅
- [ ] START RUN REPLICA
- [ ] RUN REPLICA
- [ ] REPLICA START

#### Q. What is the benefit of using MySQL Enterprise Thread Pool?
- [ ] Observability
- [ ] Monitoring
- [ ] Availability
- [x] Scalability ✅

#### Q. Which MySQL Enterprise Edition component or plug-in replaces real values with substitutes?
- [ ] MySQL Enterprise Audit
- [x] MySQL Enterprise Masking ✅
- [ ] MySQL Enterprise Authentication
- [ ] MySQL Transparent Data Encryption

#### Q. Which MySQL Enterprise Security tool allows DBAs to track user activities such as Who, What, When, How, Status, From Where, DB version, OS version, and options?
- [ ] MySQL Enterprise Transparent Data Encryption (TDE)
- [x] MySQL Enterprise Audit ✅
- [ ] MySQL Enterprise Firewall
- [ ] MySQL Enterprise Monitor

#### Q. Which three languages are supported by MySQL Shell?
- [x] JavaScript ✅
- [x] Python ✅
- [ ] Perl
- [ ] Java
- [ ] PHP
- [x] SQL ✅

#### Q. Which three operating systems are supported by MySQL?
- [x] macOS ✅
- [x] Windows ✅
- [ ] Android
- [ ] iOS
- [x] Linux ✅

#### Q. Where would you look to find easy-to-understand views that contain information about IO hot spots, locking, and costly SQL statements?
- [x] sys schema ✅
- [ ] Performance schema
- [ ] mysql schema
- [ ] Information schema

#### Q. Which schema provides runtime statistics to monitor MySQL server execution at a low level?
- [ ] sys schema
- [ ] mysql schema
- [ ] Information schema
- [x] Performance schema ✅

#### Q. Which MySQL storage engine is fully ACID compliant and also the default when creating a table?
- [ ] Memory
- [x] InnoDB ✅
- [ ] MyISAM
- [ ] Archive

#### Q. Which backup method allows you to back up only the data that has changed since the last FULL backup?
- [ ] Full
- [ ] Incremental
- [ ] Optimistic
- [x] Differential ✅
- [ ] Partial

#### Q. Which three components are part of the core MySQL database architecture?
- [x] Optimizer ✅
- [ ] Disk Parity/RAID
- [x] Parser ✅
- [ ] mysqldump
- [x] Storage Engine ✅
- [ ] MySQL Router

#### Q. How would you replicate between two InnoDB Clusters?
- [ ] Set up MySQL Replication.
- [ ] Set up MySQL InnoDB Read Replicas.
- [x] Set up MySQL InnoDB ClusterSet. ✅
- [ ] Set up MySQL ReplicaSet.

#### Q. Which three components can MySQL InnoDB Cluster use to achieve database high availability?
- [ ] MySQL online hot backup, to keep data consistent and always ready to be used
- [x] MySQL Servers with Group Replication, to replicate data to all members of the cluster ✅
- [x] MySQL Shell, to create and administer InnoDB Cluster using the built-in AdminAPI ✅
- [x] MySQL Router, to ensure client requests are load balanced and routed to the correct server ✅
- [ ] MySQL X Plugin, to enable MySQL to use the X Protocol to speed up and monitor data replication
