# Tarefa 03 — Previsão de Demanda em Mobilidade Urbana com RNNs

Atividade prática da disciplina **Arquiteturas de Deep Learning** — PUC Minas.

## Objetivo

Comparar três arquiteturas de **Redes Neurais Recorrentes** — SimpleRNN, LSTM e GRU — para prever a demanda de bicicletas compartilhadas em Washington D.C., demonstrando as vantagens das arquiteturas com memória de longo prazo sobre a RNN simples.

## Dataset

**Capital Bikeshare — Bike Sharing Dataset** (UCI Machine Learning Repository)

| Arquivo | Descrição | Linhas |
|:--------|:----------|:-------|
| `dataset/day.csv` | Registros diários de aluguel | 731 dias |
| `dataset/hour.csv` | Registros horários de aluguel | 17.379 horas |

Variáveis incluem: data, estação do ano, temperatura, umidade, velocidade do vento, feriados e contagem de aluguéis (casual, registrado e total).

## Conteúdo

```
Tarefa_03/
├── previsão_de_demanda_em_mobilidade_urbana_com_RNNs.ipynb  # Notebook principal
├── dataset/
│   ├── day.csv       # Granularidade diária
│   ├── hour.csv      # Granularidade horária
│   └── Readme.txt    # Descrição original do dataset
└── README.md
```

## O que é abordado no notebook

- Análise exploratória da série temporal de demanda
- Preparação de sequências temporais para modelos recorrentes
- Implementação e treinamento de **SimpleRNN**, **LSTM** e **GRU**
- Comparação de métricas: MAE, RMSE, R²
- Visualizações: curvas de treinamento, previsão vs. real, comparação entre modelos

## Modelos comparados

| Modelo | Característica |
|:-------|:--------------|
| SimpleRNN | Recorrência básica, sofre com dependências longas |
| LSTM | Células de memória com gates — ideal para séries longas |
| GRU | Versão simplificada do LSTM, mais rápida de treinar |

## Como executar

```bash
pip install torch numpy pandas matplotlib seaborn scikit-learn jupyter
jupyter notebook "previsão_de_demanda_em_mobilidade_urbana_com_RNNs.ipynb"
```

## Referência do dataset

Fanaee-T, H., & Gama, J. (2014). *Event labeling combining ensemble detectors and background knowledge.*  
Progress in Artificial Intelligence. Springer Berlin Heidelberg.  
Disponível em: [UCI ML Repository](https://archive.ics.uci.edu/ml/datasets/Bike+Sharing+Dataset).
