Otimização de Orçamento para Rastreamento de Doenças Cardíacas
1. Visão Geral do Projeto
Este projeto utiliza Otimização Linear para determinar a alocação mais eficiente de um orçamento de saúde pública destinado ao rastreamento (exames) de doenças cardíacas. O objetivo é maximizar o número de casos positivos detectados, focando os recursos nos grupos de pacientes (segmentos) com maior probabilidade de apresentar a doença.

O script foi desenvolvido como parte da Atividade Prática 3, aplicando técnicas de otimização prescritiva a um problema de negócio do mundo real.

2. Metodologia
O problema foi modelado como um problema de alocação de recursos e resolvido com as seguintes ferramentas e técnicas:

Linguagem: Python 3

Bibliotecas Principais:

pandas para manipulação e análise de dados.

pulp para modelagem e solução do problema de otimização linear.

Técnica: Otimização Linear para maximizar uma função objetivo sujeita a restrições.

3. Funcionalidades do Script
O script analise_cenarios.py realiza as seguintes tarefas:

Carrega e Prepara os Dados: Utiliza um dataset (atualmente mockado no código para demonstração) de pacientes para análise.

Segmenta os Pacientes: Agrupa os pacientes em perfis de risco com base em características como sexo e tipo de dor torácica.

Calcula Probabilidades: Determina a probabilidade histórica de doença para cada segmento.

Executa Análise de Cenários: Roda o modelo de otimização para diferentes níveis de orçamento definidos em uma lista.

Gera um Relatório Detalhado: Para cada cenário, exibe no console a alocação ótima de exames por segmento.

Exporta os Resultados: Salva um arquivo analise_de_cenarios_orcamento_detalhado.csv com um resumo dos resultados de todos os cenários, incluindo a alocação detalhada.

4. Como Executar o Código no Google Colab
Você pode rodar este projeto facilmente sem precisar instalar nada em seu computador, usando o Google Colab.

Passo 1: Acessar o Google Colab

Abra seu navegador e acesse https://colab.research.google.com/.

Passo 2: Criar um Novo Notebook

No menu, clique em Arquivo > Novo notebook.

Passo 3: Copiar o Código

Copie todo o conteúdo do arquivo Python e cole na célula do notebook do Colab.

Passo 4: Instalar a Biblioteca pulp

Antes de rodar o código principal, você precisa instalar a biblioteca de otimização. Adicione uma nova célula de código no topo do seu notebook, insira o comando abaixo e execute-a (clicando no ícone de "play" ou usando Shift+Enter).

!pip install pulp

Passo 5: Executar o Script de Análise

Agora, execute a célula principal que contém o código do projeto. O script irá rodar, realizar todos os cálculos e exibir os resultados no console.

Passo 6: Baixar o Arquivo CSV Gerado

Após a execução, o arquivo analise_de_cenarios_orcamento_detalhado.csv será criado no ambiente do Colab.

Para baixá-lo, clique no ícone de pasta na barra lateral esquerda.

Você verá o arquivo na lista. Clique com o botão direito sobre ele e escolha a opção Fazer o download.

5. Estrutura do Arquivo de Saída
O arquivo analise_de_cenarios_orcamento_detalhado.csv contém as seguintes colunas:

orcamento_disponivel: O valor do orçamento para aquele cenário.

custo_total_gasto: O custo real que o modelo propõe gastar, respeitando o orçamento.

total_pacientes_examinados: O número total de pessoas que devem ser examinadas.

casos_detectados_esperados: A projeção de casos positivos a serem encontrados com a alocação ótima.

detalhes_alocacao: Uma descrição textual de como os exames devem ser distribuídos entre os diferentes segmentos de pacientes.