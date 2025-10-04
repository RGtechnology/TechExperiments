# Initial OPNsense Configuration

## System: Wizard: Login

Open a browser and go to: `https://192.168.1.1` and log in as the user `root` and the password you set earlier.

![System: Wizard: Login](images/01-OPNsense-configure-login.png)

## System: Wizard: General Setup

Navigate to System > Wizard, then click `Next` to begin.

![System: Wizard: General Setup](images/02-OPNsense-configure-wizard-1.png)

## System: Wizard: General information

Provide `hostname` and `domain` and click `Next`

![System: Wizard: General information](images/03-OPNsense-configure-wizard-2.png)
![System: Wizard: General information](images/04-OPNsense-configure-wizard-3.png)

## System: Wizard: Time Server Information

Set the time server hostname (default is fine), set your timezone and click `Next`

![System: Wizard: Time Server Information](images/05-OPNsense-configure-wizard-4.png)

## System: Wizard: Configure WAN Interface

IPv4 Configuration Type: DHCP (typical for home networks)

![System: Wizard: Configure WAN Interface | DHCP](images/06-OPNsense-configure-wan-dhcp.png)

Uncheck `Block private networks` 

Note: in this Lab the OPNsense Firewall is located behind a router from the internet provider.

![System: Wizard: Configure WAN Interface | Unblock private networks](images/07-OPNsense-configure-wan-dhcp.png)

## System: Wizard: Configure LAN Interface

Provide LAN IP address and click `Next`

![System: Wizard: Configure LAN Interface](images/08-OPNsense-configure-lan.png)

## System: Wizard: Set Root Password

Click `Next` (Keep the password you set during the installation )

![System: Wizard: Set Root Password](images/09-OPNsense-password-change.png)

## System: Wizard: Reload Configuration

Click `Reload` to apply your new configuration.

![System: Wizard: Reload Configuration](images/10-OPNsense-reload.png)

![Finished](images/11-OPNsense-finished.png)

## Next Step

Continue with installing [`QEMU Guest Agent for OPNsense`](../4-install-qemu-agent/README.md)

[Back to Overview](../../README.md)
