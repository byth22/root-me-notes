# HTTP - Improper redirect

Nesse desafio há um http_redirect() para uma página de login, fazendo com que usuários não-autorizados não tenham permissão de acesso, porém o código continua a executar e permite a leitura da resposta de nossa requisição. Isso é geralmente realizado usando redirecionamento 302 Found - HTTP.

Se bloquearmos o redirect pelo Burp Suit através da função de Repeater, é possível fazer a leitura da flag:

![img0](https://user-images.githubusercontent.com/26724539/74194476-15739f80-4c38-11ea-9608-8f6fe22161f1.PNG)
