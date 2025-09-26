# ACME Certificates

Use the built-in ACME client to automatically request and renew Let's Encrypt certificates for your Proxmox node.

> **Prerequisites**:
> - DNS A record / FQDN exists  
> - API key is available (for DNS challenge)  

> ℹ️ In a cluster, add the ACME account only once in the Datacenter.  
> Each node then requests its own certificate for its individual FQDN.

## Add ACME Account


- Datacenter -> ACME -> Accounts -> Add
- Provide an account name, email address and accept TOS, then click `Register`
![Add ACME Account](images/01-add-acme-account.png)
![Add ACME Account Status](images/02-add-acme-account-status.png)

## Add Challenge Plugin
- Datacenter -> ACME -> Challenge Plugins -> Add
![Add ACME Challenge Plugin](images/03-add-acme-challenge-plugin.png)

## Add ACME Certificate
- PVE-Node -> Certificates -> ACME -> Add
![Add ACME Certificate](images/04-add-acme-certificate.png)
![Add ACME Certificate](images/05-add-acme-certificate-account.png)
![Add ACME Certificate](images/06-add-acme-certificate-order-now.png)

---
[Back to Overview](../../README.md)