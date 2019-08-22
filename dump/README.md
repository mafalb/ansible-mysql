# An ansible role for setting up a mysql server [![Build Status](https://travis-ci.com/mafalb/ansible-mysql.svg?branch=master)](https://travis-ci.com/mafalb/ansible-mysql)

## Basic Usage

```
- hosts: localhost
  roles:
    - role: mafalb.mysql/dump
```

```
- hosts: localhost
  vars:
    mysql_dump_sftp_server: some_sftp_server.example.com
  roles:
    - role: mafalb.mysql/dump
```

## Variables

```
mysql_dump_sftp_server: some_sftp_server.example.com
```
data will be dumped into a directory Documents/mysql on the sftp server

- - -

```
mysql_dump:

    - name: xxx
      databases:
        - db2           # these are dumped with lock-all-tables
        - db3           # into file xxx.sql

    - name: yyy         #  db4 and db5 will dump into file yyy.sql
      databases:
          - db4
          - db5
        
    - databases:                
        - db5           # database db5 will dump into file db5.sql
      options:
        - --no-data     # dumped with --no-data, i.e. only the tables structure
                        # you should be able to give any mysql command line option

    - name: db8
      databases:
        - db8           # database db8 will dump into file db8.sql

    - name: zzz
      databases:
        - db6           # databases db6 and db7
        - db7           # will dump into file zzz.sql

    - exclude: True
      databases:
        - these
        - databases
        - wont
        - dump
```

in the above structure, every database not mentioned will be backuped into a separate file named after the database.sql
e.g. mysql system database will dump into mysql.sql

## License

GPLv3

