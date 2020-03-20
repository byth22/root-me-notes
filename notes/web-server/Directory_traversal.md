# Directory traversal

A dica do desafio é encontrar a seção escondida na galeria de photos. E como o título indica, será uma falha de Directory Traversal.

Link: http://challenge01.root-me.org/web-serveur/ch15/ch15.php?galerie=devices

A galeria é acessada por “?galerie=device”. E foi possível visualizar novos itens apontando o diretório corrente com "?galerie=./".

![img0](https://user-images.githubusercontent.com/26724539/77127204-69895500-6a2a-11ea-9366-cca2397de111.png)

Inspecionando o item com as inicias “86hv” foi possível visualizar o nome completo “86hwnX2r”, acessa-lo e ver novos dispositivos:

![img1](https://user-images.githubusercontent.com/26724539/77127205-6a21eb80-6a2a-11ea-8abe-caf5f639c310.png)

Novamente foi possível inspecionar o novo item com as inicias “pass”, e visualizar o nome completo "password.txt" e seu diretório. Porém agora é necessário apontar o o caminho completo para o arquivo “password.txt”, pois a função “?galerie=” não parmite a leitura de arquivos .txt.

Link: http://challenge01.root-me.org/web-serveur/ch15/galerie/86hwnX2r//password.txt
