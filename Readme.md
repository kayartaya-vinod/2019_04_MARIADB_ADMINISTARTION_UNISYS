# MariaDB Administration [ http://bit.ly/vkmrdb ]

Date: 17th and 19th April 2019<br/>
Client: Unisys, Bangalore.

For any clarifications, write to me on <a href="mailto:vinod@vinod.co">vinod@vinod.co</a>

For more visit <a href="https://vinod.co">https://vinod.co</a>

### Table of content
---
<ul>
    <li><a href="#ch01">How to Create/Drop User in MariaDB</a></li>
    <li><a href="#ch02">How to Grant all the permissions to User in MariaDB</a></li>
    <li><a href="#ch03">How to Grant Full Permission on a Database to a User in MariaDB</a></li>
    <li><a href="#ch04">How to Grant Select Permission on Table/s  to User in MariaDB</a></li>
    <li><a href="#ch05">How to Grant Update Permission on Table/s to a User in MariaDB</a></li>
    <li><a href="#ch06">How to Grant Insert Permission on Table/s to a User in MariaDB</a></li>
    <li><a href="#ch07">How to Grant Drop/Create Table Permission to a User in MariaDB</a></li>
    <li><a href="#ch08">How to Grant Delete Permission on Table/s to a User in MariaDB</a></li>
    <li><a href="#ch14">How to create ROLE in MariaDB</a></li>
    <li><a href="#ch15">How to see Permissions of a user in MariaDB</a></li>
    <li><a href="#ch16">How to change Root Password for MariaDB</a></li>
    <li><a href="#sp">Stored procedure demos</a></li>
</ul>
    
<!--
<li><a href="#ch09"></a></li>
<li><a href="#ch10"></a></li>
<li><a href="#ch11"></a></li>
<li><a href="#ch12"></a></li>
<li><a href="#ch13"></a></li>
-->


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

Let's create user vk and provide full permissions on Database name "training" , We also want the vk user to have permissions to GRANT permissions on "training" databases to other users.

```sql
MariaDB > Create User 'vk'@'localhost' Identified by "topsecret";
```

Grant full permissions on training Databases to user account vk.

```sql
MariaDB > GRANT ALL ON training.* TO 'vk'@'localhost' With GRANT OPTION; 
```

</div>


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

Let's say that if we have table test in training Database and we would like to provide Select permission to user `vinod` in MariaDB. we can use below statement

```sql
MariaDB > GRANT select ON training.test to 'vinod'@'localhost' 
```

If we want to provide Select permission on all the tables in training Database to user account `vinod` in MariaDB, we can use below statement

```sql
MariaDB > GRANT select ON training.* to 'vinod'@'localhost' 
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

Let's say that if we have table "test" in training Database and we would like to provide Update permission to user "vinod" in MariaDB. we can use below statement

```sql
MariaDB > GRANT UPDATE ON training.test to 'vinod'@'localhost' 
```

If we would like to provide UPDATE permission on all the tables in training Database to user account vinod in MariaDB, we can use below statement

```sql
MariaDB > GRANT UPDATE ON training.* to 'vinod'@'localhost' 
```
</div>

<div id="ch06">

### How to Grant Insert Permission on Table/s to a User in MariaDB

Below Syntax can be used to provide INSERT permission on table/s in MariaDB.

Syntax:

On Single Table

```sql
MariaDB > GRANT INSERT ON tableName to 'UserName'@'Host' 
```

On all the tables in a database
 
```sql
MariaDB > GRANT INSERT ON DatabaseName.* to 'UserName'@'Host' 
```

Example :

Let's say that if we have table "test" in training Database and we would like to provide INSERT permission to user "vinod" in MariaDB. we can use below statement

```sql
MariaDB > GRANT INSERT ON training.test to 'vinod'@'localhost' 
```

If we would like to provide INSERT permission on all the tables in training Database to user account vinod in MariaDB, we can use below statement

```sql
MariaDB > GRANT INSERT ON training.* to 'vinod'@'localhost' 
```
</div>

<div id="ch07">

### How to Grant Drop/Create Table Permission to a User in MariaDB

Below Syntax can be used to provide Drop and Create permission on table/s in MariaDB.

Syntax:

On Single Table

```sql
MariaDB > GRANT Drop, Create ON tableName to 'UserName'@'Host' 
```

On all the tables in a database

```sql
MariaDB > GRANT Drop, Create ON DatabaseName.* to 'UserName'@'Host' 
```


Example :

Let's say that if you like to provide Drop and Create permission to user "vinod" in database training. we can use below statement

```sql
MariaDB > GRANT Drop, Create ON training.* to 'vinod'@'localhost' 
```

</div>

<div id="ch08">

### How to Grant Delete Permission on Table/s to a User in MariaDB

Below Syntax can be used to provide DELETE permission on table/s in MariaDB.

Syntax:

On Single Table

```sql
MariaDB > GRANT DELETE ON tableName to 'UserName'@'Host' 
```

On all the tables in a database
 
```sql
MariaDB > GRANT DELETE ON DatabaseName.* to 'UserName'@'Host' 
```


Example :

Let's say that if we have table "test" in training Database and we would like to provide DELETE permission to user "vinod" in MariaDB. we can use below statement

```sql
MariaDB > GRANT DELETE ON training.test to 'vinod'@'localhost' 
```

If we would like to provide DELETE permission on all the tables in training Database to user account vinod in MariaDB, we can use below statement

```sql
MariaDB > GRANT DELETE ON training.* to 'vinod'@'localhost' 
```

</div>

<div id="ch09">
</div>

<div id="ch10">
</div>

<div id="ch11">
</div>

<div id="ch12">
</div>

<div id="ch13">
</div>

<div id="ch14">

### How to create ROLE in MariaDB

Roles in MairaDB really helps to group the permissions to single object ( Role) and then you can assign role to user instead of you create each user indiviually and then grant permissions.

Syntax:

```sql
MariaDB > Create ROLE ROLE_Name;
```

Example : 

Let's say we want to create Select role with  name "developer" and then Grant Show databases and Select permission on all the tables in training Database. Once the role is created we would like to assign user shyam and john to it.

```sql
MariaDB > Create Role developer; 
```

Grant Permissions to Role " developer"


```sql
MariaDB > GRANT SHOW DATABASES ON *.* to developer;
MariaDB > GRANT ALL ON training.* to developer; 
```


Grant developer to user shyam.

```sql
MariaDB >  GRANT developer To 'shyam'@'localhost'; 
```

Now once the user shyam or john will login to MairaDB, they can use this role. Once the user login , they can check which role they are using by using below statment.


```sql
MariaDB > Select Current_Role; 
```

First time you are going to get below output.

```
+--------------+
| Current_Role |
+--------------+
| NULL         |
+--------------+
1 row in set (0.00 sec)
```

If user shyam or john will try to select the data from training database or run show databases statement, they will get permission denied error. They have to set the role first. Below statement can be used to set the role.

```sql
MariaDB >  set Role developer; 
```

Now they should be able to use all the object on wich developer has permission.
User can also set the default Role by using below statement so he/she does ont have to set the role everytime login.

```sql
MariaDB> set default role developer;
```

</div>


<div id="ch15">

### How to see Permissions of a user in MariaDB
Once you are login to MariaDB, you can run below statement to see the permission of currently login user account.

```sql
MariaDB > Show Grants;
```

If you want to check the permissions of other users, you can do as long as you have the permissions to do by using below statement.

```sql
MariaDB > SHOW GRANTS FOR vinod@localhost;
```

</div>

<div id="ch16">

### How to change Root Password for MariaDB

Scenario:

You are working as MariaDB / MySQL DBA and you need you change the password for root. How would you do that?

Solution:

You can use mysqladmin command to change the password for root user. use below statement to change the password

```
shell > sudo mysqladmin -uroot -p password mynewpassword
```

Once you will hit enter, you will be asked to provide old password for root. Provide the password for root and hit Enter. 

You are all set to login to MariaDB by using new root password. Use below command to login to MariaDB


```
shell> mysql -u root -p
```

provide new password, in my case it was mynewpassword. 

</div>

<div id="sp">

```sql
--This is an example of stored procedure

-- delimiter command defines a new symbol or a bunch of symbols to be the new delimiter

-- To execute a SP, use the call command like below:
-- call get_product_count();

use northwind;
drop procedure if exists get_product_count;
drop procedure if exists get_order_total;
drop procedure if exists get_product_groups;

delimiter $$

-- procedure to get the total number of products
create procedure get_product_count()
begin
	select count(*) as product_count from PRODUCTS;
end $$


-- procedure to get order total for a given order_id
-- (example of IN, OUT parameters)
create procedure get_order_total(IN p_order_id int, OUT p_order_total double)
begin
	select sum(unit_price*quantity*(1-discount))
		into p_order_total
		from ORDER_DETAILS
		where order_id = p_order_id;

	if p_order_total is null then
		signal SQLSTATE '45001'
		set MESSAGE_TEXT = 'Invalid order id';
	end if;
end$$

-- procedure for demonstration of variables, if-else and loops
create procedure get_product_groups(group_count int, min_price double, max_price double)
begin
	-- variables must be declared before any executable statement begins
	declare min_pr_price double;
	declare max_pr_price double;
	declare diff double;
	declare i int default 1;

	select min(unit_price), max(unit_price)
		into min_pr_price, max_pr_price
		from PRODUCTS	
		where unit_price between min_price and max_price;

	set diff = (max_pr_price - min_pr_price) / group_count;
	
	while i <= group_count do
		select product_id, product_name, unit_price
			from PRODUCTS
			where unit_price between min_pr_price and min_pr_price+diff
			order by unit_price;
		set i = i+1;
		set min_pr_price = min_pr_price+diff;
	end while;
end$$

delimiter ;
```


</div>