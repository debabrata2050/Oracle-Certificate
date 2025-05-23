# MySQL 8.4: Essentials

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

#### 2. How often are MySQL Innovation versions released?
- [x] Every quarter ✅
- [ ] Every two years
- [ ] Every year
- [ ] Every month

#### 3. Which installation method requires that you manually configure the service user?
- [ ] yum packages
- [ ] MySQL Installer
- [ ] RPM packages
- [x] binary archive ✅

#### 4. Which permissions are required for the MySQL service user?
- [ ] Shell privileges
- [ ] System privileges
- [ ] Root privileges
- [x] Data directory privileges ✅

#### 5. Which statement is true about upgrades?
- [ ] You must reinstall MySQL completely and restore from backup when upgrading from Community Edition to Enterprise Edition.
- [ ] The Upgrade Checker utility is only available in Enterprise Edition.
- [x] You can upgrade MySQL while the server is offline by replacing the binaries with new versions. ✅
- [ ] You can upgrade MySQL while the server is running.

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

#### 5. Which statement is true about PRIMARY indexes?
- [ ] You can have multiple rows with the same value in the PRIMARY index.
- [x] PRIMARY index values are replicated to every secondary index. ✅
- [ ] They speed up insert operations.
- [ ] You can have multiple PRIMARY indexes on a table.

***
