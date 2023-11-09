# Troubleshooting
If the translation does not work despite uploading in the directory `/languages/`, it is certainly due to the system. Please check if the respective system translation is installed.

With `locale -a` a list with currently installed system languages is displayed.

To add a new system language, type `dpkg-reconfigure locales` and select the language you want to install. For hosting providers with many customers, we recommend installing all common system languages.
After a system language has been installed, `locale-gen` may have to be executed here.

# List available Languages
> fruithost language list

# Fetch all Strings
To get all localizable strings from fruithost, please type following command on terminal/shell:
> fruithost language scan

# Create a new Language
After using `fruithost language scan` command, the files `$code.template` will be created. Copy this file and rename it to your given language code (for sample `en_US.po` for american english or `de_DE.po` for german).

# How to Edit `.po` Files?
All language files in the `/panel/language/` and `/modules/<name>/language/` directory can be edited with an gettext-based editor like [POEDIT](https://poedit.net).
