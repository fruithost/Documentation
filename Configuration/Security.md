# Configuration
Salts that are used in the system are stored here. These are used to encrypt critical data. Each system has its own salts, which are unique.

> [!WARNING]
> Changing the salts breaks the system. If the values are changed after installation, it is no longer possible to log in, for example.

Path: `/etc/fruithost/.security.php`

```php
<?php
	# DO NOT MODIFY, IT WILL BREAKS ALL YOUR DATA!

	define('MYSQL_PASSWORTD_SALT',	<salt>);
	define('RESET_PASSWORD_SALT',	<salt>);
	define('ENCRYPTION_SALT',	<salt>);
?>
```
