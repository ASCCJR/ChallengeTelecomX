# Challenge Telecom X – Análise de Evasão de Clientes (Churn)

## 📌 Visão Geral do Projeto

Este projeto faz parte do programa de formação em Data Science da Oracle em parceria com a Alura. O objetivo principal é realizar uma análise aprofundada dos fatores que influenciam a evasão de clientes (Churn) em uma empresa de telecomunicações fictícia, a TelecomX. Através das etapas de Extração, Transformação e Carga (ETL) e Análise Exploratória de Dados (EDA), busca-se identificar padrões e características de clientes com alto e baixo risco de cancelamento, culminando em recomendações estratégicas para otimizar a retenção.

## 🗄️ Fonte dos Dados

Os dados brutos são provenientes de um arquivo JSON hospedado no GitHub, que contém informações detalhadas sobre os clientes da TelecomX, seus serviços, dados demográficos e status de churn.

- **URL do JSON:** `https://raw.githubusercontent.com/alura-cursos/challenge2-data-science/main/TelecomX_Data.json`

## 📁 Etapas do Projeto

O projeto foi estruturado nas seguintes fases, executadas e detalhadas no notebook `TelecomX_BR.ipynb`:

### 1. 🔍 Extração de Dados

Nesta etapa, os dados brutos foram extraídos diretamente do arquivo JSON via URL e carregados em um DataFrame do Pandas para facilitar o manuseio e a análise. Foi realizada uma validação inicial para garantir a presença das colunas esperadas.

### 2. ⚙️ Transformação de Dados (ETL)

A fase de transformação foi crucial para preparar os dados para análise e modelagem. As principais ações incluíram:

- Normalização de Estruturas Aninhadas com `pd.json_normalize`
- Tratamento de valores ausentes e inconsistências
- Mapeamento e binarização de colunas categóricas
- One-hot encoding em variáveis nominais
- Conversão de tipos e renomeação de colunas para português

### 3. 📊 Análise Descritiva (EDA)

Nesta fase foram realizadas:

- Estatísticas descritivas
- Criação de variáveis auxiliares como `Total_Servicos`
- Gráficos de distribuição, boxplots e taxa de churn por categoria
- Correlação entre variáveis e churn

## 📈 Principais Descobertas e Perfil de Risco

- Taxa geral de churn: **26,54%**
- Contrato mensal, fibra ótica e cheque eletrônico estão fortemente ligados ao churn
- Clientes com contratos de 1 ou 2 anos e mais serviços contratados tendem a permanecer por mais tempo

## 💡 Recomendações Estratégicas

- Incentivar a migração para contratos de longo prazo
- Criar programa de onboarding nos primeiros 90 dias
- Revisar experiência de clientes com fibra ótica
- Promover pacotes com múltiplos serviços (cross-selling)

## ⏭️ Próximos Passos: Modelagem Preditiva

- Escalonamento de variáveis numéricas
- Separação em treino/teste
- Avaliação de modelos (Logística, Random Forest, Boosting)
- Otimização de hiperparâmetros
- Avaliação com métricas como ROC, F1-score e AUC

## ⚠️ Limitações da Análise

- Dados limitados às variáveis fornecidas
- Natureza descritiva: não prova causalidade
- Resultados não generalizáveis sem validação externa

---

## 👨‍💻 Autor

**Antonio Junior**  
🔗 GitHub: [github.com/ASCCJR](https://github.com/ASCCJR)
