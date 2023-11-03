# Modules Repository
You can use own repositorys for your modules.

So that you can use your own Git repositories, this must contain a special structure:
```
L /<module>/
  L [...]
  L /module.package
L /modules.packages/
  L <module>.zip
L /modules.list
```

## File: `modules.list`
The `modules.list` is located in the **main directory** and provides all currently usable modules that are located in the `<module>` folder of the same name. In addition to this, the packed module for installation exists as a ZIP archive in the `modules.packages` folder

## Folder: `modules.packages`
This directory contains only ready-to-install modules that are stored in a ZIP archive.

## Folder: `<modules>`
The source code of a module. This contains at least the `module.package` file with the following contents:
```!json
{
	"name":			"Modulename",
	"version":		"0.0.1",
	"category":		"EXTENDED_MANAGEMENT",
	"icon":			"network_check",
	"order":		1,
	"description":	"Description of your module..",
	"author":		{
		"name":		"Your Name",
		"email":	"mail@example.com",
		"url":		"https://example.com"
	},
	"repository":	"https://github.com/<username>/<repository>"
}
```

## Content of a Module
Please visit the [Module-Documentation](#).

## Sample Repository
Feel free to look into [our Modules Repository](https://github.com/fruithost/Modules). Here you can find a productive sample of:
- [`<modules>`](https://github.com/fruithost/Modules/tree/master/faq) Folder
- [`modules.packages`](https://github.com/fruithost/Modules/tree/master/modules.packages) Folder
- [`modules.list`](https://github.com/fruithost/Modules/blob/master/modules.list) Folder
