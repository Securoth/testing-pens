# Service Exploits

## Unquoted Service Path

## Vulnerable Services Running as Root

First, identify programs running as root

{% tabs %}
{% tab title="bash" %}
```text
ps aux | grep "^root"
```
{% endtab %}

{% tab title="auto" %}
An automatic privesc tool such as LinPeas, lin-enum or linux smart enumeration should show this information
{% endtab %}
{% endtabs %}

Identify the version numbers of those programs

{% tabs %}
{% tab title="flag" %}
Try running the program with -v or --version. If that doesnt work, try running with -h or --help or viewing the manpage to see how to check the version number.
{% endtab %}

{% tab title="dpkg" %}
```text
dpkg -l | grep <program>
```
{% endtab %}

{% tab title="rpm" %}
```text
rpm -qa | grep <program>
```
{% endtab %}
{% endtabs %}

