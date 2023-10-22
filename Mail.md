# Additional Mail-Configuration
If you host not prepared for sending mails (e.g. `sendmail`), you can add the `[optional]` mail configuration.

Path: `/etc/fruithost/.mail.php`

```php
<?php
	define('MAIL_EXTERNAL', true);
	define('MAIL_HOSTNAME', 'smtp.yourhost.com');
	define('MAIL_PORT', 	25);
	define('MAIL_USERNAME', 'no-reply@yourhost.com');
	define('MAIL_PASSWORD', '<Password>');
?>
```
