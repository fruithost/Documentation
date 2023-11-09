
# Manual installation
To install all components manual, follow these steps:

> **INFORMATION:** This document may be out of date.

### Update the system

```shell
# Pre_Config
apt-get update
apt-get upgrade
apt-get dist-upgrade
apt-get install dnsutils git tzdata
dpkg-reconfigure tzdata
apt-get install sudo vim make zip unzip chkconfig bash-completion curl dbus
export DEBIAN_FRONTEND=noninteractive
```

### Add user
```shell
# fruithost User
groupadd -g 1010 fruithost
useradd -u 1010 -s /bin/false -d /bin/null -g fruithost fruithost
```

### Set hostname
Set `$DOMAIN` to your hosting domain name (for sample `freehost24.com`)
```shell
# Set hostname
hostname $DOMAIN
echo "127.0.0.1      $DOMAIN" >> /etc/hosts
hostnamectl set-hostname "$DOMAIN"
```

### Install webserver (`Apache`, `nginx` is currently not supported!)
```shell
# Webserver
apt-get install apache2 -y
apache2 -v
```

### MySQL (we recommend `MariaDB` insteadf of `MySQL`)
```shell
# Adding MariaDB Repository
sudo apt-get install apt-transport-https curl
sudo mkdir -p /etc/apt/keyrings
sudo curl -o /etc/apt/keyrings/mariadb-keyring.pgp 'https://mariadb.org/mariadb_release_signing_key.pgp'
```
Adding following lines to your `/etc/apt/sources.list`
```shell
deb [signed-by=/etc/apt/keyrings/mariadb-keyring.pgp] https://mirror.23m.com/mariadb/repo/10.11/debian bullseye main
```

```shell
# Install MariaDB
sudo apt-get update
sudo apt-get install mariadb-server
```

```shell
# Testing the database server
mysql -u root -p"$mysqlpassword" -e "DROP DATABASE IF EXISTS test";
```

Please be sure to backup the following file: `/etc/mysql/my.cnf` and add an symlink to
`/etc/fruithost/config/mysql/global.cnf`

### Install PHP (we recommend `PHP 8.2`)
```shell
sudo apt -y install lsb-release apt-transport-https ca-certificates
sudo wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg
echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/php8.2.list
sudo apt update
sudo apt upgrade
sudo apt -y install php8.2
sudo apt install php8.2-bcmath php8.2-bz2 php8.2-cli php8.2-curl php8.2-dba php8.2-fpm php8.2-gd php8.2-gmp php8.2-imap php8.2-interbase php8.2-intl php8.2-ldap php8.2-mbstring php8.2-mysql php8.2-odbc php8.2-pgsql php8.2-snmp php8.2-soap php8.2-sqlite3 php8.2-sybase php8.2-xmlrpc php8.2-xsl php8.2-zip
sudo apt install php8.2-dev php-pear libz-dev
```

### Install google protobuf extension (Optional)
```shell
# google-protobuf extension
pecl channel-update pecl.php.net
pecl install grpc
```

### Configure `PHP 8.2` with `Apache 2`
```shell
# PHP-FPM & Apache
a2enmod proxy_fcgi setenvif headers
a2enconf php8.2-fpm
a2enmod actions fastcgi alias ssl rewrite
a2dismod php8.2
service apache2 restart
```

### Install FTP (we recommend `proFTP` because it has MySQL connection plugins)
```shell
apt-get install proftpd proftpd-mod-mysql (as inetd)
groupadd -g 2001 ftpd
useradd -u 2001 -s /bin/false -d /bin/null -g ftpd ftpd
```

### Install protected directorys on `Apache 2`
```shell
# protected dirs for apache2
apt-get install apache2-utils libaprutil1 libaprutil1-dbd-mysql
a2enmod authn_socache dbd authn_dbd authn_dbm
service apache2 restart
```

### Install RSyslog
```shell
# RSyslog
apt-get install rsyslog rsyslog-mysql 
```

If you following these steps, all recommended software is preinstalled for `fruithost`.
After pre-installation, you must upload all `fruithost` files and configure all necessary endpoints.
