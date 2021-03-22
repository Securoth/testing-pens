# SMB

## OS Discovery

try the namp script smb-os-discovery



## Nmap vuln identification

{% hint style="info" %}
be careful with the unsafe arg, it will allow checks that crash a vulnerable system.
{% endhint %}

```bash
nmap -v -p445,139 --script=smb-vuln-* --script-args=unsafe=1 -iL windows-smb-ips  
```

