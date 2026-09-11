# -ConstruindoSeuPrimeiroProdutocomUmAgenteDeIA


Sim. Posso desenvolver o Geo-Explorer completo, seguindo exatamente os requisitos do desafio e deixando o projeto organizado para você publicar no GitHub.

Eu faria de uma forma que, além de funcionar, seja fácil de você explicar em uma apresentação ou entrevista.
Estrutura que podemos construir

geo-explorer/
├── .gitignore
├── README.md
├── package.json
├── tsconfig.json
│
├── data/
│   └── trilhas.json
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
├── mcp/
│   └── server.ts
│
├── tests/
│   ├── trilha.test.ts
│   ├── desafio.test.ts
│   └── certificado.test.ts
│
└── docs/
    └── arquitetura.md

Funcionalidades

Trilha

O usuário informa, por exemplo:

Tecnologia: JavaScript
Nível: iniciante

E recebe algo semelhante a:

🚀 Trilha: JavaScript — Iniciante

Módulo 1 — Fundamentos
- Variáveis
- Tipos de dados
- Operadores

Módulo 2 — Controle de fluxo
- if/else
- switch
- loops

Módulo 3 — Funções
- Declaração de funções
- Arrow functions
- Escopo

Desafio

Tecnologia: Python
Nível: intermediário

Retornaria um desafio adequado ao nível, por exemplo:

🐍 Desafio Python — Intermediário

Crie uma função que receba uma lista de números
e retorne somente os números primos.

Entrada:
[2, 4, 5, 8, 11, 15]

Saída esperada:
[2, 5, 11]

Certificado

O usuário informa nome e trilha:

Nome: João Silva
Trilha: JavaScript — Iniciante

E o sistema gera um certificado fictício com identificador, data e informações da trilha.
MCP

Também podemos implementar o Servidor MCP solicitado pelo desafio, expondo recursos como:

get_trilha
gerar_desafio
gerar_certificado
listar_trilhas

Assim, o Geo-Explorer não fica apenas como um programa de terminal: outras ferramentas compatíveis com MCP poderão consumir suas funcionalidades.
Testes

Também podemos criar testes automatizados para verificar:

✓ trilha existente
✓ tecnologia inexistente
✓ nível inválido
✓ geração de desafio
✓ certificado
✓ dados obrigatórios
✓ erros esperados

README

E vou estruturar o README.md para cumprir exatamente o que o desafio pede:

    O que é o Geo-Explorer
    Objetivo do projeto
    Tecnologias utilizadas
    Estrutura do projeto
    Instalação
    Execução
    Uso dos comandos
    Servidor MCP
    Execução dos testes
    Melhorias realizadas
    O que foi aprendido
    Exemplos de utilização

Uma coisa importante

Como esse é um desafio de portfólio, eu não recomendo simplesmente criar um monte de código e você copiar para o GitHub sem entender.

Podemos fazer de maneira incremental:

Etapa 1 → criar projeto e Git

Etapa 2 → criar a base trilhas.json

Etapa 3 → implementar trilha

Etapa 4 → implementar desafio

Etapa 5 → implementar certificado

Etapa 6 → testes

Etapa 7 → servidor MCP

Etapa 8 → documentação

Etapa 9 → revisão final e GitHub

E em cada etapa eu posso explicar o que o código está fazendo e por que foi feito daquela maneira.

Se você quiser, podemos começar agora pela Etapa 1, criando o projeto completo em TypeScript + Node.js, que é uma escolha muito adequada para esse desafio e para o servidor MCP.
You said:
ChatGPT said:

Perfeito. Vamos fazer passo a passo, começando pela estrutura base. Vou usar Node.js + TypeScript, deixando o projeto preparado para depois adicionarmos os comandos e o servidor MCP.
Etapa 1 — Criar o projeto
1. Crie a pasta

No terminal:

mkdir geo-explorer
cd geo-explorer

Inicialize o projeto:

npm init -y

Instale o TypeScript e ferramentas de desenvolvimento:

npm install -D typescript tsx @types/node

Crie a configuração do TypeScript:

npx tsc --init

2. Estrutura inicial

Crie estas pastas:

geo-explorer/
├── data/
├── src/
│   ├── commands/
│   ├── services/
│   └── types/
├── tests/
├── mcp/
└── docs/

No Linux, pode fazer:

mkdir -p src/commands src/services src/types
mkdir -p data tests mcp docs

Agora teremos:

geo-explorer/
├── data/
├── docs/
├── mcp/
├── src/
│   ├── commands/
│   ├── services/
│   └── types/
└── tests/

3. Criar o primeiro arquivo

Crie:

src/index.ts

Coloque:

console.log("🚀 Geo-Explorer iniciado!");

Execute:

npx tsx src/index.ts

Você deverá receber:

🚀 Geo-Explorer iniciado!

Isso confirma que o ambiente básico está funcionando.
4. Configurar o package.json

Abra o package.json e deixe os scripts assim:

{
  "name": "geo-explorer",
  "version": "1.0.0",
  "description": "Plataforma de exploração de trilhas de aprendizagem com desafios e certificados fictícios.",
  "main": "dist/index.js",
  "scripts": {
    "dev": "tsx src/index.ts",
    "build": "tsc",
    "start": "node dist/index.js",
    "test": "node --test"
  },
  "keywords": [
    "typescript",
    "nodejs",
    "mcp",
    "education",
    "learning"
  ],
  "author": "",
  "license": "MIT",
  "devDependencies": {
    "@types/node": "^24.0.0",
    "tsx": "^4.0.0",
    "typescript": "^5.0.0"
  }
}

Não se preocupe se as versões instaladas pelo seu npm forem diferentes; não precisa alterar as versões manualmente.
5. Configurar o TypeScript

No tsconfig.json, podemos usar uma configuração simples:

{
  "compilerOptions": {
    "target": "ES2022",
    "module": "NodeNext",
    "moduleResolution": "NodeNext",
    "rootDir": ".",
    "outDir": "dist",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  },
  "include": [
    "src/**/*.ts",
    "mcp/**/*.ts",
    "tests/**/*.ts"
  ],
  "exclude": [
    "node_modules",
    "dist"
  ]
}

Etapa 2 — Criar nossa base de trilhas

Agora vem uma parte importante do desafio.

Vamos criar:

data/trilhas.json

Inicialmente, podemos colocar três tecnologias:

{
  "trilhas": [
    {
      "tecnologia": "JavaScript",
      "niveis": {
        "iniciante": {
          "descricao": "Fundamentos da programação com JavaScript.",
          "modulos": [
            {
              "titulo": "Fundamentos",
              "conteudos": [
                "Variáveis",
                "Tipos de dados",
                "Operadores"
              ]
            },
            {
              "titulo": "Controle de fluxo",
              "conteudos": [
                "if e else",
                "switch",
                "Loops"
              ]
            },
            {
              "titulo": "Funções",
              "conteudos": [
                "Declaração de funções",
                "Parâmetros",
                "Arrow functions"
              ]
            }
          ]
        },
        "intermediario": {
          "descricao": "Desenvolvimento de aplicações JavaScript.",
          "modulos": [
            {
              "titulo": "JavaScript moderno",
              "conteudos": [
                "Destructuring",
                "Spread e Rest",
                "Modules"
              ]
            },
            {
              "titulo": "Programação assíncrona",
              "conteudos": [
                "Promises",
                "async/await",
                "Fetch API"
              ]
            }
          ]
        }
      }
    },
    {
      "tecnologia": "Python",
      "niveis": {
        "iniciante": {
          "descricao": "Fundamentos da programação com Python.",
          "modulos": [
            {
              "titulo": "Fundamentos",
              "conteudos": [
                "Variáveis",
                "Tipos de dados",
                "Operadores"
              ]
            },
            {
              "titulo": "Estruturas de controle",
              "conteudos": [
                "if",
                "for",
                "while"
              ]
            },
            {
              "titulo": "Funções",
              "conteudos": [
                "Definição",
                "Parâmetros",
                "Retorno"
              ]
            }
          ]
        }
      }
    },
    {
      "tecnologia": "Java",
      "niveis": {
        "iniciante": {
          "descricao": "Introdução à programação com Java.",
          "modulos": [
            {
              "titulo": "Fundamentos",
              "conteudos": [
                "Variáveis",
                "Tipos primitivos",
                "Operadores"
              ]
            },
            {
              "titulo": "Orientação a objetos",
              "conteudos": [
                "Classes",
                "Objetos",
                "Métodos"
              ]
            }
          ]
        }
      }
    }
  ]
}

Isso já atende à ideia de uma base fictícia de trilhas, mas depois podemos aumentar bastante.
O que já temos

Neste ponto, nosso projeto ficará assim:

geo-explorer/
│
├── data/
│   └── trilhas.json
│
├── docs/
│
├── mcp/
│
├── src/
│   ├── commands/
│   ├── services/
│   ├── types/
│   └── index.ts
│
├── tests/
│
├── .gitignore
├── package.json
├── package-lock.json
└── tsconfig.json

Crie também um .gitignore:

node_modules/
dist/
.env
.env.*
*.log

Próxima etapa

Agora temos a fundação. Ainda não vamos criar os três comandos de uma vez.

O próximo passo será criar os tipos TypeScript e o primeiro serviço:

data/trilhas.json
        ↓
trilhaService.ts
        ↓
comando "trilha"
        ↓
resultado para o usuário

Isso é importante porque vamos separar dados, regra de negócio e comando, em vez de colocar tudo dentro do index.ts. Assim o projeto fica mais profissional e também facilita os testes.
You said:
ChatGPT said:

Ótimo. Vamos para a Etapa 3: criar os tipos e implementar o comando trilha.

A ideia agora é fazer o primeiro recurso funcionar de verdade:

Usuário
   ↓
comando trilha
   ↓
trilhaService
   ↓
trilhas.json
   ↓
resultado formatado

1. Criar os tipos

Crie:

src/types/index.ts

Coloque:

export interface Modulo {
  titulo: string;
  conteudos: string[];
}

export interface Nivel {
  descricao: string;
  modulos: Modulo[];
}

export interface Trilha {
  tecnologia: string;
  niveis: Record<string, Nivel>;
}

export interface BaseTrilhas {
  trilhas: Trilha[];
}

O que isso faz?

Estamos dizendo ao TypeScript como nossa base de dados deve ser estruturada.

Por exemplo:

Trilha

tem:

tecnologia
└── níveis
    ├── iniciante
    ├── intermediario
    └── avançado

E cada nível possui:

descricao
modulos

2. Criar o serviço de trilhas

Agora crie:

src/services/trilhaService.ts

Use:

import fs from "node:fs";
import path from "node:path";

import { BaseTrilhas, Nivel, Trilha } from "../types/index.js";

export class TrilhaService {
  private readonly trilhas: Trilha[];

  constructor() {
    const caminhoArquivo = path.resolve(
      process.cwd(),
      "data",
      "trilhas.json"
    );

    const arquivo = fs.readFileSync(caminhoArquivo, "utf-8");

    const dados: BaseTrilhas = JSON.parse(arquivo);

    this.trilhas = dados.trilhas;
  }

  listarTrilhas(): Trilha[] {
    return this.trilhas;
  }

  buscarTrilha(
    tecnologia: string,
    nivel: string
  ): Nivel | null {
    const trilha = this.trilhas.find(
      (item) =>
        item.tecnologia.toLowerCase() === tecnologia.toLowerCase()
    );

    if (!trilha) {
      return null;
    }

    return trilha.niveis[nivel.toLowerCase()] ?? null;
  }
}

3. Criar o comando trilha

Agora crie:

src/commands/trilha.ts

import { TrilhaService } from "../services/trilhaService.js";

export function executarTrilha(
  tecnologia: string,
  nivel: string
): string {
  const service = new TrilhaService();

  const resultado = service.buscarTrilha(
    tecnologia,
    nivel
  );

  if (!resultado) {
    return `❌ Não encontramos uma trilha para ${tecnologia} no nível ${nivel}.`;
  }

  let resposta = "";

  resposta += `🚀 Trilha de ${tecnologia} — ${nivel}\n\n`;
  resposta += `${resultado.descricao}\n\n`;

  resultado.modulos.forEach((modulo, indice) => {
    resposta += `📚 Módulo ${indice + 1} — ${modulo.titulo}\n`;

    modulo.conteudos.forEach((conteudo) => {
      resposta += `- ${conteudo}\n`;
    });

    resposta += "\n";
  });

  return resposta.trim();
}

Agora temos uma separação interessante:

trilha.ts
   ↓
responsável pelo comando

trilhaService.ts
   ↓
responsável pela lógica

trilhas.json
   ↓
responsável pelos dados

Isso é muito melhor do que colocar tudo em um único arquivo.
4. Fazer o index.ts receber argumentos

Agora vamos modificar:

src/index.ts

para:

import { executarTrilha } from "./commands/trilha.js";

const argumentos = process.argv.slice(2);

const comando = argumentos[0];

if (comando === "trilha") {
  const tecnologia = argumentos[1];
  const nivel = argumentos[2];

  if (!tecnologia || !nivel) {
    console.log(
      "Uso: npm run dev -- trilha <tecnologia> <nivel>"
    );

    process.exit(1);
  }

  console.log(executarTrilha(tecnologia, nivel));
} else {
  console.log("❌ Comando não reconhecido.");
  console.log("Comandos disponíveis:");
  console.log("- trilha");
}

5. Testar

Agora execute:

npm run dev -- trilha JavaScript iniciante

Deverá aparecer algo parecido com:

🚀 Trilha de JavaScript — iniciante

Fundamentos da programação com JavaScript.

📚 Módulo 1 — Fundamentos
- Variáveis
- Tipos de dados
- Operadores

📚 Módulo 2 — Controle de fluxo
- if e else
- switch
- Loops

📚 Módulo 3 — Funções
- Declaração de funções
- Parâmetros
- Arrow functions

Teste também:

npm run dev -- trilha Python iniciante

E:

npm run dev -- trilha JavaScript intermediario

Agora teste um erro:

npm run dev -- trilha PHP iniciante

Você deverá receber:

❌ Não encontramos uma trilha para PHP no nível iniciante.

🧪 Uma observação importante

Ainda não estamos usando IA para gerar a trilha.

E isso é proposital.

O desafio diz que existe uma base de trilhas fictícias. Portanto, primeiro fazemos o sistema funcionar utilizando dados determinísticos.

Depois podemos utilizar IA de maneira complementar, se quisermos evoluir o projeto.

Isso também deixa o projeto mais fácil de testar:

mesma entrada
     ↓
mesmo resultado

Em vez de depender de uma API de IA durante os testes.
📌 Estado atual do projeto

Já temos:

✅ Node.js
✅ TypeScript
✅ Estrutura de pastas
✅ Base de trilhas
✅ Tipos TypeScript
✅ Serviço de trilhas
✅ Comando "trilha"
✅ Tratamento básico de erro

Falta:

⬜ comando desafio
⬜ comando certificado
⬜ testes automatizados
⬜ servidor MCP
⬜ documentação
⬜ melhorias
⬜ publicação no GitHub

Próxima etapa

A próxima será particularmente interessante: vamos implementar o desafio, fazendo com que tecnologia + nível determinem o tipo de desafio retornado.

Depois disso, vamos criar os testes para trilha + desafio, antes de partir para o certificado e MCP.
You said:
ChatGPT said:

Perfeito. Agora vamos para a Etapa 4 — comando desafio.

Vamos manter a mesma arquitetura:

Usuário
   ↓
desafio
   ↓
DesafioService
   ↓
base de desafios
   ↓
desafio adequado à tecnologia + nível

A ideia é não colocar os desafios diretamente no código do comando.
1. Criar a base de desafios

Crie:

data/desafios.json

Use:

{
  "desafios": [
    {
      "id": 1,
      "tecnologia": "JavaScript",
      "nivel": "iniciante",
      "titulo": "Calculadora de desconto",
      "descricao": "Crie uma função que receba o preço de um produto e o percentual de desconto e retorne o preço final.",
      "entrada": "preco = 100, desconto = 15",
      "saidaEsperada": "85"
    },
    {
      "id": 2,
      "tecnologia": "JavaScript",
      "nivel": "intermediario",
      "titulo": "Filtrar números pares",
      "descricao": "Crie uma função que receba uma lista de números e retorne somente os números pares.",
      "entrada": "[1, 2, 3, 4, 5, 6]",
      "saidaEsperada": "[2, 4, 6]"
    },
    {
      "id": 3,
      "tecnologia": "Python",
      "nivel": "iniciante",
      "titulo": "Contador de vogais",
      "descricao": "Crie uma função que receba uma palavra e conte quantas vogais ela possui.",
      "entrada": "\"programacao\"",
      "saidaEsperada": "5"
    },
    {
      "id": 4,
      "tecnologia": "Python",
      "nivel": "intermediario",
      "titulo": "Números primos",
      "descricao": "Crie uma função que receba uma lista de números e retorne somente os números primos.",
      "entrada": "[2, 4, 5, 8, 11, 15]",
      "saidaEsperada": "[2, 5, 11]"
    },
    {
      "id": 5,
      "tecnologia": "Java",
      "nivel": "iniciante",
      "titulo": "Média de notas",
      "descricao": "Crie um programa que receba três notas e calcule a média do aluno.",
      "entrada": "[7, 8, 9]",
      "saidaEsperada": "8"
    }
  ]
}

Agora temos uma pequena base fictícia de desafios.
2. Criar os tipos

Abra:

src/types/index.ts

E acrescente:

export interface Desafio {
  id: number;
  tecnologia: string;
  nivel: string;
  titulo: string;
  descricao: string;
  entrada: string;
  saidaEsperada: string;
}

export interface BaseDesafios {
  desafios: Desafio[];
}

O arquivo completo ficará:

export interface Modulo {
  titulo: string;
  conteudos: string[];
}

export interface Nivel {
  descricao: string;
  modulos: Modulo[];
}

export interface Trilha {
  tecnologia: string;
  niveis: Record<string, Nivel>;
}

export interface BaseTrilhas {
  trilhas: Trilha[];
}

export interface Desafio {
  id: number;
  tecnologia: string;
  nivel: string;
  titulo: string;
  descricao: string;
  entrada: string;
  saidaEsperada: string;
}

export interface BaseDesafios {
  desafios: Desafio[];
}

3. Criar o DesafioService

Crie:

src/services/desafioService.ts

import fs from "node:fs";
import path from "node:path";

import { BaseDesafios, Desafio } from "../types/index.js";

export class DesafioService {
  private readonly desafios: Desafio[];

  constructor() {
    const caminhoArquivo = path.resolve(
      process.cwd(),
      "data",
      "desafios.json"
    );

    const arquivo = fs.readFileSync(
      caminhoArquivo,
      "utf-8"
    );

    const dados: BaseDesafios = JSON.parse(arquivo);

    this.desafios = dados.desafios;
  }

  buscarDesafio(
    tecnologia: string,
    nivel: string
  ): Desafio | null {
    const encontrados = this.desafios.filter(
      (desafio) =>
        desafio.tecnologia.toLowerCase() ===
          tecnologia.toLowerCase() &&
        desafio.nivel.toLowerCase() ===
          nivel.toLowerCase()
    );

    if (encontrados.length === 0) {
      return null;
    }

    const indice = Math.floor(
      Math.random() * encontrados.length
    );

    return encontrados[indice];
  }
}

Por que usamos filter()?

Porque podemos ter vários desafios para a mesma tecnologia e nível.

Por exemplo:

JavaScript
└── iniciante
    ├── desafio 1
    ├── desafio 2
    └── desafio 3

O serviço encontra todos e escolhe um aleatoriamente.
4. Criar o comando

Crie:

src/commands/desafio.ts

import { DesafioService } from "../services/desafioService.js";

export function executarDesafio(
  tecnologia: string,
  nivel: string
): string {
  const service = new DesafioService();

  const desafio = service.buscarDesafio(
    tecnologia,
    nivel
  );

  if (!desafio) {
    return `❌ Não encontramos desafios para ${tecnologia} no nível ${nivel}.`;
  }

  let resposta = "";

  resposta += `🎯 Desafio — ${desafio.titulo}\n\n`;
  resposta += `Tecnologia: ${desafio.tecnologia}\n`;
  resposta += `Nível: ${desafio.nivel}\n\n`;

  resposta += `📝 Descrição\n`;
  resposta += `${desafio.descricao}\n\n`;

  resposta += `📥 Entrada\n`;
  resposta += `${desafio.entrada}\n\n`;

  resposta += `📤 Saída esperada\n`;
  resposta += `${desafio.saidaEsperada}\n`;

  return resposta;
}

5. Adicionar o comando ao index.ts

Agora nosso src/index.ts precisa reconhecer dois comandos.

Substitua o conteúdo por:

import { executarTrilha } from "./commands/trilha.js";
import { executarDesafio } from "./commands/desafio.js";

const argumentos = process.argv.slice(2);

const comando = argumentos[0];

switch (comando) {
  case "trilha": {
    const tecnologia = argumentos[1];
    const nivel = argumentos[2];

    if (!tecnologia || !nivel) {
      console.log(
        "Uso: npm run dev -- trilha <tecnologia> <nivel>"
      );

      process.exit(1);
    }

    console.log(
      executarTrilha(tecnologia, nivel)
    );

    break;
  }

  case "desafio": {
    const tecnologia = argumentos[1];
    const nivel = argumentos[2];

    if (!tecnologia || !nivel) {
      console.log(
        "Uso: npm run dev -- desafio <tecnologia> <nivel>"
      );

      process.exit(1);
    }

    console.log(
      executarDesafio(tecnologia, nivel)
    );

    break;
  }

  default:
    console.log("❌ Comando não reconhecido.");
    console.log("");
    console.log("Comandos disponíveis:");
    console.log("  trilha <tecnologia> <nivel>");
    console.log("  desafio <tecnologia> <nivel>");
}

6. Testar o desafio

Execute:

npm run dev -- desafio JavaScript iniciante

Você deverá receber algo parecido com:

🎯 Desafio — Calculadora de desconto

Tecnologia: JavaScript
Nível: iniciante

📝 Descrição
Crie uma função que receba o preço de um produto
e o percentual de desconto e retorne o preço final.

📥 Entrada
preco = 100, desconto = 15

📤 Saída esperada
85

Teste Python:

npm run dev -- desafio Python intermediario

Resultado:

🎯 Desafio — Números primos

Tecnologia: Python
Nível: intermediario

📝 Descrição
Crie uma função que receba uma lista de números
e retorne somente os números primos.

📥 Entrada
[2, 4, 5, 8, 11, 15]

📤 Saída esperada
[2, 5, 11]

E teste uma tecnologia inexistente:

npm run dev -- desafio Rust iniciante

Deve retornar:

❌ Não encontramos desafios para Rust no nível iniciante.

⚠️ Uma decisão importante

Você pode perceber que usamos:

Math.random()

Isso é ótimo para o comportamento real do programa, mas cria uma pequena dificuldade para testes automatizados, porque o resultado pode mudar a cada execução.

Isso é algo que vamos resolver quando chegarmos aos testes.

Uma arquitetura ainda melhor posteriormente seria permitir que o serviço recebesse uma fonte de aleatoriedade ou um índice, mas não precisamos complicar o projeto agora.
📊 Nosso projeto agora

Já temos:

geo-explorer/
│
├── data/
│   ├── trilhas.json        ✅
│   └── desafios.json       ✅
│
├── src/
│   ├── commands/
│   │   ├── trilha.ts       ✅
│   │   └── desafio.ts      ✅
│   │
│   ├── services/
│   │   ├── trilhaService.ts    ✅
│   │   └── desafioService.ts   ✅
│   │
│   ├── types/
│   │   └── index.ts        ✅
│   │
│   └── index.ts             ✅
│
├── tests/
├── mcp/
└── docs/

Falta agora:

⬜ Certificado
⬜ Testes automatizados
⬜ Servidor MCP
⬜ README profissional
⬜ Melhorias
⬜ Git/GitHub

Próximo passo: certificado

Na próxima etapa vamos criar o terceiro comando:

npm run dev -- certificado "Seu Nome" "JavaScript" "iniciante"

Ele vai gerar um certificado fictício com ID único, data, nome, tecnologia e nível.

Depois disso teremos os três comandos principais do desafio funcionando, e aí partimos para uma parte muito importante do projeto: testes automatizados.
You said:
ChatGPT said:

Perfeito. Agora vamos implementar o terceiro comando principal: certificado. Depois dele, o fluxo básico do Geo-Explorer estará completo.
Etapa 5 — Certificado

O comando terá esta ideia:

Usuário
   ↓
certificado
   ↓
CertificadoService
   ↓
validação da trilha
   ↓
certificado fictício

Vamos gerar um certificado fictício, sem qualquer validade oficial.
1. Acrescentar o tipo de certificado

Abra:

src/types/index.ts

Acrescente ao final:

export interface Certificado {
  id: string;
  nome: string;
  tecnologia: string;
  nivel: string;
  dataEmissao: string;
  titulo: string;
}

2. Criar o CertificadoService

Crie:

src/services/certificadoService.ts

Coloque:

import crypto from "node:crypto";

import { Certificado } from "../types/index.js";
import { TrilhaService } from "./trilhaService.js";

export class CertificadoService {
  private readonly trilhaService: TrilhaService;

  constructor() {
    this.trilhaService = new TrilhaService();
  }

  gerarCertificado(
    nome: string,
    tecnologia: string,
    nivel: string
  ): Certificado | null {
    const trilha = this.trilhaService.buscarTrilha(
      tecnologia,
      nivel
    );

    if (!trilha) {
      return null;
    }

    return {
      id: crypto.randomUUID(),
      nome,
      tecnologia,
      nivel,
      dataEmissao: new Date().toLocaleDateString("pt-BR"),
      titulo: `Conclusão da Trilha de ${tecnologia}`
    };
  }
}

O que está acontecendo aqui?

Primeiro verificamos se a trilha realmente existe:

const trilha = this.trilhaService.buscarTrilha(
  tecnologia,
  nivel
);

Isso evita gerar certificado para uma trilha inexistente.

Depois:

crypto.randomUUID()

gera um identificador único para o certificado.

Por exemplo:

8c9e6d2e-3f6c-4c5f-9a72-4b7d5e1f1234

3. Criar o comando

Crie:

src/commands/certificado.ts

Use:

import { CertificadoService } from "../services/certificadoService.js";

export function executarCertificado(
  nome: string,
  tecnologia: string,
  nivel: string
): string {
  const service = new CertificadoService();

  const certificado = service.gerarCertificado(
    nome,
    tecnologia,
    nivel
  );

  if (!certificado) {
    return (
      `❌ Não foi possível gerar o certificado.\n` +
      `A trilha ${tecnologia} — ${nivel} não existe.`
    );
  }

  return `
╔══════════════════════════════════════════════╗
║                                              ║
║              🎓 CERTIFICADO                  ║
║                                              ║
║  Certificamos que                            ║
║                                              ║
║  ${certificado.nome}
║                                              ║
║  concluiu a trilha de aprendizagem           ║
║                                              ║
║  ${certificado.tecnologia} — ${certificado.nivel}
║                                              ║
║  ${certificado.titulo}
║                                              ║
║  Data de emissão: ${certificado.dataEmissao}
║                                              ║
║  ID: ${certificado.id}
║                                              ║
║  ⚠️ Certificado fictício para fins educativos║
║                                              ║
╚══════════════════════════════════════════════╝
`.trim();
}

4. Adicionar ao index.ts

Agora importe:

import { executarCertificado } from "./commands/certificado.js";

E adicione um novo case ao switch:

case "certificado": {
  const nome = argumentos[1];
  const tecnologia = argumentos[2];
  const nivel = argumentos[3];

  if (!nome || !tecnologia || !nivel) {
    console.log(
      "Uso: npm run dev -- certificado <nome> <tecnologia> <nivel>"
    );

    process.exit(1);
  }

  console.log(
    executarCertificado(nome, tecnologia, nivel)
  );

  break;
}

E atualize a parte dos comandos disponíveis:

default:
  console.log("❌ Comando não reconhecido.");
  console.log("");
  console.log("Comandos disponíveis:");
  console.log("  trilha <tecnologia> <nivel>");
  console.log("  desafio <tecnologia> <nivel>");
  console.log("  certificado <nome> <tecnologia> <nivel>");

5. Testar

Execute:

npm run dev -- certificado "João Silva" JavaScript iniciante

O resultado será aproximadamente:

╔══════════════════════════════════════════════╗
║                                              ║
║              🎓 CERTIFICADO                  ║
║                                              ║
║  Certificamos que                            ║
║                                              ║
║  João Silva
║                                              ║
║  concluiu a trilha de aprendizagem           ║
║                                              ║
║  JavaScript — iniciante
║                                              ║
║  Conclusão da Trilha de JavaScript
║                                              ║
║  Data de emissão: 28/08/2026
║                                              ║
║  ID: 7f1c...
║                                              ║
║  ⚠️ Certificado fictício para fins educativos║
║                                              ║
╚══════════════════════════════════════════════╝

Teste também:

npm run dev -- certificado "Maria Silva" Python iniciante

E uma trilha inexistente:

npm run dev -- certificado "João Silva" Rust iniciante

Deve retornar erro.
🎯 Agora temos os 3 comandos!

O requisito central do desafio está praticamente implementado:

                 GEO-EXPLORER
                      │
        ┌─────────────┼─────────────┐
        ↓             ↓             ↓
     TRILHA        DESAFIO      CERTIFICADO
        │             │             │
        ↓             ↓             ↓
     trilhas.json  desafios.json  trilhaService

Podemos executar:

npm run dev -- trilha JavaScript iniciante

npm run dev -- desafio Python intermediario

npm run dev -- certificado "João Silva" JavaScript iniciante

🧪 Próxima etapa: testes

Agora eu não recomendo continuar adicionando funcionalidades ainda.

É hora de fazer algo muito importante para o desafio: testar aquilo que já construímos.

Vamos criar testes para:

    TrilhaService
    DesafioService
    CertificadoService
    tecnologias inexistentes
    níveis inexistentes
    certificados
    estrutura dos resultados

E vamos configurar o projeto para que você consiga simplesmente executar:

npm test

e obter algo como:

✔ busca trilha JavaScript iniciante
✔ rejeita tecnologia inexistente
✔ encontra desafio Python intermediário
✔ rejeita desafio inexistente
✔ gera certificado válido
✔ rejeita certificado de trilha inexistente

6 testes
6 aprovados

Essa etapa é especialmente importante para o portfólio, porque mostra que você não apenas criou o código, mas também verificou automaticamente se ele funciona.


