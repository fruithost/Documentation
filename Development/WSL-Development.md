
Here is a guide on how to install fruithost as a development environment. The prerequisite is that your `Windows` machine supports the **Windows Subsystem for Linux** (`WSL`).

We recommend using [**Windows Terminal**](https://www.microsoft.com/store/productId/9N0DX20HK701?ocid=pdpshare).

### 1️⃣ [`WSL Installation`] Install Debian 12 (Bookworm)
Enter the following command:
> wsl --install --distribution Debian

Follow the instructions (if `WSL` has been started for the first time, restart your system later - you will receive restart information on this later).
Enter your user name and password and close the `WSL` window (not the `Windows Terminal`!).

### 2️⃣ [`WSL Configuration`] Set some Settings
#### Upgrade Version to `WSL2`
The `Version 1` of `WSL` is often set by default. Use the following command to switch to `Version 2`:
> wsl --set-default-version 2

#### Set Debian as default Distribution _`[Optional]`_
If you only enter `wsl` in the `Windows Terminal`, you can directly access the `Debian` system, otherwise the distribution must always be specified with the `-d Debian` parameter in the `WSL` command.
> wsl --set-default Debian

### 3️⃣ [`Debian`]  Configure the system
#### Login with root
First enter the command `wsl --user root` in the `Windows Terminal`. This starts `Debian` and you log in with the user name **root**. 

Note that the next steps must be carried out **only** with the user `root`, as you need admin rights to set up the system.

#### Set a password for root
> [!WARNING]
> ❗ Only for **development** ❗
> You will need the password later if you want to connect to the system with **MySQL** or the **SFTP** client.

Enter the following command and follow the instructions.
> passwd

#### Change hostname
For the development environment, we assume that the **my.fruit** domain is used. The `fruithost` panel can be accessed after installation via the web address [http://my.fruit/](http://my.fruit/).

> hostname my.fruit
> hostnamectl set-hostname my.fruit
> nano /etc/hosts

![IMAGE_HOST_CONFIG]

####  Restart Networking
We restart the network interfaces so that the set host name is adopted:
> sudo /etc/init.d/networking restart

#### Check IP-Address of Debian
> ip address

![IMAGE_IP_ADDRESS]

Make a note of this **IP address**, as this is the IP of the `Debian` system. The entire server can be reached from here.

#### Hinzufügen der Dienste (Auto-Start)
Since `Debian` does not have an active program service running under `WSL` by default, we need to edit two files to make `Debian` run automatically with `systemd`.

Follow the instructions below:
https://github.com/fruithost/Documentation/blob/main/WSL2.md

### 4️⃣ [`Debian`]  Pre-Installation
#### Install CURL
> apt update
> apt install curl

### 5️⃣ [`fruithost`] Start the installer
Enter the installation command (as already described in the normal [installation instructions](https://github.com/fruithost/Documentation/blob/main/Installation.md)) and follow the instructions:
> curl -o- https://raw.githubusercontent.com/fruithost/Installers/master/debian.sh | bash

The installation takes some time (**about 10 - 20 minutes**) because a brand new installed system has to be updated and some packages are automatically compiled by packet-manager.

#### Fix the hostname
Look in the VirtualHost from the panel to see whether the host name was taken over during installation, as the system is not a real root server, this information, which is automatically available from a hosting provider, is missing:

> nano /etc/fruithost/config/apache2/panel.conf

![IMAGE_HOST_PANEL]

Check if the Hostname `my.fruit` was successfully written, otherwise correct it.

After a change, restart the webserver with following command:
> service apache2 restart

Now you can open [http://my.fruit/](http://my.fruit/) on your webbrowser and log in to your account.

### 6️⃣ [`Windows`]  Registering domains for development
Open **with administrator privileges** the File `C:\Windows\System32\drivers\etc\hosts` with an Code-Editor (for Sample `Notepad++`).

And add developing domains to the hostfile, based on the given **IP address** from `Debian` (as in 3️⃣ ["Check IP-Address of Debian"] described):
```
# Panel-Domain
172.24.71.136 my.fruit

# Sample Domains for Testing
172.24.71.136 example1.fruit
172.24.71.136 example2.fruit
172.24.71.136 example3.fruit
172.24.71.136 example4.fruit
172.24.71.136 example5.fruit
```
#### Congratulations, you're done!

# Additional things
### Installing SSH for remote connect
> apt install ssh

Change configuration of SSH
> nano /etc/ssh/sshd_config

Add following lines (or modify the lines where the options are given):
```
PermitRootLogin yes
```
And restarting ssh:
> service ssh restart

### Modify MySQL to access outside via Root
> nano /etc/mysql/mariadb.conf.d/50-server.cnf

Add following lines (or modify the lines where the options are given):
```
#bind-address 127.0.0.1
```
And restart mysql:
> service mariadb restart

Log into mysql:
> mysql -u root
> use mysql; GRANT ALL ON *.* to 'root'@'%' IDENTIFIED BY '&lt;YourRootPassword&gt;' WITH GRANT OPTION;
> FLUSH PRIVILEGES;
> exit;

[IMAGE_IP_ADDRESS]: https://github.com/fruithost/Documentation/blob/main/Images/IMAGE_IP_ADDRESS.PNG
[IMAGE_HOST_CONFIG]: https://github.com/fruithost/Documentation/blob/main/Images/IMAGE_HOST_CONFIG.PNG
[IMAGE_HOST_PANEL]: https://raw.githubusercontent.com/fruithost/Documentation/main/Images/IMAGE_HOST_PANEL.PNG

