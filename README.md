# Polls NLW(Next Level Week)

**Requisitos**:
- Node.js 20.11.0
- Docker [Get Docker](https://docs.docker.com/get-docker/)
- NPM 10.2.4


## Rodando o Projeto
- Depois de instalado os requisitos, rodaremos o comando **npm install** para instalar todas as dependências do projeto.
- Em seguida **npm run dev** que rodara o projeto local na **porta:3333**.
- E por fim o comando **Docker**: docker compose up -d, que deixará as aplicações configuradas rodando em background.

## Rotas para Testes

**_Criando enquete_**: 

- Tipo: Post
- url: http://localhost:3333/polls
- dados: title(titulo da enquete) & options(opções de votos).
- response: pollId(id da enquete utilizado na próxima rota).

**_Visualizando enquete e opções de votos_**:
- Tipo: Get
- url: http://localhost:3333/polls/<"id da enquete(pollId)">
- dados: sem dados para o envio.
- response: Enquete com titulo e opções e votos(obs: em options, pegar o id da opção a qual votará).

**_Votando na opção desejada_**:
- Tipo: Post
- url: http://localhost:3333/polls/<"id da opção desejada">/votes
- dados: pollOptionId: id da opção
- response: Sem dados de resposta

**_Real time_**:
*Essa é uma rota de web socket, lembre de conferir se no seu **API Client** a opção **Web Socket** ao criar uma nova rota*
- Tipo: web socket
- url: ws://localhost:3333/polls/<"id da enquete criada">/results
- dados: sem dados para envio
- response: opções votadas em tempo real.
