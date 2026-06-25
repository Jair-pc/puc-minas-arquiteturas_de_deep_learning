# Tarefa 02 — Classificação de Imagens Territoriais com CNN

Atividade prática da disciplina **Arquiteturas de Deep Learning** — PUC Minas.

## Objetivo

Treinar **Redes Neurais Convolucionais (CNN)** para classificar imagens de cenas naturais e urbanas em seis categorias, comparando uma CNN simples com uma CNN regularizada (Batch Normalization + Dropout).

## Dataset

**Intel Image Classification** — disponível no Kaggle.

| Campo | Detalhe |
|:------|:--------|
| Classes | `buildings`, `forest`, `glacier`, `mountain`, `sea`, `street` |
| Imagens de treino | 14.034 |
| Imagens de teste | 3.000 |
| Imagens para predição | 7.301 (sem rótulo) |
| Fonte | [Kaggle — Intel Image Classification](https://www.kaggle.com/datasets/puneet6060/intel-image-classification) |

> **O dataset de imagens não está incluído neste repositório por ser muito grande (~370 MB).**  
> Faça o download no link acima e extraia as pastas na estrutura abaixo antes de rodar o notebook.

### Estrutura esperada do dataset

```
Tarefa_02/
├── seg_train/
│   └── seg_train/
│       ├── buildings/
│       ├── forest/
│       ├── glacier/
│       ├── mountain/
│       ├── sea/
│       └── street/
├── seg_test/
│   └── seg_test/
│       └── (mesmas 6 classes)
├── seg_pred/
│   └── seg_pred/
│       └── (imagens sem rótulo)
├── classificacao_imagens_territoriais_cnn.ipynb
└── README.md
```

## Conteúdo

```
Tarefa_02/
├── classificacao_imagens_territoriais_cnn.ipynb  # Notebook principal
└── README.md
```

## O que é abordado no notebook

- Carregamento e visualização das imagens com TensorFlow/Keras
- Data augmentation para ampliar o dataset de treino
- Construção de uma **CNN simples** (baseline)
- Construção de uma **CNN regularizada** (Batch Normalization + Dropout)
- Comparação de desempenho entre os dois modelos
- Matriz de confusão e relatório de classificação por classe
- Predição em imagens novas (sem rótulo)

## Como executar

```bash
pip install tensorflow numpy pandas matplotlib seaborn scikit-learn jupyter
jupyter notebook classificacao_imagens_territoriais_cnn.ipynb
```

> Recomendado: **Python 3.10 ou 3.11** para melhor compatibilidade com TensorFlow no Windows.
