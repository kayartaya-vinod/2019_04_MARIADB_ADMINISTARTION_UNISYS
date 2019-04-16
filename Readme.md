# MariaDB Administration [ http://bit.ly/vkmrdb ]

Date: 17th and 19th April 2019<br/>
Client: Unisys, Bangalore.

### Table of content
---
<ul>
    <li><a href="#ch01">How to Create/Drop User in MariaDB</a></li>
</ul>

<div id="ch01">

## How to Create/Drop User in MariaDB

Create User in MariaDB:
To create a user in MariaDB , you can use below Syntax

```sql
MariaDB > Create User 'UserName'@'Server' IDENTIFIED BY 'YourPassword';
```

Let's say if you need to create user Aamir with password =Aamir$Password, you will be using below statement



MariaDB > Create user 'Aamir'@'localhost' Identified by ' Aamir$Password';

To get the list of all users , below statement can be used.
MariaDB > Select * from mysql.user; 

Drop User in MariaDB: 
To drop user in MariaDB , you can use below statement
MariaDB > Drop User 'UserName'@'HostName';
Let's say if you would like to drop user Aamir that you have created in Localhost, you can use below statement
MariaDB > Drop user 'Aamir'@'Localhost'; 
</div>
