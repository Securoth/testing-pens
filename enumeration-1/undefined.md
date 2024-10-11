# SMB

## OS Discovery

try the namp script smb-os-discovery

```bash
nmap -p139,445 --script=smb-os-discovery <target>
```

## Nmap vuln identification

{% hint style="info" %}
be careful with the unsafe arg, it will allow checks that crash a vulnerable system.
{% endhint %}

```bash
nmap -v -p445,139 -Sv --script=smb-vuln-* --script-args=unsafe=1 -iL windows-smb-ips  
```

## # Browsing Shares

smbmap is the most reliable tool to view and explore shares

<pre class="language-bash"><code class="lang-bash"># List open shares
smbmap -H $target

# recursive list with depth of 5 - might need to increase depth
<strong>smbmap -H $target -R --depth 10
</strong>
# automatically download files that match regex (or just use the filename)
smbmap -H $target -R --depth 10 -A &#x3C;regex>
</code></pre>

for manual browsing [smbclientng ](https://github.com/p0dalirius/smbclient-ng)is easier to user than smbclient

```bash
smbclientng --host $t -u $u -p $p -d $d
```

