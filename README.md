# Desafio TelecomX: Análise de Evasão de Clientes (Churn Analysis)

Este repositório contém o projeto desenvolvido como parte do programa de formação em Data Science oferecido pela **Oracle em parceria com a Alura**. O objetivo principal é realizar uma análise aprofundada dos dados de uma empresa de telecomunicações, a TelecomX, para identificar os principais fatores que levam à evasão de clientes (Churn) e propor recomendações estratégicas baseadas em dados.

## 🎯 Objetivo do Projeto

O propósito desta análise é:

  * Realizar o processo de Extração, Transformação e Carga (ETL) dos dados de clientes da TelecomX.
  * Conduzir uma Análise Exploratória de Dados (EDA) para identificar padrões, tendências e correlações que influenciam o Churn.
  * Gerar insights acionáveis e recomendações estratégicas para aprimorar a retenção de clientes.
  * Preparar um dataset limpo e estruturado para futuras etapas de modelagem preditiva de Churn.

## 📁 Estrutura do Repositório

Este repositório está organizado para facilitar a compreensão e a execução do projeto:

  * **`_DESAFIO_2_.ipynb`**: O principal Jupyter Notebook que documenta todas as etapas do projeto, incluindo ETL, EDA, interpretação dos resultados e recomendações.
  * **`README.md`**: Este arquivo, que você está lendo, fornece uma visão geral do projeto, seus objetivos, estrutura e instruções de uso.
  * **`telecom_data_transformed.csv`**: O resultado do pipeline de ETL. Este arquivo CSV contém o dataset limpo, normalizado e com variáveis categóricas codificadas (One-Hot Encoded), pronto para ser utilizado em modelos de Machine Learning.
  * **`imagens/`**: Esta pasta armazena as visualizações geradas durante a EDA e utilizadas para ilustrar os insights no README.
      * `IMAGEM_1.png`: Gráfico da Taxa de Churn por Tipo de Contrato.
      * `IMAGEM 2.png`: Gráfico da Taxa de Churn por Número de Serviços Contratados.
      * `IMAGEM 3.png`: Heatmap de Correlação das Variáveis com o Churn.

## ⚙️ Tecnologias e Bibliotecas

O projeto foi desenvolvido em Python e utiliza as seguintes bibliotecas:

  * `pandas`: Para manipulação e análise de dados.
  * `json`: Para trabalhar com o formato JSON dos dados brutos.
  * `requests`: Para extrair dados diretamente de uma URL.
  * `matplotlib`: Para criação de visualizações estáticas.
  * `seaborn`: Para criação de visualizações estatísticas mais atraentes e informativas.

## 📊 Principais Gráficos e Insights Obtidos

A Análise Exploratória de Dados (EDA) revelou padrões cruciais sobre o comportamento de Churn dos clientes da TelecomX. A taxa de churn na base de dados analisada é de aproximadamente 26.57%. Abaixo, apresentamos os gráficos mais relevantes e seus insights:

### 1\. Taxa de Churn por Tipo de Contrato
![](IMAGEM_1.png)

Este gráfico é fundamental para entender a relação entre o tipo de contrato do cliente e sua propensão ao cancelamento.

  * **Insight:** Clientes com contratos **Mês a Mês** são os mais propensos ao Churn, com uma taxa de **42.71%**. Em contraste, clientes com contratos anuais ou bienais têm uma taxa de churn significativamente mais baixa, de **6.78%**. Isso sugere que a fidelização por meio de contratos mais longos é uma estratégia eficaz.

### 2\. Taxa de Churn por Número de Serviços Contratados

Esta visualização ilustra como a quantidade de serviços que um cliente possui se relaciona com sua taxa de Churn.

  * **Insight:** Há uma clara tendência de diminuição da taxa de churn à medida que o número de serviços contratados aumenta, o que indica que clientes com muitos serviços são mais leais. Clientes com 1 serviço têm uma taxa de churn de 34.52%, que atinge um pico com 2 serviços (37.72%). Em contrapartida, clientes com 7 serviços apresentam a menor taxa de churn, de **5.29%**.

### 3\. Matriz de Correlação com o Churn (Heatmap)

O heatmap de correlação permite visualizar a força e a direção da relação linear entre cada variável e a variável alvo `Churn`.

  * **Insight:**
      * **Correlação Positiva Mais Forte com Churn**:
          * `account.Contract_Month-to-month`: **0.4** (clientes com contratos mensais tendem a churnar mais).
          * `internet.InternetService_Fiber optic`: **0.31** (clientes com Fibra Óptica tendem a churnar mais).
          * `account.PaymentMethod_Electronic check`: **0.3** (pagamento via cheque eletrônico está associado a maior Churn).
      * **Correlação Negativa Mais Forte com Churn**:
          * `customer.tenure`: **-0.35** (quanto maior o tempo de contrato, menor o Churn).
          * `account.Contract_Two year`: **-0.3** (contratos de dois anos estão fortemente associados a menor Churn).
          * `internet.InternetService_No`: **-0.23** (clientes que não têm serviço de internet apresentam uma correlação negativa).

## 📈 Próximos Passos: Modelagem Preditiva

Esta análise exploratória forneceu uma base sólida para a compreensão do Churn na TelecomX. O próximo estágio crucial é o desenvolvimento de um **Modelo Preditivo de Churn**, que permitirá à TelecomX:

  * **Identificar Clientes em Risco:** Prever com antecedência quais clientes têm maior probabilidade de cancelar seus serviços, permitindo intervenções proativas.
  * **Otimizar Intervenções:** Direcionar esforços de retenção (ofertas personalizadas, suporte proativo, etc.) de forma mais eficaz e com maior retorno sobre o investimento.

As etapas para a construção do modelo incluirão:

1.  **Preparação Final dos Dados:** O dataset `telecom_data_transformed.csv` já está bem estruturado. Será necessário realizar o escalonamento de variáveis numéricas (e.g., Padronização ou Normalização) para otimizar o desempenho de algoritmos de Machine Learning que são sensíveis à escala dos dados.
2.  **Divisão do Dataset:** Separação do dataset em conjuntos de treino e teste (e validação, se necessário) para garantir uma validação robusta do modelo e evitar *overfitting*.
3.  **Seleção e Otimização de Modelos:** Experimentação com uma variedade de algoritmos de classificação (e.g., Regressão Logística, Random Forest, Gradient Boosting, SVM, XGBoost) e ajuste fino de seus hiperparâmetros para encontrar a melhor performance.
4.  **Avaliação de Desempenho:** Utilização de métricas apropriadas para problemas de classificação desbalanceada (dado que Churn geralmente é um evento minoritário), como Precisão, Recall, F1-Score, e a Curva ROC/AUC.

## ⚠️ Limitações da Análise Atual

É importante considerar as seguintes limitações no escopo desta análise exploratória:

  * **Dados Estáticos:** A análise é baseada em um *snapshot* dos dados em um determinado momento. O comportamento do cliente e os fatores de Churn podem mudar ao longo do tempo, exigindo futuras reavaliações e atualizações do modelo.
  * **Ausência de Causalidade:** As correlações identificadas não implicam necessariamente em causalidade. Embora indiquem associações fortes, outros fatores não presentes no dataset (e.g., ações da concorrência, qualidade do serviço percebida em aspectos não quantificados, eventos de vida do cliente) podem estar influenciando o Churn. Experimentos controlados (como Testes A/B, já sugeridos como recomendação) seriam necessários para estabelecer causalidade.
  * **Variáveis Disponíveis:** A análise está restrita às variáveis fornecidas no dataset. A inclusão de dados adicionais (e.g., histórico de interações com o suporte, reclamações, dados demográficos mais detalhados, feedback de pesquisas de satisfação) poderia fornecer insights mais ricos e melhorar a capacidade preditiva de um modelo futuro.
  * **Generalização:** Os *insights* e as recomendações são específicos para a base de clientes da TelecomX analisada. A generalização para outras empresas de telecomunicações ou mercados deve ser feita com cautela e após validação adicional.

Apesar dessas limitações, os resultados obtidos fornecem uma base sólida e acionável para o desenvolvimento de estratégias de retenção.

-----

**Desenvolvido por:** [https://github.com/ASCCJR](https://github.com/ASCCJR)

**Parte do programa:** Oracle + Alura Data Science Formation
