<h1> :bar_chart: Análise de Evasão de Clientes (Churn) </h1>

<h2>:round_pushpin: Introdução ao Projeto</h2>

Este projeto faz parte de um desafio de Machine Learning voltado para um problema de negócio: a evasão de clientes (Churn).
O objetivo foi desenvolver modelos capazes de prever quais clientes têm maior chance de cancelar seus serviços e, a partir disso, propor estratégias de retenção.

<h2>:books: Linguagem e Bibliotecas Utilizadas</h2>

* Python

* Pandas

* Numpy

* Matplotlib

* Seaborn

* Scikit-learn

* Statsmodels

<h2>:notebook_with_decorative_cover: Como Utilizar o Projeto</h2>

<h2>1. Clone o repositório ou baixe os arquivos .ipynb</h2>

```bash
git clone https://github.com/Gu1lhermeOliveira/Challenge_TelecomX_parte2.git
````

2. Execute o notebook no Jupyter ou Google Colab
```bash
jupyter notebook Analise_Parte2.ipynb
````
<h2>:dart: Objetivos da Análise</h2>

* Preparar os dados para a modelagem (tratamento, encoding, normalização).

* Realizar análise de correlação e seleção de variáveis.

* Treinar dois ou mais modelos de classificação (ex.: Logistic Regression, Random Forest).

* Avaliar o desempenho dos modelos com métricas (Accuracy, Recall, Precision, F1, ROC AUC).

* Interpretar os resultados, incluindo a importância das variáveis.

* Gerar insights estratégicos sobre os fatores que mais influenciam a evasão.

<h2>:chart_with_downwards_trend: Visualizações e Resultados</h2>
1. Curva ROC dos Modelos

2. Matriz de Confusão

3. Importância das Variáveis

4. Distribuição da Evasão por Perfil de Cliente

<h2>:bulb: Insights e Principais Fatores</h2>

<h3>Perfil de Clientes</h3>

* Clientes com contrato mensal têm maior probabilidade de evasão.

* Alto gasto mensal + pouco tempo de contrato é um forte indicador de churn.

* Atrasos de pagamento estão diretamente ligados a maiores taxas de cancelamento.

* Qualidade e Serviços

* Clientes que não utilizam determinados serviços (ex.: pacotes adicionais) cancelam com mais frequência.

* Insatisfação com suporte/atendimento aparece como variável relevante.

* Fatores de Negócio

* Tipo de plano e meio de pagamento influenciam diretamente na retenção.

* Contratos anuais ou mais longos apresentam menor índice de cancelamento.

<h2>:hammer_and_wrench: Estratégias de Retenção</h2>

* Clientes novos → campanhas de onboarding, benefícios nos primeiros meses.

* Planos com alta taxa de churn → revisar precificação e oferecer pacotes customizados.

* Atraso de pagamento → flexibilizar formas de pagamento e criar alertas automáticos.

* Queda no uso do serviço → campanhas de engajamento personalizadas (e-mail, push, notificações no app).

<h2>:mag_right: Interpretação & Explainability</h2>

* SHAP Values e Permutation Importance para explicar previsões.

* Partial Dependence Plots (PDP) para avaliar impacto de variáveis específicas.

* Calibração de probabilidades para criar scorecards de risco de churn.

<h2>:triangular_flag_on_post: Próximos Passos</h2>

* Otimizar hiperparâmetros dos modelos (GridSearch / RandomizedSearch).

* Avaliar divisão temporal (time-series split) para sazonalidade.

* Desenvolver pipeline de deploy (API ou batch scoring).

* Monitorar drift e atualizar modelo conforme novas informações.

<h2>⚠️ Autor do Projeto</h2>

Guilherme Dias de Oliveira
🔗 Linkedin: www.linkedin.com/in/guilhermedooliveira
