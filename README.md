---
description: Setting Up Your Pentesting Environment
---

# Workstation Setup

## Installing the Operating System

* Download the ISO for the operating system of your choice
  * [Kali ](https://www.kali.org/downloads/)is the most widely used
  * [Parrot](https://parrotlinux.org/download/) is lighter and has more tools
* Verify the sha256 hashsum of the file using on the following methods

{% tabs %}
{% tab title="PoSH" %}
```aspnet
Get-FileHash \path\to\file
```
{% endtab %}

{% tab title="Bash" %}
```bash
sha256sum <file>
```
{% endtab %}

{% tab title="7-ZIP" %}
* Open 7-Zip and browse to the file
* Right click the file -&gt; CRC -&gt; SHA-256
{% endtab %}
{% endtabs %}

* Use the New Virtual Machine Wizard in VMware Workstation to create a VM from the ISO file
* Boot the VM and follow the interactive installer using the following settings:
  * Use the entire virtual disk
  * Install on a single partition
  * No LVM
  * No encrypted volumes

{% hint style="info" %}
These installer settings are ideal for a virtual machine that will be wiped or rolled back on a regular basis. For a semi-permanent bare-metal installation, encrypted volumes should be used and LVM is preferred.
{% endhint %}

## Enabling SSH Access

SSH access from the host may seem unnecessary with the ability to interact directly with the VM, but using an SSH client is lower latency and saves resources if you run your VM in headless mode.

### Option 1: Quick, Insecure, Ephemeral

```bash
#install openssh server
apt install -y openssh-server

#configure to allow root login
echo "PermitRootLogin yes" >> /etc/ssh/sshd_config

#start the ssh service
systemctl start ssh.socket
```

### Option 2: Permanent, More Secure

```bash
#install openssh server
apt install -y openssh-server

#
```

