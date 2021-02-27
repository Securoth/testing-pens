# Port Scanning

## Full Port Scan

 This scan checks all 65,535 ports on all **live** systems.

1. List all targets in a text file, one per line.
2. ```
   nmap -p- -iR -iL targets.txt
   ```

## All Host, Full Port Scan

This scan checks all 65,535 ports on **all** systems.

1. List targets in a text file, one per line
2. Run the following using the tool of your choice:

{% tabs %}
{% tab title="Nmap" %}
```bash
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
```text

```
{% endtab %}

{% tab title="Bash" %}
```text

```
{% endtab %}

{% tab title="Python" %}
```text

```
{% endtab %}

{% tab title="C" %}
```text

```
{% endtab %}
{% endtabs %}

