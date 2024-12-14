# Projeto kube-news

### Objetivo
O projeto Kube-news é uma aplicação escrita em NodeJS e tem como objetivo ser uma aplicação de exemplo pra trabalhar com o uso de containers.

### Configuração
Pra configurar a aplicação, é preciso ter um banco de dados Postgre e pra definir o acesso ao banco, configure as variáveis de ambiente abaixo:

DB_DATABASE => Nome do banco de dados que vai ser usado.

DB_USERNAME => Usuário do banco de dados.

DB_PASSWORD => Senha do usuário do banco de dados.

DB_HOST => Endereço do banco de dados.

### Intrunções para o Dev Containers
instale a extenção **[Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)** no seu VSCode

`Reopen in Container`

*no terminal incie a aplicação*
 
`cd src`
`node server.js` ou `npm run start`

>A ***[aplicação](http://localhost:8080)*** fiacara acessível na porta 8080

>O ***[prometheus](http://localhost:9090/targets)*** ficara acessível na porta 9090


> O ***[grafana](http://localhost:3000)*** ficara acessível na porta 3000

*credenciais para acessar o grafana*

user: `dev` 
password: `passDev`
