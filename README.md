# Previsão de Custos Médicos e Identificação de Alto Risco — Modelagem Estatística

 **Disciplina:** Modelagem Estatística — 2º Bimestre  
 **Instituição:** CESUPA  
 **Autores:** Filipe César e Everton Gustavo  
 **Data:** Dezembro/2025  

---

## Visão Geral do Projeto

Este projeto aplica técnicas avançadas de Estatística e Machine Learning para:

- **Prever despesas médicas individuais** (`charges`),  
- **Identificar beneficiários com alto risco de sinistralidade**,  
- **Avaliar relações causais entre fatores comportamentais e custos médicos.**

O trabalho foi desenvolvido seguindo um pipeline reprodutível de *data science*, com foco em rigor estatístico, visualização interpretativa (*data storytelling*) e análise crítica dos modelos.

O dataset utilizado é o **Medical Cost Personal Dataset (Kaggle)**, contendo informações reais sobre segurados do sistema de saúde dos EUA. Licença: Domínio Público 

---

## Objetivos

| Área | Objetivo | Métrica Primária |
|------|----------|----------------|
| **Regressão** | Estimar o valor exato dos custos médicos (`charges`) | R², RMSE, MAE |
| **Classificação** | Identificar indivíduos com alto custo (`high_cost = 1`) | Recall, F1, AUC-ROC |
| **Inferência Estatística** | Verificar se fatores como tabagismo e BMI têm impacto significativo | Teste t, ANOVA, p-values |

---

## Tecnologias Utilizadas

| Categoria | Ferramentas |
|----------|-------------|
| Manipulação de Dados | `pandas`, `numpy` |
| Visualização | `matplotlib`, `seaborn` (com princípios Gestalt) |
| Estatística | `scipy`, `statsmodels` (diagnóstico, VIF, resíduos, p-values) |
| Machine Learning | `scikit-learn`, `RandomizedSearchCV`, `GridSearchCV` |
| AutoML (documentado) | `pycaret` (fluxo referenciado; não executado por incompatibilidade Python 3.12) |

---

## Metodologia

O pipeline foi estruturado da seguinte forma:

1. **Coleta e documentação do dataset**
2. **EDA com testes estatísticos:**
   - Shapiro-Wilk (normalidade)
   - T-test (fumantes vs. não fumantes)
   - ANOVA (impacto da região)
   - Correlações
3. **Feature Engineering:**
   - `log(charges)` → reduzir assimetria
   - `high_cost` → classificador baseado no percentil 75
4. **Modelagem Base:**
   - Regressão Linear, Polinomial
   - Gaussian Naive Bayes
   - Regressão Logística
5. **Otimização:**
   - **RandomizedSearchCV** → Gradient Boosting (Regressão)
   - **GridSearchCV** → Logistic Regression (Classificação, foco em Recall)
6. **Avaliação Final:**
   - métricas + matriz de confusão + ROC + comparação tabelada
7. **Discussão de vieses, limitações e uso real**

---

## Resultados

| Tarefa | Modelo Final | Desempenho |
|--------|-------------|------------|
| **Regressão** | Gradient Boosting + RandomSearchCV | **R² ≈ 0.88**, menor RMSE da análise |
| **Classificação** | Logistic Regression + GridSearchCV | **Recall > 0.90**, AUC-ROC elevada |
| **Baseline Comparativo** | DummyClassifier e Linear Regression | Serviram como referência inferior |

---

## Insights Principais (EDA)

| Achado | Implicação de Negócio |
|--------|-----------------------|
| **Tabagismo é o maior driver de custo (p < 0.001)** | Fator obrigatório em precificação, tarifação dinâmica e segmentação |
| **BMI interage com tabagismo de forma não linear** | Justifica o uso de modelos polinomiais e métodos baseados em árvores |
| **Transformação log melhora estabilidade dos resíduos** | Fundamental para inferência estatística via OLS |

---

## Estrutura do Repositório

medical-cost-modeling

│
├── notebook.ipynb

├── README.md

└── requirements.txt, Dependências do ambiente


## Como Executar

```bash
# 1. Clonar o repositório
git clone https://github.com/SEU_USUARIO/NOME_DO_REPO.git

# 2. Entrar na pasta
cd NOME_DO_REPO

# 3. Instalar dependências
pip install -r requirements.txt

# 4. Executar o projeto
jupyter notebook notebook.ipynb

```
