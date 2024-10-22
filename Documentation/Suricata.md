# Suricata Installation Guide

This guide covers the steps to install, upgrade, and remove Suricata on your system.

## 1. Install Required Packages

First, install the `software-properties-common` package, which allows you to manage software sources:

``` bash
sudo apt-get install software-properties-common
```
2. Add Suricata PPA

To ensure you get the latest stable version of Suricata, add the official Suricata PPA (Personal Package Archive):

bash

sudo add-apt-repository ppa:oisf/suricata-stable

3. Update the Package List

Update your package lists to reflect the newly added Suricata repository:

bash

sudo apt-get update

4. Install Suricata

Now, install the latest stable version of Suricata:

bash

sudo apt-get install suricata

After installation, you can proceed with configuring Suricata as part of your setup.
Upgrading Suricata

To upgrade Suricata to the latest version, run the following commands:

bash

sudo apt-get update
sudo apt-get upgrade suricata

Removing Suricata

If you need to uninstall Suricata from your system, use this command:

bash

sudo apt-get remove suricata

For further information on Suricata and its setup, you can visit the official OISF Launchpad.
