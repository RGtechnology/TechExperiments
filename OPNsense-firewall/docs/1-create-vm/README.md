# Create a New VM for OPNsense
![Proxmox | create Virtual Machine](images/proxmox-create-vm.png)

## Create: Virtual Machine | General
Provide a unique ID and a descriptive name for your VM. 

![Proxmox | create Virtual Machine | General](images/01-create-vm-general.png)

## Create: Virtual Machine | OS
Choose the OPNsense ISO image you uploaded to Proxmox.

![Proxmox | create Virtual Machine | OS](images/02-create-vm-os.png)

## Create: Virtual Machine | System
Check the box to enable the Qemu Agent for better VM management.

![Proxmox | create Virtual Machine | System](images/03-create-vm-system.png)

## Create: Virtual Machine | Disks
Specify the size and storage location for the virtual disk.

![Proxmox | create Virtual Machine | Disks](images/04-create-vm-disks.png)

## Create: Virtual Machine | CPU
Allocate CPU resources: 1 socket, 2 cores, and set the type to "host".

![Proxmox | create Virtual Machine | CPU](images/05-create-vm-cpu.png)

## Create: Virtual Machine | Memory
Allocate 8 GB of RAM for the VM.

![Proxmox | create Virtual Machine | Memory](images/06-create-vm-memory.png)

## Create: Virtual Machine | Network
Configure the LAN interface: use `vmbr1`, set VLAN to 30, and disable the firewall.

![Proxmox | create Virtual Machine | Network](images/07-create-vm-network-1.png)

## Create: Virtual Machine | Confirm
Review your settings and create the VM without starting it.

![Proxmox | create Virtual Machine | Confirm](images/08-create-vm-confirm.png)

## Add: Network Device
Add an additional network device for the WAN interface: use `vmbr1`, set VLAN to 999, and disable the firewall.

![Proxmox | create Virtual Machine | Add additional network device](images/09-add-network-device.png)