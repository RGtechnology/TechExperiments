# Install OPNsense

## Boot from Installation Media
Insert the ISO image into the virtual CD/DVD drive of the previously created virtual machine, then power it on. Use the Proxmox console to do the installation.

![OPNsense Installer | boot](images/01-OPNsense-install.png)

## Start Installation

Log in as the user `installer` with the password `OPNsense` to proceed the installation.

![OPNsense Installer | login](images/02-OPNsense-install-login.png)

## Select Keyboard Layout

Choose your preferred keyboard layout from the list.

![OPNsense Installer | keyboard layout](images/03-OPNsense-install-keyboard.png)

## Configure Disk

Select the disk where you want to install OPNsense. Choose the appropriate disk formatting option.

![OPNsense Installer | Disk Format](images/04-OPNsense-install-disk-format.png)
![OPNsense Installer | Select Disk](images/05-OPNsense-install-disk-select.png)
![OPNsense Installer | Configure Swap](images/06-OPNsense-install-ufs-config.png)
![OPNsense Installer | UFS Configuration](images/07-OPNsense-install-ufs-config-confirm.png)

## Installation Progress
The installation process will begin. This may take a few minutes.

![OPNsense Installer | Progress](images/08-OPNsense-install-progress.png)

## Change Root Password

Once the installation is complete, choose the option to change the root password.

![OPNsense Installer | Change Root Password](images/09-OPNsense-install-password.png)

## Reboot System

Reboot the system to complete the installation.

![OPNsense Installer | Reboot](images/10-OPNsense-install-reboot.png)

## Initial Login

After rebooting, log in as the user `root` and the password you set earlier.

![OPNsense Installer | login](images/11-OPNsense-install-login.png)

## Assign Interfaces

Assign the network interfaces (e.g., WAN, LAN) as per your network setup.

![OPNsense Installer | Assign Interfaces](images/12-OPNsense-assign-interfaces.png)
![OPNsense Installer | Assign Interfaces-2](images/13-OPNsense-assign-interfaces-2.png)

## Initial Configuration

![OPNsense Installer | Finished](images/14-OPNsense-finished.png)

Your OPNsense firewall is now ready to use! From this point, [continue with the initial configuration](../3-initial-opnsense-configuration/README.md) in a browser window.
