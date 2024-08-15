# Automatic installation
The simplest way to install the fruithost infrastructure is, to execute following shell script:

## Preparations `Optional`
Before the installation script can be used, `curl` must be installed:
```shell
apt-get update
apt-get install curl
```

## Install

```shell
bash <(curl -L -o- https://update.fruithost.de/install || wget -O - https://update.fruithost.de/install)
```

#### Compatibility
Currently only the distribution `Ubuntu` and `Debian` is supported. An installation on other derivatives is possible, but may lead to package compatibility problems.

Following Linux-Distributions are fully checked:
| Name | Version | Infos |
|------|---------|-------|
| Ubuntu | 22.04 (LTS) | ** ProFTPD-Modules not available |

> [!NOTE]
> We recommend that you carry out the [installation manually](Manual%20Installation.md) if you are using an unsupported system.
