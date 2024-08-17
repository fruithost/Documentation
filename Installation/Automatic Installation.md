# Automatic installation
The simplest way to install the fruithost infrastructure is, to execute following shell script:

## Install
The installation **takes up to 15 minutes**, depending on the Internet connection and CPU/RAM of the target server.

```shell
bash <(curl -L -o- https://update.fruithost.de/install || wget -O - https://update.fruithost.de/install)
```

#### Compatibility
Currently only the distribution `Ubuntu` and `Debian` is supported. An installation on other derivatives is possible, but may lead to package compatibility problems.

Following Linux-Distributions are fully checked:
| Compatiblity | Name | Version |
|--------------|------|---------|
| ✅ | Ubuntu | 24.04 LTS (Noble Numbat) |
| ✅ | Ubuntu | 22.04.4 LTS (Jammy Jellyfish) |
| ⚠️ | Ubuntu* | 20.04.6 LTS (Focal Fossa) |
| ⚠️ | Ubuntu*, ** | 18.04.6 LTS (Bionic Beaver) |


\* **ProFTPD** will not run here, bcause for these distributions are missing mods there are not on official ubuntu-repositorys.

** Newer versions from **PHP** are currently not supported. Max Version is `7.2`!

> [!NOTE]
> We recommend that you carry out the [installation manually](Manual%20Installation.md) if you are using an unsupported system.
