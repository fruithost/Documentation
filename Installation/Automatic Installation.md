# Automatic installation
The simplest way to install the fruithost infrastructure is, to execute following shell script:

## Preparations
Before the installation script can be used, `curl` must be installed:
```shell
apt-get update
apt-get install curl
```

## Install

```shell
curl -o- https://raw.githubusercontent.com/fruithost/Installers/master/debian.sh | bash
```

#### Compatibility
Currently only the distribution `Debian` is supported. An installation on `Ubuntu` (or other derivatives) is possible, but may lead to package compatibility problems.

> We recommend that you carry out the [installation manually](Manual Installation.md) if you are using an unsupported system.