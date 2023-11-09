# Additional Mail-Configuration
If you host not prepared for sending mails (e.g. `sendmail`), you can add the `[optional]` mail configuration.

Path: `/etc/fruithost/.mail.php`

```php
<?php
	define('MAIL_EXTERNAL', true);
	define('MAIL_HOSTNAME', <hostname>);
	define('MAIL_PORT', 	25);
	define('MAIL_USERNAME', <username>); // Mostly your E-Mail Address
	define('MAIL_PASSWORD', <Password>);
?>
```
