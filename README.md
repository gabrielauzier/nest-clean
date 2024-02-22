<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

  <p align="center">A progressive <a href="http://nodejs.org" target="_blank">Node.js</a> framework for building efficient and scalable server-side applications.</p>
    <p align="center">
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/v/@nestjs/core.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/l/@nestjs/core.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/dm/@nestjs/common.svg" alt="NPM Downloads" /></a>
<a href="https://circleci.com/gh/nestjs/nest" target="_blank"><img src="https://img.shields.io/circleci/build/github/nestjs/nest/master" alt="CircleCI" /></a>
<a href="https://coveralls.io/github/nestjs/nest?branch=master" target="_blank"><img src="https://coveralls.io/repos/github/nestjs/nest/badge.svg?branch=master#9" alt="Coverage" /></a>
<a href="https://discord.gg/G7Qnnhy" target="_blank"><img src="https://img.shields.io/badge/discord-online-brightgreen.svg" alt="Discord"/></a>
<a href="https://opencollective.com/nest#backer" target="_blank"><img src="https://opencollective.com/nest/backers/badge.svg" alt="Backers on Open Collective" /></a>
<a href="https://opencollective.com/nest#sponsor" target="_blank"><img src="https://opencollective.com/nest/sponsors/badge.svg" alt="Sponsors on Open Collective" /></a>
  <a href="https://paypal.me/kamilmysliwiec" target="_blank"><img src="https://img.shields.io/badge/Donate-PayPal-ff3f59.svg"/></a>
    <a href="https://opencollective.com/nest#sponsor"  target="_blank"><img src="https://img.shields.io/badge/Support%20us-Open%20Collective-41B883.svg" alt="Support us"></a>
  <a href="https://twitter.com/nestframework" target="_blank"><img src="https://img.shields.io/twitter/follow/nestframework.svg?style=social&label=Follow"></a>
</p>
  <!--[![Backers on Open Collective](https://opencollective.com/nest/backers/badge.svg)](https://opencollective.com/nest#backer)
  [![Sponsors on Open Collective](https://opencollective.com/nest/sponsors/badge.svg)](https://opencollective.com/nest#sponsor)-->

## Descrição

Aplicação backend de estudos, feita durante o bootcamp Ignite da @rocketseat, utilizando o framework [Nest](https://github.com/nestjs/nest) com TypeScript.

## Instalação

Instale as dependências de desenvolvimento.
```bash
$ pnpm install
```

## Configuração 

O serviço de autenticação JWT desta aplicação utiliza o algoritmo de criptografia RSA-256 para a geração das chaves pública e privada.

Veja abaixo como proceder para a geração e configuração das chaves em seu projeto, no Linux/MacOS.

Execute o seguinte comando para gerar uma chave privada RSA de 2048 bits e salvá-la em um arquivo chamado `private_key.pem`:
```bash
$ openssl genpkey -algorithm RSA -out private_key.pem -pkeyopt rsa_keygen_bits:2048
```

Execute o seguinte comando para extrair a chave pública correspondente e salvá-la em um arquivo chamado `public_key.pem`:
```bash
$ openssl rsa -pubout -in private_key.pem -out public_key.pem
```

Com as chaves criadas, você deve convertê-las para um base64, capaz de ser utilizado no arquivo .env
```bash
$ base64 -w 0 private_key.pem > private_key_base64.txt

$ base64 -w 0 public_key.pem > public_key_base64.txt
```

## Execução

Suba o contâiner do banco de dados. 
```bash
$ docker-compose up
```

Atualize o banco de dados para a última versão.
```bash
$ pnpm prisma migrate dev
```

Inicie a aplicação em modo de desenvolvimento.
```bash
# development
$ pnpm start

# watch mode
$ pnpm start:dev

# production mode
$ pnpm start:prod
```

 (Opcional) Instale a extensão Rest Client no seu VSCode. Assim, você pode testar as requisições no arquivo `client.http`

 (Opcional) Inicie o modo studio do banco de dados.
```bash
$ pnpm prisma studio
```

