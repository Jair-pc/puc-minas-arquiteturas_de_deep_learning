# Tarefa 03 — Previsão de Demanda em Mobilidade Urbana com RNNs

Atividade prática da disciplina **Arquiteturas de Deep Learning** — PUC Minas.

![Previsão de Demanda em Mobilidade Urbana](Previsão%20de%20Demanda%20em%20Mobilidade%20Urbana_.png)

---

## Contexto de Negócio

Uma empresa de mobilidade urbana oferece bicicletas compartilhadas em uma grande cidade. A operação precisa prever a demanda de aluguel de bicicletas nas próximas horas para apoiar decisões como:

- reposicionar bicicletas entre estações
- planejar equipes de manutenção e redistribuição
- antecipar horários de pico
- melhorar a disponibilidade do serviço
- reduzir estações vazias ou lotadas
- apoiar decisões operacionais baseadas em dados climáticos e temporais

Neste desafio, o objetivo é construir modelos recorrentes para prever a quantidade de bicicletas alugadas com base no comportamento histórico da demanda e em variáveis contextuais.

---

## Dataset

**Bike Sharing Dataset** — UCI Machine Learning Repository / Kaggle:  
https://www.kaggle.com/datasets/lakshmi25npathi/bike-sharing-dataset/code

O dataset contém registros horários de aluguel de bicicletas, incluindo:

- data e hora
- estação do ano, mês, hora do dia
- feriado, dia da semana, dia útil
- condições climáticas
- temperatura, sensação térmica, umidade, velocidade do vento
- quantidade total de bicicletas alugadas

| Arquivo | Descrição | Linhas |
|:--------|:----------|:-------|
| `dataset/day.csv` | Registros diários | 731 dias |
| `dataset/hour.csv` | Registros horários | 17.379 horas |

---

## Objetivo Técnico

Construir e comparar três modelos recorrentes para prever a **demanda total de bicicletas na próxima hora**:

| Modelo | Característica |
|:-------|:--------------|
| **SimpleRNN** | Recorrência básica, sofre com dependências longas |
| **LSTM** | Células de memória com gates — ideal para séries longas |
| **GRU** | Versão simplificada do LSTM, mais rápida de treinar |

---

## Entregáveis

- Visualização inicial da série temporal
- Explicação do pré-processamento realizado
- Construção das janelas temporais
- Treinamento dos três modelos
- Comparação das métricas (MAE, RMSE, R²)
- Gráfico Real × Previsto
- Discussão sobre limitações das arquiteturas

---

## Conteúdo

```
Tarefa_03/
├── previsão_de_demanda_em_mobilidade_urbana_com_RNNs.ipynb  # Notebook principal
├── dataset/
│   ├── day.csv          # Granularidade diária
│   ├── hour.csv         # Granularidade horária
│   └── Readme.txt       # Descrição original do dataset
├── Previsão de Demanda em Mobilidade Urbana_.png            # Imagem de capa
├── comparacao_metricas.png
├── real_vs_previsto_todos.png
├── serie_temporal.png
└── README.md
```

---

## Como executar

```bash
pip install torch numpy pandas matplotlib seaborn scikit-learn jupyter
jupyter notebook "previsão_de_demanda_em_mobilidade_urbana_com_RNNs.ipynb"
```

---

## Referência do dataset

Fanaee-T, H., & Gama, J. (2014). *Event labeling combining ensemble detectors and background knowledge.*  
Progress in Artificial Intelligence. Springer Berlin Heidelberg.  
[UCI ML Repository](https://archive.ics.uci.edu/ml/datasets/Bike+Sharing+Dataset)
