# 1 Getting Started with MySQL

## 1.1 What is MySQL?

&emsp;&emsp;MySQL is a robust database management system designed for managing relational databases. It is open-source software supported by Oracle, meaning that we can use MySQL without any cost. Additionally, we will have the flexibility to modify its source code to tailor it to our specific requirements.

&emsp;&emsp;Despite being open-source software, we also have the option to purchase a commercial license from Oracle, which provides access to premium support services.

> MySQL? What’s in a name?  
> &emsp;&emsp;MySQL got its name from the daughter of one of its co-founders, Monty Widenius, whose name is My. Combining ‘My’ with ‘SQL,’ we get MySQL.

## 1.2 Installing MySQL on Linux

1. Click <a href="https://dev.mysql.com/downloads/mysql/" target="_blank">here</a> to download MySQL Community Server.

2. Unpack the downloaded file and put it somewhere.

```bash
tar -pxvf mysql-8.3.0-linux-glibc2.28-x86_64.tar.xz
mv mysql-8.3.0-linux-glibc2.28-x86_64 /opt
```

3. Write the configuration file **my.cnf** and place it in the root directory of MySQL.

```config
[mysqld]
user=mysql
basedir=/opt/mysql-8.0.36-glibc2.28-x86_64
datadir=/opt/mysql-8.0.36-glibc2.28-x86_64/data
port=3306
pid-file=/opt/mysql-8.0.36-glibc2.28-x86_64/data/mysqld.pid
max_connections=200
max_connect_errors=10
character-set-server=utf8mb4
default-storage-engine=INNODB
default_authentication_plugin=mysql_native_password

# case-sen
lower_case_table_names=0
group_concat_max_len=102400

[mysql]
default-character-set=utf8mb4

[client]
port=3306
default-character-set=utf8mb4
```

4. Create `mysql` user and user group, and then set the owner and group of the entire MySQL package as `mysql`

```bash
groupadd mysql
useradd -r -g mysql mysql 

chown -R mysql /opt/mysql-8.0.36-glibc2.28-x86_64
chgrp -R mysql /opt/mysql-8.0.36-glibc2.28-x86_64
```

5. Initialize the `mysqld` service.

```bash
cd /opt/mysql-8.0.36-glibc2.28-x86_64/bin
./mysqld --user=mysql --initialize
```

6. Create `mysqld` service `/etc/systemd/system/mysqld.service`.

```
[Unit]
Description=Mysql8 Server
Documentation=man:mysqld(8)
Documentation=http://dev.mysql.com/doc/refman/en/using-systemd.html
After=network.target
After=syslog.target

[Service]
User=mysql
Group=mysql
PIDFile=/opt/mysql-8.0.36-glibc2.28-x86_64/data/mysqld.pid
ExecStart=/opt/mysql-8.0.36-glibc2.28-x86_64/bin/mysqld --defaults-file=/opt/mysql-8.0.36-glibc2.28-x86_64/my.cnf

[Install]
WantedBy=multi-user.target
```

7. Enable the service.

```bash
systemctl start mysqld.service  # start the service
systemctl enable mysqld.service  # auto-start the service once the system boots
```

8. Login and change the password of root.

```sql



```

# 2 Querying Data

## 2.1 `SELECT FROM` and `SELECT`

&emsp;&emsp;The **SELECT** statement allows us to select data from one or more tables. To write a SELECT statement in MySQL, we use this syntax:

```sql
SELECT select_list
FROM table_name;
```

In this syntax, we need to:

1. Specify one or more columns from which we want to select data after the **SELECT** keyword. If the select_list has multiple columns, we need to separate them by a comma `,`.
2. Specify the name of the table from which we want to select data after the **FROM** keyword.

> Note:  
> &emsp;&emsp;The semicolon `;` is optional, which denotes the end of a statement. If we have two or more statements, we need to use the semicolon `;` to separate them so that MySQL will execute each statement individually.  
> &emsp;&emsp;The By convention, we write the SQL keywords in uppercase. However, it’s not mandatory. Because **SQL is case-insensitive**, we can write the SQL statement in lowercase, uppercase, etc.

&emsp;&emsp;In MySQL, the SELECT statement doesn’t require the FROM clause. The following example uses the SELECT statement to perform a simple calculation:

```sql
SELECT 1 + 1;
```

&emsp;&emsp;MySQL has many built-in functions. We can use the SELECT statement to execute one of these functions.

&emsp;&emsp;For example, the following statement uses the `NOW()` function in the SELECT statement to return the current date and time of the server where MySQL server is running:

```sql
SELECT NOW();
```

> Note:  
> &emsp;&emsp;The `NOW()` function doesn’t have any parameters. To call it, we just place the parentheses `()` after the function name.

&emsp;&emsp;If a function has parameters, we need to pass arguments into it. For example, to concatenate multiple strings into a single string, we can use the `CONCAT()` function:

```sql
SELECT CONCAT('John',' ','Doe');
```

> Note:  
> &emsp;&emsp;The `CONCAT()` function accepts one or more strings and concatenates them into a single string.

## 2.2 Column alias

&emsp;&emsp;By default, MySQL uses the expression specified in the SELECT clause as the column name of the result set. To change a column name of the result set, we can use a column alias:

```sql
SELECT expression AS column_alias;
```

&emsp;&emsp;The **AS** keyword is optional, so we can skip it like this:

```sql
SELECT expression column_alias;
```

&emsp;&emsp;If the column alias contains spaces, we need to place it inside quotes like this:

```sql
SELECT CONCAT('Jane',' ','Doe') AS 'Full name';
```

## 2.3 Sorting Data

&emsp;&emsp;When we use the SELECT statement to query data from a table, the order of rows in the result set is unspecified. To sort the rows in the result set, we add the **ORDER BY** clause to the SELECT statement.

&emsp;&emsp;The following illustrates the syntax of the ORDER BY clause:

```sql
SELECT select_list
FROM table_name
ORDER BY 
    column1 [ASC|DESC],
    column2 [ASC|DESC],
    ...;
```

&emsp;&emsp;This ORDER BY clause sorts the result set by the values in the column1 **in ascending order**:

```sql
ORDER BY column1 ASC;
```

&emsp;&emsp;And this ORDER BY clause sorts the result set by the values in the column1 **in descending order**:

```sql
ORDER BY column1 DESC;
```

> Note: By default, the ORDER BY clause uses ASC if we don’t explicitly specify any option.

&emsp;&emsp;If we want to sort the result set by multiple columns, we specify a comma-separated list of columns in the ORDER BY clause:

```sql
ORDER BY
   column1,
   column2;
```

&emsp;&emsp;It is possible to sort the result set by a column in ascending order and then by another column in descending order:

```sql
ORDER BY
    column1 ASC,
    column2 DESC;
```

## 2.4 Filtering data

### 2.4.1 WHERE 

&emsp;&emsp;The **WHERE** clause allows us to specify a search condition for the rows returned by a query. The following shows the syntax of the WHERE clause:

```sql
SELECT select_list
FROM table_name
WHERE search_condition;
```

> Note:  
> &emsp;&emsp;The search_condition is a combination of one or more expressions using the logical operator `AND`, `OR` and `NOT`.


# 3 Managing Databases

# 4 MySQL data types

# 5 Working with Tables

# 6 MySQL constraints

# 7 Modifying data in MySQL

