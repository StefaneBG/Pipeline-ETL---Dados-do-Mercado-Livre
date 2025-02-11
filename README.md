# Pipeline ETL - Dados do Mercado Livre

## Descrição do Projeto

Este projeto consiste em um pipeline ETL (Extração, Transformação e Carga) completo que realiza as seguintes tarefas:
1. Extrai dados da API pública do Mercado Livre com base em um termo de busca específico.
2. Armazena os resultados em um DataFrame do Pandas.
3. Realiza transformações nos dados, como renomear colunas, alterar tipos de dados, remover valores nulos e criar novas colunas.
4. Salva os dados transformados em um arquivo CSV.
5. Envia o arquivo CSV para um bucket no Google Cloud Storage (GCS) chamado `mercadolivre_seunome`.
6. Converte o arquivo CSV em coleções e os envia para o MongoDB Atlas.
7. Cria um banco de dados SQL chamado `mercado` e o abastece com os dados do arquivo CSV.
8. Conecta o Cloud SQL ao BigQuery para enviar os dados do banco `mercado` para um conjunto de dados chamado `mercado_livre` no BigQuery.
9. Envia os arquivos CSV diretamente para outro conjunto de dados no BigQuery chamado `mercado2`.
10. Conecta os dados do conjunto `mercado_livre` no BigQuery a um relatório no Looker Studio.

## Ferramentas Utilizadas

- **API do Mercado Livre**: Para extração dos dados de produtos.
- **Python**: Linguagem principal para o pipeline ETL.
- **Pandas**: Para manipulação e transformação dos dados.
- **Google Cloud Platform (GCP)**:
  - **Google Cloud Storage (GCS)**: Para armazenamento dos arquivos CSV.
  - **Cloud SQL**: Para criação e gerenciamento do banco de dados SQL.
  - **BigQuery**: Para armazenamento e análise de dados em larga escala.
- **MongoDB Atlas**: Para armazenamento dos dados em formato de coleções.
- **Looker Studio**: Para criação de relatórios e visualizações interativas.

## Passos do Pipeline ETL

### 1. Extração dos Dados
- Utilização da API do Mercado Livre para buscar produtos com base em um termo específico.
- Os dados são armazenados em um DataFrame do Pandas.

### 2. Transformação dos Dados
- Renomeação de colunas para padronização.
- Alteração de tipos de dados (ex.: strings para números).
- Remoção de valores nulos ou inconsistentes.
- Criação de novas colunas, se necessário (ex.: cálculo de preços com desconto).

### 3. Armazenamento em CSV
- Os dados transformados são salvos em um arquivo CSV.

### 4. Envio para o Google Cloud Storage (GCS)
- O arquivo CSV é enviado para um bucket no GCS chamado `mercadolivre_seunome`.

### 5. Envio para o MongoDB Atlas
- O arquivo CSV é convertido em coleções e enviado para o MongoDB Atlas.

### 6. Criação do Banco de Dados SQL
- Um banco de dados chamado `mercado` é criado no Cloud SQL.
- Os dados do arquivo CSV são inseridos no banco de dados.

### 7. Conexão do Cloud SQL ao BigQuery
- Os dados do banco `mercado` são enviados para um conjunto de dados chamado `mercado_livre` no BigQuery.

### 8. Envio Direto para o BigQuery
- O arquivo CSV é enviado diretamente para outro conjunto de dados no BigQuery chamado `mercado2`.

### 9. Criação de Relatórios no Looker Studio
- Os dados do conjunto `mercado_livre` no BigQuery são conectados ao Looker Studio para criação de relatórios e visualizações.

## Instruções para Reprodução

### Pré-requisitos
- **Google Cloud Platform (GCP)**: Conta ativa com acesso ao GCS, Cloud SQL e BigQuery.
- **MongoDB Atlas**: Conta ativa e cluster configurado.
- **Python 3.x**: Para execução do pipeline.
- Bibliotecas Python: pandas, requests, google-cloud-storage, pymongo, sqlalchemy, google-cloud-bigquery.
