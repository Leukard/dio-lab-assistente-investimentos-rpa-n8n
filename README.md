# 🚀 Assistente de Investimentos Automatizado com RPA e IA Generativa

Projeto desenvolvido para o Desafio de Projeto da **DIO (Digital Innovation One)**: *Criando um Assistente de Investimentos com RPA e IA Generativa*.

## 📌 Arquitetura da Solução

```text
[Página HTML (GitHub Pages)] ──(RPA em Python)──> [Webhook N8N]
                                                      │
[Base de Ativos: docs/data.csv] ──────────────────────┼──> [Cruzamento de Dados]
                                                      │
                                                      └──> [Agente de IA Generativa]
                                                                  │
                                                                  └──> [Mensagem Personalizada]
```

## 🛠️ Tecnologias e Ferramentas Utilizadas

* **Python + BeautifulSoup:** Utilizado para criar o robô de extração (RPA) via Web Scraping da página de clientes.
* **N8N Workflow:** Orquestração completa do fluxo de dados (Webhook, Parse, Match de perfis e requisição de IA).
* **IA Generativa (OpenAI / Gemini Agent):** Geração dinâmica e humanizada de recomendações financeiras personalizadas.
* **GitHub Pages & CSV:** Hospedagem da aplicação web simulada e banco de dados de produtos financeiros.

## ⚙️ Decisões Técnicas

1. **RPA de Extração:** O script simula a navegação humana e faz a leitura estruturada da tabela de clientes em HTML sem depender de APIs expostas.
2. **Orquestração Modular no N8N:** O fluxo recebe o array de clientes, realiza o parsing e cruza as informações com o arquivo de recomendações `data.csv`.
3. **Hiperpersonalização via IA:** O agente recebe as variáveis do cliente (Nome, Saldo e Perfil) e compõe uma recomendação sob medida garantindo alinhamento de perfil de risco.

## 📁 Estrutura de Arquivos

```text
.
├── README.md
├── docs/
│   ├── index.html
│   └── data.csv
├── n8n/
│   └── workflow.json
└── src/
    └── extrair_clientes.py
```

## 🚀 Como Executar o Projeto

1. Importe o arquivo `n8n/workflow.json` para a sua instância do **N8N**.
2. Ative o nó de **Webhook** no N8N para gerar a URL de recepção dos dados.
3. Insira a URL no arquivo `src/extrair_clientes.py` e execute o script em Python.
4. O N8N receberá o payload, lerá o arquivo `docs/data.csv` e gerará os relatórios de investimentos com a IA Generativa.
