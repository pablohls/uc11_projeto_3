# Otimização de Orçamento para Rastreamento de Doenças Cardíacas

Este projeto utiliza Otimização Linear para determinar a alocação mais eficiente de um orçamento de saúde pública destinado ao rastreamento (exames) de doenças cardíacas. O objetivo é maximizar o número de casos positivos detectados, focando os recursos nos grupos de pacientes (segmentos) com maior probabilidade de apresentar a doença.

## 📌 Metodologia

O problema foi modelado como um problema de alocação de recursos e resolvido com as seguintes ferramentas e técnicas:

Linguagem: Python 3

Bibliotecas Principais:

pandas para manipulação e análise de dados.

pulp para modelagem e solução do problema de otimização linear.

Técnica: Otimização Linear para maximizar uma função objetivo sujeita a restrições.

## 📂 Funcionalidades do Script

O código é dividido em três classes principais:

O script analise_cenarios.py realiza as seguintes tarefas:

Carrega e Prepara os Dados: Utiliza um dataset (atualmente mockado no código para demonstração) de pacientes para análise.

Segmenta os Pacientes: Agrupa os pacientes em perfis de risco com base em características como sexo e tipo de dor torácica.

Calcula Probabilidades: Determina a probabilidade histórica de doença para cada segmento.

Executa Análise de Cenários: Roda o modelo de otimização para diferentes níveis de orçamento definidos em uma lista.

Gera um Relatório Detalhado: Para cada cenário, exibe no console a alocação ótima de exames por segmento.

Exporta os Resultados: Salva um arquivo analise_de_cenarios_orcamento_detalhado.csv com um resumo dos resultados de todos os cenários.

---

## 🚀 Como Executar o Código no Google Colab

Você pode rodar este projeto facilmente sem precisar instalar nada em seu computador, usando o Google Colab.

1. **Acessar o Google Colab**: Abra seu navegador e acesse https://colab.research.google.com/.
2. **Criar um Novo Notebook**: No menu, clique em Arquivo > Novo notebook.
3. **Instalar a Biblioteca pulp**: Antes de rodar o código principal, você precisa instalar a biblioteca de otimização. Adicione uma nova célula de código no topo do seu notebook, insira o comando abaixo e execute-a.

```bash
!pip install pulp
```

4. **Executar o Script de Análise**: Copie todo o conteúdo do arquivo Python, cole na célula seguinte do seu notebook e execute-a. O script irá realizar todos os cálculos e exibir os resultados no console.
5. **Baixar o Arquivo CSV Gerado**: Após a execução, o arquivo analise_de_cenarios_orcamento_detalhado.csv será criado no ambiente do Colab. Para baixá-lo, clique no ícone de pasta na barra lateral esquerda, clique com o botão direito sobre o nome do arquivo e escolha a opção Fazer o download.

## 🔧 Estrutura do Arquivo de Saída

O arquivo analise_de_cenarios_orcamento_detalhado.csv contém as seguintes colunas:

| Parâmetro         | Descrição |
|-------------------|-----------|
| `orcamento_disponivel` | O valor do orçamento para aquele cenário. |
| `custo_total_gasto`  | O custo real que o modelo propõe gastar, respeitando o orçamento. |
| `total_pacientes_examinados`  | O número total de pessoas que devem ser examinadas. |
| `casos_detectados_esperados`  | A projeção de casos positivos a serem encontrados com a alocação ótima. |
| `detalhes_alocacao`  | Uma descrição textual de como os exames devem ser distribuídos. |