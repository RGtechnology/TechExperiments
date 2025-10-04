# Sending Email via Gmail SMTP

This guide explains how to configure a Proxmox VE or Proxmox Backup Server host to send notification emails through **Gmail**.

> **Prerequisites:**
>
> - Proxmox host with root shell access
> - A Google account with **2-Step Verification enabled**
> - A **Gmail App Password**  
  (Google Account → Security → 2-Step Verification → App Passwords → choose “Mail”)

> **Notes:**
> - Always use an **App Password**, not your main Gmail password.
> - Gmail’s SMTP server signs outgoing messages, so no SPF/DKIM setup on your side is needed.
> - For multiple Proxmox hosts just copy this configuration.

## Step 1 - Install required package

This provides SASL authentication modules needed by Postfix.

```bash
apt update
apt install libsasl2-modules
```

## Step 2 – Store SMTP credentials

Create or edit `/etc/postfix/sasl_passwd`:

```bash
[smtp.gmail.com]:587 yourname@gmail.com:YOUR_APP_PASSWORD
```

Generate the hash and protect the file:

```bash
postmap /etc/postfix/sasl_passwd
chmod 600 /etc/postfix/sasl_passwd /etc/postfix/sasl_passwd.db
```

## Step 3 – Configure Postfix

Configure Postfix to relay mail through Gmail with STARTTLS and SASL authentication.

Edit `/etc/postfix/main.cf` and add or adjust the following lines:

```ini
myhostname = pve9-node1.yourdomain.tld

relayhost = [smtp.gmail.com]:587
smtp_tls_security_level = encrypt
smtp_tls_loglevel = 1
smtp_sasl_auth_enable = yes
smtp_sasl_password_maps = hash:/etc/postfix/sasl_passwd
smtp_sasl_security_options = noanonymous
smtp_sasl_tls_security_options = noanonymous

```

## Step 4 - Rewrite local senders to Gmail (Envelope/Sender header)

Create /etc/postfix/sender_canonical_maps:
```bash
root    yourname@gmail.com
www-data yourname@gmail.com
```
Activate:
```bash
postconf -e 'sender_canonical_maps = hash:/etc/postfix/sender_canonical_maps'
postmap /etc/postfix/sender_canonical_maps
postfix reload
```

## Step 5 - Rewrite the “From:” header (Display name)
If you want the mails to show the hostname instead of “root” in the visible From line.

Create /etc/postfix/smtp_header_checks:
```txt
/^From:\s*.*/ REPLACE From: "pve9-node1" <yourname@gmail.com>
```
(Adjust the name/address as needed.)

Activate:
```bash
postconf -e 'smtp_header_checks = regexp:/etc/postfix/smtp_header_checks'
postfix reload
```

This happens right before sending via Gmail, so it catches all mails reliably.

## Step 6 – Reload Postfix Configuration

Apply the configuration changes:

```bash
postfix reload
```

## Step 7 – Send a test mail

Use the `mail` command to send a test message:

```bash
echo "Test mail from Proxmox" | mail -s "Proxmox Test" youraddress@example.com
```

Or via the Proxmox Web UI: **Datacenter → Notifications → Test Email**.

## Step 8 - Optional: Aliases for incoming system mail
If you want local system mail to be forwarded to your real address (e.g. Cron output):

Edit /etc/aliases:
```txt
root: yourname@gmail.com
```
Then:
```bash
newaliases
```

---
[Back to Overview](../../README.md)