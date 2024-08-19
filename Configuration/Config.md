# Configuration
This is the default configuration of Fruithost.

Path: `/etc/fruithost/.config.php`

```php
<?php
	# Database Connection
	define('DATABASE_HOSTNAME',		'localhost');
	define('DATABASE_PORT',			3306);
	define('DATABASE_USERNAME',		<username>);
	define('DATABASE_PASSWORD',		<password>);
	define('DATABASE_NAME',			<database>);
	define('DATABASE_PREFIX',		'fh_');

	# Paths
	define('HOST_PATH',			'/var/fruithost/users/');
	define('CONFIG_PATH',			'/var/fruithost/config/');	# @since 1.0.4
	define('LOG_PATH',			'/var/fruithost/logs/');
?>
```
