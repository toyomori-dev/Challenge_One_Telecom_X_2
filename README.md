# Challenge_One_Telecom_X_2
Challenge Telecom X: Análise Preditiva de evasão de clientes - Parte 2

# Análise de Evasão de Clientes - Telecom X

Este projeto tem como objetivo analisar os dados de clientes da empresa Telecom X para identificar os principais fatores que influenciam o cancelamento de serviços, também conhecido como churn. A análise exploratória de dados (EDA) foi realizada utilizando Python e suas bibliotecas, como pandas, matplotlib e seaborn.

## O Problema

A Telecom X está enfrentando um alto índice de cancelamentos de clientes. Para combater esse problema, a equipe de Data Science precisa entender o comportamento dos clientes que decidem sair, a fim de criar estratégias de retenção eficazes e, futuramente, desenvolver modelos preditivos.

## Dados

O conjunto de dados, em formato JSON, foi obtido a partir de uma API da Telecom X. Ele contém informações sobre:
- Dados demográficos dos clientes (`Gênero`, `Idoso`, `Possui_Companheiro`, `Possui_Dependentes`).
- Informações contratuais e de serviço (`Meses_de_Contrato`, `Telefone_Ativo`, `Multiplas_Linhas`, `Tipo_Internet`, `Tipo_Contrato`).
- Informações sobre o consumo e a conta (`Valor_Mensal`, `Valor_Total`, `Fatura_Digital`, `Forma_Pagamento`).
- O status de evasão do cliente (`Cancelamento`).

## Passos Realizados

1.  **Extração**: Os dados foram extraídos do JSON e carregados em um DataFrame do pandas.
2.  **Transformação e Limpeza**:
    -   As colunas aninhadas no JSON foram normalizadas para criar uma estrutura de dados plana.
    -   As colunas foram renomeadas para o português para facilitar a análise.
    -   Valores nulos na coluna `Valor_Total` foram removidos, pois correspondiam a clientes com pouco tempo de contrato.
    -   Valores vazios na coluna `Cancelamento` foram substituídos por "Não informado" para uma análise mais precisa.
    -   Uma nova variável, `Conta_Diarias`, foi criada para oferecer uma visão detalhada do gasto diário do cliente.
3.  **Análise e Visualização**:
    -   Foi realizada uma análise descritiva das variáveis numéricas (`Meses_de_Contrato`, `Valor_Mensal`, `Valor_Total`, `Conta_Diarias`).
    -   Gráficos de barra e histogramas foram gerados para visualizar a distribuição da evasão em relação a cada variável.
    -   Uma matriz de correlação foi criada para entender a relação entre as variáveis numéricas e o status de cancelamento.

## Principais Insights

-   **Distribuição Geral do Churn**: Cerca de 25,8% dos clientes da Telecom X cancelaram seus serviços.
-   **Variáveis Categóricas e Churn**:
    -   Clientes com contrato mensal têm alta taxa de cancelamento.
    -   Formas de pagamento como "Electronic Check" e o tipo de internet 'Fiber Optic' estão mais associadas à evasão.
    -   Clientes que não possuem serviços extras tendem a sair com mais frequência.
-   **Variáveis Numéricas e Churn**:
    -   Clientes recém-chegados apresentam cancelamento elevado.
    -   O cancelamento é mais comum na faixa de valor entre R$70,00 e R$100,00.
-   **Correlação**:
    -   A correlação entre `Meses_de_Contrato` e `Cancelamento_Num` é negativa (-0.35), indicando que, quanto mais tempo o cliente permanece na empresa, menor a probabilidade de ele cancelar.
    -   A correlação entre `Valor_Mensal` e `Cancelamento_Num` é positiva (0.19), mostrando que um gasto mensal maior pode estar relacionado a uma maior taxa de churn.

## Recomendações Estratégicas

Com base nos insights obtidos, as seguintes ações são recomendadas para a Telecom X:

1.  **Incentivar contratos de longo prazo**: Criar programas de fidelidade, oferecer descontos progressivos ou benefícios exclusivos para clientes que optam por assinaturas anuais.
2.  **Ampliar o valor dos serviços adicionais**: Estimular a adesão a pacotes como suporte técnico premium, segurança online ou benefícios exclusivos para quem utiliza mais serviços da empresa.
3.  **Revisar métodos de pagamento**: Reduzir a dependência do electronic check, promovendo opções mais convenientes como débito automático, cartão de crédito ou PIX, para facilitar transações e reduzir cancelamentos.
4.  **Aprimorar o suporte nos primeiros meses**: Implementar uma jornada de boas-vindas personalizada, com contato proativo, ofertas especiais e suporte dedicado para os novos clientes.
