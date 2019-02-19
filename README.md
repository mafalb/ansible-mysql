# An ansible role for setting up a mysql server [![Build Status](https://travis-ci.com/mafalb/ansible-mysql.svg?branch=master)](https://travis-ci.com/mafalb/ansible-mysql)

## Basic Usage

```
- hosts: localhost
  roles:
    - role: mafalb.mysql/server
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
mysql_type: default
```
The type of mysql to be installed

- default: the mysql that comes with your Operating System
- mysql_community: the mysql as provided by Oracle

```
mysql_version: 5.5
```

For ```mysql_type: default``` it does not make sense to specify an explicit version
For ```mysql_type: mysql_community``` this role is only tested with 5.5 (for now)

## License

GPLv3

