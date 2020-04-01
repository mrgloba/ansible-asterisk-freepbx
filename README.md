asterisk-freepbx
=========

Installs and configures Asterisk and FreePBX

Requirements
------------

Debian 10 (Buster). On other versions is not yet tested.

Role Variables
--------------

##### NodeJS
	nodejs_upstream: true
Installs from upstream or use distro repositories.

	nodejs_upstream_version: 10
If installs from upstream, require version number.
##### ODBC Connector
	odbc_install_srcdir: /usr/src/mariadb-connector-odbc

TMP folder for sources.

	odbc_install_version: 3.1.6
	odbc_install_prefix: /usr/local

##### Asterisk

	asterisk_db_name: asterisk
	asterisk_cdrdb_name: asteriskcdrdb
	asterisk_db_user: asterisk
	asterisk_db_pass: asteriskPassw0rd
	asterisk_user: asterisk
	asterisk_group: asterisk
	asterisk_user_home: /var/lib/asterisk
	asterisk_install_srcdir: /usr/src/ansible_asterisk/

TMP folder for sources

	asterisk_version: 16

Currently tested only with 16 version

##### MariaDB

	mysql_host: localhost

Use internal or external MariaDB server

	mysql_install: true

Install internal MariaDB server

	mysql_root_user: root
	mysql_root_pass: ""

You can set root password of existing DB server or live it blank for install internal DB server

	mysql_socket: /var/run/mysqld/mysqld.sock

##### FreePBX

	freepbx_srcdir: /usr/src/ansible_freepbx

TMP folder for sources

	freepbx_http_root: /var/www/html
	freepbx_install_ucp: false

Installs User Control Panel module

	freepbx_version: 15

Which version of FreePBX need to install. Currently support 14 an 15 only

Dependencies
------------

No dependencies

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - mrgloba.ansible_asterisk_freepbx

License
-------

MIT

