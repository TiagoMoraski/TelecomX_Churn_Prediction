# TelecomX - Churn Prediction

## 1. Introdução
Este projeto é a **segunda parte** do desafio Telecom X, focada em prever a evasão de clientes (Churn) para uma empresa de telecomunicações.  
Na **primeira parte**, realizamos o processo de ETL e a análise exploratória.  
Nesta etapa, criamos modelos preditivos para identificar clientes com alto risco de cancelamento.

## 2. Problema
A empresa enfrenta uma alta taxa de cancelamento de clientes e precisa identificar padrões e variáveis que influenciam o churn, de forma a criar ações preventivas.

## 3. Processo ETL
O dataset utilizado foi obtido a partir dos dados tratados na Parte 1 do desafio, exportados para o ficheiro **TelecomX_Clean.csv**.  
No processo de ETL:
- Extração: leitura do CSV no Google Colab usando Pandas.
- Transformação: limpeza, tratamento de valores ausentes, normalização e codificação.
- Carga: dataset pronto salvo para uso na modelagem.

## 4. Análise Exploratória (EDA)
Foram gerados gráficos e estatísticas para identificar padrões:
- Distribuição de churn por contrato.
- Comparação de mensalidade e total gasto.
- Análise por tempo de permanência.
- Correlações entre variáveis.

## 5. Modelagem Preditiva
Testamos três algoritmos:
- Logistic Regression
- Decision Tree
- Random Forest

### Resultados iniciais (threshold padrão 0.5)

| Modelo              | Acurácia | Precisão (Churn) | Recall (Churn) | F1 (Churn) | ROC-AUC |
|---------------------|----------|------------------|----------------|------------|---------|
| Logistic Regression | 0.803    | 0.65             | 0.54           | 0.59       | 0.841   |
| Random Forest       | 0.796    | 0.66             | 0.47           | 0.55       | 0.817   |
| Decision Tree       | 0.723    | 0.48             | 0.46           | 0.47       | 0.639   |

O modelo **Logistic Regression** apresentou melhor equilíbrio entre métricas e interpretabilidade.

### Otimização e Threshold
Após ajuste de hiperparâmetros (`C = 5.0`) e mudança do threshold para **0.55**, obtivemos:
- Acurácia: 0.766
- ROC-AUC: 0.841
- Recall (Churn): 0.76
- F1 (Churn): 0.63

Matriz de Confusão:
## 6. Principais Variáveis Influentes
1. `account_Charges.Total`
2. `customer_tenure`
3. `account_Charges.Monthly`
4. `account_Contract_Month-to-month`
5. `account_PaymentMethod_Electronic check`
6. `internet_OnlineSecurity_No`
7. `internet_TechSupport_No`

## 7. Recomendações
- Ofertas de retenção para clientes com contrato mensal e pagamento por "Electronic check".
- Programas de fidelização para clientes com baixo tempo de permanência.
- Pacotes que incluam segurança online e suporte técnico.

## 8. Conclusão
<o da evasão.
