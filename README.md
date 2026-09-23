## Mercado de Trabalho e Economia Popular no Brasil
Análises estatísticas e produção de tabelas a partir dos microdados da PNAD Contínua, com foco em indicadores relacionados à Economia Popular no Brasil.

## 👤 Autor
- **Vinicius**
- Data do projeto: **2025-06-14**

---

## 📘 Descrição Geral
Este projeto utiliza R e o pacote **PNADcIBGE** para:
- Ler e rotular microdados da **Pesquisa Nacional por Amostra de Domicílios Contínua (PNAD Contínua)**.
- Criar variáveis derivadas relacionadas ao mercado de trabalho e economia popular.
- Aplicar pesos amostrais usando o pacote **survey**.
- Gerar tabelas estatísticas ponderadas.
- Exportar resultados consolidados em múltiplos ficheiros Excel.

O documento principal é um arquivo **R Markdown (.Rmd)** que descreve toda a metodologia aplicada.

---

## 📂 Fonte dos Microdados
Os microdados da PNAD Contínua podem ser baixados no portal do IBGE:

https://www.ibge.gov.br/estatisticas/sociais/saude/9173-pesquisa-nacional-por-amostra-de-domicilios-continua-trimestral.html?=&t=microdados

---

## 🧰 Bibliotecas utilizadas
Os principais pacotes utilizados são:

- `dplyr`, `tidyverse` — Manipulação e transformação de dados  
- `readr`, `readxl`, `openxlsx`, `writexl` — Importação e exportação de dados  
- `PNADcIBGE` — Leitura e rotulagem dos microdados da PNAD  
- `survey` — Análise estatística com pesos amostrais  
- `data.table` — Manipulação de dados em alta performance  
- `stringr` — Manipulação de texto  

---

## 📁 Estrutura do Script
O script realiza as seguintes etapas:

### **1. Importação e preparação dos microdados**
- Leitura dos ficheiros TXT e dicionários do IBGE  
- Aplicação de rótulos  
- Seleção das variáveis relevantes  
- Conversão para `data.table`  
- Criação de variáveis derivadas (ECO, CBO2, Conta_própria, ID, Faixa, Posicao, Informal, entre outras)

### **2. Mesclagem com dicionário de ocupações**
- Junção da variável `V4010` com descrições de cargos

### **3. Definição do design amostral**
- Estruturação do objeto `surveydesign` com pesos da PNAD (V1028)

### **4. Criação de tabelas ponderadas**
O projeto cria:
- Tabelas históricas  
- Tabelas de variáveis originais  
- Tabelas específicas da Economia Popular  
- Tabelas de médias de renda (função `resumo_stats`)  

### **5. Exportação**
Os resultados são exportados em múltiplos ficheiros `.xlsx`, com abas temáticas:

- `3T25.xlsx`  
- `PNAD_Resumo2.xlsx`  
- `PNAD_Resumo3.xlsx`  
- `PNAD_Resumo4.xlsx`  

---

## ▶️ Como executar o projeto

1. Instale os pacotes necessários:

```r
install.packages(c("tidyverse","PNADcIBGE","survey","data.table","readxl","writexl","openxlsx"))
