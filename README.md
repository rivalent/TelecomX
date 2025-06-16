# Análise Exploratória de Dados (EDA) de Evasão de Clientes em Telecomunicações

## Visão Geral do Projeto

Este projeto tem como objetivo realizar uma **Análise Exploratória de Dados (EDA)** detalhada em um conjunto de dados de clientes de uma empresa de telecomunicações. O foco principal é entender os fatores que contribuem para a evasão de clientes (churn), identificando padrões e comportamentos que levam os clientes a cancelar seus serviços. Através desta análise, buscaremos extrair insights valiosos que podem informar estratégias de retenção de clientes.

## Objetivo

* **Compreender a Distribuição de Churn:** Visualizar a proporção de clientes que evadiram versus os que permaneceram.
* **Identificar Fatores Categóricos:** Analisar como variáveis categóricas (como tipo de contrato, método de pagamento, tipo de serviço de internet, etc.) se relacionam com a taxa de evasão.
* **Explorar Relações Numéricas:** Investigar a distribuição de variáveis numéricas (como tempo de serviço, custo mensal/total) entre clientes que evadiram e os que não evadiram.
* **Descobrir Correlações:** Calcular e visualizar a correlação entre diferentes variáveis, incluindo a relação com a variável de churn, para identificar as influências mais fortes.
* **Gerar Insights Acionáveis:** Fornecer conclusões baseadas em dados para ajudar a empresa a desenvolver estratégias de retenção de clientes mais eficazes.

## Conjunto de Dados

O conjunto de dados utilizado é de uma empresa de telecomunicações e contém informações sobre diversos clientes, incluindo:
* Informações demográficas (gênero, idade, parceiro, dependentes).
* Serviços contratados (serviço de telefone, múltiplas linhas, internet, segurança online, backup, etc.).
* Informações da conta (tempo de serviço, tipo de contrato, fatura digital, método de pagamento, custos).
* Status de evasão (`Churn`).

## Metodologia e Etapas da Análise

O projeto seguiu as seguintes etapas principais:

1.  **Carregamento e Exploração Inicial dos Dados:**
    * Carregamento do dataset (formato JSON).
    * Inspeção inicial para entender a estrutura dos dados, tipos de variáveis e identificar possíveis problemas.
2.  **Limpeza e Pré-processamento dos Dados:**
    * Renomeação de colunas para maior clareza (português).
    * Tratamento de valores ausentes, especialmente na coluna `Custo_Total`.
    * Padronização de valores, convertendo 'Yes'/'No' e outras categorias binárias para 1/0 para facilitar a análise numérica e de modelagem.
    * Conversão de tipos de dados (`Custo_Total`, `Custo_Mensal` para numérico).
    * Criação da variável `Custo_Diario`.
3.  **Análise Descritiva:**
    * Cálculo de métricas estatísticas básicas (média, mediana, desvio padrão, mínimo, máximo, quartis) para variáveis numéricas e categóricas.
    * Visão geral da distribuição de cada variável.
4.  **Análise da Distribuição de Evasão (Churn):**
    * Visualização da proporção geral de clientes com e sem churn através de gráficos de barras e pizza.
5.  **Análise da Evasão por Variáveis Categóricas:**
    * Utilização de tabelas de contingência e gráficos de barras agrupados para entender a taxa de churn em relação a `Gênero`, `Idoso`, `Parceiro`, `Dependentes`, `Contrato`, `Método_Pagamento`, `Serviço_Internet`, e outros serviços adicionais.
6.  **Análise da Evasão por Variáveis Numéricas:**
    * Emprego de Box Plots e KDE Plots para comparar a distribuição de `Meses_Servico`, `Custo_Mensal`, `Custo_Total` e `Custo_Diario` entre clientes que evadiram e os que não evadiram.
7.  **Análise de Correlação (Opcional - Adicional):**
    * Cálculo da matriz de correlação de Pearson para identificar relações lineares entre variáveis numéricas.
    * Visualização da matriz de correlação usando um heatmap.
    * Criação de uma nova feature `Total_Servicos_Contratados` e análise de sua relação com o churn.

## Principais Descobertas e Insights

A análise exploratória revelou insights cruciais sobre os fatores de evasão:

* **Taxa de Churn Elevada:** Aproximadamente **25.76%** dos clientes evadiram, indicando um problema significativo de retenção.
* **Contrato Mensal é Crítico:** Clientes com **contratos mensais** apresentam uma taxa de churn alarmante de **41.32%**, em contraste com apenas 2.77% para contratos de dois anos.
* **Método de Pagamento:** O **"Cheque eletrônico"** está associado a uma taxa de churn de **43.80%**, enquanto métodos automáticos (cartão/transferência) têm taxas bem mais baixas.
* **Serviço de Internet:** Clientes de **"Fibra Óptica"** têm uma taxa de churn de **40.56%**, muito superior a outros tipos de internet ou a quem não tem internet. Isso sugere problemas específicos com este serviço.
* **Serviços Adicionais:** A presença de serviços como **Segurança Online**, **Backup Online**, **Proteção de Dispositivo** e, principalmente, **Suporte Técnico** está fortemente correlacionada com uma **MENOR** taxa de evasão. Clientes que utilizam Suporte Técnico, por exemplo, têm taxa de churn de apenas 14.76%.
* **Demografia:**
    * Clientes **idosos** (SeniorCitizen) têm uma taxa de churn significativamente mais alta (40.27%).
    * Clientes **sem parceiro** ou **sem dependentes** são mais propensos ao churn (32.03% e 30.34%, respectivamente).
* **Fatura Digital:** Curiosamente, clientes com **fatura digital** têm uma taxa de churn mais alta (32.50%).
* **Tempo de Serviço (`Meses_Servico`):** Há uma forte **correlação negativa** com o churn; quanto maior o tempo de serviço, menor a probabilidade de evasão.
* **Custo Mensal vs. Churn:** Clientes com **custos mensais mais altos** tendem a ter maior probabilidade de evasão.

## Recomendações Preliminares

Com base nos insights, as seguintes ações estratégicas são sugeridas:

* **Incentivar Contratos de Longo Prazo:** Criar ofertas atrativas para clientes com contratos mensais migrarem para planos de um ou dois anos.
* **Melhorar a Experiência da Fibra Óptica:** Investigar e resolver problemas de qualidade, desempenho ou suporte para clientes de Fibra Óptica.
* **Promover Serviços de Valor Agregado:** Campanhas focadas em Segurança Online, Backup, Proteção de Dispositivo e Suporte Técnico podem aumentar a retenção.
* **Analisar o Método de Pagamento "Cheque eletrônico":** Entender as causas da alta evasão associada a este método para propor soluções.
* **Desenvolver Programas de Retenção Segmentados:** Focar em grupos de alto risco como idosos e clientes de curto prazo.

## Ferramentas e Tecnologias

* `Python`
* `Pandas` para manipulação e análise de dados.
* `Matplotlib` e `Seaborn` para visualização de dados.

## Autor

* rivalent

---