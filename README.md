# Discovery

## Full Port Scan

 This scan touches all 65,535 ports on all live systems.

 1. List all targets in a text file, one per line.

2. Run the following

{% tabs %}
{% tab title="Nmap" %}
```bash
nmap -p- -iR -iL targets.txt 
```
{% endtab %}
{% endtabs %}

## All Host, Full Port Scan

This scan touches all 65,535 ports on all systems, including those which are not believed to be live.

1. List targets in a text file, one per line
2. Run the following

{% tabs %}
{% tab title="Nmap" %}
```text
nmap -p- -iR -Pn -iL targets.txt
```
{% endtab %}

{% tab title="Rustscan" %}
```bash
#!/bin/bash
#target list must be ips, not networks
input="~/targets/txt"
while IFS= read -r line
do
  rustscan "$line"
done < "$input"
```
{% endtab %}

{% tab title="Masscan" %}

{% endtab %}

{% tab title="Bash" %}

{% endtab %}

{% tab title="Python" %}

{% endtab %}

{% tab title="C" %}

{% endtab %}
{% endtabs %}



