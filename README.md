# 🔴 Pokédex AI V2

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![Groq](https://img.shields.io/badge/Groq-F55036?style=for-the-badge)
![REST API](https://img.shields.io/badge/REST-API-009688?style=for-the-badge)
![Generative AI](https://img.shields.io/badge/Generative-AI-8A2BE2?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Em%20Desenvolvimento-success?style=for-the-badge)

Aplicação interativa desenvolvida em **Python + Streamlit** que combina dados em tempo real da **PokéAPI** com Inteligência Artificial Generativa através da **Groq API**.

O projeto permite conversar com uma Pokédex inteligente capaz de identificar Pokémon nas perguntas, consultar dados estruturados e utilizar um LLM para gerar respostas contextualizadas.

---

## 🎯 Objetivo do Projeto

O objetivo da **Pokédex AI V2** é demonstrar, de forma prática, como integrar:

- APIs REST
- Inteligência Artificial Generativa
- Large Language Models (LLMs)
- Engenharia de Prompt
- Processamento de dados
- Gerenciamento de estado
- Interface web com Python
- Segurança de variáveis de ambiente

A aplicação utiliza dados da **PokéAPI** como contexto para fornecer informações estruturadas ao modelo de linguagem e gerar respostas contextualizadas sobre cada Pokémon.

---

## ✨ Funcionalidades

- 🔎 Identificação automática do Pokémon citado na pergunta
- 🖼️ Exibição da imagem oficial disponível na PokéAPI
- 📊 Consulta de stats
- ⚡ Consulta de tipos
- 🧬 Linha evolutiva
- 🛡️ Fraquezas, resistências e imunidades
- 🎯 Consulta de habilidades
- 📏 Altura e peso
- 🤖 Respostas geradas por IA utilizando Groq
- 💬 Histórico de conversa com `st.session_state`
- 🔐 Proteção da API Key
- 🛡️ Proteção básica contra Prompt Injection
- 🌐 Consumo de dados externos via API REST

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
      │    Dados    │               │     LLM     │
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

| Tecnologia | Utilização |
| --- | --- |
| Python | Linguagem principal |
| Streamlit | Interface web |
| Groq | Inferência do modelo de IA |
| PokéAPI | Fonte de dados dos Pokémon |
| Requests | Consumo de APIs REST |
| python-dotenv | Gerenciamento de variáveis de ambiente |
| st.session_state | Histórico da conversa |

---

## 📂 Estrutura do Projeto

```text
PokedexAi/
│
├── app.py
├── config.toml
├── requirements.txt
└── README.md
```

### Principais arquivos

### `app.py`

Arquivo principal da aplicação.

Responsável por:

- Interface Streamlit
- Processamento das perguntas
- Comunicação com a PokéAPI
- Integração com Groq
- Gerenciamento do histórico
- Construção do contexto enviado ao LLM

### `requirements.txt`

Contém as dependências necessárias para executar o projeto.

### `config.toml`

Arquivo de configuração utilizado pela aplicação.

### `README.md`

Documentação principal do projeto.

---

# ⚙️ Executando Localmente

## 1. Clone o repositório

```bash
git clone https://github.com/renatwo/PokedexAi.git
```

Entre na pasta do projeto:

```bash
cd PokedexAi
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

### Linux / macOS

```bash
python3 -m venv .venv
source .venv/bin/activate
```

---

## 3. Instale as dependências

```bash
pip install -r requirements.txt
```

---

## 4. Configure a chave da Groq

Crie um arquivo chamado:

```text
.env
```

Na raiz do projeto.

Depois adicione:

```env
GROQ_API_KEY=sua_chave_da_groq_aqui
```

> ⚠️ Nunca envie sua chave de API real para um repositório público.

É recomendado adicionar o arquivo `.env` ao `.gitignore`.

Exemplo:

```gitignore
.env
.venv/
__pycache__/
```

---

## 5. Execute a aplicação

```bash
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

O projeto utiliza práticas básicas de segurança para evitar a exposição de credenciais e reduzir tentativas simples de manipulação das instruções da IA.

## 🔐 Variáveis de ambiente

A chave da Groq é carregada através da variável:

```env
GROQ_API_KEY
```

Isso evita manter a credencial diretamente no código-fonte.

---

## 🚫 Proteção de credenciais

Arquivos contendo credenciais e configurações locais não devem ser enviados ao GitHub.

Exemplo recomendado de `.gitignore`:

```gitignore
.env
.venv/
__pycache__/
*.pyc
```

---

## 🛡️ Prompt Injection

A aplicação possui proteção básica contra tentativas de manipulação das instruções internas enviadas ao modelo.

> As proteções utilizadas possuem finalidade educacional e não substituem mecanismos avançados de segurança utilizados em aplicações de produção.

---

# 🧩 Conceitos Aplicados

Este projeto demonstra conhecimentos relacionados a:

- Python
- APIs REST
- JSON
- Inteligência Artificial Generativa
- Large Language Models
- Engenharia de Prompt
- Integração de APIs
- Manipulação de dados
- Gerenciamento de sessão
- Streamlit
- Variáveis de ambiente
- Segurança de API Keys
- Prompt Injection
- Contextualização de LLM com dados externos

---

# 📸 Screenshots

Como evolução do projeto, poderão ser adicionadas imagens demonstrando a aplicação em funcionamento.

Estrutura sugerida:

```text
PokedexAi/
│
├── docs/
│   ├── pokedex-home.png
│   └── pokedex-chat.png
│
├── app.py
├── config.toml
├── requirements.txt
└── README.md
```

Exemplo de utilização no README:

```markdown
![Pokédex AI](./docs/pokedex-home.png)
```

---

# 🚧 Roadmap

## ✅ Implementado

- [x] Integração com PokéAPI
- [x] Integração com Groq
- [x] Interface Streamlit
- [x] Histórico de conversa
- [x] Consulta de tipos
- [x] Consulta de habilidades
- [x] Consulta de stats
- [x] Linha evolutiva
- [x] Fraquezas e resistências
- [x] Proteção da API Key
- [x] Proteção básica contra Prompt Injection

## 🔜 Próximas melhorias

- [ ] Comparação entre dois Pokémon
- [ ] Sistema de batalha utilizando IA
- [ ] Cache de consultas da PokéAPI
- [ ] Memória persistente
- [ ] Separação do projeto em módulos
- [ ] Testes automatizados
- [ ] Deploy público
- [ ] Suporte a múltiplos modelos de IA
- [ ] Adicionar screenshots da aplicação
- [ ] Criar `.gitignore`
- [ ] Criar `.env.example`

---

# 🔮 Possível Evolução da Arquitetura

Uma evolução futura do projeto poderá separar as responsabilidades em diferentes módulos.

```text
PokedexAi/
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
├── docs/
│   ├── pokedex-home.png
│   └── pokedex-chat.png
│
├── app.py
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

Essa organização facilitaria:

- Manutenção do código
- Testes automatizados
- Escalabilidade
- Reutilização de funções
- Separação de responsabilidades
- Evolução do projeto

---

# 📌 Status do Projeto

🟢 **Projeto funcional e em evolução**

Novas funcionalidades poderão ser adicionadas conforme novos conceitos de desenvolvimento, integração de sistemas e Inteligência Artificial forem estudados.

---

## 💡 Aprendizados

Durante o desenvolvimento deste projeto foram aplicados conceitos de integração entre APIs tradicionais e modelos de Inteligência Artificial.

A **PokéAPI** funciona como fonte estruturada de dados, enquanto o **LLM executado através da Groq** atua como camada de interpretação e geração de linguagem natural.

Essa arquitetura demonstra como:

> **APIs + Python + LLMs podem trabalhar em conjunto para criar aplicações inteligentes baseadas em dados externos.**

Além do desenvolvimento da aplicação, o projeto permite praticar conceitos importantes de engenharia de software, documentação técnica, segurança de credenciais e integração entre serviços externos.

---

## 📄 Licença

Projeto desenvolvido para fins educacionais e de portfólio.

---
