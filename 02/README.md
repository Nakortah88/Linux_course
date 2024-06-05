# Создал 2 виртуальные машины в GCP, на одной из них поднял Ansible, на другой ничего не поднимал. Сделал ДЗ по методичке, все заработало. 

nakortah@ubuntu02:~$ sudo lsof -i -P -n | grep LISTEN
systemd-r   437 systemd-resolve   13u  IPv4  18203      0t0  TCP 127.0.0.53:53 (LISTEN)
sshd        745            root    3u  IPv4  24901      0t0  TCP *:2222 (LISTEN)
sshd        745            root    4u  IPv6  24903      0t0  TCP *:2222 (LISTEN)
sshd        745            root    5u  IPv4  24905      0t0  TCP *:22 (LISTEN)
sshd        745            root    6u  IPv6  24907      0t0  TCP *:22 (LISTEN)
nginx      2977            root   11u  IPv4 715913      0t0  TCP *:8080 (LISTEN)
nginx     51531          nobody   11u  IPv4 715913      0t0  TCP *:8080 (LISTEN)

# Внутренний IP.

nakortah@ubuntu01:~$ curl http://10.128.0.6:8080
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
    body {
        width: 35em;
        margin: 0 auto;
        font-family: Tahoma, Verdana, Arial, sans-serif;
    }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>

# По внешнему изначально был недоступен, открыл порт в GCP и все заработало и снаружи.

nakortah@ubuntu01:~$ curl http://34.28.254.130:8080
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
    body {
        width: 35em;
        margin: 0 auto;
        font-family: Tahoma, Verdana, Arial, sans-serif;
    }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
