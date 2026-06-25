# Arquiteturas de Deep Learning

Repositório com as atividades práticas da disciplina **Arquiteturas de Deep Learning** da Pós-Graduação em IA Generativa e Aplicações com LLMs da **PUC Minas**.

| Campo | Detalhe |
|:------|:--------|
| **Instituição** | Pontifícia Universidade Católica de Minas Gerais |
| **Programa** | Pós-Graduação em IA Generativa e Aplicações com LLMs |
| **Professor** | Antônio dos Santos Ramos Neto |
| **Aluno** | Jair Pereira da Silva Junior |

---

## Tarefas

| Tarefa | Tema | Técnica | Dataset |
|:-------|:-----|:--------|:--------|
| [Tarefa 01](./Tarefa_01/) | Previsão de Churn de Clientes | MLP (Perceptron Multicamadas) | Telco Customer Churn |
| [Tarefa 02](./Tarefa_02/) | Classificação de Imagens Territoriais | CNN (Rede Neural Convolucional) | Intel Image Classification |
| [Tarefa 03](./Tarefa_03/) | Previsão de Demanda em Mobilidade Urbana | RNN / LSTM / GRU | Capital Bikeshare (Washington D.C.) |
| [Tarefa 04](./Tarefa_04/) | Transformers e Atenção no Atendimento ao Cliente | Transformers + LoRA Fine-Tuning | Gerado em aula (HuggingFace) |

---

## Estrutura do Repositório

```
.
├── Tarefa_01/
│   ├── churn_mlp.ipynb             # Notebook principal
│   ├── Telco-Customer-Churn.csv    # Dataset
│   └── README.md
├── Tarefa_02/
│   ├── classificacao_imagens_territoriais_cnn.ipynb   # Notebook principal
│   └── README.md                   # Instruções para baixar o dataset de imagens
├── Tarefa_03/
│   ├── previsão_de_demanda_em_mobilidade_urbana_com_RNNs.ipynb  # Notebook principal
│   ├── dataset/
│   │   ├── day.csv                 # Dataset diário
│   │   └── hour.csv                # Dataset horário
│   └── README.md
└── Tarefa_04/
    ├── transformers_e_atencao_em_atendimento_ao_cliente.ipynb   # Notebook principal
    └── README.md
```

---

## Como executar

Cada tarefa tem seu próprio `README.md` com instruções detalhadas. De forma geral:

```bash
# 1. Clone o repositório
git clone https://github.com/Jair-pc/puc-minas-arquiteturas_de_deep_learning.git
cd puc-minas-arquiteturas_de_deep_learning

# 2. Crie um ambiente virtual (recomendado Python 3.10 ou 3.11)
python -m venv venv
venv\Scripts\activate   # Windows
# source venv/bin/activate  # Linux/Mac

# 3. Instale as dependências da tarefa desejada e execute o notebook
cd Tarefa_01
jupyter notebook
```

---

## Tecnologias utilizadas

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-2.x-orange)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00)
![HuggingFace](https://img.shields.io/badge/HuggingFace-Transformers-yellow)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626)
