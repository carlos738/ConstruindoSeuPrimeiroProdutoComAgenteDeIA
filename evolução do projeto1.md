🚀 Geo-Explorer — Projeto 2

Uma plataforma educacional fictícia para exploração de trilhas de aprendizagem, desafios de programação, bootcamps, formações e certificados.

O Geo-Explorer Projeto 2 representa uma evolução da primeira versão do projeto, ampliando a aplicação para trabalhar com diferentes níveis de aprendizagem e percursos educacionais.

O projeto foi desenvolvido com foco em aprendizado prático de TypeScript, Node.js, organização de software, testes automatizados, manipulação de dados JSON e integração com MCP.

    ⚠️ Aviso: todos os conteúdos, trilhas, desafios, bootcamps, formações e certificados apresentados neste projeto são fictícios e possuem finalidade exclusivamente educacional.

📋 Sumário

    Sobre o projeto
    Objetivos
    Evolução do Projeto 1
    Funcionalidades
    Trilhas
    Desafios
    Bootcamps
    Formações
    Certificados
    Tecnologias utilizadas
    Arquitetura
    Estrutura do projeto
    Dados
    Comandos
    Instalação
    Execução
    Testes
    MCP
    Git e GitHub
    Melhorias futuras
    Aprendizados
    Conclusão
    Licença

📖 Sobre o projeto

O Geo-Explorer Projeto 2 é uma aplicação de linha de comando que simula uma plataforma de educação em tecnologia.

A primeira versão do projeto trabalhava principalmente com:

    Trilhas;
    Desafios;
    Certificados.

Nesta segunda versão, a plataforma foi ampliada para oferecer uma estrutura educacional mais completa:

                       GEO-EXPLORER
                            │
              ┌─────────────┼─────────────┐
              │             │             │
           Trilhas       Desafios      Certificados
              │
              ├─────────────┐
              │             │
          Bootcamps      Formações

A ideia é permitir que o usuário comece estudando uma tecnologia específica e posteriormente avance para programas maiores.
🎯 Objetivos

O Projeto 2 possui como objetivos:

    Evoluir a primeira versão do Geo-Explorer.
    Praticar TypeScript.
    Trabalhar com Node.js.
    Utilizar arquivos JSON como fonte de dados.
    Organizar uma aplicação em camadas.
    Separar comandos e serviços.
    Criar novos tipos de conteúdo educacional.
    Implementar validações.
    Criar testes automatizados.
    Trabalhar com identificadores únicos.
    Melhorar a documentação.
    Explorar o conceito de MCP.
    Utilizar IA como ferramenta de apoio ao desenvolvimento.
    Criar uma base preparada para futuras funcionalidades.

🔄 Evolução do Projeto 1

O Projeto 1 tinha uma estrutura mais simples:

Trilha
Desafio
Certificado

O Projeto 2 amplia essa estrutura:

Trilha
   │
   ├── Desafios
   │
   ├── Bootcamps
   │
   ├── Formações
   │
   └── Certificados

Projeto 1

data/
├── trilhas.json
└── desafios.json

Projeto 2

data/
├── trilhas.json
├── desafios.json
├── bootcamps.json
└── formacoes.json

Essa mudança permite representar diferentes níveis de uma plataforma educacional.
✨ Funcionalidades

O Geo-Explorer Projeto 2 possui cinco funcionalidades principais.
📚 1. Trilhas

Permite consultar uma trilha de aprendizagem por:

    Tecnologia;
    Nível.

Exemplo:

npm run dev -- trilha JavaScript iniciante

🎯 2. Desafios

Permite gerar um desafio relacionado a uma tecnologia e nível.

Exemplo:

npm run dev -- desafio Python intermediario

Quando existem vários desafios compatíveis, o sistema pode selecionar um deles aleatoriamente.
🏕️ 3. Bootcamps

Permite consultar programas intensivos compostos por várias tecnologias.

Exemplo:

npm run dev -- bootcamp "Bootcamp Full Stack JavaScript"

Um bootcamp pode possuir:

    Nome;
    Descrição;
    Nível;
    Duração;
    Tecnologias;
    Trilhas;
    Projeto final.

🎓 4. Formações

Representam percursos educacionais maiores.

Uma formação pode combinar:

    Trilhas;
    Bootcamps;
    Tecnologias;
    Projetos finais.

Exemplo:

npm run dev -- formacao "Formação Desenvolvedor Full Stack"

📜 5. Certificados

Permite gerar certificados fictícios relacionados às trilhas.

Exemplo:

npm run dev -- certificado "Maria Silva" Python iniciante

Cada certificado recebe um identificador único.
📚 Trilhas

As trilhas representam o nível mais básico da plataforma.

Cada trilha está relacionada a uma tecnologia.

O Projeto 2 pode trabalhar com:

JavaScript
TypeScript
Python
React
Node.js
SQL
Git
Docker

Cada tecnologia pode possuir diferentes níveis:

Iniciante
Intermediário
Avançado

Exemplo:

JavaScript
├── Iniciante
├── Intermediário
└── Avançado

Uma trilha possui módulos e conteúdos.

Exemplo:

JavaScript — Iniciante

Módulo: Fundamentos
├── Variáveis
├── Tipos de dados
├── Operadores
└── Condicionais

Módulo: Funções
├── Declaração
├── Parâmetros
├── Retorno
└── Arrow Functions

🎯 Desafios

Os desafios permitem colocar em prática os conhecimentos adquiridos nas trilhas.

Cada desafio possui:

ID
Tecnologia
Nível
Título
Descrição
Entrada
Saída esperada

Exemplo:

🎯 Contador de vogais

Tecnologia: JavaScript
Nível: Iniciante

Descrição:
Crie uma função que receba uma palavra e
conte quantas vogais existem nela.

Entrada:
programacao

Saída esperada:
5

Outro exemplo:

🎯 API de tarefas

Tecnologia: Python
Nível: Avançado

Descrição:
Crie uma API que permita cadastrar,
listar e remover tarefas.

🏕️ Bootcamps

Bootcamps representam programas intensivos.

Eles agrupam diferentes tecnologias e trilhas em um único percurso.
Bootcamp Full Stack JavaScript

🚀 Bootcamp Full Stack JavaScript

Nível: Intermediário
Duração: 12 semanas

Tecnologias:

JavaScript
TypeScript
React
Node.js
SQL
Git

Projeto final:

Desenvolver uma aplicação web completa
com frontend, backend e banco de dados.

Bootcamp Python Backend

🐍 Bootcamp Python Backend

Nível: Intermediário
Duração: 10 semanas

Tecnologias:

Python
SQL
Git
Docker

Projeto final:

Construir uma API REST completa
para gerenciamento de tarefas.

Bootcamp Frontend Moderno

🎨 Bootcamp Frontend Moderno

Nível: Iniciante
Duração: 8 semanas

Tecnologias:

JavaScript
React
Git

Projeto final:

Construir uma aplicação frontend
responsiva utilizando React.

Bootcamp DevOps Fundamentals

⚙️ Bootcamp DevOps Fundamentals

Nível: Intermediário
Duração: 8 semanas

Tecnologias:

Git
Docker
Node.js

Projeto final:

Containerizar uma aplicação e criar
um fluxo básico de integração contínua.

🎓 Formações

As formações representam percursos maiores.

Elas podem combinar diversas trilhas e bootcamps.
Formação Desenvolvedor Full Stack

🎓 Formação Desenvolvedor Full Stack

Categoria:
Desenvolvimento Web

Nível:
Iniciante

Duração:
6 meses

Trilhas:

JavaScript
TypeScript
React
Node.js
SQL
Git
Docker

Projeto final:

Desenvolver uma aplicação web completa
com autenticação, API, banco de dados
e interface.

Formação Backend com Python

🎓 Formação Backend com Python

Categoria:
Backend

Nível:
Intermediário

Duração:
5 meses

Trilhas:

Python
SQL
Git
Docker

Projeto final:

Construir uma plataforma backend
com Python.

Formação Frontend Developer

🎓 Formação Frontend Developer

Categoria:
Frontend

Nível:
Iniciante

Duração:
4 meses

Trilhas:

JavaScript
React
Git

Formação DevOps

🎓 Formação DevOps

Categoria:
DevOps

Nível:
Intermediário

Duração:
4 meses

Trilhas:

Git
Docker
Node.js

📜 Certificados

O sistema permite gerar certificados fictícios para trilhas existentes.

Exemplo:

npm run dev -- certificado "João Silva" JavaScript iniciante

O certificado pode apresentar:

========================================

             GEO-EXPLORER

        CERTIFICADO FICTÍCIO

Certificamos que

            João Silva

concluiu a trilha

       JavaScript — Iniciante

Data de emissão:
10/09/2026

ID:
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx

========================================

Documento exclusivamente educacional.
Sem validade acadêmica ou profissional.

O ID é gerado utilizando:

crypto.randomUUID()

🛠️ Tecnologias utilizadas

    Node.js
    TypeScript
    npm
    JSON
    Git
    GitHub
    MCP

Dependências principais:

typescript
tsx
@types/node

🏗️ Arquitetura

O projeto utiliza separação de responsabilidades.

A entrada da aplicação passa pelo src/index.ts.

                         Usuário
                            │
                            ▼
                       src/index.ts
                            │
       ┌────────────────────┼────────────────────┐
       │          │         │         │           │
       ▼          ▼         ▼         ▼           ▼
    Trilha     Desafio   Bootcamp  Formação  Certificado
       │          │         │         │           │
       ▼          ▼         ▼         ▼           ▼
    Service     Service   Service   Service     Service
       │          │         │         │           │
       └──────────┴─────────┴─────────┴───────────┘
                            │
                            ▼
                         JSON

Essa estrutura permite que a aplicação cresça sem concentrar toda a lógica em um único arquivo.
📁 Estrutura do projeto

geo-explorer/
│
├── data/
│   ├── trilhas.json
│   ├── desafios.json
│   ├── bootcamps.json
│   └── formacoes.json
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
│   │   ├── bootcamp.ts
│   │   ├── formacao.ts
│   │   └── certificado.ts
│   │
│   ├── services/
│   │   ├── trilhaService.ts
│   │   ├── desafioService.ts
│   │   ├── bootcampService.ts
│   │   ├── formacaoService.ts
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
│   ├── bootcamp.test.ts
│   ├── formacao.test.ts
│   └── certificado.test.ts
│
├── .gitignore
├── package.json
├── package-lock.json
├── tsconfig.json
└── README.md

🗃️ Dados

Os dados educacionais são armazenados em arquivos JSON.
Trilhas

data/trilhas.json

Desafios

data/desafios.json

Bootcamps

data/bootcamps.json

Formações

data/formacoes.json

Essa abordagem permite adicionar novos conteúdos sem alterar diretamente os serviços.
💻 Comandos
Trilha

npm run dev -- trilha JavaScript iniciante

Desafio

npm run dev -- desafio Python intermediario

Bootcamp

npm run dev -- bootcamp "Bootcamp Full Stack JavaScript"

Formação

npm run dev -- formacao "Formação Desenvolvedor Full Stack"

Certificado

npm run dev -- certificado "Maria Silva" Python iniciante

💻 Instalação

Clone o projeto:

git clone <URL_DO_REPOSITORIO>

Entre na pasta:

cd geo-explorer

Instale as dependências:

npm install

▶️ Execução

Durante o desenvolvimento:

npm run dev

Executar uma trilha:

npm run dev -- trilha TypeScript iniciante

Executar um desafio:

npm run dev -- desafio JavaScript intermediario

Consultar um bootcamp:

npm run dev -- bootcamp "Bootcamp Python Backend"

Consultar uma formação:

npm run dev -- formacao "Formação Backend com Python"

Gerar um certificado:

npm run dev -- certificado "João Silva" JavaScript iniciante

🧪 Testes

Os testes automatizados verificam as principais funcionalidades.
Trilhas

    Busca existente.
    Tecnologia inexistente.
    Nível inexistente.

Desafios

    Busca existente.
    Busca inexistente.
    Tecnologia inexistente.
    Nível inexistente.

Bootcamps

    Busca existente.
    Busca inexistente.

Formações

    Busca existente.
    Busca inexistente.

Certificados

    Geração de certificado.
    Validação da trilha.
    ID único.
    Erro para trilha inexistente.

Executar os testes:

npm test

🔌 Servidor MCP

O projeto também possui uma camada experimental para integração através do Model Context Protocol — MCP.

O servidor está localizado em:

mcp/server.ts

A ideia é permitir que ferramentas compatíveis com MCP acessem funcionalidades do Geo-Explorer.

Operações planejadas:

listar_trilhas
get_trilha

gerar_desafio

listar_bootcamps
get_bootcamp

listar_formacoes
get_formacao

gerar_certificado

A arquitetura:

                  Ferramenta MCP
                        │
                        ▼
                  Servidor MCP
                        │
          ┌─────────────┼─────────────┐
          │             │             │
          ▼             ▼             ▼
       Trilhas       Desafios     Certificados
          │             │             │
          └─────────────┼─────────────┘
                        │
               ┌────────┴────────┐
               ▼                 ▼
           Bootcamps         Formações
               │                 │
               └────────┬────────┘
                        ▼
                  Geo-Explorer

O MCP funciona como uma camada de integração e não substitui os serviços existentes.
📦 Git e GitHub

Inicializar o repositório:

git init

Adicionar arquivos:

git add .

Criar commit:

git commit -m "feat: evolui Geo-Explorer para projeto 2"

Adicionar o repositório remoto:

git remote add origin <URL_DO_REPOSITORIO>

Enviar para o GitHub:

git branch -M main
git push -u origin main

Nunca envie:

.env
senhas
tokens
chaves de API
credenciais

O .gitignore deve conter pelo menos:

node_modules/
dist/
.env

🚀 Melhorias realizadas

A segunda versão adiciona:

    Novas trilhas.
    Novos desafios.
    Bootcamps.
    Formações.
    Novos serviços.
    Novos comandos.
    Novos testes.
    Estrutura de dados ampliada.
    Relacionamento entre trilhas e bootcamps.
    Relacionamento entre trilhas e formações.
    Maior organização arquitetural.
    Estrutura preparada para expansão.
    Integração planejada com MCP.
    Documentação atualizada.

🔮 Melhorias futuras

O projeto pode continuar evoluindo.
🌐 Interface Web

Criar uma interface utilizando:

    React;
    Next.js;
    Vue;
    HTML;
    CSS;
    JavaScript.

🤖 Inteligência Artificial

A IA poderia gerar desafios personalizados.

Exemplo:

Tecnologia: Python
Nível: Avançado
Tema: APIs

        ↓

       IA

        ↓

Desafio personalizado

Também poderia:

    Gerar dicas;
    Explicar soluções;
    Avaliar respostas;
    Adaptar dificuldades;
    Recomendar trilhas.

👤 Usuários

Adicionar:

    Cadastro;
    Login;
    Perfil;
    Histórico;
    Trilhas concluídas;
    Bootcamps concluídos;
    Formações concluídas;
    Certificados emitidos.

📊 Progresso

Adicionar acompanhamento:

JavaScript — Iniciante

████████████████░░░░ 80%

4 de 5 módulos concluídos

🏆 Gamificação

Adicionar:

    XP;
    Níveis;
    Badges;
    Conquistas;
    Ranking;
    Sequência de estudos.

🗄️ Banco de dados

Substituir os arquivos JSON por:

    SQLite;
    PostgreSQL;
    MySQL;
    MongoDB.

📄 Certificados em PDF

Criar certificados fictícios em PDF com layout visual.
🔎 Sistema de recomendação

O sistema poderá recomendar conteúdos de acordo com o progresso do usuário.

Exemplo:

Você concluiu:

JavaScript — Iniciante
React — Iniciante

Próxima recomendação:

🚀 TypeScript — Iniciante

🧠 Aprendizados

O desenvolvimento do Geo-Explorer Projeto 2 permitiu aprofundar conhecimentos em:

    Node.js;
    TypeScript;
    Tipagem;
    JSON;
    Organização de projetos;
    Separação de responsabilidades;
    Arquitetura de software;
    Serviços;
    Comandos;
    Testes automatizados;
    Git;
    GitHub;
    MCP;
    Documentação;
    Modelagem de dados;
    Utilização de IA durante o desenvolvimento.

Um dos principais aprendizados é que utilizar IA no desenvolvimento não significa apenas gerar código.

É necessário:

    Entender o problema.
    Planejar a solução.
    Definir a arquitetura.
    Revisar o código.
    Executar os testes.
    Corrigir problemas.
    Documentar as decisões.
    Saber explicar o funcionamento do projeto.

A IA é utilizada como ferramenta de apoio, enquanto as decisões técnicas continuam sendo responsabilidade do desenvolvedor.
🏁 Conclusão

O Geo-Explorer Projeto 2 representa uma evolução da primeira versão da aplicação.

A plataforma passou de uma estrutura baseada principalmente em trilhas, desafios e certificados para um modelo mais completo:

                 GEO-EXPLORER
                      │
       ┌──────────────┼──────────────┐
       │              │              │
    Trilhas        Desafios      Certificados
       │
       ├──────────────┐
       │              │
   Bootcamps      Formações

A aplicação continua simples, porém apresenta uma arquitetura organizada e preparada para receber novas funcionalidades.

O projeto pode futuramente evoluir para uma plataforma completa de aprendizagem, incluindo:

    Interface web;
    Usuários;
    Banco de dados;
    IA;
    Gamificação;
    Sistema de progresso;
    Certificados em PDF;
    Recomendações personalizadas;
    Integrações através do MCP.

Mais importante do que a quantidade de funcionalidades é compreender como as partes do sistema se relacionam e como uma aplicação pode evoluir de maneira organizada.
📄 Licença

Este projeto foi desenvolvido para fins educacionais.

Você pode adaptar, modificar e evoluir o projeto de acordo com seus objetivos de estudo e portfólio.

    ⚠️ Todos os conteúdos apresentados no Geo-Explorer são fictícios e possuem finalidade exclusivamente educacional.

    Os certificados, cursos, trilhas, bootcamps e formações não possuem validade acadêmica ou profissional.


