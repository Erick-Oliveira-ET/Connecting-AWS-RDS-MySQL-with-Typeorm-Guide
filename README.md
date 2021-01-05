# Connecting AWS RDS MySQL with Typeorm Guide

I had a tough time trying to figure out how to do the connection between Typeorm, a ORM node module, and the Amazon Relational Database Service's (RDS) MySQL/MariaDB because, surprisingly there isn't an specific tutorial for that. So, here I am in the hope to help someone with the same problem.

First, it's necessary to create the database. For that, access the [rds home page](aws.amazon.com/rds/home), click in create database and the options are - most of then are the default setting, you can change the name and chose the password, BUT DON'T FORGET THE FREE TIER OPTION THIS DATABASES ARE EXPENSIVE:

After everything, just click in create database and wait the database be generated. After that, go to the database and, in the connectivity & security, go to the VPC Security groups and click the option that appears. In the new page, make sure the option with the VPC ID matches the VPC of your database - if you just have one database you'll probably just have one VPC and one Security Group Option. In the bottom of this page, there's some tabs: go to inbound and click edit it. In origin type select "My IP", type "MySQL/Aurora" and save.

Now, important part. TypeORM needs a config for MySQL to work named "database". This field is refering to the schema inside the database created. However, there's nothing inside the database. To fix that problem, you open the MySQL WorkBench, connect a new database using the host, username, password and port and when created the connection, create a new schema and use the name of that schema on the TypeORM's database field. 

That's the end. Thank you for the attention.
