# An ansible role for setting up a mysql server [![Build Status](https://travis-ci.com/mafalb/ansible-mysql.svg?branch=master)](https://travis-ci.com/mafalb/ansible-mysql)

## Basic Usage

```
- hosts: localhost
  roles:
    - role: mafalb.mysql/dump
```

```
- hosts: localhost
  roles:
  - role: mafalb.mysql/server
    mysql_type: mysql_community
    mysql_version: 5.5
```

## Variables

```
mysql_dump:

  with_content:

    - name: xxx
      databases:
        - db2           # these are dumped with lock-all-tables
        - db3           # into file xxx.sql

    - name: yyy     #  db4 and db5 will dump into file yyy.sql
      databases:
          - db4
          - db5
        
  without_content:      # dumped with --no-data, i.e. only the tables structure

    - databases:                
        - db5           # database db5 will dump into file db5.sql

    - name: db8
      databases:
        - db8           # database db8 will dump into file db8.sql

    - name: zzz
      databases:
        - db6           # databases db6 and db7
        - db7           # will dump into file zzz.sql

  exclude:              # won't dump at all
    databases:
      - db9
      - db10
```

in the above structure, every database not mentioned will be backuped into a separate file named after the database.sql
e.g. mysql system database will dump into mysql.sql

## License

GPLv3

