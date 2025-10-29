# 🧠 PSA Data Test — Engenharia de Dados  

> “É melhor entregar algo simples que funciona do que algo complexo pela metade.”  

## 🎯 Objetivo do Projeto  
Este projeto foi desenvolvido como parte de um teste técnico para Engenheiro(a) de Dados, com o objetivo de demonstrar habilidades em:

- Construção de **pipelines de ingestão** com **Python e Databricks**  
- Estruturação de um **Data Lake no BigQuery (GCP)**  
- Criação de camadas **Bronze, Silver e Gold**  
- Aplicação de **boas práticas de ETL/ELT, otimização e governança de dados**  
- Integração entre **Databricks e Google BigQuery**  

---

## 📁 Estrutura do Projeto  

teste-engenheiro-dados/
│
├── dados/
│ ├── dados_clientes.csv
│ ├── notas_fiscais.xml
│ ├── analises_tributarias.txt
│ ├── tarefas_projetos.json
│ └── logs_sistema.html
│
├── scripts/
│ ├── pipeline_ingestao.py # Ingestão dos arquivos para o BigQuery via API
│ ├── pipeline_databricks_notebook # Notebook Databricks com origem em Delta Lake
│ ├── data_quality.py # Checagens de qualidade de dados
│ └── requirements.txt # Dependências do projeto
│
├── sql/
│ ├── arquitetura_camadas.sql # DDL e DML das camadas Bronze/Silver/Gold
│ └── queries_otimizadas.sql # Consultas otimizadas e exemplos
│
├── docs/
│ ├── README.md
│ ├── dicionario_dados.md
│ ├── otimizacoes.md
│ └── diagrama_arquitetura.png
│
└── psa-data-test/ # Projeto configurado no BigQuery


---

## ⚙️ Tecnologias Utilizadas  

- **Python 3.8+**  
- **Databricks Community Edition**  
- **Google BigQuery (Sandbox gratuito)**  
- **Delta Lake (camadas Bronze, Silver e Gold)**  
- **Bibliotecas principais:**  
  - `pandas`  
  - `google-cloud-bigquery`  
  - `xmltodict`  
  - `beautifulsoup4`  
  - `json`  
  - `pyspark`  
  - `delta-spark`  
  - `logging`  

---

## 🚀 Execução do Projeto  

### 1️⃣ Configuração do ambiente local  
```bash
python -m venv venv
source venv/bin/activate     # Linux/Mac
venv\Scripts\activate        # Windows
pip install -r scripts/requirements.txt
2️⃣ BigQuery Sandbox

Acesse o BigQuery Sandbox

Crie o projeto: psa-data-test

Crie os datasets: psa_raw, psa_curated, psa_analytics

3️⃣ Pipeline no Python
python scripts/pipeline_ingestao.py


✅ Lê e transforma os 5 arquivos originais (CSV, XML, TXT, JSON, HTML)
✅ Faz parsing com xmltodict e BeautifulSoup
✅ Carrega os dados brutos na camada Bronze (BigQuery)

4️⃣ Pipeline no Databricks (Delta Lake)

Executado no Databricks Community Edition, o notebook pipeline_databricks_notebook realiza:

Ingestão da camada Bronze;

Limpeza e padronização (camada Silver);

Criação das tabelas de análise (camada Gold) no formato Delta;

Escrita final para o BigQuery via conector spark-bigquery.

🧱 Arquitetura do Data Lake
Camada	Ambiente	Descrição	Exemplo
Bronze	Python / Databricks	Dados brutos no formato original	psa_raw.clientes
Silver	Databricks (Delta)	Dados limpos e padronizados	psa_curated.notas_fiscais
Gold	BigQuery	Dados analíticos e agregados	psa_analytics.resumo_clientes_tributos

📊 O diagrama da arquitetura está disponível em:
docs/diagrama_arquitetura.png

⚡ Otimização e Performance

Arquivo: docs/otimizacoes.md

Principais técnicas aplicadas:

Particionamento por data_emissao no BigQuery

Clustering por cliente_id

Desnormalização controlada em visões analíticas

Conversão de CSV → Delta format (armazenamento colunar otimizado)

🔍 Qualidade e Governança

Arquivo: scripts/data_quality.py

Validações implementadas:

Campos obrigatórios não nulos

Formatos válidos (CNPJ, datas ISO)

Duplicatas removidas

Metadados e dicionário de dados (docs/dicionario_dados.md)

📚 Próximos Passos

Orquestração com Apache Airflow (DAG de ingestão)

Integração de Workflows Databricks

CI/CD com GitHub Actions

Monitoramento com Data Catalog e Lineage

Uso de Delta Live Tables

👩‍💻 Autora

Kálita Ribeiro Mariano
💼  Engenheira de Dados 
📍 Cuiabá - MT, Brasil
📧 kalitamariano07@gmail.com

🔗 linkedin.com/in/kálitamariano

