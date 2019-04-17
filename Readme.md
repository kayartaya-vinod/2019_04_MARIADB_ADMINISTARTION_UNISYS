# MariaDB Administration [ http://bit.ly/vkmrdb ]

Date: 17th and 19th April 2019<br/>
Client: Unisys, Bangalore.

### Table of content
---
<ul>
    <li><a href="#ch01">How to Create/Drop User in MariaDB</a></li>
    <li><a href="#ch02"></a></li>
    <li><a href="#ch03"></a></li>
    <li><a href="#ch04"></a></li>
    <li><a href="#ch05"></a></li>
    <li><a href="#ch06"></a></li>
    <li><a href="#ch07"></a></li>
    <li><a href="#ch08"></a></li>
    <li><a href="#ch09"></a></li>
    <li><a href="#ch10"></a></li>
    <li><a href="#ch11"></a></li>
    <li><a href="#ch12"></a></li>
</ul>

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

