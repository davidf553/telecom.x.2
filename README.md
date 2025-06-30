# Telecom X - Parte 2 📊🔍

Este projeto tem como objetivo **prever o churn de clientes** de uma operadora de telecomunicações com base em variáveis relevantes, utilizando técnicas de ciência de dados e aprendizado de máquina.

## 🎯 Objetivo da Análise

A análise foi realizada com o intuito de:

- Entender o comportamento dos clientes que cancelam o serviço.
- Identificar variáveis relevantes para prever o churn.
- Construir um modelo preditivo eficaz para antecipar o risco de cancelamento.

---

## 🗂️ Estrutura do Projeto

TelecomX_2.ipynb # Notebook principal com toda a análise
data/
├── TelecomX_Data.json # Fonte de dados (carregada via URL)
├── dados_tratados.csv # (Opcional) Versão limpa dos dados
visualizacoes/
├── churn_por_servico.png
├── matriz_confusao.png
├── feature_importance.png

markdown
Copiar
Editar

---

## 🧹 Preparação dos Dados

### 📊 Tipos de Variáveis

- **Categóricas**: `gender`, `internet_type`, `contract`, `payment_method`, etc.
- **Numéricas**: `tenure`, `monthly_charges`, `total_charges`, etc.

### 🔁 Processamento

1. **Conversão do alvo**:
   - A variável `Churn` foi convertida de `"Yes"/"No"` para `1/0`.

2. **Desaninhamento de dicionários**:
   - As colunas `customer`, `phone`, `internet`, e `account` foram desmembradas em múltiplas colunas.

3. **Codificação**:
   - Utilizou-se `pd.get_dummies()` para variáveis categóricas antes da modelagem.

4. **Normalização**:
   - Não foi necessário normalizar devido ao uso de Random Forest (não sensível à escala).

5. **Split treino/teste**:
   - Separação dos dados em 70% treino e 30% teste usando `train_test_split`.

---

## 📈 Análise Exploratória (EDA)

Durante a EDA, foram gerados gráficos e insights como:

- Distribuição de churn por tipo de contrato.
- Correlação entre tempo de permanência (`tenure`) e churn.
- Importância de variáveis (via Random Forest).
- Matriz de confusão para avaliar o desempenho do modelo.

---

## 🤖 Modelagem

- Algoritmo utilizado: `RandomForestClassifier`
- Métricas de avaliação:
  - AUC (Área sob a curva ROC)
  - Matriz de confusão
  - `classification_report` com precisão, recall e f1-score.

Justificativas:
- A Random Forest foi escolhida por lidar bem com dados mistos (numéricos e categóricos) e por fornecer boas métricas de importância de variáveis.

---

## ▶️ Como Executar

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/TelecomX.git
cd TelecomX
2. Instale as dependências
bash
Copiar
Editar
pip install -r requirements.txt
Ou instale manualmente:

bash
Copiar
Editar
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
3. Execute o notebook
bash
Copiar
Editar
jupyter notebook TelecomX_2.ipynb
Os dados são carregados automaticamente via URL no notebook.

🧾 Créditos
Desenvolvido como parte do desafio de Data Science da Alura: Telecom X - Parte 2.
