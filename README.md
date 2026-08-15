# 🔴 Pokédex AI V2

Aplicação em **Python + Streamlit** que combina a **PokéAPI** com um LLM via **Groq**.

## O que esta versão faz

- Busca automaticamente o Pokémon citado na pergunta.
- Exibe a imagem oficial disponível na PokéAPI.
- Obtém tipos, habilidades, stats, altura, peso e linha evolutiva.
- Calcula relações de fraqueza, resistência e imunidade a partir dos tipos.
- Envia os dados estruturados para a Groq gerar uma resposta conversacional.
- Mantém histórico do chat com `st.session_state`.
- Possui proteção básica contra prompt injection.
- Mantém a `GROQ_API_KEY` fora do código.
- Usa texto preto sobre o fundo amarelo para melhorar a leitura.

## Estrutura

```text
pokedex_ai_v2/
├── .streamlit/
│   └── config.toml
├── .env.example
├── .gitignore
├── app.py
├── requirements.txt
└── README.md
```

## 1. Abra a pasta no VS Code

Extraia o ZIP e abra a pasta `pokedex_ai_v2` no VS Code.

## 2. Crie um ambiente virtual

### Windows PowerShell

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

## 3. Instale as dependências

```powershell
pip install -r requirements.txt
```

## 4. Configure a chave da Groq

Faça uma cópia de `.env.example` e renomeie para:

```text
.env
```

Depois abra o `.env` e substitua:

```env
GROQ_API_KEY=sua_chave_da_groq_aqui
```

pela sua chave real.

> O `.env` está no `.gitignore`, então não deve ser enviado ao GitHub.

## 5. Execute

```powershell
streamlit run app.py
```

O Streamlit normalmente abrirá:

```text
http://localhost:8501
```

## Exemplos de perguntas

- Me fale sobre Pikachu
- Quais são as fraquezas do Charizard?
- Como o Eevee evolui?
- Quais habilidades o Bulbasaur possui?

## Tecnologias

- Python
- Streamlit
- Groq
- PokéAPI
- Requests
- python-dotenv

## Segurança

A chave da Groq é carregada de variável de ambiente / `.env` e não fica hardcoded no código.

Nunca faça commit do arquivo `.env`.
