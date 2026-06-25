# Tarefa 04 — Central Inteligente de Atendimento com LLMs e LoRA

Atividade prática da disciplina **Arquiteturas de Deep Learning** — PUC Minas.

![Central Inteligente de Atendimento](Central%20Inteligente%20de%20Atendimento%20com%20LLMs%20e%20LoRA.png)

---

## Contexto de Negócio

Uma empresa recebe diariamente centenas de reclamações de clientes por formulário online, e-mail, chat, redes sociais e central de atendimento.

O time de atendimento deseja usar IA para apoiar a triagem inicial dessas reclamações. A solução deve ajudar a:

- classificar o tipo da reclamação
- identificar produto ou serviço citado
- estimar urgência
- extrair o principal problema
- gerar uma resposta inicial ao cliente
- adaptar o comportamento do modelo com LoRA

---

## Dataset

Base pública de reclamações de consumidores disponível no Hugging Face, derivada de reclamações do **Consumer Financial Protection Bureau (CFPB)**:  
https://huggingface.co/datasets/claritystorm/cfpb-consumer-complaints

**Modelo recomendado:** `Qwen/Qwen2.5-0.5B-Instruct`

---

## Objetivo Técnico

Construir uma solução com LLM capaz de:

1. Ler uma reclamação textual real
2. Classificar a categoria principal
3. Extrair informações relevantes
4. Gerar uma resposta inicial ao cliente
5. Criar um dataset instrucional com as reclamações
6. Fazer fine-tuning generativo com LoRA
7. Comparar respostas antes e depois do LoRA

---

## O que é abordado no notebook

### Parte 1 — Por que Transformers?
- Limitações das RNNs: sequencialidade e esquecimento de longo prazo
- Vantagens dos Transformers: processamento paralelo e atenção direta

### Parte 2 — Mecanismo de Atenção
- Visualização de pesos de atenção e self-attention
- Query, Key e Value (Q, K, V)
- Fórmula: `Attention(Q, K, V) = softmax(QKᵀ / √dₖ) · V`

### Parte 3 — Análise de Sentimento com Transformer Pré-Treinado
- Modelo: `cardiffnlp/twitter-xlm-roberta-base-sentiment`
- Classificação de avaliações em positivo / neutro / negativo

### Parte 4 — LLM Instrucional com Qwen
- Modelo: `Qwen/Qwen2.5-0.5B-Instruct` (494M parâmetros)
- Classificação, extração de informações e geração de respostas ao cliente

### Parte 5 — Fine-Tuning com LoRA
- Criação de dataset instrucional com padrão de resposta definido
- Treinamento com apenas **0,11% dos parâmetros** atualizados
- Comparação: resposta antes × depois do fine-tuning

---

## Modelos utilizados

| Modelo | Tarefa | Parâmetros |
|:-------|:-------|:-----------|
| `twitter-xlm-roberta-base-sentiment` | Análise de sentimento | ~125M |
| `Qwen2.5-0.5B-Instruct` | Geração de texto + LoRA fine-tuning | ~494M |

---

## Conteúdo

```
Tarefa_04/
├── transformers_e_atencao_em_atendimento_ao_cliente.ipynb        # Notebook principal
├── Central Inteligente de Atendimento com LLMs e LoRA.png        # Imagem de capa
└── README.md
```

---

## Como executar

```bash
pip install torch transformers datasets accelerate sentencepiece peft jupyter
jupyter notebook transformers_e_atencao_em_atendimento_ao_cliente.ipynb
```

> Na primeira execução, os modelos são baixados automaticamente via HuggingFace (~2 GB).  
> O fine-tuning com LoRA pode levar **15–30 minutos em CPU**.
