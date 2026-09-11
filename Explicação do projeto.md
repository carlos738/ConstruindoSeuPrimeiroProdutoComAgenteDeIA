🚀 Geo-Explorer

Uma plataforma educacional fictícia para exploração de trilhas de aprendizagem, desafios de programação e certificados.

O projeto foi desenvolvido como parte de um desafio prático de construção de um produto utilizando um agente de IA como apoio durante o processo de desenvolvimento.

⚠️ Aviso: os certificados e conteúdos utilizados neste projeto são fictícios e possuem finalidade exclusivamente educacional.

📋 Sumário
Sobre o projeto
Objetivos
Funcionalidades
Tecnologias utilizadas
Arquitetura do projeto
Estrutura de diretórios
Etapa 1 — Criação do projeto
Etapa 2 — Base de trilhas
Etapa 3 — Comando Trilha
Etapa 4 — Comando Desafio
Etapa 5 — Comando Certificado
Etapa 6 — Testes
Etapa 7 — Servidor MCP
Como instalar
Como executar
Exemplos
Git e GitHub
Melhorias realizadas
Possíveis melhorias futuras
Aprendizados
Licença
📖 Sobre o projeto

O Geo-Explorer é uma aplicação de linha de comando criada para simular uma plataforma de aprendizagem.

A aplicação disponibiliza três funcionalidades principais:

Trilha — apresenta uma trilha de estudos de acordo com a tecnologia e o nível escolhidos.
Desafio — apresenta um desafio de programação correspondente à tecnologia e ao nível.
Certificado — gera um certificado fictício para uma trilha existente.

Os conteúdos utilizados pela aplicação são armazenados em arquivos JSON, permitindo que novas tecnologias, módulos e desafios sejam adicionados sem necessidade de alterar a lógica principal da aplicação.

🎯 Objetivos

O projeto tem como principais objetivos:

Praticar desenvolvimento com TypeScript.
Trabalhar com Node.js.
Organizar uma aplicação utilizando separação de responsabilidades.
Trabalhar com arquivos JSON como fonte de dados.
Criar comandos de linha de comando.
Implementar validações.
Criar testes automatizados.
Desenvolver documentação técnica.
Conhecer o conceito de servidor MCP.
Utilizar um agente de IA como ferramenta de apoio ao desenvolvimento.
Criar um projeto que possa ser utilizado como peça de portfólio.
✨ Funcionalidades
📚 Trilha

Permite consultar uma trilha de aprendizagem informando:

Tecnologia
Nível

Exemplo:

npm run dev -- trilha JavaScript iniciante


O sistema consulta a base de trilhas e apresenta os módulos e conteúdos disponíveis.

🎯 Desafio

Permite solicitar um desafio de programação utilizando:

Tecnologia
Nível

Exemplo:

npm run dev -- desafio Python intermediario


O sistema procura desafios compatíveis e seleciona um deles.

O desafio contém:

Título
Tecnologia
Nível
Descrição
Entrada
Saída esperada
🎓 Certificado

Permite gerar um certificado fictício para uma trilha existente.

Exemplo:

npm run dev -- certificado "João Silva" JavaScript iniciante


O certificado contém:

Nome do participante
Tecnologia
Nível
Data de emissão
ID único
Título da trilha

Os certificados são apenas simulados e não possuem validade acadêmica ou profissional.

🛠️ Tecnologias utilizadas
Node.js
TypeScript
npm
JSON
Git
GitHub
MCP (Model Context Protocol)

Dependências principais de desenvolvimento:

TypeScript
tsx
@types/node
🏗️ Arquitetura do projeto

O projeto utiliza uma separação simples entre dados, tipos, serviços e comandos.

Usuário
   │
   ▼
src/index.ts
   │
   ├──────────────┬──────────────┐
   ▼              ▼              ▼
Trilha         Desafio       Certificado
   │              │              │
   ▼              ▼              ▼
TrilhaService DesafioService CertificadoService
   │              │              │
   ▼              ▼              ▼
trilhas.json   desafios.json   trilhas.json


Essa organização evita concentrar toda a lógica em um único arquivo.

📁 Estrutura de diretórios
geo-explorer/
│
├── data/
│   ├── trilhas.json
│   └── desafios.json
│
├── docs/
│   └── arquitetura.md
│
├── mcp/
│   └── server.ts
│
├── src/
│   ├── commands/
│   │   ├── trilha.ts
│   │   ├── desafio.ts
│   │   └── certificado.ts
│   │
│   ├── services/
│   │   ├── trilhaService.ts
│   │   ├── desafioService.ts
│   │   └── certificadoService.ts
│   │
│   ├── types/
│   │   └── index.ts
│   │
│   └── index.ts
│
├── tests/
│   ├── trilha.test.ts
│   ├── desafio.test.ts
│   └── certificado.test.ts
│
├── .gitignore
├── package.json
├── package-lock.json
├── tsconfig.json
└── README.md

🔨 Etapa 1 — Criação do projeto

O primeiro passo foi criar o projeto Node.js.

mkdir geo-explorer
cd geo-explorer
npm init -y


Depois foram instaladas as ferramentas necessárias para desenvolvimento com TypeScript:

npm install -D typescript tsx @types/node


O TypeScript foi inicializado com:

npx tsc --init


Também foram criadas as pastas responsáveis por organizar o projeto.

📚 Etapa 2 — Base de trilhas

A base de dados fictícia foi criada em:

data/trilhas.json


A estrutura permite cadastrar diferentes tecnologias e níveis.

Exemplo:

{
  "tecnologia": "JavaScript",
  "niveis": {
    "iniciante": {
      "descricao": "Fundamentos da programação com JavaScript.",
      "modulos": []
    }
  }
}


A utilização de JSON permite alterar os conteúdos sem modificar diretamente a lógica da aplicação.

🧩 Etapa 3 — Comando Trilha

Foi criado o serviço:

src/services/trilhaService.ts


Sua responsabilidade é:

Ler a base de trilhas.
Procurar a tecnologia.
Procurar o nível.
Retornar os dados encontrados.

Depois foi criado:

src/commands/trilha.ts


Esse arquivo é responsável por transformar os dados encontrados em uma resposta amigável para o usuário.

Exemplo:

npm run dev -- trilha JavaScript iniciante


Fluxo:

Comando
   ↓
trilha.ts
   ↓
TrilhaService
   ↓
trilhas.json
   ↓
Resultado

🎯 Etapa 4 — Comando Desafio

Foi criada uma segunda base:

data/desafios.json


Ela contém desafios associados a:

Tecnologia
Nível
Título
Descrição
Entrada
Saída esperada

Foi criado o:

src/services/desafioService.ts


Esse serviço localiza os desafios compatíveis.

Quando existem vários desafios para a mesma tecnologia e nível, um deles é escolhido aleatoriamente.

O comando utilizado é:

npm run dev -- desafio JavaScript iniciante

🎓 Etapa 5 — Comando Certificado

O terceiro recurso desenvolvido foi o certificado.

Foi criado:

src/services/certificadoService.ts


Esse serviço primeiro verifica se a trilha informada realmente existe.

Caso exista, um certificado fictício é criado.

Para gerar o identificador único foi utilizado:

crypto.randomUUID()


O comando é:

npm run dev -- certificado "João Silva" JavaScript iniciante


O sistema apresenta um certificado contendo os dados do participante e um identificador único.

🧪 Etapa 6 — Testes

Os testes têm como objetivo verificar se as funcionalidades continuam funcionando corretamente após alterações no código.

Entre os cenários testados estão:

Busca de trilha existente.
Busca de tecnologia inexistente.
Busca de nível inexistente.
Busca de desafio existente.
Busca de desafio inexistente.
Geração de certificado.
Tentativa de gerar certificado para uma trilha inexistente.

Os testes devem ser executados com:

npm test


A utilização de testes automatizados ajuda a identificar regressões e aumenta a confiabilidade do projeto.

🔌 Etapa 7 — Servidor MCP

Uma das etapas do desafio é apresentar o conceito de MCP — Model Context Protocol.

O MCP permite disponibilizar funcionalidades e recursos de uma aplicação para ferramentas compatíveis com esse protocolo.

No Geo-Explorer, a ideia é disponibilizar operações como:

listar_trilhas
get_trilha
gerar_desafio
gerar_certificado


A arquitetura pode ser representada da seguinte forma:

Ferramenta compatível com MCP
             │
             ▼
       Servidor MCP
             │
       ┌─────┼─────┐
       ▼     ▼     ▼
    Trilha Desafio Certificado
       │     │     │
       └─────┼─────┘
             ▼
       Geo-Explorer


O MCP não substitui a lógica existente. Ele funciona como uma camada que permite que outras ferramentas acessem as funcionalidades do projeto.

💻 Como instalar

Clone o repositório:

git clone <URL_DO_REPOSITORIO>


Entre na pasta:

cd geo-explorer


Instale as dependências:

npm install

▶️ Como executar

Durante o desenvolvimento:

npm run dev


Para executar um comando específico:

npm run dev -- trilha JavaScript iniciante


Depois de compilar o projeto:

npm run build


A aplicação compilada pode ser executada com:

npm start

📌 Exemplos de utilização
Consultar uma trilha
npm run dev -- trilha JavaScript iniciante

Gerar um desafio
npm run dev -- desafio Python intermediario

Gerar certificado
npm run dev -- certificado "Maria Silva" Python iniciante

Tecnologia inexistente
npm run dev -- trilha Rust iniciante


O sistema deve informar que a trilha não foi encontrada.

🌱 Como adicionar uma nova trilha

Uma das vantagens da estrutura utilizada é que novas trilhas podem ser adicionadas diretamente ao arquivo:

data/trilhas.json


Por exemplo:

{
  "tecnologia": "Go",
  "niveis": {
    "iniciante": {
      "descricao": "Introdução à linguagem Go.",
      "modulos": [
        {
          "titulo": "Fundamentos",
          "conteudos": [
            "Variáveis",
            "Tipos",
            "Funções"
          ]
        }
      ]
    }
  }
}


Depois disso, o comando poderá consultar a nova tecnologia sem que seja necessário criar um novo serviço.

🌱 Como adicionar um novo desafio

Novos desafios podem ser adicionados em:

data/desafios.json


Exemplo:

{
  "id": 10,
  "tecnologia": "Go",
  "nivel": "iniciante",
  "titulo": "Soma de números",
  "descricao": "Crie uma função que some dois números.",
  "entrada": "5 e 7",
  "saidaEsperada": "12"
}

📦 Git e GitHub

Depois de criar o projeto, o repositório pode ser inicializado com:

git init


Adicione os arquivos:

git add .


Crie o primeiro commit:

git commit -m "feat: cria estrutura inicial do Geo-Explorer"


Depois, associe o projeto ao repositório remoto:

git remote add origin <URL_DO_REPOSITORIO>


E envie os arquivos:

git branch -M main
git push -u origin main


Nunca envie senhas, tokens, chaves de API ou outras informações privadas para o GitHub.

O .gitignore deve impedir que arquivos como node_modules, arquivos .env e a pasta de build sejam enviados acidentalmente.

🚀 Melhorias realizadas

Durante o desenvolvimento, algumas decisões foram tomadas para deixar o projeto mais organizado:

Separação entre comandos e serviços.
Separação entre código e dados.
Criação de tipos TypeScript.
Tratamento de tecnologias inexistentes.
Tratamento de níveis inexistentes.
Identificador único para certificados.
Seleção aleatória de desafios.
Estrutura preparada para testes.
Estrutura preparada para integração com MCP.
Documentação do projeto.
🔮 Possíveis melhorias futuras

O projeto pode continuar evoluindo.

Algumas possibilidades:

🌐 Interface web

Criar uma interface utilizando:

React
Next.js
Vue
HTML/CSS/JavaScript
🤖 Integração com IA

Utilizar um modelo de IA para gerar desafios dinamicamente.

Por exemplo:

Tecnologia: Python
Nível: avançado
Tema: APIs

        ↓

IA

        ↓

Desafio personalizado

🗄️ Banco de dados

Substituir os arquivos JSON por:

SQLite
PostgreSQL
MySQL
MongoDB
👤 Sistema de usuários

Adicionar:

Cadastro.
Login.
Histórico de desafios.
Trilhas concluídas.
Certificados emitidos.
📊 Progresso

Adicionar acompanhamento da evolução:

JavaScript — Iniciante

████████████████░░░░ 80%

4 de 5 módulos concluídos

🏆 Gamificação

Adicionar:

XP.
Níveis.
Badges.
Ranking.
Conquistas.
📄 Certificado em PDF

Em uma versão futura, o certificado fictício poderia ser renderizado em PDF com um layout visual mais elaborado.

🧠 Aprendizados

O desenvolvimento do Geo-Explorer permitiu praticar conceitos importantes de desenvolvimento de software.

Entre os principais aprendizados estão:

Organização de projetos Node.js.
Utilização do TypeScript.
Tipagem de dados.
Leitura e manipulação de arquivos JSON.
Separação de responsabilidades.
Criação de serviços.
Criação de comandos.
Tratamento de erros.
Geração de identificadores únicos.
Testes automatizados.
Controle de versão com Git.
Publicação de projetos no GitHub.
Conceitos básicos de integração via MCP.
Utilização de agentes de IA como ferramenta de apoio ao desenvolvimento.

Um dos principais aprendizados foi perceber que utilizar IA no desenvolvimento não significa simplesmente gerar código.

É importante:

Entender o problema.
Planejar a estrutura.
Revisar o código gerado.
Executar e testar.
Corrigir problemas.
Documentar as decisões.
Conseguir explicar o funcionamento do projeto.
🏁 Conclusão

O Geo-Explorer demonstra uma aplicação simples, mas estruturada, capaz de trabalhar com trilhas de aprendizagem, desafios de programação e certificados fictícios.

O projeto também serve como base para futuras evoluções, podendo receber uma interface web, banco de dados, autenticação, inteligência artificial, gamificação e novas integrações através do MCP.

Mais importante do que a quantidade de funcionalidades é a compreensão da arquitetura e das decisões tomadas durante o desenvolvimento.

📄 Licença

Este projeto foi desenvolvido para fins educacionais.

Você pode adaptar, modificar e evoluir o projeto de acordo com seus objetivos de estudo e portfólio.
