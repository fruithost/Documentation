# Module Example

## File Structure
>
>⠀〰️ 📁 `/modules`
>
>⠀⠀⠀⠀〰️ 📁`/<name>`
>
>⠀⠀⠀⠀⠀⠀⠀⠀〰️ 📁`/languages`
>
>⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀📄 `<code>.po`
>
>⠀⠀⠀⠀⠀⠀⠀⠀〰️ 📁`/setup`
>
>⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀📄 `install.php`
>
>⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀📄 `deinstall.php`
>
>⠀⠀⠀⠀⠀⠀⠀📄 `module.package`
>
>⠀⠀⠀⠀⠀⠀⠀📄 `daemon.php`
>
>⠀⠀⠀⠀⠀⠀⠀📄 `module.php`

## `module.package`
```json
{
	"name":			"ExampleModule",
	"version":		"1.0.0",
	"category":		<NavigationCategory>,
	"icon":			<NavigationIcon>,
	"order":		<NavigationOrder>,
	"description":	"This is an description.",
	"author":		{
		"name":		"Your Name",
		"email":	<email>,
		"url":		<url>
	},
	"repository":	<github-url>
}
```

### Possible Values

| | | |
|-|-|-|
| `<NavigationCategory>` | `string` | Possible values: `ACCOUNT_MANAGEMENT`, `DATABASE_MANAGEMENT`, `DOMAIN_MANAGEMENT`, `MAIL_MANAGEMENT`, `FTP_MANAGEMENT`, `HOSTING_MANAGEMENT`, `EXTENDED_MANAGEMENT`, `SUPPORT_MANAGEMENT`, `ADMIN_MANAGEMENT`, `SERVER_MANAGEMENT` |
| `<NavigationIcon>` | `string` | A `name` of an [Material Icon](https://fonts.google.com/icons?icon.set=Material+Icons) |
| `<NavigationOrder>` | `int` | The position of the module in the navigation |

## `module.php`

```php
<?php
	use fruithost\ModuleInterface;

	class ExampleModule extends ModuleInterface {
		public function init() {
			/*
                		Is called up when the module is initialized by the module manager.

               			Not all methods are available at this point and there is no guarantee that another module is already accessible here.
            		*/
		}
		
        	public function preLoad() {
			/*
                		Is called up shortly before the module is actively used.
            		*/
		}

		public function load() {
			/*
                		Is called up as soon as the module is actively used (for example by calling it up via the menu).
            		*/
		}
		
		public function onPOST($data = []) {
			/*
                		This is called when a POST request is fired on the module page.
           		*/
		}
		
		public function content() {
			/*
                		The content of the module that is displayed/output in the UI.
            		*/
		}
	}
?>
```

## `setup/install.php` & `setup/deinstall.php`
A PHP file that is used/called as soon as the module is installed or uninstalled by the system administrator. Database operations can be carried out here, for example.

> [!WARNING]
> Currently, these files are executed with root rights of the [Daemon](https://github.com/fruithost/Binary). The behavior may be changed in future versions.

To install the module, enter the following command via Shell:
> fruithost install <name>

To uninstall the module, enter the following command via Shell:
> fruithost deinstall <name>

A module can be activated with the following command:
> fruithost enable <name>

or deactivated:
> fruithost disable <name>

## `daemon.php`
This file is called up by the [Daemon](https://github.com/fruithost/Binary) every minute. Batch processing that does not take place in the user's UI can take place here, for example.

> [!WARNING]
> Currently, these file are executed with root rights of the [Daemon](https://github.com/fruithost/Binary). The behavior may be changed in future versions.
