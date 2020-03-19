# CRLF


Segundo a [Acunetix](https://www.acunetix.com/websitesecurity/crlf-injection/), CRLF injection ocorre quando o invasor consegue injetar os caracteres CRLF em um aplicatino web, por exemplo, usando um formulário de entrada ou uma solicitação HTTP.

É importante observar que há uma declaração na descrição do desafio recomendando que se faça uma injeção de dados falsa no campo de log.

Tentando fazer um autenticação com uma combinação de credencias qualquer (teste:teste), é gerado um log no campo “Authentication log ” abaixo:

![img0](https://user-images.githubusercontent.com/26724539/77103578-63c74b80-69f9-11ea-8842-df39cd47dd92.png)

Tentativa de injeção com CRLF (%0d%0a) obteve sucesso com alteração no get request:

http://challenge01.root-me.org/web-serveur/ch14/?username=teste%0D%0Aguest&password=

![img1](https://user-images.githubusercontent.com/26724539/77103579-65910f00-69f9-11ea-8415-bcb1fb6c7b76.png)

E gerando um log exatamente como no trecho acima na parte de “admin authenticated.” e “guest failed to authenticate.”, a flag é retornada:

http://challenge01.root-me.org/web-serveur/ch14/?username=admin%20authenticated.%0D%0Aguest&password=

![img2](https://user-images.githubusercontent.com/26724539/77103588-69bd2c80-69f9-11ea-933b-a7289b2a68d6.png)
