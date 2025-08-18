# Análise de Evasão de Clientes (Churn) — Projeto de Machine Learning

## 1) Objetivo
Prever a **evasão de clientes (churn)** e identificar os **fatores que mais influenciam** a decisão de cancelamento, orientando **estratégias de retenção**.

## 2) Dados
- **Fonte dos dados:** `dados_limpos.csv`
- **Variável-alvo:** `churn`

## 3) Pré-processamento
- Limpeza de dados (nulos, tipos, *outliers*).
- *Encoding* de variáveis categóricas (One-Hot/Ordinal, conforme o caso).
- Padronização/normalização para modelos lineares e SVM.
- *Split* treino/teste e validação cruzada estratificada.
- Balanceamento (se necessário): `class_weight='balanced'` e/ou `SMOTE`.

## 4) Modelagem
Modelos avaliados:
  - Logistic Regression
  - Random Forest

Métricas calculadas (teste e CV): Accuracy, Precision, Recall, F1, ROC AUC, *Matriz de Confusão*.

### 4.1) Desempenho dos modelos
- plt.plot(fpr, tpr, color='blue', label=f'Random Forest (AUC = {roc_auc:.2f})')
- Acurácia: 0.7502369668246446
- accuracy: 0.75
- Acurácia: 0.7758293838862559
- accuracy: 0.78
- precision: 1
- precision: 1
- recall: 1
- recall: 1
- f1: 0.91
- f1: 0.85
- ROC AUC: 0.8453605281539812
- ROC AUC: 0.8238280346471589

> Observação: utilize ROC AUC e Recall como métricas-chave para **priorizar a captura de churn** (falsos negativos são mais custosos).

## 5) Seleção de Variáveis
Variáveis consideradas no modelo:
- (lista de variáveis será preenchida após a seleção de features)

### 5.1) Importância das variáveis / *Feature Importance*
As importâncias serão detalhadas por modelo (coeficientes padronizados, Gini/ganho, ou permutação).

> Interpretação: variáveis com maior importância/coeficiente absoluto têm maior contribuição para explicar a evasão (sinal positivo → aumenta a chance de churn; negativo → reduz).

## 6) Principais Fatores que Influenciam a Evasão
- **Preço/Plano**: diferenças de plano, upgrades/downgrades e descontos aplicados.
- **Engajamento/uso**: número de interações, dias ativos, consumo de serviços.
- **Qualidade de serviço**: reclamações, tempo de atendimento, falhas/incidentes.
- **Perfil/antiguidade**: tempo de contrato, região, segmento de cliente.
- **Pagamentos**: atrasos, inadimplência, meio de pagamento.

_(Ajuste esta lista com base nas importâncias observadas acima.)_

## 7) Estratégias de Retenção
**Estratégias de retenção sugeridas (orientadas por dados):**
- **Clientes com alto tempo de espera/suporte:** priorizar SLA de atendimento, filas dedicadas, e canais assíncronos.
- **Planos com alto índice de cancelamento:** revisar política de preço e benefícios; testar *bundles* e descontos condicionados à fidelização.
- **Baixo engajamento/uso do serviço:** campanhas de reativação (e-mail, push), conteúdos de onboarding e *nudges* dentro do app.
- **Clientes com histórico de atraso de pagamento:** oferecer meios de pagamento flexíveis, lembretes proativos e renegociação automática.
- **Sinais precoces (queda no uso, reclamações):** acionar *playbooks* de retenção via CRM com ofertas personalizadas.

**Priorize ações orientadas pelos fatores mais importantes do seu modelo.** Exemplos:
- Se **tempo de contrato curto** for determinante → campanhas de *onboarding* e benefícios nos primeiros 90 dias.
- Se **plano X** concentrar churn → experimentar precificação dinâmica, *trial* de recursos premium e suporte dedicado.
- Se **queda de uso** antecede o churn → *alerts* de risco + oferta de valor (créditos, conteúdos, funcionalidades).

## 8) Interpretação & Explainability
- **SHAP/Permutação** para explicar previsões individuais e globais.
- **Parcial Dependence/ICE** para entender o efeito marginal de variáveis-chave.
- **Calibração de probabilidades** (CalibratedClassifierCV) para *scorecards* acionáveis no CRM.

## 9) Como Reproduzir
```bash
# 1) Clonar e instalar dependências
pip install -r requirements.txt

# 2) Executar a análise
jupyter notebook Analise_Parte2.ipynb

# 3) (Opcional) Rodar pipeline
python src/train.py --config configs/default.yaml
```

## 10) Estrutura do Repositório
```
.
├─ data/                # dados brutos e processados (gitignore)
├─ notebooks/
│  └─ Analise_Parte2.ipynb
├─ src/
│  ├─ features/         # transformação de dados
│  ├─ models/           # treino, avaliação, persistência
│  └─ utils/            # métricas, plots, helpers
├─ reports/
│  └─ figures/          # gráficos (ROC, confusão, SHAP)
├─ configs/             # parâmetros de treino/valid.
└─ README.md
```

## 11) Próximos Passos
- Ajuste de *threshold* para balancear Recall vs. Precisão conforme o custo de retenção.
- *Hyperparameter tuning* (Grid/Random/Bayes) do melhor modelo.
- Validação temporal (*time-based split*) se houver sazonalidade.
- Deploy do modelo (API/Batch) + monitoramento de *drift*.

---

> **Nota**: este README foi gerado automaticamente a partir do notebook, preenchendo o que foi possível (modelos detectados: Logistic Regression, Random Forest). Recomenda-se revisar as métricas e a lista de variáveis conforme os resultados mais recentes.
