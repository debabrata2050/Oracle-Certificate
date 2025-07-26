# Oracle Exam 1Z0-909: MySQL 8.0 Database Developer Dump

#### Q. Your program which uses a MySQL connector receives this error: Client does not support authentication protocol requested by server. The account running the program uses caching_sha2_password.
Which two resolve this conflict?
- [x] Upgrade the connector to a version that supports caching_sha2_password. ✅
- [ ] Place this in the root directory of your shell account:  
      [mysqld]  
      require_secure_transport-OFF
- [ ] Disable TLS/SSL authentication.
- [x] Change the user account to use mysql_native_password. ✅
- [ ] Use blank RSA or SSL certificates.

#### Q. A MySQL server has been provided self signed certificates by your corporate Certificate Authority.  
The server is only accessible from your private network and all name resolution is provided by a private DNS service.  
Which two statements are true?
- [ ] Self signed certificates provide more trust than those signed by a trusted CA.
- [ ] Public trusted CA certificates are more trustworthy than those signed by the corporate CA.
- [x] Public trusted CA certificates and those signed by the corporate CA can provide the same level of technical security. ✅
- [ ] Public trusted CA certificates are more technically secure than those signed by the corporate CA.
- [x] Public trusted CA certificates and those signed by the corporate CA provide the same level of trust in the destination host ✅

#### Q. The employee table includes these columns:
**e_id INT, e_name VARCHAR(45), dept_id INT, salary INT**  
You must create a stored function, getMaxSalary (), which returns the maximum salary paid for a given department id.
Which statement will create the function?
- [ ] CREATE FUNCTION getMaxSalary (v_dept_id INT) RETURNS INT  
DETERMINISTIC  
BEGIN  
DECLARE msalary INT;  
SELECT MAX(salary) INTO msalary FROM employee WHERE dept_id = v_dept_id;  
RETURN msalary;  
END  
- [ ] CREATE FUNCTION getMaxSalary (v_dept_id INT) RETURNS INT  
DECLARE msalary INT;  
BEGIN  
SELECT MAX(salary) INTO msalary FROM employee WHERE dept_id = v_dept_id;  
getMaxSalary:= msalary;  
RETURN;  
END  
- [x] CREATE FUNCTION getMaxSalary (v_dept_id INT) RETURNS INT  
DETERMINISTIC  
BEGIN  
DECLARE msalary INT;  
USE schemaName;  
SELECT MAX(salary) INTO msalary FROM employee WHERE dept_id = v_dept_id;  
RETURN msalary;  
END ✅
- [ ] CREATE FUNCTION getMaxSalary(v_dept_id INT) RETURNS CHAR(50)  
BEGIN  
SELECT MAX(salary) INTO @m FROM employee WHERE dept_id = v_dept_id;  
RETURN m;  
END

#### Q. Examine this statement:
```sql
DELIMITER //
CREATE PROCEDURE get_num_empO            #line 1 
BEGIN                                    #line 2 
    INSERT INTO employee (emp_id, emp_name) VALUES (102, 'John');  #line 3 
    SELECT COUNT(*) INTO @m FROM employee;           #line 4 
END;
//
```
What is required to create this procedure successfully?
- [ ] user who creates the procedure needing the CREATE and EXECUTE privileges
- [x] user who creates the procedure needing the CREATE ROUTINE privilege ✅
- [ ] inserting COMMIT: SET @m :- 0; before line 4
- [ ] inserting DEFINER 'username'@'localhost' clause into the CREATE PROCEDURE statement
- [ ] inserting USE `<database>`; before line 3

#### Q. Which two statements would generate this bar graph?

| Name    | Gender | Sport  | GPA_Graph                                                                 |
|---------|--------|--------|----------------------------------------------------------------------------|
| Elaine  | F      | Netball| ################################################ |
| Frank   | M      | Polo   | ############################################### |
| Charles | M      | Polo   | ############################################# |
| Isabel  | F      | Netball| ############################################ |
| Julie   | F      | Netball| ########################################### |
| Harriet | F      | Hockey | ###################################### |
| Larry   | M      | Hockey | ################################### |
| David   | M      | NULL   | ################################ |


- [ ] SELECT Name, Gender, Sport, CONCAT('#', GPA*10) AS GPA_Graph  
FROM players ORDER BY GPA DESC;
- [ ] SELECT Name, Gender, Sport, LENGTH (GPA*10, '#') AS GPA_Graph  
FROM players ORDER BY GPA DESC:
- [x] SELECT Name, Gender, Sport, RPAD(", GPA*10, ") AS GPA_Graph  
FROM players ORDER BY GPA DESC; ✅
- [ ] SELECT Name, Gender, Sport, CHAR LENGTH('#', GPA*10) AS GPA_Graph  
FROM players ORDER BY GPA DESC;
- [x] SELECT Name, Gender, Sport, REPEAT('#', GPA*10) AS GPA_Graph  
FROM players ORDER BY GPA DESC; ✅

#### Q. Examine the table's contents
```sql
mysql> SELECT id, last_login FROM login_history LIMIT 5;
+----+------------+
| id | last_login |
+----+------------+
|  1 | 2019-05-02 |
|  2 | NULL       |
|  3 | NULL       |
|  4 | 2019-05-06 |
|  5 | 2020-09-02 |
+----+------------+
5 rows in set (0.00 sec)

```
You must determine the number of non-null dates in the last_ login column.  
Which function call will satisfy this requirement?
- [ ] FOUND_ROWS()
- [x] COUNT(last_login) ✅
- [ ] ROW_COUNT()
- [ ] COUNT(*)
- [ ] SUM(last_login)
- [ ] DISTINCT(last_login)

#### Q. Examine this statement:
```sql
SELECT c.Region,
    COUNT (DISTINCT cl.language) AS NumLanguages,
    GROUP_CONCAT (DISTINCT cl.language) AS LanguagesSpoken
FROM country AS c, countrylanguage AS cl
WHERE c.Code = cl.CountryCode
GROUP BY c.Region
HAVING NumLanguages < 10;
```
Which two are true?
- [x] It returns a list of languages spoken for each region in the report. ✅
- [ ] It returns an error as DISTINCT is not allowed in the GROUP_CONCAT function.
- [x] It limits the regions to ones that speak less than 10 languages. ✅
- [ ] It creates a list of 10 languages that are spoken across all regions.
- [ ] It returns an error if only_ full_ group_ by is enabled in sql_ mode.

#### Q. Examine this statement:
```sql
SHOW CREATE VIEW cityview\G;
************************** 1. row ****************************
View: cityview
Create View: CREATE ALGORITHM=TEMPTABLE DEFINER='root'@'localhost'
SQL SECURITY DEFINER VIEW `cityview`
AS
select `city`.`Name` AS `name`, `city`.`Population` AS `Population`
from `city`
character_set_client: utf8mb4
collation_connection: utf8mb4_0900_a
Now examine this statement executed as root and output:
UPDATE cityview SET Population=2643585 WHERE Name="Roma";
ERROR: 1288 (HY000): The target table cityview of the UPDATE is not updatable
```
What must precede the UPDATE to avoid this error?
- [ ] SET autocommit=1;
- [ ] START TRANSACTION;
- [ ] UNLOCK TABLES;
- [x] ALTER ALGORITHM-MERGE VIEW cityview AS SELECT Name, Population FROM city; ✅
- [ ] SET optimizer_switch='derived_merge=on';

#### Q. Examine the structure of the emp table:
```sql
+--------+--------------+------+-----+---------+-----------------+
| Field  | Type         | Null | Key | Default | Extra           |
+--------+--------------+------+-----+---------+-----------------+
| id     | int(11)      | NO   | PRI | NULL    | auto_increment  |
| name   | varchar(25)  | YES  |     | NULL    |                 |
| SALARY | int(11)      | YES  |     | NULL    |                 |
| email  | varchar(25)  | NO   |     | NULL    |                 |
+--------+--------------+------+-----+---------+-----------------+
```
Examine the structure of emp_vul view that is based on the emp table:
```sql
+--------+-------------+------+-----+---------+-------+
| Field  | Type        | Null | Key | Default | Extra |
+--------+-------------+------+-----+---------+-------+
| name   | varchar(25) | YES  |     | NULL    |       |
| salary | int(11)     | YES  |     | NULL    |       |
+--------+-------------+------+-----+---------+-------+
```
Now, examine this statement:  
```mysql> INSERT INTO emp_vul VALUES ('John', 10000);```  
What is true about executing the statement?
- [ ] It returns an error because the id column is not included in the view definition.
- [ ] It inserts a row in the emp table.
- [x] It returns an error because the email column has no default value. ✅
- [ ] It inserts a row in the view only.

#### Q. Examine the structure of the emp table:
```sql
+--------+--------------+------+-----+---------+-----------------+
| Field  | Type         | Null | Key | Default | Extra           |
+--------+--------------+------+-----+---------+-----------------+
| id     | int(11)      | NO   | PRI | NULL    | auto_increment  |
| name   | varchar(25)  | YES  |     | NULL    |                 |
| SALARY | int(11)      | YES  |     | NULL    |                 |
| email  | varchar(25)  | YES  |     | NULL    |                 |
+--------+--------------+------+-----+---------+-----------------+
```
Examine the structure of emp_vul view that is based on the emp table:
```sql
+--------+-------------+------+-----+---------+-------+
| Field  | Type        | Null | Key | Default | Extra |
+--------+-------------+------+-----+---------+-------+
| name   | varchar(25) | YES  |     | NULL    |       |
| salary | int(11)     | YES  |     | NULL    |       |
+--------+-------------+------+-----+---------+-------+
```
Now, examine this statement:  
```sql
mysql> INSERT INTO emp_vul VALUES ('Alice', 20000);
```  
What is true about executing the statement?
- [ ] It returns an error because the PRIMARY KEY column is not selected for the view definition.
- [ ] It inserts a row in the view only.
- [ ] It returns an error because an INSERT operation is not allowed on views.
- [x] It inserts a row in the emp table. ✅

#### Q. Examine this statement and output
```sql
CREATE TABLE geom (g GEOMETRY NOT NULL, SPATIAL INDEX(g));
Query OK, 0 rows affected, 1 warning (0.01 sec)
```
An attempt is made to add an SRID attribute to the column using the statement:
```sql
ALTER TABLE geom MODIFY COLUMN g geometry NOT NULL SRID 0;
```
Which is true?
- [ ] Execution succeeds with a warning.
- [ ] An error is generated because SRID 0 is an invalid identifier value.
- [x] An error is generated because the index prevents changes to the column. ✅
- [ ] Execution succeeds and allows the use of the index by the optimizer

#### Q. Examine this statement which executes successfully:
```sql
 SET @r:= 2;
 ```  
Which query updates the value of @r to 0?
- [ ] SELECT 'Car' LIKE 'Ca?' INTO @r;
- [x] SELECT STRCMP('Car', 'Ca?") >= 0 INTO @r; ✅
- [ ] SELECT 'Car' REGEXP(Ca?") >= 0 INTO @r;
- [ ] SELECT 'Car' RLIKE 'Ca?' INTO @r;

#### Q. Examine this statement which executes successfully:
```sql
CREATE TABLE band (
`song` varchar(50) NOT NULL,
`year` int NOT NULL) 
ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE utf8mb4_0900_ai_ci;
SELECT * FROM band;
```
```sql
+---------------------------+------+
| song                      | year |
+---------------------------+------+
| Come Together             | 1969 |
| The Long and Winding Road | 1970 |
| The Fool on the Hill      | 1967 |
| Hey Jude                  | 1968 |
| Here Comes the Sun        | 1969 |
| Love Me Do                | 1963 |
+---------------------------+------+
```
Now, examine this desired output:
```sql
+----------------------+------+
| song                 | year |
+----------------------+------+
| The Fool on the Hill | 1967 |
+----------------------+------+
```

- [ ] SELECT * FROM band  
WHERE song RLIKE 'the' COLLATE latini_general_cs  
AND song RLIKE '^the' COLLATE latini_general_ci;  
- [x] SELECT * FROM band  
WHERE song RLIKE 'the' COLLATE utf8mb4_0900_as_cs  
AND song RLIKE '^the' COLLATE utf8mb4_0900_ai_ci; ✅
- [ ] SELECT * FROM band  
WHERE song RLIKE '^the'  
AND SUBSTRING(song, 4) RLIKE "the" COLLATE utf8mb4_0900 _as _es;  
- [ ] SELECT * FROM band  
WHERE song RLIKE 'the"  
AND song RLIKE "the';  
- [ ] SELECT * FROM band  
WHERE song RLIKE 'the' COLLATE utf8mb4_0900 _ai _ci  
AND song RLIKE "the' COLLATE utf8mb4_0900 _ai ci;

#### Q. Examine these statements which execute successfully:
```sql
CREATE TABLE 'city' (
'ID' int NOT NULL AUTO INCREMENT,
'Name' char(35) NOT NULL DEFAULT,
'CountryCode' char(3) NOT NULL DEFAULT,
PRIMARY KEY ('ID')
) ENGINE=InnoDB;

CREATE TABLE 'country' (
'Code' char (3) NOT NULL DEFAULT,
'Name' char(52) NOT NULL DEFAULT,
PRIMARY KEY ('Code')
) ENGINE=InnoDB;
```

city and country contain thousands of rows.
Now, examine this statement which executes successfully:
```sql
SELECT city.Name, country.Name
FROM city, country
WHERE city.CountryCode=country.Code AND city.Name="Roma";
```
Which two are true?
- [x] Execution plan will be improved by creating a composite index (Name, CountryCode) on city table. ✅
- [ ] Execution plan performs two full table scans.
- [ ] Execution plan uses a temporary table.
- [x] Execution plan performs at most one full table scan. ✅
- [ ] Execution plan will be improved by creating an index (Name) on country table.

#### Q. Examine this statement:
```sql
DECLARE not_found CONDITION FOR SQLSTATE '02000';
```
In which two statements can not_found be used?
- [x] In a LEAVE statement to exit a loop. ✅
- [ ] In a SIGNAL statement.
- [ ] In a WHILE loop.
- [ ] In a handler declaration.
- [x] In an IF statement. ✅

#### Q. Examine this command which executes successfully.
```sql
CREATE FUNCTION grade (score INT) RETURNS CHAR NO SQL
    BEGIN
        DECLARE grade CHAR;
        IF score > 85 THEN
            SET grade = 'A';
        ELSE IF Score > 65 THEN
            SET grade = 'B';
        ELSE IF score > 50 THEN
            SET grade = 'C';
        ELSE IF score > 40 THEN
            SET grade = 'D';
        END IF;
        RETURN grade;
    END
```

Which two display the correct output for the given statement?
- [x] SELECT grade(30), grade(40), grade (50);  
```sql
+-----------+-----------+-----------+
| grade(30) | grade(40) | grade(50) |
+-----------+-----------+-----------+
|           |     D     |     C     |
+-----------+-----------+-----------+
```
- [ ] SELECT grade(65), grade(75), grade (85);  
```sql
+-----------+-----------+-----------+
| grade(65) | grade(75) | grade(85) |
+-----------+-----------+-----------+
|     C     |     B     |     B     |
+-----------+-----------+-----------+
```
- [x] SELECT grade(80), grade(85), grade (90);  
```sql
+-----------+-----------+-----------+
| grade(80) | grade(85) | grade(90) |
+-----------+-----------+-----------+
|     B     |     A     |     A     |
+-----------+-----------+-----------+
```
- [ ] SELECT grade(40), grade(50), grade (60);  
```sql
+-----------+-----------+-----------+
| grade(40) | grade(50) | grade(60) |
+-----------+-----------+-----------+
|     D     |     C     |     C     |
+-----------+-----------+-----------+
```
- [ ] SELECT grade(-1), grade(0), grade(1000);  
```sql
+-----------+-----------+-------------+
| grade(-1) | grade(0)  | grade(1000) |
+-----------+-----------+-------------+
|  NULL     |  NULL     |     A       |
+-----------+-----------+-------------+
```

#### Q. The variables c and d are declared as integer types.
Examine these initialization statements with placeholder value `<pl>`, which execute successfully.  
SET c = <pl>;  
SET d = 0;  
Now, examine this loop which executes successfully.
```sql
REPEAT
SET d=d +1
SET c = c + 1;
UNTIL c > 3
END REPEAT;
```
Which loop is equivalent to this loop for all valid values of <pl>?
- [ ] 
```sql
WHILE c <= 3 DO
SET d = d + 1 :
SET c = c + 1 :
END WHILE;
```
- [ ]  
```sql
b: LOOP
SET d = d + 1 :
SET c = c + 1:
IF c > 3 THEN LEAVE b; END IF;
END LOOP b;
```
- [x] ✅
```sql
 b: LOOP
IF c > 3 THEN LEAVE b; END IF;
SET d = d + 1:
SET c - c + 1;
END LOOP b;  
```
- [ ] 
```sql
WHILE C < 3 DO
SET d = d + 1:
SET c = c + 1:
END WHILE;
```

#### Q. You require only the owner and type fields for documents whose owner is Sven, that exist in the pets collection.
Which two will do this?
- [x] db.pets. find("owner = owner"). fields("owner", "type").bind("owner", "Sven") ✅
- [ ] db.pets.find("owner = Sven")
- [ ] db.pets.select(["owner", "type"]).where ("owner - 'Sven' ")
- [x] db.pets.select(["owner", "type"]).where("owner = name").bind("name", "Sven") ✅
- [ ] db.pets. find("owner - 'Sven"") fields("owner", "type")


#### Q. Examine this table definition:
```sql
+----------------+--------------+------+-----+---------+--------------------+
| Field          | Type         | Null | Key | Default | Extra              |
+----------------+--------------+------+-----+---------+--------------------+
| doc            | json         | YES  |     | NULL    |                    |
| _id            | varbinary(32)| NO   | PRI | NULL    | STORED GENERATED   |
| _json_schema   | json         | YES  |     | NULL    | VIRTUAL GENERATED  |
+----------------+--------------+------+-----+---------+--------------------+
```
The table must always remain a valid document store collection.  
What restriction does this impose on any added column?
- [ ] The column must be a GENERATED column referencing any attribute of doc.
- [x] The column must be a GENERATED column referencing only an existing attribute of doc. ✅
- [ ] The column must be used in a UNIQUE constraint.
- [ ] The column must have a DEFAULT value.

#### Q. Examine this statement which executes successfully:
```sql
CREATE TABLE work (
'job_no' INT NOT NULL,
'data' JSON NOT NULL,
'name' VARCHAR(30) GENERATED ALWAYS AS (JSON_EXTRACT('data', '$.first_name')) VIRTUAL, PRIMARY KEY ('job_no')
) ENGINE=INNODB;
```
The table is populated with a range of values including jobs for Robert, John, and Katie.
Now, examine this statement and output:
```sql
SELECT job_no, name
FROM work
WHERE name = 'Robert'
Empty set (0.0007 sec)
```
Why is an empty result set returned?
- [ ] The virtual values in the name column must be accessed using functions.
- [ ] The JSON_EXTRACT O function requires a length value that matches the field length in the schema.
- [x] The JSON datatype cannot be used in VIRTUAL columns. ✅
- [ ] The SELECT requires JSON_UNQUOTE 0 in the WHERE clause.
- [ ] Table statistics must be updated to generate values for the name column.

#### Q. Examine these statements and output:
```java
try {
    con = DriverManager.getConnection("jdbc:mysql://127.0.0.1:8019?serverTimezone=UTC",
    "root",
    "Oraclel*");
    Statement statement = con.createStatement();
    ResultSet rSet = statement.executeQuery("SELECT * FROM city WHERE name LIKE 'Ro%';");
    rSet.last();
    System.out.println("Rows: "+ rSet.getRow());
}
catch (SQLException ex) {
    System.ouf.println("Exception: " + ex.toString0);
}
Exception: java.sqlSQLException: No database selected
```
The city table belongs to the world database.
Which two are true?
- [ ] The SELECT statement was executed correctly and returned zero rows.
- [ ] The connection string sets the default database to mysql.
- [x] The desired database can be specified with con.setCatalog("world"): ✅
- [ ] The database cannot be specified in the SELECT statement.
- [ ] Connection establishment to the database failed.
- [x] Default database can be specified with :getConnection ("jdbc:mysql://127.0.0.1:8019/world?serverTimezone=UTC&user=root&password=Oracle1*"); ✅

#### Q. Examine the content of the employee table:
```sql
+--------+----------+-----+
| emp_id | empname  | age |
+--------+----------+-----+
|   1    | Kathy    | 24  |
|   2    | Liril    | 25  |
+--------+----------+-----+
```
Now examine this PHP script:
```php
$dsn = "mysql:host=localhost;dbname=dbname;charset=utf8mb4";
## --- insert here--
try {
    $pdo = new PDO (Sdsn, 'username', 'password', Soptions);
} catch (PDOException $e) {
throw new PDOException ($e -> getMessage(), (int)$e -> getCode());
}
$stmt = $pdo->query('SELECT * FROM employee');
while ($row = $stmt-> fetch()) {
echo nl2br($row[1]." 's age is: ".$row['age']."\n");
}
```
Finally examine this desired output:  
Kathy's age is: 24  
Liril's age is: 25  
Which can be inserted to display as expected?
- [ ] $options = [PDO::ATTR_DEFAULT_FETCH_MODE => PDO:: FETCH_ASSOC];
- [x] $options = [PDO::ATTR_DEFAULT_FETCH_MODE => PDO:: FETCH_BOTH]; ✅
- [ ] $options = [PDO::ATTR_DEFAULT_FETCH_MODE => PDO:: FETCH_CLASS];
- [ ] $options = [PDO::ATTR_DEFAULT_FETCH_MODE => PDO:: PDO::FETCH_OBJ];

#### Q. Which two are true about event scheduling?
- [x] Events require the events data dictionary table in mysql system database. ✅
- [x] event_scheduler variable can be disabled at runtime. ✅
- [ ] SHOW EVENTS; lists all the events of all databases.
- [ ] An event can only be dropped by its DEFINER.
- [ ] An event is associated with a table, not a schema.

#### Q. A session has been established using the Java connector and successfully queried data.  
What method optimizes resource usage for unused connections?
- [ ] Let the connection pool class handle closing the connection object.
- [ ] Let the Java garbage collector close the unused connection object.
- [x] Check if a connection exists and call the close () method of the connection object. ✅
- [ ] Allow the session to time out and MySQL Server will close the connection

#### Q. A server hosts MySQL Server and Apache Webserver supporting a PHP/PDO based application.  
The application must be migrated from PHP to their Java application server on another host. The MySQL instance remains on the original host.  
Examine the PDO connection string used in the existing application:
```
mysql:host-localhost;dbname=sales;unix_socket=/var/run/mysql.sock
```
Which two prevent Java from using the Unix socket?
- [x] The socket can only be accessed from the local host. ✅
- [x] The socket is not implemented in Connector/J driver. ✅
- [ ] Java treats the socket file as insecure.
- [ ] The X Dev API protocol must be enabled to use sockets in Connector/J driver.
- [ ] socket is a reserved word in Java.

#### Q. Examine this partial Python code which executes successfully.
```python
conn = mysql.connector.conn(**conn_params)
cursor = conn.cursor(raw=True)
```
What is true about this code?
- [ ] The result is returned asynchronously.
- [ ] It converts MySQL DATETIME to Python datetime values.
- [x] It skips conversions from SQL to native formatted data types. ✅
- [ ] The result is returned as a raw BLOB.
- [ ] The result is returned in a simple tabular form.

#### Q. Examine this code and output:
```python
try:
    conn.autocommit = False
        cursor = conn.cursor
        cursor.execute("INSERT INTO band (song, year) VALUES ('From Me to You', 1964)")
except mysql.connector. Error as error:
        print ("Unable to insert the record, error is:")
        print (error)
try:
    cursor execute ("UPDATE band SET year= 1969 WHERE song = 'Come Together';")
except mysql.connector. Error as error:
        print ("Unable to update the record, error is:")
        print (error)
try:
    conn.commit()
except mysql.connector. Error as error2:
    print (error2)
    Unable to update the record, error is:
    1205 (HY000): Lock wait timeout exceeded; try restarting transaction
```
MySQL Server is configured with:  
innodb_rollback_on timeout=OFF  
Which two are true?
- [ ] The transaction is committed.
- [x] The transaction never started. ✅
- [x] Only the INSERT statement completes successfully. ✅
- [ ] Both statements complete successfully
- [ ] The transaction is rolled back.

#### Q. Examine this statement that executes successfully.
```sql
SELECT c.firstname, c.lastname, o.order_number
FROM customers c LEFT OUTER JOIN orders o USING (customer number)
ORDER BY c.customer number;
```
Which query will return the same result?
- [ ]  
```sql
SELECT c.firstname, c.lastname, o.order_number
FROM orders o INNER JOIN customers c ON c.customer_number = o.customer_number
ORDER BY c.customer_number;
```
- [ ]  
```sql
SELECT c.firstname, c.lastname, o.order_number
FROM customers c OUTER JOIN orders o ON c.customer_number = o.customer_number
ORDER BY c.customer_number;
```
- [ ]  
```sql
SELECT c.firstname, c.lastname, o.order_number
FROM orders o, customers c WHERE c.customer_number = o.customer_number
ORDER BY c.customer_number;
```
- [ ]   ✅
```sql
SELECT c.firstname, c.lastname, o.order_number
FROM orders o RIGHT OUTER JOIN customers c ON c.customer_number = o.customer_number
ORDER BY c.customer_number;
```

#### Q. You must write a statement that combines the first_name and last_name columns from the employees table as "last_name, first_name."  
Which two statements will do this?
- [ ] SELECT GROUP_CONCAT (last_name, first_name) FROM employees;
- [ ] SELECT last_name + ',' + first_name FROM employees;
- [x] SELECT CONCAT_WS(',', last_name, first_name) FROM employees; ✅
- [x] SELECT CONCAT (last_ name,',', first _name) FROM employees; ✅
- [ ] SELECT (last _name, ',', first_name) FROM employees;

#### Q. Examine this statement which you executed and its output:
```sql
SELECT ename, esalary, ebonus
FROM employees;
```
```sql
+------------------------+-------------+------------+
| ename                  | esalary     | ebonus     |
+------------------------+-------------+------------+
| Duangkaew Piveteau     | 158526.0000 | 23109.0000 |
| Mary Sluis             | 154070.0000 | 7181.0000  |
| Patricio Bridgland     | 94771.0000  | 23578.0000 |
| Eberhardt Terkki       | 91648.0000  | 8346.0000  |
| Berni Genin            | 113928.0000 | 27998.0000 |
| Guoxiang Nooteboom     | 94698.0000  | 26954.0000 |
| Kazuhito Cappelletti   | 71703.0000  | 20777.0000 |
| Cristinel Bouloucos    | 154424.0000 | 22021.0000 |
| Kazuhide Peha          | 77013.0000  | NULL       |
| Lillian Haddadi        | 141791.0000 | NULL       |
| Mayuko Warwick         | 137916.0000 | NULL       |
+------------------------+-------------+------------+
```
You must return the ename and the sum of the esalary and ebonus as etotal_pay for all employees.  
Which will return the desired result?
- [x] SELECT ename, (esalary + COALESCE (ebonus, 0.0000)) AS etotal_pay FROM employees; ✅
- [ ] SELECT ename, (esalary + ebonus) AS etotal_pay FROM employees;
- [ ] SELECT ename, (esalary + ebonus) AS etotal_pay FROM employees WHERE ebonus IS NOT NULL ;
- [ ] SELECT ename, SUM(esalary + ebonus) AS etotal_pay FROM employees;
- [ ] SELECT ename, SUM(esalary + ebonus) AS etotal_pay FROM employees GROUP BY ename;

#### Q. The collection col contains all episodes for all seasons for a TV show.  
Examine this document which has an example of the details for each episode:
```json
{
"_id": "00005cbee2d10000000000000001",
"name": "Days Gone Bye",
"number": 1,
"season": 1,
"airdate": "2010-10-31",
"airtime": "22:00",
"runtime": 60
}
```
Which query returns all episode names from the first season?
- [x] SELECT doc->>"$.name" FROM col WHERE doc->>"$.season" = "1"; ✅
- [ ] SELECT doc-> "$.name" FROM col WHERE doc->"$.season" = "1";
- [ ] SELECT name FROM col WHERE season = 1;
- [ ] SELECT "$.name" FROM col WHERE "$.season" = "1";

#### Q. Examine this statement which produces one row:
```sql
mysql> SELECT JSON_PRETTY (product) FROM fshop;
{"name": "orange",
"varieties":
[
    {"VarietyName":"clementine",
    "Origin": ["PA", "BU"]},
    {"VarietyName": "tangerine",
    "Origin": ["CH", "JP"]}
]
}
```
Now, examine this statement:
```sql
SELECT JSON_ TYPE (product-> "S.varieties")
FROM fshop;
```
Which output will be returned?
- [ ] STRING
- [ ] ARRAY
- [ ] OBJECT
- [x] NULL ✅
- [ ] BLOB

#### Q. Examine this statement and output:
```sql
mysql> CREATE TABLE tab (i int NOT NULL) ENGINE=csv;
ERROR 1 (HY000): Can't create/write to file './dbo/tab_402.sdi' (OS errno 13 Permission denied)
```
What causes the error?
- [ ] The engine is disabled.
- [ ] The database server is running in read-only mode.
- [ ] The SET LOCAL_ INFILE option has not been enabled.
- [ ] The database user does not have sufficient privilege.
- [ ] The database client process does not have sufficient privilege.
- [x] The database server process does not have sufficient privilege. ✅

#### Q. Which statement is true about the SHOW ERRORS command?
- [x] It cannot display information for more than max_error_count server system variable setting. ✅
- [ ] It displays similar diagnostics results as GET DIAGNOSTICS.
- [ ] It displays errors that have occurred since the start time of the current session.
- [ ] It displays errors that have occurred since the server last restarted.

#### Q. Which statement is true?
- [ ] SHOW WARNINGS displays errors, warnings, and notes.
- [x] SHOW COUNT(*) WARNINGS displays the number of warnings only. ✅
- [ ] SHOW WARNINGS displays warnings from DDL statements only.
- [ ] SHOW WARNINGS displays the same result as an EXPLAIN command.
- [ ] SHOW COUNT(*) WARNINGS and SELECT @@warning_count display the same result

#### Q. Which change will prevent negative ages to be inserted into the people table?
- [ ] 
```sql
ALTER TABLE people ADD COLUMN valid_age=ABS(check_age) GENERATED ALWAYS;
```
- [ ] 
```sql
DELIMITER //
CREATE TRIGGER agecheck AFTER INSERT ON people FOR EACH ROW IF NEW.age < 0 THEN SET NEW.age = 0; END IF;//
DELIMITER;
```
- [x] 
```sql
DELIMITER //
CREATE TRIGGER agecheck BEFORE INSERT ON people FOR EACH ROW IF NEW.age < 0 THEN SET NEW.age = 0; END IF;//
DELIMITER;
```
- [x] ✅
```sql
ALTER TABLE people ADD CONSTRAINT check_age CHECK (ABS(age)>=0);
```

#### Q. Examine these commands which execute successfully:
```sql
mysql> CREATE TABLE income (acct_num INT, amount DECIMAL(10,2));
mysql> CREATE TRIGGER subtotal BEFORE INSERT ON income
        FOR EACH ROW SET @subtotal = @subtotal + NEW.amount;
```
Which is true for the income table?
- [ ] The trigger activates after any row in the table has been updated.
- [ ] The trigger body SET causes trigger activation.
- [ ] The trigger activates after any row has been inserted into the table.
- [x] Execution of an INSERT statement causes the trigger to activate. ✅

#### Q. Examine these statements issued from Session 1 which execute successfully:
```sql
Session 1> SET transaction isolation 'SERIALIZABLE';
Session 1> START TRANSACTION;
Session 1> SELECT FROM world.city WHERE name='Roma' AND CountryCode='ITA';
```
Now, examine this statement issued from Session 2:
```sql
Session 2> UPDATE world.city SET population=2660000 WHERE name='Roma' AND CountryCode='ITA';
```
What is the outcome of the UPDATE statement in Session 2?
- [ ] The transaction in Session 1 will be rolled back automatically.
- [x] The staternent will wait for the transaction in Session 1 to finish. ✅
- [ ] The row will be updated immediately.
- [ ] A deadlock will occur.

#### Q. Examine these commands which execute successfully in the sequence shown in Sessions S1 and S2:
```sql
S1> SET AUTOCOMMIT-ON;
S1> SET SESSION TRANSACTION ISOLATION LEVEL REPEATABLE READ;
S1> SELECT * FROM emp;
    S2> SET AUTOCOMMIT-ON;
    S2> SET SESSION TRANSACTION ISOLATION LEVEL READ COMMITTED;
    S2> START TRANSACTION;
    S2> INSERT INTO emp values (103, 'Ring', 50000, 30);
```
Now, examine this statement that execute successfully in S1:
```sql
S1> SELECT * FROM emp:
```
Which is true about the result of the SELECT statement?
- [ ] The inserted row is not returned because the isolation level is READ COMMITTED in S2.
- [ ] The inserted row is returned because the transaction is auto committed in S2.
- [ ] The inserted row is returned because the isolation level is REPEATABLE READ in S1.
- [x] The inserted row is not returned because the transaction still active in S2. ✅

#### Q. Examine this statement and output:
```sql
mysql> SELECT @@GLOBAL.sql_mode, @@SESSION.sql_mode, @@sql_mode\G
******** 1. row ***********
@@GLOBAL.sql_mode: STRICT_TRANS_TABLES, NO_ENGINE_SUBSTITUTION
@@SESSION.sql mode: STRICT_TRANS_TABLES, NO_ENGINE_SUBSTITUTION
    @@sql_mode: STRICT_TRANS_TABLES, NO_ENGINE_SUBSTITUTION
1 row in set (0.00 sec)
```
Now examine this statement which executes successfully:
```sql
SET SQL_MODE=TRADITIONAL;
```
Which statement is true?
- [ ] The SQL mode is changed for all sessions using the current account to TRADITIONAL.
- [ ] The global SQL mode is changed to TRADITIONAL.
- [x] The session SQL mode is changed to TRADITIONAL. ✅
- [ ] No change is made unless the account has the CONNECTION ADMIN privilege.

#### Q. Examine this CRUD operation:
```js
JS> col.find()
{
"id": "00005e8585eb0000000000000009",
"name": "fred"
}
1 document in set (0.0003 sec)
```
Which two SQL statements are valid?
- [x] ALTER TABLE col ADD COLUMN result INT GENERATED ALWAYS as (doc->>"$.result") VIRTUAL NOT NULL; ✅
- [ ] ALTER TABLE col ADD COLUMN result INT GENERATED ALWAYS as (doc->>"$.result") STORED NOT NULL;
- [ ] ALTER TABLE col ADD COLUMN result INT GENERATED ALWAYS as (doc->>"$.result") STORED DEFAULT '0';
- [ ] ALTER TABLE col ADD COLUMN result INT GENERATED ALWAYS as (doc->>"$.result") STORED;
- [ ] ALTER TABLE col ADD COLUMN result INT GENERATED ALWAYS as (doc->>"$.result") VIRTUAL DEFAULT 0;

#### Q. You must enforce data integrity for data inserted in a JSON column.  
Which statement successfully creates a CONSTRAINT in a JSON column?
- [x] CREATE TABLE fshop (product JSON CHECK (JSON_VALID (product))); ✅
- [ ] CREATE TABLE fshop (product JSON, f INT GENERATED ALWAYS AS (product-> "$.id"));
- [ ] CREATE TABLE fshop (id INT NOT NULL AUTO INCREMENT, product JSON, PRIMARY KEY(id)) ENGINE=InnoDB;
- [ ] CREATE TABLE fshop (id INT NOT NULL AUTO INCREMENT, product JSON, CHECK (id>0)) ENGINE=InnoDB;

#### Q. Examine the layout of the employees table.
```sql
CREATE TABLE 'employees' (
'emp_no' INT NOT NULL,
'birth_date' DATE NOT NULL,
'first_name' VARCHAR(14) NOT NULL,
'last name' VARCHAR(16) NOT NULL,
'network_name' VARCHAR(15) NOT NULL,
'gender' ENUM('M', 'F') NOT NULL,
'hire_date' DATE NOT NULL,
PRIMARY KEY ('emp_no'),
UNIQUE KEY 'network name' ('network name'),
KEY 'hire_date' ('hire_date')
) ENGINE=InnODB DEFAULT CHARSET=utf8mb4 COLLATE utf8mb4_0900_ai_ci;
```
Which column in the employees table represents the table's clustered index?
- [ ] hire_date
- [x] emp_no ✅
- [ ] network_name
- [ ] gender

#### Q. Examine these statements which execute successfully:
```sql
CREATE TABLE `photos` (
  `id` INT(11) NOT NULL AUTO_INCREMENT,
  `title` VARCHAR(255) DEFAULT NULL,
  `description` TEXT,
  `created_at` DATETIME DEFAULT NULL,
  `updated_at` DATETIME DEFAULT NULL,
  `file_name` VARCHAR(255) DEFAULT NULL,
  `privacy` CHAR(1) NOT NULL DEFAULT 'A',
  `rating` INT DEFAULT 0,
  `valid_upload` TINYINT(1) DEFAULT 1,
  `relevant` TINYINT(1) DEFAULT 0,
  `album_id` INT DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=1734438 DEFAULT CHARSET=utf8;
```
```sql
SELECT title,
  created_at,
  updated_at
FROM photos ph
INNER JOIN 
  photo_data pd ON pd.album_id = ph.album_id
WHERE ph.rating IN (12)
  AND pd.owner_id IN ('S')
  AND ph.privacy = 'S'
  AND pd.hidden = '0'
  AND pd.valid_upload = 1
  AND pd.url IS NOT NULL
GROUP BY ph.id
HAVING COUNT(ph.id) > 2
ORDER BY ph.id DESC
LIMIT 12;
```
Which additional index on table photos will improve performance for the query?
- [ ] ('title', 'created_at', 'updated_at')
- [x] ('album_id', 'privacy', 'rating') ✅
- [ ] ('valid_upload')
- [ ] ('title', 'id')

#### Q. Examine the appointments table definition which contains one million rows:
```sql
CREATE TABLE `appointments` (
  `id` INT(11) NOT NULL AUTO_INCREMENT,
  `attendant_id` INT(11) NOT NULL,
  `attendant_session_id` INT(11) NOT NULL,
  `start` DATETIME NOT NULL,
  `end` DATETIME NOT NULL,
  `date` DATE NOT NULL,
  `created_by` VARCHAR(20) NOT NULL,
  `created_at` DATETIME DEFAULT CURRENT_TIMESTAMP,
  `payment` INT(11) NOT NULL DEFAULT 0,
  `credit` INT(11) NOT NULL DEFAULT 0,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

```
Now, examine this statement which executes successfully.
```sql
SELECT attendant_id,
  payment,
  credit
FROM appointments
WHERE attendant_session_id = 510
  AND created_by = 'jsmith';
```
Which statement will improve query performance?
- [ ] ALTER TABLE appointments add index IX_1 (credit, payment);
- [ ] ALTER TABLE appointments add index IX_4 (attendant_id, payment, credit);
- [ ] ALTER TABLE appointments add index IX_3 (attendant_id, created_by);
- [x] ALTER TABLE appointments add index IX_2 (attendant_session_ id, created_by); ✅

#### Q. Examine this sequence of statements issued by two concurrent sessions within three seconds of each other:
```sql
Session 1> SELECT GET_LOCK(`mylock1`, 70);
    Session 2> SELECT GET_LOCK(`mylock2`,70);
    Session 2> SELECT GET_LOCK(`mylock1`,70);
Session 1> SELECT GET_LOCK(`mylock2`,70);
```
What will happen in Session 1 after the last statement is executed?
- [ ] The lock will be immediately granted
- [ ] A deadlock error is returned.
- [ ] A timeout will be returned after the wait timeout interval has expired.
- [x] An error will be returned after 70 seconds. ✅

#### Q. Examine this statement that executes successfully in an interactive session:
```sql
session 0> LOCK TABLES test.tl READ,
test.t2 WRITE;
```
The user running this session now goes to lunch for an hour.  
Now, examine these statements executed independently in separate sessions while Session 0 is still active:
```sql
session 1> SELECT * FROM test.t2;
session 2> SELECT * FROM test.t2 FOR UPDATE NOWAIT;
session 3> SELECT * FROM test.tl;
session 4> INSERT INTO test.t1 VALUES (0, 'a', 'b');
session 5> SELECT * FROM t1 FOR UPDATE NOWAIT;
```
How many of them will complete while Session 0 is still active?
- [x] 2 ✅
- [ ] 1
- [ ] 3
- [ ] 4
- [ ] 0
- [ ] 5

#### Q. AUTOCOMMIT mode is enabled for a session.  
Which is true?
- [ ] The BEGIN statement can be used to start multi statement transaction and it will disable the AUTOCOMMIT mode permanently for the session.
- [ ] The current session AUTOCOMMIT mode can be disabled using SET GLOBAL.
- [x] Every SQL statement executes as a transaction. ✅
- [ ] Statements that fail must be rolled back explicitly.
- [ ] The START TRANSACTION statement is unsupported in this mode.

#### Q. Examine these statements issued from Session 1 which execute successfully:
```sql
Session 1>
SET autocommit=1;
SELECT * FROM band FOR UPDATE;
```
Session 1 remains idle while another user starts Session 2.
Now, examine these statements issued from Session 2 which execute successfully:
```sql
Session 2>
BEGIN;
UPDATE band SET song-CONCAT("Here Comes the", song) WHERE song LIKE "%Sun";
```
Which two are true?
- [ ] Session 1 does not block Session 2.
- [ ] Session 1 takes a shared lock on all the rows in the band table.
- [x] Statements in Session 2 are committed. ✅
- [ ] Session 2 does not start a transaction.
- [x] Session 1 must commit before the UPDATE in Session 2 can complete. ✅
- [ ] Session 2 takes an exclusive lock on all the rows in the band table.

#### Q. A program executes a START TRANSACTION statement in AUTOCOMMIT mode.  
Which two are true?
- [ ] All changes to any table rows commit immediately.
- [x] AUTOCOMMIT mode is enabled again after executing a ROLLBACK statement. ✅
- [x] It temporarily disables AUTOCOMMIT mode. ✅
- [ ] Every SQL statement executes as a transaction.
- [ ] AUTOCOMMIT mode is enabled again only by executing a COMMIT statement

#### Q. Examine these MySQL Shell statements:
```js
mysql-js> nc = db.createCollection('person');
mysql-js> nc.add({name: "Kate", city: "Paris"});
mysql-js> nc.add({name: "Bill", city: "London"});
mysql-js> nc.add({name: "John", place: "New York"});
mysql-js> nc.add({name: "Mary", place: "Boston", country: "USA"});
```
What is true about the attempts to add documents to the collection?
- [x] All documents are added without any error or warning. ✅
- [ ] All documents are added and cause a warning.
- [ ] First two documents are added, then mismatched field names cause an error.
- [ ] First three documents are added, then different number of fields cause an error

#### Q. Examine this SQL statement:
```sql
SELECT Name, Population FROM country
WHERE Name LIKE 'United%'
LIMIT 5;
```
Which two statements provide equivalent results using the X DevAPI protocol?
- [ ] db.country.select([Name LIKE "United%"', 'Population>-0']).limit(5)
- [ ] db.country.fields (['Name', 'Population']) select('limit=5').where(Name LIKE "United%")
- [ ] db.country.fields(['Name', 'Population']).where('Name LIKE "United%"').select().limit(5)
- [x] db.country.select(['Name', 'Population']).limit(5).where('Name LIKE "United%"') ✅
- [x] db.country.select(['Name', 'Population']).where('Name LIKE:param').bind('param', 'United%').limit(5) ✅

#### Q. Select three languages for which Oracle MySQL publishes drivers.
- [x] Node.js ✅
- [x] Python ✅
- [ ] Lua
- [ ] Erlang
- [ ] Ruby
- [x] Java ✅
- [ ] Go

#### Q. Which is an advantage of the PHP Data Objects (PDO) PDO_MySQL module compared with other interfaces?
- [x] PDO is database agnostic which makes porting to other databases potentially easier. ✅
- [ ] PDO supports more MySQL features than mysqli.
- [ ] PDO is designed to let you treat database tables exclusively as objects.
- [ ] PDO includes support for the X DevAPI API.

#### Q. Examine the output:
```sql
*************************** 1. row ***************************
EXPLAIN: {
  "query_block": {
    "select_id": 1,
    "cost_info": {
      "query_cost": "0.45"
    },
    "table": {
      "table_name": "country",
      "access_type": "ALL",
      "rows_examined_per_scan": 2,
      "rows_produced_per_join": 2,
      "filtered": "100.00",
      "cost_info": {
        "read_cost": "0.25",
        "eval_cost": "0.20",
        "prefix_cost": "0.45",
        "data_read_per_join": "224"
      },
      "used_columns": [
        "code",
        "Name",
        "Continent",
        "LanguageId"
      ]
    }
  }
}
1 row in set, 1 warning (0.00 sec)
```
Which EXPLAIN command will obtain the output?
- [x] EXPLAIN FORMAT=JSON ✅
- [ ] EXPLAIN FORMAT=TRADITIONAL
- [ ] EXPLAIN FORMAT=TREE
- [ ] EXPLAIN PARTITIONS
- [ ] EXPLAIN ANALYZE

#### Q. Which two statements are valid for using with a query to obtain its query execution plan?
- [ ] ANALYZE QUERY FOR
- [ ] SHOW QUERY PLAN
- [x] EXPLAIN EXTENDED ✅
- [x] EXPLAIN ✅
- [ ] DESCRIBE

#### Q. Which three evaluate to a temporal value?
- [x] SYSDATE()-1 ✅
- [ ] MONTH('01-05-2020')
- [x] SYSDATE() ✅
- [ ] TO_DAYS ('2020-05-01')
- [x] '2020-05-01' - INTERVAL 1 DAY ✅
- [ ] '2020-05-01'

#### Q. A table has these attributes:  
1. It has more than 1 million rows.  
2. It has a date_of_birth column defined with the DATETIME data type.  
3. The date_of_birth column is indexed.  
Which is the most efficient WHERE clause that returns all customers born in the year 2000?
- [ ] WHERE YEAR(date_of_birth) = 2000
- [x] WHERE date_of_birth >= '2000-01-01' AND date_of_birth < '2001-01-01' ✅
- [ ] WHERE date_of_birth BETWEEN '2000-01-01' AND '2001-01-01'
- [ ] WHERE date_of_birth BETWEEN '2000-01-01' AND '2000-12-31'
- [ ] CHECK date_of_birth LIKE '2000%'

#### Q. Which two are true about MySQL Document Store?
- [x] It helps to store data items in a schema-less key-value store. ✅
- [ ] It can store documents greater than 4 GB.
- [ ] It depends heavily on strictly typed data.
- [x] It allows one to bypass the SQL layer of the server. ✅
- [ ] There is no access to relational tables

#### Q. Which two are true about PREPARE statements?
- [ ] They are accessible in other active sessions.
- [x] They can be created with the same name as an existing prepared statement in the same session. ✅
- [ ] They can be nested.
- [ ] They retain their resources even if the connection to the database is lost.
- [x] They can be created and executed within a stored routine. ✅

#### Q. What are three general advantages to prepared statements?
- [ ] They allow queries to run in parallel.
- [ ] They cause the server to parse the statement each time it is executed.
- [x] They reduce network traffic between client and server. ✅
- [x] They reduce CPU overhead. ✅
- [ ] They cache data before sending it to the MySQL Server.
- [ ] They take advantage of dynamic cursor declarations.
- [x] They allow for dynamic SQL in stored routines. ✅

#### Q. Examine these statements which execute successfully.
```sql
SET SQL_MODE = '';
SELECT 2 * -3 AS a, 2 * -3 AS b, CAST(2 * -3 AS UNSIGNED) AS c;
```
What is the result?
- [ ] 
```sql
+-----+-----+-----+
| a   | b   | c   |
+-----+-----+-----+
| -6  | -6  | -6  |
+-----+-----+-----+
```
- [ ] 
```sql
+-----+--------+-----+
| a   | b      | c   |
+-----+--------+-----+
| -6  | NULL   |  6  |
+-----+--------+-----+
```
- [x] ✅
```sql
+-----+-----+----------------------+
| a   | b   | c                    |
+-----+-----+----------------------+
| -6  | -6  | 18446744073709551610 |
+-----+-----+----------------------+
```
- [ ] 
```sql
+-----+-----+-----+
| a   | b   | c   |
+-----+-----+-----+
| -6  | -6  |  6  |
+-----+-----+-----+
```
- [ ] 
```sql
+-----+-----+-----+
| a   | b   | c   |
+-----+-----+-----+
| -6  |  0  |  6  |
+-----+-----+-----+
```

#### Q. Examine this statement and output:
```sql
SELECT * FROM exam_result;
```
```sql
+-----+--------+
| sid | score  |
+-----+--------+
|  1  | 75.235 |
|  2  | 75.234 |
|  3  | 75.253 |
|  4  | 75.257 |
+-----+--------+
```
Now, examine these desired output values:

```sql
+-----+--------+
| sid | score  |
+-----+--------+
|  1  | 75.2   |
|  2  | 75.2   |
|  3  | 75.3   |
|  4  | 75.3   |
+-----+--------+
```
Which statement updates the table data as required?
- [ ] UPDATE exam_result SET score = CEIL(TRUNCATE(score, 1));
- [ ] UPDATE exam_result SET score = CEIL(ROUND(score, 1));
- [ ] UPDATE exam_result SET score = TRUNCATE(score, 1);
- [ ] UPDATE exam_result SET score = ROUND(CEIL(score), 1);
- [ ] UPDATE exam_result SET score = TRUNCATE(CEIL(score), 1);
- [x] UPDATE exam_result SET score = ROUND ✅
