# Social Engineering

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
```

```
{% endtab %}
{% endtabs %}

