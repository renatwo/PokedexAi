# 🔴 Pokédex AI

Uma **Pokédex interativa desenvolvida em Python**, utilizando **Streamlit + Inteligência Artificial Generativa**, capaz de responder perguntas sobre Pokémon, incluindo tipos, habilidades, fraquezas, resistências, evoluções e curiosidades.

O projeto utiliza um **LLM através da API da Groq**, além de implementar boas práticas de arquitetura, segurança de credenciais e proteção contra prompt injection.

---

## 🚀 Demonstração

Faça perguntas como:

* Quais são as fraquezas do Charizard?
* Como o Eevee evolui?
* Quais habilidades o Pikachu pode ter?
* Qual é o tipo do Bulbasaur?
* Quais são as resistências do Gengar?

A Pokédex utiliza IA para gerar uma resposta estruturada e contextualizada.

---

## 🧠 Tecnologias utilizadas

* 🐍 **Python**
* 🎈 **Streamlit**
* 🤖 **Groq API**
* 🧠 **Llama 3.3 70B**
* 🔐 **Variáveis de ambiente**
* 🛡️ **Prompt Guard / Prompt Sandboxing**
* 🧩 **Arquitetura modular**
* 💬 **Interface de chat com histórico**

---

## 🏗️ Arquitetura

O projeto foi estruturado separando responsabilidades entre diferentes componentes.

```text
Usuário
   │
   ▼
Streamlit UI
   │
   ▼
PromptGuard
   │
   ├── Sanitização do input
   ├── Limitação de caracteres
   ├── Escape de HTML
   └── Proteção contra Prompt Injection
   │
   ▼
GroqService
   │
   ▼
Groq API
   │
   ▼
Llama 3.3 70B
   │
   ▼
Resposta da Pokédex
```

### `GroqService`

Responsável exclusivamente pela comunicação com a API da Groq.

Isso mantém a lógica da API separada da interface da aplicação.

### `PromptGuard`

Responsável por tratar o conteúdo enviado pelo usuário antes de encaminhá-lo ao modelo.

Entre as proteções implementadas estão:

* Sanitização do input;
* Remoção de caracteres de controle;
* Escape de HTML;
* Limitação do tamanho das mensagens;
* Separação entre System Prompt e User Input;
* Proteções contra tentativas de Prompt Injection e Jailbreak.

### Streamlit UI

Responsável pela interface da aplicação, histórico da conversa e interação com o usuário.

---

## 🛡️ Segurança

O projeto foi desenvolvido evitando a exposição de credenciais.

A chave da Groq **não é armazenada diretamente no código**.

A aplicação utiliza:

```env
GROQ_API_KEY=sua_chave_aqui
```

A variável é recuperada através do ambiente:

```python
os.environ.get("GROQ_API_KEY")
```

> ⚠️ Nunca publique sua API Key no GitHub.

---

## 📂 Estrutura sugerida do projeto

```text
pokedex-ai/
│
├── app.py
├── requirements.txt
├── .gitignore
├── .env.example
└── README.md
```

---

## ⚙️ Como executar o projeto

### 1. Clone o repositório

```bash
git clone https://github.com/SEU-USUARIO/pokedex-ai.git
```

Entre na pasta:

```bash
cd pokedex-ai
```

---

### 2. Crie um ambiente virtual

Windows:

```bash
python -m venv .venv
```

Ative:

```bash
.venv\Scripts\activate
```

Linux/macOS:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

---

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

Exemplo de `requirements.txt`:

```txt
streamlit
groq
```

---

### 4. Configure sua API Key

Crie sua variável de ambiente:

#### PowerShell

```powershell
$env:GROQ_API_KEY="sua-chave"
```

#### Linux/macOS

```bash
export GROQ_API_KEY="sua-chave"
```

---

### 5. Execute a aplicação

```bash
streamlit run app.py
```

Depois, acesse o endereço exibido pelo Streamlit no navegador.

Normalmente:

```text
http://localhost:8501
```

---

## 🤖 Modelo utilizado

O projeto está configurado para utilizar:

```text
llama-3.3-70b-versatile
```

através da API da **Groq**.

Parâmetros principais:

```python
temperature = 0.6
max_tokens = 700
```

---

## 🔐 Proteção contra Prompt Injection

Uma das características do projeto é a implementação de uma camada chamada:

```python
PromptGuard
```

O conteúdo enviado pelo usuário é tratado como **entrada não confiável** e separado das instruções principais do sistema.

Exemplo conceitual:

```xml
<SYSTEM_INSTRUCTIONS>
Instruções confiáveis da aplicação
</SYSTEM_INSTRUCTIONS>

<USER_INPUT>
Conteúdo enviado pelo usuário
</USER_INPUT>
```

Essa abordagem ajuda a reduzir tentativas de manipulação das instruções do agente.

---

## 💬 Gerenciamento de conversa

O histórico da conversa é armazenado utilizando:

```python
st.session_state
```

Isso permite que as mensagens permaneçam disponíveis durante os reruns do Streamlit.

Também existe uma opção na sidebar para:

```text
🗑️ Limpar conversa
```

---

## 🎨 Interface

A aplicação possui uma interface personalizada inspirada visualmente em uma Pokédex, utilizando:

* CSS customizado;
* Tema vermelho e amarelo;
* Chat interativo;
* Sidebar com exemplos de perguntas;
* Histórico de mensagens;
* Indicador de carregamento enquanto a IA responde.

---

## 🎯 Objetivos do projeto

Este projeto foi criado com objetivo de praticar conceitos relacionados a:

* Desenvolvimento com Python;
* Inteligência Artificial Generativa;
* Consumo de APIs;
* Integração com LLMs;
* Engenharia de Prompt;
* Segurança de aplicações com IA;
* Prompt Injection;
* Streamlit;
* Organização e arquitetura de código;
* Gerenciamento seguro de credenciais.

---

## 🔮 Próximas melhorias

Algumas funcionalidades que podem ser adicionadas futuramente:

* [ ] Integração com PokéAPI
* [ ] Exibição de imagens dos Pokémon
* [ ] Número oficial da Pokédex
* [ ] Estatísticas de batalha
* [ ] Altura e peso
* [ ] Busca por geração
* [ ] Comparação entre Pokémon
* [ ] Sistema RAG com dados oficiais
* [ ] Cache das consultas
* [ ] Deploy público
* [ ] Testes automatizados

---

## 👨‍💻 Autor

**Renato Queiroz**

Estudante de Inteligência Artificial Aplicada e desenvolvedor focado em:

* Inteligência Artificial Generativa
* Python
* Automação
* Agentes de IA
* APIs REST
* Integração de Sistemas

### GitHub

[github.com/renatwo](https://github.com/renatwo)

---

## ⭐ Sobre o projeto

Este projeto faz parte do meu portfólio de estudos e desenvolvimento em **Inteligência Artificial, Python e aplicações baseadas em LLMs**.

Se o projeto foi útil ou interessante, considere deixar uma ⭐ no repositório.
