# 🏥 Previsão de Custos Médicos & Análise de Risco

> **Projeto:** Modelagem Estatística | **Instituição:** CESUPA  
> **Status:** Concluído ✅

## 📋 Sobre o Projeto
Este projeto aplica técnicas avançadas de Ciência de Dados e Estatística para analisar custos médicos individuais e prever riscos de sinistralidade para seguradoras de saúde. 

O desenvolvimento seguiu um pipeline rigoroso de **Data Storytelling**, cobrindo desde a Análise Exploratória de Dados (EDA) com testes de hipóteses até a implementação e otimização de modelos de Machine Learning.

### 🎯 Objetivos de Negócio
1.  **Regressão (Previsão de Valor):** Estimar o custo médico exato (`charges`) com base em variáveis demográficas (idade, região) e comportamentais (BMI, tabagismo).
2.  **Classificação (Gestão de Risco):** Identificar segurados de **Alto Risco** (custo acima da mediana) para precificação ajustada e programas de prevenção.
3.  **Inferência Estatística:** Validar estatisticamente (via Teste T e ANOVA) quais fatores têm causalidade real no aumento de custos.

---

## 🛠️ Ferramentas e Metodologia
O projeto foi desenvolvido em **Python 3.12**, priorizando a reprodutibilidade e a interpretabilidade dos modelos.

* **Manipulação de Dados:** Pandas, Numpy.
* **Visualização (Gestalt):** Seaborn, Matplotlib.
* **Estatística Inferencial:** Statsmodels (Diagnóstico de resíduos, VIF, P-values).
* **Machine Learning:** Scikit-Learn.
    * *Modelos:* Regressão Linear, Polinomial, Logística, Naive Bayes e Gradient Boosting.
    * *Otimização:* RandomizedSearchCV (Tuning de Hiperparâmetros).

> **Nota Técnica:** Optou-se pelo uso de `RandomizedSearchCV` do Scikit-Learn para a otimização (no lugar do PyCaret) para garantir controle granular dos hiperparâmetros e total compatibilidade com o ambiente Python 3.12.

---

## 🚀 Como Executar o Projeto

### Pré-requisitos
Certifique-se de ter o Python instalado. Recomenda-se o uso de um ambiente virtual (venv).

```bash
# 1. Clone este repositório
git clone [https://github.com/SEU_USUARIO/NOME_DO_REPO.git](https://github.com/SEU_USUARIO/NOME_DO_REPO.git)

# 2. Acesse a pasta do projeto
cd NOME_DO_REPO

# 3. Instale as dependências
pip install -r requirements.txt

# 4. Execute o Jupyter Notebook
jupyter notebook
````

-----

## 📈 Resultados Chave

A aplicação de modelos não-lineares e otimização de hiperparâmetros gerou ganhos expressivos na precisão:

| Modelo | Tarefa | Métrica Principal | Performance |
| :--- | :--- | :--- | :--- |
| **Gradient Boosting (Tuned)** | Regressão | R² (Explicação da Variância) | **\~0.88** 🏆 |
| **Regressão Polinomial** | Regressão | R² | \~0.86 |
| **Regressão Linear (Baseline)** | Regressão | R² | \~0.75 |
| **Regressão Logística** | Classificação | Recall (Sensibilidade) | **\> 0.90** |

### 🔍 Principais Insights (EDA)

1.  **O Fator Crítico:** Tabagismo é o maior determinante de custo ($p < 0.05$).
2.  **Interação Perigosa:** A relação entre BMI (Índice de Massa Corporal) e Custo não é linear. Para fumantes, o aumento do BMI faz o custo crescer exponencialmente, o que justifica a superioridade dos modelos Polinomiais e de Boosting.

-----

## 📁 Estrutura do Repositório

```text
├── notebook.ipynb   # Código fonte completo, narrativa e gráficos
├── requirements.txt               # Lista de bibliotecas necessárias
├── README.md                      # Documentação do projeto
└── (Outros arquivos de config do git)
```

## ⚖️ Créditos e Licença

  * **Dataset:** [Medical Cost Personal Datasets (Kaggle)](https://www.kaggle.com/mirichoi0218/insurance)
  * **Fonte dos Dados:** Dados públicos baseados no censo dos EUA (Domínio Público / ODbL).
  * **Alunos:** Filipe César e Everton Gustavo


*Projeto desenvolvido para a disciplina de Modelagem Estatística (2º Bimestre) - CESUPA.*


