# wmcp-skystrata-dev

## Description

Rapid development environment for the SkyStrata project for ProKarma.

## Installation

### Pre-Requisites

Download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) and [Vagrant](https://www.vagrantup.com/downloads.html)

### Quick Start

#### Starting Vagrant (Virtual box)
Clone this repo to your project file, then execute:

```
vagrant up
```

This will use the `Vagrantfile` to set ports, synced directories, and provision scripts:

```
/scripts/vagrant-utils.sh 
```

Installs system updates, Docker and Docker Compose, NVM (version 10) and two shell scripts, `/usr/local/bin/dev` and `/usr/local/run` 


#### Getting into the Vagrant box with SSH

Once the machine has been created and provisioned run the following 

```
vagrant ssh // when prompted for a password, use `vagrant`
```

Once inside the vagrant shell you will see the current directory copied to the `/vagrant` directory. From this root directory:

```
cd repos/web
npm install -g next react react-dom
npm install --no-bin-links
npm run dev
```

## Windows users

For Windows users, you must set the Intel Virtualization options to `ENABLED` in BIOS, and check the `Settings -> Windows Features -> Hyper-V` to make sure they are off. [See this article](https://stackoverflow.com/questions/37955942/vagrant-up-vboxmanage-exe-error-vt-x-is-not-available-verr-vmx-no-vmx-code)

For NodeJS and NPM, see the following:

[Install Node for Windows 10](https://blog.risingstack.com/node-js-windows-10-tutorial/)
which points to
[Command Line Upgrade Node for Windows](https://github.com/felixrieseberg/npm-windows-upgrade#usage)

When installing the packages, use the `--no-bin-links` flag to prevent an `EPROTO: protocol error` on symlinks

Python py_copcg errors: 
`pip install git+https://github.com/nwcell/psycopg2-windows.git@win64-py34#egg=psycopg2`