# Tarefa 01 — Previsão de Churn de Clientes com MLP

Atividade prática da disciplina **Arquiteturas de Deep Learning** — PUC Minas.

## Objetivo

Construir um modelo de **Perceptron Multicamadas (MLP)** para prever quais clientes de uma empresa de telecomunicações têm maior probabilidade de cancelar o serviço (**churn**), usando a rede neural como classificador binário.

## Dataset

**Telco Customer Churn** — fornecido pela IBM como dataset de exemplo.

| Campo | Detalhe |
|:------|:--------|
| Arquivo | `Telco-Customer-Churn.csv` |
| Linhas | 7.043 clientes |
| Features | 20 atributos (contrato, serviços, cobrança, etc.) |
| Target | `Churn` (Sim / Não) |

## Conteúdo

```
Tarefa_01/
├── churn_mlp.ipynb          # Notebook principal
├── Telco-Customer-Churn.csv # Dataset
└── README.md
```

## O que é abordado no notebook

- Análise exploratória dos dados (EDA)
- Pré-processamento: encoding, normalização, tratamento de valores ausentes
- Construção de uma MLP com PyTorch / Keras
- Treinamento e avaliação (acurácia, F1-score, matriz de confusão)
- Interpretação dos resultados

## Como executar

```bash
pip install torch numpy pandas matplotlib seaborn scikit-learn jupyter
jupyter notebook churn_mlp.ipynb
```

## Referência do dataset

IBM Telco Customer Churn — disponível no [Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn).
