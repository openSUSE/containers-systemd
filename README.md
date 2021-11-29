# Systemd service files to run container via systemd and podman

This repository contains various systemd service and configuration files
to run openSUSE container via podman controlled by systemd.

Currently supported are:
  * bind
  * dhcp-server
  * dhcp6-server
  * dovecot
  * fetchmail
  * haproxy
  * mariadb
  * minidlna
  * nginx
  * openldap
  * postfix
  * roundcube
  * samba
  * spamassassin
  * squid
  * wsdd

Additional, there is the `container-image-prune.timer` to cleanup
unnamed images once a day. 

## bind

  * /usr/etc/default/container-bind contains generic settings
  * /etc/default/container-bind is for the admin to overwrite them

## dhcp-server/dhcp6-server

  * /usr/etc/default/container-dhcp contains generic settings for the dhcpd4 and dhcpd6 daemons. It is required to set DHCPD_INTERFACES. During the first start, example ${CONFIG_DIR}/dhcpd.conf or ${CONFIG_DIR}/dhcpd6.conf are created.
  * /etc/default/container-dhcp is for the admin to overwrite them

## dovecot

  * /usr/etc/default/container-dovecot contains generic settings
  * /etc/default/container-dovecot is for the admin to overwrite them

## fetchmail

  * /usr/etc/default/container-fetchmail contains generic settings
  * /etc/default/container-fetchmail is for the admin to overwrite them

## haproxy

  * /usr/etc/default/container-haproxy contains generic settings
  * /etc/default/container-haproxy is for the admin to overwrite them

## mariadb

  * /usr/etc/default/container-mariadb contains generic settings
  * /etc/default/container-mariadb is for the admin to overwrite them
  * /etc/mariadb-secrets contain files for the first start to setup the mariadb database and can be changed via SECRETS_DIR in the /etc/default/container-mariadb file. They are only read if mariadb needs to initialize the data the first time. They should not be readable and deleted after the initialization was successfull, so that nobody can steal them.
    * ${SECRETS_DIR}/MYSQL_ROOT_PASSWORD (required)
    * ${SECRETS_DIR}/MYSQL_ROOT_HOST
    * ${SECRETS_DIR}/MYSQL_DATABASE
    * ${SECRETS_DIR}/MYSQL_USER
    * ${SECRETS_DIR}/MYSQL_PASSWORD

## minidlna

  * /usr/etc/default/container-minidlna contains generic settings
  * /etc/default/container-minidlna is for the admin to overwrite them

## nginx

  * /usr/etc/default/container-nginx contains generic settings
  * /etc/default/container-nginx is for the admin to overwrite them

## openldap

  * /usr/etc/default/container-openldap contains generic settings
  * /etc/default/container-openldap is for the admin to overwrite them
  * /etc/openldap-secrets contain files for the first start to setup the openldap database and can be changed via SECRETS_DIR in the /etc/default/container-openldap file. They are only read if database needs to be initialized the first time. They should not be readable and deleted after the initialization was successfull, so that nobody can steal them.
    * ${SECRETS_DIR}/LDAP_ADMIN_PASSWORD (required)
    * ${SECRETS_DIR}/LDAP_CONFIG_PASSWORD (required)

## postfix

  * /usr/etc/default/container-postfix contains generic settings
  * /etc/default/container-postfix is for the admin to overwrite them

## roundcube

  * /usr/etc/default/container-roundcube contains generic settings
  * /etc/default/container-roundcube is for the admin to overwrite them

## spamassassin

  * /usr/etc/default/container-spamassassin contains generic settings
  * /etc/default/container-spamassassin is for the admin to overwrite them

## squid

  * /usr/etc/default/container-squid contains generic settings
  * /etc/default/container-squid is for the admin to overwrite them


