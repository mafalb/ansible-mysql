# An ansible role for setting up a mysql server [![Build Status](https://travis-ci.com/mafalb/ansible-mysql.svg?branch=master)](https://travis-ci.com/mafalb/ansible-mysql)

## Basic Usage

```
# install default mariadb/mysql server
#
- hosts: localhost
  roles:
    - role: mafalb.mysql/server
```

## Variables

```
mafalb_mysql_server_package: mariadb_server
```

The name of the package. Platform specific sensible defaults are set by this role.

## License

GPLv3

