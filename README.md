# 🔴 Pokédex AI V2

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge\&logo=python\&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge\&logo=streamlit\&logoColor=white)
![Groq](https://img.shields.io/badge/Groq-F55036?style=for-the-badge)
![REST API](https://img.shields.io/badge/REST-API-009688?style=for-the-badge)
![Generative AI](https://img.shields.io/badge/Generative-AI-8A2BE2?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Em%20Desenvolvimento-success?style=for-the-badge)

Aplicação interativa desenvolvida em **Python + Streamlit** que combina dados em tempo real da **PokéAPI** com Inteligência Artificial Generativa através da **Groq API**.

O projeto permite conversar com uma Pokédex inteligente capaz de identificar Pokémon nas perguntas, consultar dados estruturados e utilizar um LLM para gerar respostas contextualizadas.

---

## 🎯 Objetivo do Projeto

O objetivo da **Pokédex AI V2** é demonstrar, de forma prática, como integrar:

* APIs REST
* Inteligência Artificial Generativa
* Large Language Models (LLMs)
* Engenharia de Prompt
* Processamento de dados
* Gerenciamento de estado
* Interface web com Python
* Segurança de variáveis de ambiente

A aplicação utiliza dados da **PokéAPI** como contexto para fornecer informações estruturadas ao modelo de linguagem e gerar respostas mais contextualizadas sobre cada Pokémon.

---

## ✨ Funcionalidades

* 🔎 Identificação automática do Pokémon citado na pergunta
* 🖼️ Exibição da imagem oficial disponível na PokéAPI
* 📊 Consulta de stats
* ⚡ Consulta de tipos
* 🧬 Linha evolutiva
* 🛡️ Fraquezas, resistências e imunidades
* 🎯 Consulta de habilidades
* 📏 Altura e peso
* 🤖 Respostas geradas por IA utilizando Groq
* 💬 Histórico de conversa com `st.session_state`
* 🔐 Proteção da API Key
* 🛡️ Proteção básica contra Prompt Injection
* 🌐 Consumo de dados externos via API REST

---

## 🤖 Como funciona

O usuário realiza uma pergunta como:

```text
Quais são as fraquezas do Charizard?
```

A aplicação identifica o Pokémon mencionado e executa o seguinte fluxo:

```text
Usuário
   ↓
Streamlit
   ↓
Identificação do Pokémon
   ↓
PokéAPI
   ↓
Coleta dos dados estruturados
   ↓
Processamento das informações
   ↓
Construção do contexto
   ↓
Groq API + LLM
   ↓
Resposta contextualizada
   ↓
Interface Streamlit
```

Dessa forma, o modelo de linguagem recebe informações externas estruturadas antes de gerar a resposta para o usuário.

---

## 🧠 Arquitetura

A aplicação utiliza uma arquitetura baseada em **API + processamento Python + LLM**.

```text
                  ┌─────────────────┐
                  │     Usuário     │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │    Streamlit    │
                  │       UI        │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │ Processamento   │
                  │     Python      │
                  └──────┬─────┬────┘
                         │     │
             ┌───────────┘     └───────────┐
             ▼                             ▼
      ┌─────────────┐               ┌─────────────┐
      │   PokéAPI   │               │  Groq API   │
      │ Dados       │               │     LLM     │
      └──────┬──────┘               └──────┬──────┘
             │                             │
             └─────────────┬───────────────┘
                           ▼
                  ┌─────────────────┐
                  │    Resposta     │
                  │ Contextualizada │
                  └─────────────────┘
```

---

## 🚀 Tecnologias Utilizadas

| Tecnologia       | Utilização                             |
| ---------------- | -------------------------------------- |
| Python           | Linguagem principal                    |
| Streamlit        | Interface web                          |
| Groq             | Inferência do modelo de IA             |
| PokéAPI          | Fonte de dados dos Pokémon             |
| Requests         | Consumo de APIs REST                   |
| python-dotenv    | Gerenciamento de variáveis de ambiente |
| st.session_state | Histórico da conversa                  |

---

## 📂 Estrutura do Projeto

```text
pokedex_ai_v2/
│
├── .streamlit/
│   └── config.toml
│
├── .env.example
├── .gitignore
├── app.py
├── requirements.txt
└── README.md
```

### Principais arquivos

### `app.py`

Arquivo principal da aplicação.

Responsável por:

* Interface Streamlit
* Processamento das perguntas
* Comunicação com a PokéAPI
* Integração com Groq
* Gerenciamento do histórico
* Construção do contexto enviado ao LLM

### `requirements.txt`

Contém todas as dependências necessárias para executar o projeto.

### `.env.example`

Arquivo de exemplo demonstrando quais variáveis de ambiente precisam ser configuradas.

### `.gitignore`

Impede que arquivos sensíveis e desnecessários sejam enviados ao GitHub.

---

# ⚙️ Executando Localmente

## 1. Clone o repositório

```bash
git clone https://github.com/SEU-USUARIO/pokedex_ai_v2.git
```

Entre na pasta:

```bash
cd pokedex_ai_v2
```

---

## 2. Crie um ambiente virtual

### Windows PowerShell

```powershell
python -m venv .venv
```

Ative o ambiente:

```powershell
.\.venv\Scripts\Activate.ps1
```

---

## 3. Instale as dependências

```powershell
pip install -r requirements.txt
```

---

## 4. Configure a chave da Groq

Faça uma cópia do arquivo:

```text
.env.example
```

Renomeie para:

```text
.env
```

Depois configure sua chave:

```env
GROQ_API_KEY=sua_chave_da_groq_aqui
```

> ⚠️ Nunca envie sua chave de API real para um repositório público.

O arquivo `.env` deve permanecer no `.gitignore`.

---

## 5. Execute a aplicação

```powershell
streamlit run app.py
```

O Streamlit normalmente disponibilizará a aplicação em:

```text
http://localhost:8501
```

---

# 💬 Exemplos de Perguntas

Você pode conversar naturalmente com a Pokédex.

```text
Me fale sobre Pikachu.
```

```text
Quais são as fraquezas do Charizard?
```

```text
Como o Eevee evolui?
```

```text
Quais habilidades o Bulbasaur possui?
```

```text
Quais são os stats do Mewtwo?
```

```text
Quais tipos são fortes contra Gengar?
```

---

# 🛡️ Segurança

O projeto utiliza algumas boas práticas básicas de segurança.

## 🔐 Variáveis de ambiente

A chave da Groq é armazenada através da variável:

```env
GROQ_API_KEY
```

A credencial não fica hardcoded diretamente no código.

---

## 🚫 `.gitignore`

Arquivos contendo credenciais e informações locais não devem ser enviados ao GitHub.

Exemplo:

```gitignore
.env
.venv/
__pycache__/
```

---

## 🛡️ Prompt Injection

A aplicação possui proteção básica contra tentativas de manipulação das instruções internas enviadas ao modelo.

> As proteções utilizadas têm finalidade educacional e não substituem mecanismos avançados de segurança para aplicações em produção.

---

# 🧩 Conceitos Aplicados

Este projeto demonstra conhecimentos relacionados a:

* Python
* APIs REST
* JSON
* Inteligência Artificial Generativa
* Large Language Models
* Engenharia de Prompt
* Integração de APIs
* Manipulação de dados
* Gerenciamento de sessão
* Streamlit
* Variáveis de ambiente
* Segurança de API Keys
* Prompt Injection
* Contextualização de LLM com dados externos

---

# 📸 Screenshots

Uma boa prática para o portfólio é adicionar imagens da aplicação funcionando.

Crie uma pasta:

```text
docs/
```

Exemplo:

```text
pokedex_ai_v2/
│
├── docs/
│   ├── pokedex-home.png
│   └── pokedex-chat.png
│
├── app.py
├── requirements.txt
└── README.md
```

## 🏠 Tela Principal

```markdown
![Pokédex AI](./docs/pokedex-home.png)
```

## 💬 Conversa com a IA

```markdown
![Chat Pokédex](./docs/pokedex-chat.png)
```

---

# 🚧 Roadmap

### Implementado

* [x] Integração com PokéAPI
* [x] Integração com Groq
* [x] Interface Streamlit
* [x] Histórico de conversa
* [x] Consulta de tipos
* [x] Consulta de habilidades
* [x] Consulta de stats
* [x] Linha evolutiva
* [x] Fraquezas e resistências
* [x] Proteção da API Key
* [x] Proteção básica contra Prompt Injection

### Próximas melhorias

* [ ] Comparação entre dois Pokémon
* [ ] Sistema de batalha utilizando IA
* [ ] Cache de consultas da PokéAPI
* [ ] Memória persistente
* [ ] Separação do projeto em módulos
* [ ] Testes automatizados
* [ ] Deploy público
* [ ] Suporte a múltiplos modelos de IA

---

# 🔮 Possível Evolução da Arquitetura

Uma evolução futura do projeto pode separar as responsabilidades em módulos.

```text
pokedex_ai_v2/
│
├── services/
│   ├── pokeapi.py
│   └── groq_service.py
│
├── utils/
│   └── security.py
│
├── .streamlit/
│   └── config.toml
│
├── app.py
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

Isso facilitaria:

* Manutenção do código
* Testes
* Escalabilidade
* Reutilização de funções
* Separação de responsabilidades

---

# 📌 Status do Projeto

🟢 **Projeto funcional e em evolução**

Novas funcionalidades poderão ser adicionadas conforme novos conceitos de desenvolvimento, integração de sistemas e Inteligência Artificial forem estudados.

---

## 💡 Aprendizados

Durante o desenvolvimento deste projeto foram aplicados conceitos de integração entre APIs tradicionais e modelos de Inteligência Artificial.

A **PokéAPI** funciona como fonte estruturada de dados, enquanto o **LLM executado através da Groq** atua como camada de interpretação e geração de linguagem natural.

Essa arquitetura demonstra como:

**APIs + Python + LLMs podem trabalhar em conjunto para criar aplicações inteligentes baseadas em dados externos.**

---

## 📄 Licença

Projeto desenvolvido para fins educacionais e de portfólio.
