# Automatic installation
The simplest way to install the fruithost infrastructure is, to execute following shell script:

## Pre-Installation
```shell
apt update && apt install curl
```

## Install
The installation **takes up to 15 minutes**, depending on the Internet connection and CPU/RAM of the target server.

```shell
bash <(curl -L -s -o- https://update.fruithost.de/install)
```

#### Requirements
> [!NOTE]
> 
> This refers exclusively to the web panel; user-specific PHP versions for hosting users can be changed at any time.
> 
The fruithost-Panel needs **minimum** `PHP 8.1`.

#### Compatibility
Currently only the distribution `Ubuntu` and `Debian` is supported. An installation on other derivatives is possible, but may lead to package compatibility problems.

Following Linux-Distributions can be used:
| Compatiblity | Name | Version |
|--------------|------|---------|
|     |        |       |
| ✅ | Debian | 13 (trixie) |
| ✅ | Debian | 12.5 (bookworm) |
|     |        |       |
| ✅ | Ubuntu | 24.04 LTS (Noble Numbat) |
| ✅ | Ubuntu | 22.04.4 LTS (Jammy Jellyfish) |
| ⚠️ | Ubuntu* | 20.04.6 LTS (Focal Fossa) |
| ⛔ | Ubuntu | **OUTDATED:** 18.04.6 LTS (Bionic Beaver) |


\* **ProFTPD** will not run here, bcause for these distributions are missing mods there are not on official ubuntu-repositorys.

> [!NOTE]
> We recommend that you carry out the [installation manually](Manual%20Installation.md) if you are using an unsupported system.
