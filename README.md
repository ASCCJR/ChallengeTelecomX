# Challenge Telecom X: Análise de Evasão de Clientes (Churn Prediction)

Este repositório contém o projeto desenvolvido como parte do programa de formação em Data Science oferecido pela **Oracle em parceria com a Alura**. O objetivo principal é realizar uma análise aprofundada dos dados de uma empresa de telecomunicações, a TelecomX, para identificar os principais fatores que levam à evasão de clientes (Churn) e propor recomendações estratégicas baseadas em dados.

## 🎯 O Propósito da Análise

O propósito central desta análise é **compreender e combater o Churn de clientes na TelecomX**. A evasão de clientes é um problema crítico que afeta diretamente a receita e a sustentabilidade de qualquer negócio de telecomunicações. Ao identificar os padrões e as características dos clientes que cancelam seus serviços, a empresa pode:

* **Implementar estratégias de retenção proativas:** Agir antes que o cliente decida sair, oferecendo incentivos ou soluções personalizadas.
* **Otimizar o portfólio de serviços:** Identificar quais serviços ou planos estão associados a maior ou menor Churn, permitindo ajustes.
* **Melhorar a experiência do cliente:** Entender os pontos de dor que levam à insatisfação e à saída.
* **Reduzir custos de aquisição:** É mais barato reter um cliente existente do que adquirir um novo.
* **Apoiar futuras modelagens preditivas:** Fornecer os *insights* e os dados limpos necessários para a construção de modelos de Machine Learning que prevejam o Churn com antecedência.

Em suma, o projeto visa transformar dados em conhecimento acionável para aumentar a fidelidade dos clientes e o valor do negócio da TelecomX.

## 📁 Estrutura do Projeto e Organização dos Arquivos

Este repositório está organizado de forma a facilitar a compreensão e a execução do projeto:

* `TelecomX_BR.ipynb`: Este é o arquivo principal do Jupyter Notebook, onde toda a análise de dados foi realizada. Ele contém as etapas de ETL (Extração, Transformação e Carga), Análise Exploratória de Dados (EDA), a interpretação dos resultados e as recomendações estratégicas.
* `README.md`: Este arquivo, que você está lendo agora, fornece uma visão geral do projeto, seu propósito, estrutura e instruções de execução.
* `imagens/`: Esta pasta contém todas as imagens utilizadas no README para ilustrar os gráficos e *insights* obtidos na análise.
    * `IMAGEM 1.png`: Gráfico da Taxa de Churn por Tipo de Contrato.
    * `IMAGEM 2.png`: Gráfico da Taxa de Churn por Número de Serviços Contratados.
    * `IMAGEM 3.png`: Heatmap de Variáveis Correlacionadas com o Churn.
    * `IMAGEM 4.png`: Box Plots da Distribuição de Variáveis Numéricas Contínuas.
    * `IMAGEM 5.png`: Box Plots de Variáveis Numéricas por Churn.
    * `IMAGEM 6.png`: Gráficos de Barras da Taxa de Churn para Outras Variáveis Categóricas.

## 📊 Exemplos de Gráficos e Insights Obtidos

Durante a Análise Exploratória de Dados (EDA), diversas visualizações foram criadas para extrair *insights* valiosos. Abaixo estão alguns exemplos de gráficos e as principais descobertas:

### Taxa de Churn por Tipo de Contrato

Este gráfico é fundamental para entender a relação entre o tipo de contrato do cliente e sua propensão a cancelar.

* **Insight:** Clientes com **contrato mensal** são os maiores preditores de Churn, com uma taxa de **42,71%**. Em contraste, contratos de **dois anos** têm apenas **2,85%** de Churn, e contratos de **um ano** **11,28%**.

![Taxa de Churn por Tipo de Contrato](imagens/IMAGEM%201.png)

### Taxa de Churn por Número de Serviços Contratados

Esta visualização demonstra como o engajamento do cliente com os serviços da TelecomX impacta a retenção.

* **Insight:** A taxa de Churn **diminui drasticamente** à medida que o cliente contrata mais serviços adicionais. Por exemplo, clientes com 0 serviços (apenas o plano básico, sem adicionais) têm a maior taxa de Churn (43.75%), que cai para 5.79% para clientes com 7 serviços.

![Taxa de Churn por Número de Serviços Contratados](imagens/IMAGEM%202.png)

### Matriz de Correlação com o Churn (Heatmap)

O heatmap de correlação visualiza a força e a direção da relação entre cada variável e o Churn.

* **Insight:** Variáveis como `Contrato_Mensal` (0.40) e `Internet_FibraOtica` (0.31) apresentaram **correlação positiva** com o Churn. Já `Meses_Contrato` (-0.35) e `Contrato_DoisAnos` (-0.30) mostraram **correlação negativa**.

![Variáveis Correlacionadas com o Churn](imagens/IMAGEM%203.png)

### Box Plots de Variáveis Numéricas por Churn

Esses gráficos permitem visualizar a distribuição e a mediana de variáveis numéricas (`Meses_Contrato`, `Gasto_Mensal`, `Gasto_Total`) para clientes que deram Churn (1) e que não deram (0).

* **Insight:** Clientes que deram Churn (1) tendem a ter **menor `Meses_Contrato`** e **menor `Gasto_Total`**. O `Gasto_Mensal` de clientes com Churn tende a ser **mais alto** do que os que não deram, o que pode indicar sensibilidade ao preço ou expectativas não atendidas.

![Meses_Contrato, Gasto_Mensal e Gasto_Total por Churn](imagens/IMAGEM%205.png)

### Taxa de Churn para Outras Variáveis Categóricas

Este conjunto de gráficos de barras detalha a taxa de Churn para diversas outras características dos clientes, como gênero, se é idoso, serviços específicos e método de pagamento.

* **Insight:**
    * **Idosos:** Apresentam uma taxa de Churn maior (41.7%) do que não idosos (25.7%).
    * **Fatura Online:** Associada a uma taxa de Churn maior (39.4%).
    * **Internet Fibra Ótica:** Demonstra uma taxa de Churn significativamente maior (41.9%), corroborando o insight da matriz de correlação.
    * **Pagamento por Cheque Eletrônico:** Associado a uma das maiores taxas de Churn (43.9%).

![Taxa de Churn por Diversas Variáveis Categóricas](imagens/IMAGEM%206.png)

## 🚀 Próximos Passos (Modelagem Preditiva)

Esta análise exploratória fornece uma base sólida. O próximo estágio é o desenvolvimento de um **Modelo Preditivo de Churn**, que permitirá à TelecomX:

* **Identificar Clientes em Risco:** Prever com antecedência quais clientes têm maior probabilidade de cancelar.
* **Otimizar Intervenções:** Direcionar esforços de retenção de forma mais eficaz e personalizada.

As etapas para a construção do modelo incluirão:

1.  **Escalonamento de Variáveis Numéricas:** Padronização ou normalização para otimizar o desempenho de algoritmos de Machine Learning.
2.  **Divisão do Dataset:** Separação em conjuntos de treino e teste para validação robusta do modelo.
3.  **Seleção e Otimização de Modelos:** Experimentação com algoritmos de classificação (Regressão Logística, Random Forest, Gradient Boosting, etc.) e ajuste fino de hiperparâmetros.
4.  **Avaliação de Desempenho:** Utilização de métricas apropriadas para classificação desbalanceada (e.g., Precisão, Recall, F1-Score, Curva ROC/AUC).

## ⚠️ Limitações da Análise

É importante considerar as seguintes limitações:

* **Dados:** A análise baseia-se exclusivamente nos dados fornecidos para o desafio. Potenciais vieses ou incompletudes nos dados originais podem influenciar os *insights*.
* **Variáveis:** A análise está restrita às variáveis disponíveis no dataset. Fatores externos (concorrência, economia) ou internos não registrados (feedback qualitativo) poderiam oferecer perspectivas adicionais.
* **Natureza Descritiva:** Esta análise é primariamente descritiva e exploratória, identificando correlações e padrões. Ela não estabelece causalidade direta sem experimentos controlados (como Testes A/B, já sugeridos).
* **Generalização:** Os *insights* são específicos para a base de clientes da TelecomX e podem não ser diretamente aplicáveis a outras empresas sem validação.

## 🤝 Contribuições

Contribuições, sugestões e melhorias para este projeto são muito bem-vindas! Sinta-se à vontade para abrir *issues* para discutir ideias ou enviar *pull requests* com suas modificações.

---

**Desenvolvido por:** [https://github.com/ASCCJR]

**Parte do programa:** Oracle + Alura Data Science Formation
