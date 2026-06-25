# Tarefa 04 — Transformers e Atenção no Atendimento ao Cliente

Atividade prática da disciplina **Arquiteturas de Deep Learning** — PUC Minas.

## Objetivo

Explorar o mecanismo de **Atenção** e a arquitetura **Transformer**, entendendo por que elas substituíram as RNNs. Em seguida, aplicar um **LLM instrucional (Qwen)** para automatizar o atendimento ao cliente — classificação, extração de informações e geração de respostas — e realizar **fine-tuning com LoRA** para adaptar o modelo a um padrão específico de resposta.

## Conteúdo

```
Tarefa_04/
├── transformers_e_atencao_em_atendimento_ao_cliente.ipynb  # Notebook principal
└── README.md
```

> O notebook baixa os modelos automaticamente via HuggingFace na primeira execução (~2 GB no total). Não há dataset externo para baixar.

## O que é abordado no notebook

### Parte 1 — Por que Transformers?
- Limitações das RNNs: sequencialidade e esquecimento de longo prazo
- Vantagens dos Transformers: processamento paralelo e atenção direta

### Parte 2 — Mecanismo de Atenção
- Visualização de pesos de atenção
- Self-attention: como cada palavra olha para as demais
- Query, Key e Value (Q, K, V) — analogia com busca em biblioteca
- Fórmula `Attention(Q, K, V) = softmax(QKᵀ / √dₖ) · V`

### Parte 3 — Análise de Sentimento com Transformer Pré-Treinado
- Modelo: `cardiffnlp/twitter-xlm-roberta-base-sentiment`
- Classificação de avaliações de clientes em positivo / neutro / negativo

### Parte 4 — LLM Instrucional com Qwen
- Modelo: `Qwen/Qwen2.5-0.5B-Instruct` (494M parâmetros)
- Classificação de reclamações por categoria
- Extração de informações estruturadas
- Geração de respostas empáticas ao cliente

### Parte 5 — Fine-Tuning com LoRA
- O que é LoRA (Low-Rank Adaptation) e por que é eficiente
- Criação de dataset de fine-tuning com padrão de resposta definido
- Treinamento: apenas **0,11% dos parâmetros** são atualizados
- Comparação: resposta antes × depois do fine-tuning

## Modelos utilizados

| Modelo | Tarefa | Parâmetros |
|:-------|:-------|:-----------|
| `twitter-xlm-roberta-base-sentiment` | Análise de sentimento | ~125M |
| `Qwen2.5-0.5B-Instruct` | Geração de texto + LoRA | ~494M |

## Como executar

```bash
pip install torch transformers datasets accelerate sentencepiece peft jupyter
jupyter notebook transformers_e_atencao_em_atendimento_ao_cliente.ipynb
```

> Na primeira execução, os modelos serão baixados automaticamente (~2 GB).  
> A etapa de fine-tuning pode levar **15–30 minutos em CPU**.
