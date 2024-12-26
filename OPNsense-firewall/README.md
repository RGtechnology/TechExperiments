# OPNsense Firewall on Proxmox

In this TechExperiment, we will create an OPNsense firewall as a virtual machine (VM) on Proxmox, using a modem/router from your internet provider configured with DHCP.

![TechExperiment | OPNsense environment overview](images/OPNsense-environment-overview.png)


## Prerequisites
- A [Proxmox VE (Virtual Environment)](https://proxmox.com/en/downloads) server
- A modem/router from your internet provider with DHCP enabled
- An [OPNsense ISO image](https://opnsense.org/download/)

## Create a New VM for OPNsense
| Create: Virtual Machine | Details
| -------------------- | ---------------------------------------- |
| General | Provide a unique ID and a descriptive name for your VM.|
| OS | Choose the OPNsense ISO image you uploaded to Proxmox.|
| System | Check the box to enable the Qemu Agent for better VM management.|
| Disks | Specify the size and storage location for the virtual disk.|
| CPU | Allocate CPU resources: 1 socket, 2 cores, and set the type to "host".|
| Memory | Allocate 8 GB of RAM for the VM.|
| Network |Configure the LAN interface: use vmbr1, set VLAN to 30, and disable the firewall.|
| Confirm | Review your settings and create the VM without starting it.|
| Add: Network Device | Add an additional network device for the WAN interface: use vmbr1, set VLAN to 999, and disable the firewall.|

- [Show Details with screenshots](docs/1-create-vm/README.md)

## Install OPNsense

🚧 **Under Construction** 🚧

This chapter is currently being written and will be added in the next few days. Stay tuned for updates!

- [Show Details with screenshots](docs/2-install-opnsense/README.md)

## Initial OPNsense Configuration

🚧 **Under Construction** 🚧

This chapter is currently being written and will be added in the next few days. Stay tuned for updates!

- [Show Details with screenshots](docs/3-initial-opnsense-configuration/README.md)

## Install QEMU Guest Agent

🚧 **Under Construction** 🚧

This chapter is currently being written and will be added in the next few days. Stay tuned for updates!

- [Show Details with screenshots](docs/4-install-qemu-agent/README.md)
