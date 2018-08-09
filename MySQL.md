ssh jumpbox.yoursite.com
[username@name ~]$ ssh db.env.yoursite.com

[username@name ~]$ mysql -u iluciano -p
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g...

// If you have multiples dbs, select the one you want to use
mysql> use yourdb_name

// Your db is ready to be queried
Database changed
mysql>
