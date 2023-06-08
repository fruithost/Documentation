# Troubleshooting
If the translation does not work despite uploading in the directory `/languages/`, it is certainly due to the system. Please check if the respective system translation is installed.

With `locale -a` a list with currently installed system languages is displayed.

To add a new system language, type `dpkg-reconfigure locales` and select the language you want to install. For hosting providers with many customers, we recommend installing all common system languages.
