# Assistente financeiro pessoal

Chatbot financeiro pessoal construído com a **API da OpenAI**, com memória de contexto persistente ao longo da conversa.

## Funcionalidades

- **Memória de conversa**: mantém contexto completo de todos os gastos registrados na sessão
- **Categorização automática**: classifica gastos por categoria (alimentação, transporte, lazer, etc.)
- **Análise financeira**: calcula totais, identifica padrões e sugere dicas personalizadas
- **Resumo sob demanda**: gera relatório completo da sessão com categorias e recomendações
- **Persistência**: salva e carrega histórico de conversas em JSON

## Conceitos de IA aplicados

| Conceito | Implementação |
|---|---|
| Gerenciamento de contexto | Histórico completo enviado a cada chamada |
| System Prompt | Persona e regras de comportamento do assistente |
| Stateless API | Reconstrução do estado via histórico de mensagens |
| Temperature tuning | 0.7 para respostas naturais mas consistentes |

## Como usar

### 1. Clone e instale dependências
```bash
git clone https://github.com/laurabluna/assistente_financeiro.git
cd assistente
pip install -r requirements.txt
```

### 2. Configure sua chave da OpenAI
```bash
export OPENAI_API_KEY='sua-chave-aqui'
```

### 3. Execute via terminal
```bash
python main.py
```

## Exemplo de uso

```
Você: Gastei R$45 no almoço e R$12 no café hoje.
    Bot: Registrado! Alimentação: R$57,00 hoje

Você: Paguei R$80 de Uber essa semana.
    Bot: Transporte: R$80,00. Total acumulado: R$137,00

Você: /resumo
    Bot: Resumo da sessão:
    Alimentação: R$57,00 (41,6%)
    Transporte: R$80,00 (58,4%)
    Total: R$137,00
    Dica: Considere caronas ou transporte público
```

## 🗂️ Estrutura do projeto

```
assistente-financeiro/
├── src/
│   └── chatbot.py         
├── notebooks/
│   └──   
├── main.py                 
├── requirements.txt
└── README.md
```

## 🛠️ Stack

- **Python 3.11+**
- **OpenAI SDK** (`openai>=1.30.0`) — chamadas diretas à API
- **Notebook** — registros
- **Modelo**: `gpt-4o-mini` 