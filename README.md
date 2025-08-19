# Análise de Evasão de Clientes – Desafio Telecom X

Este repositório contém a análise exploratória de dados (EDA) sobre a evasão de clientes (churn) da empresa fictícia de telecomunicações "Telecom X". O projeto aborda um ciclo completo de análise, desde a extração e tratamento de dados brutos até a geração de insights e recomendações de negócio.

## 🎯 Objetivo do Projeto

O objetivo principal deste desafio foi realizar um processo completo de **Extração, Transformação e Carga (ETL)** e uma **Análise Exploratória de Dados (EDA)** para identificar os principais fatores que influenciam a evasão de clientes. Com base nos padrões encontrados, o projeto visa fornecer recomendações estratégicas para a empresa focar em ações de retenção mais eficazes.

## 📖 Processo de Análise

O projeto foi estruturado em duas grandes etapas:

### 1. Extração, Transformação e Carga (ETL)

A primeira fase focou em preparar os dados para a análise, seguindo os passos:

- **Extração:** Os dados foram extraídos de um arquivo `TelecomX_Data.json`, que possuía uma estrutura aninhada.
- **Transformação:**
    - Os dados JSON foram normalizados para um formato tabular (DataFrame) utilizando a biblioteca **Pandas**.
    - Foi realizada uma limpeza criteriosa, que incluiu:
        - Remoção de registros com a coluna `Churn` vazia.
        - Tratamento da coluna de gastos totais (`account.Charges.Total`), que continha valores em branco e estava em formato de texto, convertendo-a para tipo numérico.
        - Renomeação de todas as colunas para o português para facilitar a interpretação (ex: `customer.gender` para `Genero`).
        - Padronização dos valores categóricos (ex: `Yes`/`No` para `Sim`/`Nao`).
- **Carga:** Ao final do processo, um novo arquivo, `dados_tratados.csv`, foi gerado, contendo os dados limpos e prontos para a análise.

### 2. Análise Exploratória de Dados (EDA)

Com os dados tratados, a segunda fase consistiu em investigar visualmente a relação entre as variáveis e a evasão de clientes, utilizando as bibliotecas **Matplotlib** e **Seaborn**. As principais análises visuais incluíram:

- Distribuição geral do Churn.
- Relação do Churn com dados demográficos (gênero, se é idoso).
- Impacto do tipo de contrato (mensal, um ano, dois anos) na taxa de evasão.
- Influência do tipo de serviço de internet (Fibra Óptica vs. DSL) no cancelamento.

## 🛠️ Ferramentas e Bibliotecas

- **Linguagem:** Python
- **Bibliotecas:**
    - `Pandas`: Para extração e manipulação de dados.
    - `Matplotlib` e `Seaborn`: Para visualização de dados e geração de gráficos.
    - `JSON`: Para manipulação do arquivo de dados original.
- **Ambiente:** Jupyter Notebook / Google Colab.

## 💡 Principais Achados (Insights)

A análise exploratória revelou um perfil claro de cliente com alta propensão à evasão:

1.  **Tipo de Contrato:** Clientes com **contratos mensais** têm uma taxa de churn drasticamente superior àqueles com contratos de longo prazo (um ou dois anos). Este é o indicador mais forte de evasão.
2.  **Serviço de Internet:** Clientes que utilizam **Fibra Óptica** cancelam o serviço com mais frequência do que os clientes de DSL, o que pode indicar problemas de preço, qualidade ou satisfação com este serviço específico.
3.  **Perfil Demográfico:** **Clientes idosos** (`SeniorCitizen`) demonstram uma maior tendência a cancelar o serviço em comparação com clientes mais jovens.

## 🚀 Recomendações

Com base nos insights gerados, as seguintes ações são recomendadas para a Telecom X:

- **Focar na Migração de Contratos:** Criar campanhas e oferecer incentivos (descontos, benefícios) para que clientes de planos mensais migrem para contratos de 1 ou 2 anos.
- **Investigar a Satisfação com a Fibra Óptica:** Realizar uma análise mais aprofundada sobre a experiência dos clientes de fibra para entender os motivos da alta taxa de churn (ex: custo, instabilidade, suporte técnico).
- **Criar Ofertas Direcionadas:** Desenvolver pacotes e ofertas especiais para o público idoso, visando aumentar a fidelidade desse segmento.

## Como Executar o Projeto

1.  Certifique-se de ter o arquivo de dados `TelecomX_Data.json` na mesma pasta do notebook.
2.  Abra o arquivo `TelecomX_BR_Pedro.ipynb` em um ambiente como Jupyter ou Google Colab.
3.  Execute as células sequencialmente para realizar o processo de ETL, a análise exploratória e visualizar o relatório final.
