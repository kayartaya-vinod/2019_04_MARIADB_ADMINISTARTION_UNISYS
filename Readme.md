# MariaDB Administration [ http://bit.ly/vkmrdb ]

Date: 17th and 19th April 2019<br/>
Client: Unisys, Bangalore.

### Table of content
---
<ul>
    <!--
    <li><a href="#ch01">How to Create/Drop User in MariaDB</a></li>
    <li><a href="#ch02">How to Grant all the permissions to User in MariaDB</a></li>
    <li><a href="#ch03">How to Grant Full Permission on a Database to a User in MariaDB</a></li>
    <li><a href="#ch04">How to Grant Select Permission on Table/s  to User in MariaDB</a></li>
    <li><a href="#ch05">How to Grant Update Permission on Table/s to a User in MariaDB</a></li>
    <li><a href="#ch06"></a></li>
    <li><a href="#ch07"></a></li>
    <li><a href="#ch08"></a></li>
    <li><a href="#ch09"></a></li>
    <li><a href="#ch10"></a></li>
    <li><a href="#ch11"></a></li>
    <li><a href="#ch12"></a></li>
    -->
</ul>

<!--
<div id="ch01">

## How to Create/Drop User in MariaDB

### Create User in MariaDB:

To create a user in MariaDB , you can use below Syntax

```sql
MariaDB > Create User 'UserName'@'Server' IDENTIFIED BY 'YourPassword';
```

Let's say if you need to create user `vinod` with password `topsecret`, you will be using below statement


```sql
MariaDB > Create user 'vinod'@'localhost' Identified by 'topsecret';
```

To get the list of all users , below statement can be used.

```sql
MariaDB > Select * from mysql.user; 
```

### Drop User in MariaDB: 

To drop user in MariaDB , you can use below statement

```sql
MariaDB > Drop User 'UserName'@'HostName';
```

Let's say if you would like to drop user `vinod` that you have created in Localhost, you can use below statement

```sql
MariaDB > Drop user 'vinod'@'Localhost'; 
```
</div>

<div id="ch02">

## How to Grant all the permissions to User in MariaDB

If you would like to provide all permissions like root user to user account, you can use below command.

First of all let's create a user by using below :

Syntax:
```sql
MariaDB > Create User 'UserName'@'localhost';
```

To provide all permission including with GRANT , below syntax can be use

```sql
MariaDB > GRANT ALL ON *.* To 'UserName'@'HostName'  With GRANT OPTION;
```

Example:

Let's say that you would like to create user `vinod` and provide him all the permissions.

```sql
MariaDB > Create user 'vinod'@'localhost' Identified by 'topsecret'; 
MariaDB > GRANT ALL ON *.* to 'vinod'@'localhost' With Grant Option;
```

</div>

<div id="ch03">

### How to Grant Full Permission on a Database to a User in MariaDB

To provide full permissions on a database to user, you will be using below syntax.

Syntax:

```sql
MariaDB > GRANT ALL ON DatabaseName.* TO 'UserName'@'Host' WITH GRANT OPTION;
```

WITH GRANT OPTION, user will be able to provide permissions to other users on the database. If you don't want that then remove the "With GRANT OPTION" from above statement.

Example: 

Let's create user TB and provide full permissions on Database name "TechBrothers" , We also want the TB user to have permissions to GRANT permissions on "TechBrothers" databases to other users.

```sql
MariaDB > Create User 'vk'@'localhost' Identified by "topsecret";
```

Grant full permissions on TechBrothers Databases to user account TB.

```sql
MariaDB > GRANT ALL ON TechBrothers.* TO 'vk'@'localhost' With GRANT OPTION; 
```

</div>

-->

<div id="ch04">

### How to Grant Select Permission on Table/s  to User in MariaDB

Below Syntax can be used to provide select permission on table/s in MariaDB.

Syntax:

On Single Table

```sql
MariaDB > GRANT select ON tableName to 'UserName'@'Host' 
```

On all the tables in a database

```sql 
MariaDB > GRANT select ON DatabaseName.* to 'UserName'@'Host' 
```

Example :

Let's say that if we have table test in Techbrothers Database and we would like to provide Select permission to user `vinod` in MariaDB. we can use below statement

```sql
MariaDB > GRANT select ON Techbrothers.test to 'vinod'@'localhost' 
```

If we want to provide Select permission on all the tables in Techbrothers Database to user account `vinod` in MariaDB, we can use below statement

```sql
MariaDB > GRANT select ON Techbrothers.* to 'vinod'@'localhost' 
```

</div>

<div id="ch05">

### How to Grant Update Permission on Table/s to a User in MariaDB

Below Syntax can be used to provide UPDATE permission on table/s in MariaDB.

Syntax:

On Single Table

```sql
MariaDB > GRANT UPDATE ON tableName to 'UserName'@'Host' 
```

On all the tables in a database

```sql
MariaDB > GRANT UPDATE ON DatabaseName.* to 'UserName'@'Host' 
```

Example :

Let's say that if we have table "test" in Techbrothers Database and we would like to provide Update permission to user "vinod" in MariaDB. we can use below statement

```sql
MariaDB > GRANT UPDATE ON Techbrothers.test to 'vinod'@'localhost' 
```

If we would like to provide UPDATE permission on all the tables in Techbrothers Database to user account vinod in MariaDB, we can use below statement

```sql
MariaDB > GRANT UPDATE ON Techbrothers.* to 'vinod'@'localhost' 
```
</div>

<div id="ch06">

</div>

<div id="ch07">
</div>

<div id="ch08">
</div>

<div id="ch09">
</div>

<div id="ch10">
</div>

<div id="ch11">
</div>

<div id="ch12">
</div>
