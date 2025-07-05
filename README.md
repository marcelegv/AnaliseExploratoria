# AnaliseExploratoria - README do Projeto de Análise de Dados de Vendas
Notebook desenvolvido em atendimento ao MVP da Sprint Análise de Dados de Boas práticas

Este notebook contém uma análise exploratória de dados de vendas, focada em entender padrões de compra, sazonalidade e o comportamento do consumidor.

Objetivo Geral

O objetivo principal deste projeto é extrair insights acionáveis dos dados de vendas, respondendo a perguntas-chave sobre:

    Sazonalidade das compras: Como o volume de compras e o preço médio variam ao longo do ano e dos meses?

    Perfil do consumidor: Qual a relação entre a faixa etária do consumidor e seus hábitos de compra, incluindo o ticket médio?

    Padrões de compra por gênero: Existem diferenças no comportamento de compra entre gêneros ao longo do tempo?

Estrutura do Notebook

O notebook está organizado nas seguintes seções principais:

    Configuração Inicial e Importação de Bibliotecas:

        Carrega as bibliotecas Python necessárias (pandas, matplotlib, seaborn, numpy, sklearn) e realiza as configurações básicas para visualização.

    Carregamento e Pré-processamento de Dados:

        Carrega o dataset de vendas.

        Limpeza e Tratamento Inicial:

            Conversão de Tipos: Garante que as colunas estejam nos formatos corretos (ex: 'Date' como datetime).

            Tratamento de Valores Ausentes (Imputação): Preenche dados faltantes em colunas numéricas (ex: 'Age' com a mediana) e categóricas (ex: 'Gender' com 'Não Informado') para garantir a integridade do dataset.

            Validação de Dados: Verifica e corrige inconsistências, como datas fora do período de interesse (ex: datas fora de 2023).

        Engenharia de Features (Criação de Novas Características):

            Extração de Componentes de Data: Cria novas colunas a partir da data da transação (ex: 'Dia da Semana', 'Mês', 'Dia do Mês') para capturar padrões sazonais de compra.

            Criação de Faixas Etárias: Discretiza a coluna 'Age' em 'Faixas Etárias' para análise de grupos de consumidores.

            Codificação de Variáveis Categóricas (One-Hot Encoding): Transforma variáveis textuais/categóricas (ex: 'Gender', 'Product Category', 'Dia da Semana', 'Mês', 'Dia do Mês') em um formato numérico binário compreensível pelos modelos de Machine Learning, evitando a multicolinearidade perfeita.

            Escalonamento de Features Numéricas (Padronização): Aplica o StandardScaler à coluna 'Age' para garantir que sua escala numérica não domine o processo de aprendizado do modelo, colocando-a em uma escala comum (média 0, desvio padrão 1) e facilitando a comparação com outras features. Importante: Este escalonamento é aplicado seletivamente apenas às features numéricas contínuas, preservando as features binárias resultantes do One-Hot Encoding.

        Divisão de Features e Target: Separa o dataset em variáveis preditoras (features) e a variável alvo (target: 'Total Amount' ou 'Valor Total Gasto'), preparando os dados para a modelagem futura.

        Divisão em Conjuntos de Treino e Teste: Separa os dados em conjuntos de treino e teste para avaliar a performance do modelo em dados não vistos.

    Análise de Sazonalidade e Preço Médio por Mês:

        Calcula o preço médio por unidade agrupado por mês e ano.

        Gera um gráfico de linhas para visualizar a evolução do preço médio ao longo do tempo.

    Funções Auxiliares:

        Inclui funções para formatação de eixos de data e definição de títulos/rótulos para garantir que os gráficos de tempo sejam legíveis e padronizados.

    Análise do Comportamento do Consumidor por Faixa Etária:

        Calcula o ticket médio por faixa etária e apresenta em um gráfico de barras (barplot), mostrando o valor médio para cada grupo.

        Explora a distribuição do ticket médio dentro de cada faixa etária utilizando um boxplot, permitindo a identificação de variabilidade e outliers.

        Analisa a distribuição geral do ticket médio utilizando um histograma, com indicação das frequências.

    Sazonalidade nas Compras por Gênero:

        Calcula o total de compras (ou volume de gastos) agrupado por mês e gênero.

        Gera um gráfico de linhas para visualizar a evolução dos gastos mensais para cada gênero.

    Análise de Correlação (Época da Compra vs. Faixa Etária):

        Explora visualmente a relação entre o dia do mês da compra e a faixa etária utilizando heatmaps (um para cada mês ou consolidado anualmente), para identificar padrões de comportamento ao longo do mês.

        Sugestão Futura: Poderiam ser incluídos testes estatísticos (Qui-Quadrado, Spearman) para quantificar essa correlação.

Como Executar o Notebook

    Abertura: Abra este notebook no GitHub ou em um ambiente Jupyter (Lab/Notebook/Colab).

    Ambiente: Certifique-se de estar conectado a um ambiente de execução (runtime) com as dependências instaladas.

    Execução: Execute as células sequencialmente. O notebook foi projetado para ser executado de cima para baixo.

Dependências

Este notebook requer as seguintes bibliotecas Python:

    pandas

    matplotlib

    seaborn

    numpy

    scikit-learn (para pré-processamento e escalonamento)

    scipy (para testes estatísticos, se incluídos)

Insights Chave Esperados

Ao final da análise, esperamos ter respostas para perguntas como:

    Existem meses específicos em que o ticket médio é significativamente maior ou menor?

    Qual faixa etária apresenta o maior/menor ticket médio?

    Existe uma diferença perceptível nos padrões de gastos mensais entre homens e mulheres?

    Pessoas de certas faixas etárias tendem a fazer compras em dias específicos do mês (início, meio, fim)?
