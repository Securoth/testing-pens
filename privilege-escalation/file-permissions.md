# File Permissions

## /etc/shadow

Read Access: crack hash offline

Write access: replace hash with known hash

## /etc/passwd

{% hint style="info" %}
A hash specific in passwd will take precedence over /etc/shadow
{% endhint %}

Read Access: crack hash offline

Write access: replace hash with known hash or erase hash

Append: add new user with UID of root \(0\)

## Backups

Backed up files may not have the same permissions as the original. Look around for backups and check the permissions.

## Sudo

First see if sudo su is allowed, if not try the following:

* sudo -s
* sudo -i
* sudo /bin/bash
* sudo passwd

Finally, check if you can passwordless sudo any binaries with sudo -l or an automated privesc checker. Look up that binary in GTFOBins/LOLBAS.

If nothing is available on GTFO/LOL check for the LD\_PRELOAD or LDLIBRARY PATH __variable. If present, compile a reverse shell shared object and pass via sudo.



