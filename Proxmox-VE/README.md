# Proxmox Virtual Environment - PVE

In this TechExperiment, we will walk through the process of setting up a Proxmox VE node, providing a foundation for managing virtual machines and containers in your HomeLab.

> **Proxmox Virtual Environment** is a complete open-source platform for enterprise virtualization. With the built-in web interface you can easily manage VMs and containers, software-defined storage and networking, high-availability clustering, and multiple out-of-the-box tools using a single solution. 
<br><br>Proxmox Server Solutions GmbH. *Proxmox Virtual Environment Documentation*.  
  Available at: [https://www.proxmox.com/en/proxmox-ve](https://www.proxmox.com/en)

## Disclaimer

This guide offers a straightforward introduction to a common HomeLab scenario and is not intended to replace the comprehensive [official documentation](https://proxmox.com/en/products/proxmox-virtual-environment/get-started). It is designed to assist newcomers in setting up their own HomeLab quickly and efficiently.

### Notice on Screenshots and Trademarks

Some of the screenshots used in this documentation display the web interface of [Proxmox VE](https://www.proxmox.com).  
© Proxmox Server Solutions GmbH – used with proper attribution.  

The Proxmox logo and the name “Proxmox®” are registered trademarks of Proxmox Server Solutions GmbH.  
This documentation is an independent project and is **not affiliated with, endorsed by, or officially associated with Proxmox**.  


## Hardware

- Intel 64 or AMD64 with Intel VT/AMD-V CPU flag.
- Memory, minimum 2 GB for OS and Proxmox VE services. Plus designated memory for guests. 

> Source: https://proxmox.com/en/products/proxmox-virtual-environment/requirements 

## Get Started

### Setup

| Step                 | Description |
| -------------------- | ---------------------------------------- |
| **1** | Boot Installer from USB |
| **2** | Agree EULA |
| **3** | Define Target Disk |
| **4** | Define Location and Timezone |
| **5** | Define Password and E-Mail address |
| **6** | Define Network Configuration|
| **7** | Install Proxmox VE|

- [Show Details with screenshots](docs/01-setup/README.md )

### Initial Configuration

| Step                 | Description |
| -------------------- | ---------------------------------------- |
| **1** | Open a browser go to: `https://192.168.1.11:8006` and log in as the user `root` and the password you set earlier. |
| **2** | Navigate to PVE Node > Updates > Repositories |
| **3** | Add "no-subsription repositories" for CEPH and PVE |
| **4** | Disable "enterprise repositories"|
| **5** | Update PVE Node |

- [Show Details with screenshots](docs/02-initial-configuration/README.md)

### ACME Certificates

Use the built-in ACME client to automatically request and renew Let's Encrypt certificates for your Proxmox node.

| Step                 | Description |
| -------------------- | ---------------------------------------- |
| **ACME Account** | Datacenter -> ACME -> Accounts -> Add |
| **Challenge Plugin** | Datacenter -> ACME -> Challenge Plugins -> Add |
| **ACME Certificate** | PVE-Node -> Certificates -> ACME -> Add |

- [Show Details with screenshots](docs/03-acme-certificates/README.md )

# Sending Email via Gmail SMTP

How to configure a Proxmox VE or Proxmox Backup Server host to send notification emails through **Gmail**.

| Step                 | Description |
| -------------------- | ---------------------------------------- |
| **1** | Install required package (libsasl2-modules) |
| **2** | Store SMTP credentials in `/etc/postfix/sasl_passwd` |
| **3** | Configure Postfix (`/etc/postfix/main.cf`) |
| **4** | Rewrite local senders to Gmail (Envelope/Sender header) |
| **5** | Rewrite the “From:” header (Display name) |
| **6** | Reload Postfix Configuration |
| **7** | Send a test mail |
| **8** | Optional: Aliases for incoming system mail |

- [Show Details](docs/04-email-notification/README.md )