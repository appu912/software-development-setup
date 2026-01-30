# PostgreSQL setup on Ubuntu/Debian

*PostgreSQL is an open-source Object-relational database management system (ORDBMS).*

### Installation

1. Since we are on ubuntu which is debian based, we can use the apt repository for installation. Its an advanced package tool.
2. So the first step is to update the apt repository using the below command.
```console
user@ubuntu:~$ sudo apt update
```
3. Now we can install postgres using the below command.
```console
user@ubuntu:~$ sudo apt install postgresql
```
4. Check if postgresql is correctly installed using the below command.
```console
user@ubuntu:~$ psql --version
```
5. You will see the following output. It means that postgresql version 16 is installed.
```console
psql (PostgreSQL) 16.11 (Ubuntu 16.11-0ubuntu0.24.04.1)
```

### Running postgresql

1. After installing postgresql, we'll check if the postgresql server is running or not. Execute the below system command.
```console
user@ubuntu:~$ sudo systemctl status postgresql@16-main.service
```
2. You'll see something like this in the output.
```console
Active: active (running)
```
3. This means your server is running properly.
4. Now postgresql provides an admin user `postgres` which can create, update, modify and delete databases. So we'll login into the terminal using this user. Execute the below command.
```console
user@ubuntu:~$ sudo -i -u postgres
```
5. This will switch your shell user to postgres user. Your terminal will look something like this.
```console
postgres@ubuntu:~$
```
6. Now you can use psql to connect to some database, create tables, schemas etc.
```console
postgres@ubuntu:~$ psql
```
7. Now you'll enter the interactive mode.
```console
postgres=#
```
