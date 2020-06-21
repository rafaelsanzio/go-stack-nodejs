<h1 align="center">
  Challenge GoStack NodeJS 🚀
  <p align="center">
  <img src="https://img.shields.io/badge/tech-backend-lightgrey" />

  <a href="https://nodejs.org/en/">
    <img src="https://img.shields.io/badge/framework-NodeJS-green" />
  </a>

  <a href="https://github.com/Rocketseat">
    <img src="https://img.shields.io/badge/source-rocketseat-blueviolet" />
  </a>
  </p>
</h1>

Primeiro desafio em [NodeJS](https://nodejs.org/en/ "NodeJS") da [RocketSeat](https://rocketseat.com.br/ "RocketSeat"), passado no bootcamp GoStack 12. 

A proposta é simples: criar uma API para gerenciar repositórios (Fakes), utilizando as operações de CRUD (Create, Read Update, Delete), armazenando os dados em varáveis, na memória. Sendo também possível dar likes nos repositórios.

## Getting Started ▶️
- **Passo 1**: executar a instalação do [NodeJS](https://nodejs.org/en/ "NodeJS")
- **Passo 2**: git clone do projeto gostack-nodejs
```bash
  # Navegando até a pasta do projeto
  $ cd gostack-nodejs

  # Instalando todas as depêndencias necessárias
  $ npm install

  # Starting o backend da aplicação
  $ npm run dev
```

## Conceitos 📕
### API Rest
É a interface que permite comunicar o seu sistema com outras aplicações, por meio do modelo requisição e reposta. Porém, diferente o modelo **MVC**, a resposta obtida não é uma página **HTML**, somente os dados relvantes para a página criada no front-end.

### Parâmetros da Requisição
São dados complementares ao método http. Temos:

* **Route params** - selecionar registros específicos - na url: '/:parametro'

* **Query Params** - filtrar resultados de uma busca - na url: '?chave=valor'

### Métodos HTTP
É o tipo de requisição que se faz a uma rota. Os principais, são:

* **GET** http://localhost:3333/repositories ⇒ Busca informações do back-end

* **POST** http://localhost:3333/repositories ⇒ Cria uma informação no back-end
```json
 #Objeto para criação de novo repositório
{
  "title": "Desafio ReactNative",
  "url": "http://github.com/rafaelsanzio/desafio-react-native",
  "techs": ["ReactNative"]
}
```

* **PUT** http://localhost:3333/repositories/1 ⇒ Altera uma informação no back-end
```json
 #Objeto para alteração do repositório
{
  "title": "Desafio ReactJS",
  "url": "http://github.com/rafaelsanzio/desafio-react-js",
  "techs": ["ReactJS"]
}
```

* **DELETE** http://localhost:3333/repositories/1 ⇒ Deleta uma informação no back-end

	#### - HTTP Codes - Respostas
	Na resposta dada ao cliente é mandado junto um código **HTTP** que seguem padrões:

	**1xx**: Os códigos que iniciam com um são informativos.

	**2xx**: Para quando teve sucesso na requisição.

	- 200: SUCCESS
	- 201: CREATED
  
  **3xx**: Usado para informar redirecionamento

	- 301: MOVED PERMANENTLY
	- 302: MOVED

  **4xx**: Algum erro vindo do cliente, geralmente algum dado que faltou ou o tipo é diferente por exemplo.
  
  - 400: BAD REQUEST
  - 401: UNAUTHORIZED
  - 404: NOT FOUND
  
  
  **5xx**: Algum erro inesperado ocorrido no servidor

  - 500: INTERNAL SERVER ERROR
  

### Middlewares
Middlewares são interceptadores de requisições, podendo interromper totalmente requisições, ou alterar os dados da mesma.

Eles são funções que recebem os parâmetros **request**, **response** e **next**. São utilizados quando queremos que trechos de códigos sejam disparados em uma ou mais rotas da aplicação.

**Exemplo**:

```javascript
  function logRequest(request, response, next) {
    const { method, url } = request
    const logLbael = `[${method.toUpperCase()}] ${url}`;
    console.log(logLabel);
	  
    /* Caso o next não seja execultado, a requisição é interrompida */
    return next();
  }

  app.use('/repositories/:id', logRequest);
```

## Considerações :congratulations:
- Projeto desenvolvido no Bootcamp - GoStack da [RocketSeat](https://rocketseat.com.br/ "RocketSeat")  by:

- <img width="20px" src="https://img.icons8.com/fluent/96/github.png" /> [Rafael Sanzio](https://github.com/rafaelsanzio "Rafael Sanzio")
 
- <img width="20px" src="https://img.icons8.com/color/2x/linkedin.png" /> [Rafael Sanzio](https://www.linkedin.com/in/rafael-sanzio-012778143/ "Rafael Sanzio")
