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
To create an new Language file, please type follwing command:
> fruithost language add xx_XX

**xx_XX** is the language code for your country. For sample america has `en_US`, germany has `de_DE`,..

# How to Edit `.po` Files?
All language files in the `/language/` directory can be edited with an gettext-based editor like [POEDIT](https://poedit.net).
