# Kali Setup

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

This scan touches all 65,535 ports on **all** systems.

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

## Host a Tracking Pixel

A tracking pixel is a 1x1 image, hosted on a remote server, that is linked from an email. Because of its small size it is usually invisible to the naked eye. When the recipient downloads the image, information about their ip address, OS, and browser will be recorded in the server access log.

{% tabs %}
{% tab title="Apache" %}
```bash
#install apache web server and imagemagick
apt install -y apache2 imagemagick

#create the pixel
convert -size 1x1 xc:transparent pixel.jpg

#stop apache server
systemctl stop apache2

#move tracking pixel to webroot directory
mv pixel.jpg /var/www/html/

#start apache server
systemctl start apache2

#view the most recent access log entries
tail -f /var/log/apache2/access.log
```
{% endtab %}

{% tab title="Nginx" %}
```bash
#install nginx web server and imagemagick
apt install -y nginx imagemagick

#create the pixel
convert -size 1x1 xc:transparent pixel.jpg


```
{% endtab %}

{% tab title="http.server" %}

{% endtab %}
{% endtabs %}

