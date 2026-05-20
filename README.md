# powerbi-modelagem-dax

Este projeto foi desenvolvido com foco na modelagem de dados e criação de cálculos utilizando DAX no Power BI.

O objetivo principal é transformar dados brutos em informações analíticas através da construção de modelos relacionais, medidas DAX e dashboards interativos, aplicando conceitos fundamentais de Business Intelligence.

Durante o desenvolvimento foram utilizadas técnicas de transformação de dados, modelagem dimensional, criação de métricas e construção de análises dinâmicas.

Objetivos do Projeto
Objetivo Geral

Aplicar técnicas de modelagem e transformação de dados utilizando DAX no Power BI.

Objetivos Específicos
Importar e transformar dados;
Criar modelos relacionais;
Desenvolver medidas DAX;
Criar colunas calculadas;
Trabalhar com KPIs;
Construir dashboards interativos;
Aplicar boas práticas em Business Intelligence.
Tecnologias Utilizadas
Power BI Desktop
Power Query
DAX
Modelagem Dimensional
SQL
GitHub

Desenvolvimento do Projeto
1. Importação dos Dados

Os dados foram importados para o Power BI através de arquivos CSV.

Bases utilizadas
Clientes;
Produtos;
Vendas;
Calendário.

2. Transformação dos Dados no Power Query

Foram realizadas transformações para padronizar e organizar os dados.

Transformações aplicadas
Alteração de tipos de dados;
Remoção de duplicidades;
Tratamento de valores nulos;
Renomeação de colunas;
Criação de colunas condicionais;
Mesclagem de tabelas.

3. Modelagem Relacional

Foi criado um modelo dimensional com relacionamentos entre tabelas.

Estrutura criada
Tabela	Tipo
Fato_Vendas	Fato
Dim_Clientes	Dimensão
Dim_Produtos	Dimensão
Dim_Calendario	Dimensão
Relacionamentos
Origem	Destino	Tipo
Fato_Vendas	Dim_Clientes	Muitos para Um
Fato_Vendas	Dim_Produtos	Muitos para Um
Fato_Vendas	Dim_Calendario	Muitos para Um

4. Criação de Medidas DAX

Foram desenvolvidas medidas analíticas utilizando DAX.

Total de Vendas
Total Vendas = SUM(Fato_Vendas[Valor_Venda])
Total de Lucro
Total Lucro = SUM(Fato_Vendas[Lucro])
Quantidade Vendida
Qtd Vendida = SUM(Fato_Vendas[Quantidade])
Ticket Médio
Ticket Medio =
DIVIDE(
    [Total Vendas],
    COUNT(Fato_Vendas[ID_Venda]),
    0
)
Margem de Lucro
Margem Lucro =
DIVIDE(
    [Total Lucro],
    [Total Vendas],
    0
)
Crescimento de Vendas
Crescimento Vendas =
VAR VendasAtual = [Total Vendas]
VAR VendasAnterior =
    CALCULATE(
        [Total Vendas],
        PREVIOUSMONTH(Dim_Calendario[Data])
    )
RETURN
DIVIDE(
    VendasAtual - VendasAnterior,
    VendasAnterior,
    0
)
5
. Colunas Calculadas

Também foram criadas colunas calculadas.

Exemplo
Ano = YEAR(Fato_Vendas[Data_Venda])

6. Criação dos Dashboards

Foram desenvolvidos dashboards interativos para análise dos dados.

Indicadores Utilizados
Total de vendas;
Total de lucro;
Ticket médio;
Margem de lucro;
Crescimento mensal.
Visuais Criados
Gráfico de barras;
Gráfico de linhas;
Cartões KPI;
Tabelas;
Segmentadores;
Dashboard interativo.
Recursos Interativos
Segmentadores

Filtros dinâmicos por:

Ano;
Produto;
Cliente;
Região.
Tooltips

Informações adicionais ao passar o mouse nos gráficos.

Drill Through

Navegação detalhada entre páginas.

Boas Práticas Aplicadas
Padronização de nomenclaturas;
Organização do modelo de dados;
Uso correto de medidas e colunas;
Separação entre fato e dimensão;
Layout organizado;
Utilização de DAX otimizado.
Aprendizados Obtidos

Durante o desenvolvimento deste projeto foi possível aprender:

Modelagem dimensional;
Transformação de dados;
Criação de medidas DAX;
Construção de dashboards interativos;
Uso do Power Query;
Criação de KPIs;
Boas práticas de Business Intelligence.

Conclusão

O projeto permitiu aplicar conceitos fundamentais de modelagem de dados e desenvolvimento de cálculos analíticos utilizando DAX no Power BI.

Além da criação das medidas e dashboards, foi possível estruturar um modelo dimensional eficiente e preparado para análises de Business Intelligence.
