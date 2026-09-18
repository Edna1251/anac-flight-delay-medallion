## 🚀 Projeto Pipeline de Dados - Voe Bem (Arquitetura Medalhão)

Pipeline de Engenharia de Dados desenvolvido durante a Imersão de Engenharia de Dados com IA da Alura, utilizando **Databricks**, **PySpark** e **Delta Lake**. O projeto processa dados públicos do setor aéreo brasileiro disponibilizados pela ANAC.

---

## 🏗️ Arquitetura do Projeto (Medallion Architecture)

O projeto segue o padrão de mercado de arquitetura em camadas para garantir qualidade, rastabilidade e governança dos dados:

1. **Bronze (Raw):** Ingestão dos dados brutos em formato CSV (incluindo o tratamento especial para arquivos VRA com cabeçalhos personalizados da ANAC), aplicando metadados de auditoria e padronização de colunas.
2. **Silver (Refined):** Limpeza de dados, remoção de duplicatas, tratamento de espaços vazios (`trim`) e tipagem rigorosa de datas e horários utilizando funções seguras do Spark (`try_to_timestamp` e `coalesce`).
3. **Gold (Aggregated):** Criação de tabelas agregadas e visões de negócio prontas para consumo analítico e visualização em ferramentas de BI.

---

## 📂 Estrutura do Repositório

```text
├── 01_bronze.py         # Ingestão e carga dos dados brutos (VRA e Aeródromos)
├── 02_silver.py         # Limpeza, padronização e conversão de tipos
└── 03_gold.py           # Agregações de negócio e métricas de voos
