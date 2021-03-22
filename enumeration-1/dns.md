# DNS

## Locating Domain Server

First scan the network for systems with port 53 open. These are likely candidates for a dns server.

```bash
nmap -Pn -p53 -oG dns-maybe.gnmap 192.168.1.X/24
```

Then, grep the outputted file to view the systems with the open port.

```bash
grep open dns-maybe.gnmap
```

Extract the IP addresses to a file

```bash
grep open dns-maybe.gnmap | cut -d " " -f 2 > dns-maybe-ips.txt
```

Use nmap to enumerate the port 53 service of each candidate

```bash
nmap -iL dns-mayve-ips -sV -p53
```

When you find it, add it to your resolv.conf or pass it to nmap manually using the --dns-server flag

