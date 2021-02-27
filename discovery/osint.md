# OSINT

## Whois Lookup

Whois reveals information about the owner of a domain. Personal details may be obscured if the registrant paid extra.

{% tabs %}
{% tab title="Bash" %}
```text
whois <domain>
```
{% endtab %}

{% tab title="ICANN" %}
1. Browse to [https://lookup.icann.org/](https://lookup.icann.org/)
2. Enter the domain name and click "Lookup"
{% endtab %}
{% endtabs %}

## Website Footprinting

Learning about the programming languages and web frameworks used in a website can help you find appropriate exploits down the road.

### Netcraft Report

Netcraft is a tech company that offers a website profiling too. It provides a wealth of information including subdomains and web technologies in use. Not every website is in the database, it has to be visited by users of their browser extensions [searchdns.netcraft.com](http://searchdns.netcraft.com)

### Shodan

A search engine that scans internet connected devices. Like a search engine for devices instead of websites.

### Security Headers Scan

Looks at HTTP response headers and flags which any important ones which are missing. [securityheaders.com](http://securityheaders.com)

### Qualys SSL Server Test

Checks which SSL and TLS versions, as well as which specific ciphers, are supported by the server.

