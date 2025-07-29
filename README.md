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

* **`telecomx_br.ipynb`**: O principal Jupyter Notebook que documenta todas as etapas do projeto, incluindo ETL, EDA, interpretação dos resultados e recomendações.
* **`README.md`**: Este arquivo, que você está lendo, fornece uma visão geral do projeto, seus objetivos, estrutura e instruções de uso.
* **`dados_telecom_tratados.csv`**: O resultado do pipeline de ETL. Este arquivo CSV contém o dataset limpo, normalizado e com variáveis categóricas codificadas (One-Hot Encoded), pronto para ser utilizado em modelos de Machine Learning.
* **`imagens/`**: Esta pasta armazena as visualizações geradas durante a EDA e utilizadas para ilustrar os insights no README.
    * `IMAGEM 1.png`: Gráfico da Taxa de Churn por Tipo de Contrato.
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

A Análise Exploratória de Dados (EDA) revelou padrões cruciais sobre o comportamento de Churn dos clientes da TelecomX. Abaixo, apresentamos os gráficos mais relevantes e seus insights:

### 1. Taxa de Churn por Tipo de Contrato

Este gráfico é fundamental para entender a relação entre o tipo de contrato do cliente e sua propensão ao cancelamento.

* **Insight:** Clientes com contratos **Mês a Mês** (`Month-to-month`) são os mais propensos ao Churn, com uma taxa de **42,71%**. Em contraste, contratos de **dois anos** (`Two year`) têm a menor taxa de Churn, com apenas **2,85%**, enquanto contratos de **um ano** (`One year`) registram **11,28%**. Isso sugere que a fidelização por meio de contratos mais longos é uma estratégia eficaz.

![Taxa de Churn por Tipo de Contrato](IMAGEM%201.png)

### 2. Taxa de Churn por Número de Serviços Contratados

Esta visualização ilustra como a quantidade de serviços que um cliente possui se relaciona com sua taxa de Churn.

* **Insight:** A taxa de Churn não é linearmente decrescente com o número de serviços. Clientes com **0 serviços** (apenas o plano básico, sem adicionais) apresentam uma taxa de Churn de **25,0%**. Curiosamente, a taxa **aumenta significativamente para clientes com 3, 4 ou 5 serviços** (atingindo picos de **59,16%** para 3 serviços), e **depois diminui para aqueles com um número maior de serviços (6 a 9)**, chegando a **8,26%** para 9 serviços. Isso indica que o ponto de maior risco de Churn está entre os clientes que contratam um número moderado de serviços.

![Taxa de Churn por Número de Serviços Contratados](IMAGEM%202.png)

### 3. Matriz de Correlação com o Churn (Heatmap)

O heatmap de correlação permite visualizar a força e a direção da relação linear entre cada variável e a variável alvo `Churn_Yes`.

* **Insight:**
    * **Correlação Positiva Mais Forte com Churn**:
        * `internet.InternetService_Fiber optic`: **0.307** (clientes com Fibra Óptica tendem a churnar mais).
        * `account.PaymentMethod_Electronic check`: **0.301** (pagamento via cheque eletrônico está associado a maior Churn).
        * `account.Charges.Monthly`: **0.193** (encargos mensais mais altos moderadamente associados a maior Churn).
        * `customer.SeniorCitizen`: **0.151** (clientes idosos tendem a churnar mais).
    * **Correlação Negativa Mais Forte com Churn**:
        * `customer.tenure`: **-0.354** (quanto maior o tempo de contrato, menor o Churn).
        * `account.Contract_Two year`: **-0.302** (contratos de dois anos estão fortemente associados a menor Churn).
        * Variáveis que indicam a **ausência de serviços de internet** (`internet.OnlineSecurity_No internet service`, `internet.StreamingMovies_No internet service`, `internet.OnlineBackup_No internet service`, `internet.InternetService_No`, `internet.TechSupport_No internet service`, `internet.DeviceProtection_No internet service`, `internet.StreamingTV_No internet service`) apresentaram correlações negativas em torno de **-0.228**. Isso é lógico, pois clientes sem internet não churnam por motivos relacionados a esses serviços.

![Variáveis Correlacionadas com o Churn](IMAGEM%203.png)

## 📈 Próximos Passos: Modelagem Preditiva

Esta análise exploratória forneceu uma base sólida para a compreensão do Churn na TelecomX. O próximo estágio crucial é o desenvolvimento de um **Modelo Preditivo de Churn**, que permitirá à TelecomX:

* **Identificar Clientes em Risco:** Prever com antecedência quais clientes têm maior probabilidade de cancelar seus serviços, permitindo intervenções proativas.
* **Otimizar Intervenções:** Direcionar esforços de retenção (ofertas personalizadas, suporte proativo, etc.) de forma mais eficaz e com maior retorno sobre o investimento.

As etapas para a construção do modelo incluirão:

1.  **Preparação Final dos Dados:** O dataset `dados_telecom_tratados.csv` já está bem estruturado. Será necessário realizar o escalonamento de variáveis numéricas (e.g., Padronização ou Normalização) para otimizar o desempenho de algoritmos de Machine Learning que são sensíveis à escala dos dados.
2.  **Divisão do Dataset:** Separação do dataset em conjuntos de treino e teste para garantir uma validação robusta do modelo e evitar overfitting.
3.  **Seleção e Otimização de Modelos:** Experimentação com uma variedade de algoritmos de classificação (e.g., Regressão Logística, Random Forest, Gradient Boosting, SVM, XGBoost) e ajuste fino de seus hiperparâmetros para encontrar a melhor performance.
4.  **Avaliação de Desempenho:** Utilização de métricas apropriadas para problemas de classificação desbalanceada (dado que Churn geralmente é um evento minoritário), como Precisão, Recall, F1-Score, e a Curva ROC/AUC.

## ⚠️ Limitações da Análise Atual

É importante considerar as seguintes limitações no escopo desta análise exploratória:

* **Dados Estáticos:** A análise é baseada em um *snapshot* dos dados em um determinado momento. O comportamento do cliente e os fatores de Churn podem mudar ao longo do tempo, exigindo futuras reavaliações e atualizações do modelo.
* **Ausência de Causalidade:** As correlações identificadas não implicam necessariamente em causalidade. Embora indiquem associações fortes, outros fatores não presentes no dataset (e.g., ações da concorrência, qualidade do serviço percebida em aspectos não quantificados, eventos de vida do cliente) podem estar influenciando o Churn. Experimentos controlados (como Testes A/B, já sugeridos como recomendação) seriam necessários para estabelecer causalidade.
* **Variáveis Disponíveis:** A análise está restrita às variáveis fornecidas no dataset. A inclusão de dados adicionais (e.g., histórico de interações com o suporte, reclamações, dados demográficos mais detalhados, feedback de pesquisas de satisfação) poderia fornecer insights mais ricos e melhorar a capacidade preditiva de um modelo futuro.
* **Interpretação:** Algumas interpretações, como as nuances nos picos da taxa de Churn por número de serviços, são baseadas em padrões observados e podem se beneficiar de validação adicional ou de um conhecimento mais profundo do negócio (domínio).
* **Generalização:** Os *insights* e as recomendações são específicos para a base de clientes da TelecomX analisada. A generalização para outras empresas de telecomunicações ou mercados deve ser feita com cautela e após validação.

## 🤝 Contribuições

Contribuições, sugestões e melhorias para este projeto são muito bem-vindas! Sinta-se à vontade para abrir *issues* para discutir ideias ou enviar *pull requests* com suas modificações.

---

**Desenvolvido por:** [https://github.com/ASCCJR](https://github.com/ASCCJR)

**Parte do programa:** Oracle + Alura Data Science Formation
