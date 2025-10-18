# Projeto 02 – Arte dos Dados  
**Autor:** Juan Pablo Moreno Oliveira  
**Tema:** Trabalho 02 - Instituto Arte dos Dados Turma 02
---

## Visão Geral

Este projeto tem como objetivo aplicar práticas de **engenharia de dados** e **análise exploratória (EDA)** em um conjunto de dados que descreve características de motoristas e veículos, considerando variáveis como:
- **Anos de prática**
- **Número de acidentes anteriores**
- **Quilometragem anual**
- **Data de Fabricação do veículo**

O trabalho busca compreender **relações, tendências e inferências mais amplas** que ajudem a descrever perfis de risco, padrões de direçionamento do mercado e fatores relacionados à experiência e comportamento dos condutores e do mercado de seguros automotivos. Todo o material usado nesse projeto pode ser encontrado no GitHub MathMachado/DSWP e o livro 'Estatística Prática para Cientístas de Dados' - Peter & Andrew Bruce (2019), ou nas salas de aula da Universidade Federal do ABC.

**Leia o arquivo HTML para melhor vizualização!**
---

## Arquitetura do Projeto (Medallion Architecture)

A estrutura segue o padrão **Medallion Architecture**, dividida em três camadas principais:

| Camada | Descrição | Principais Tarefas |
|:-------|:-----------|:------------------|
| 🟤 **Bronze** | Dados brutos, sem tratamento. | Ingestão dos dados originais. |
| ⚪ **Silver** | Dados limpos e padronizados. | - Tratamento de valores ausentes (mediana)<br>- Conversão de tipos<br>- Tratamento de variáveis categóricas<br>- Tratamento de outliers |
| 🟡 **Gold** | Dados prontos para análise e modelagem. | - Análises estatísticas e visuais<br>- Geração de insights e inferências<br>- Preparação para relatórios finais |
---
## Estrutura de Diretórios

```bash
Projeto_02_ADD/
│
├── DataLake/
│   ├── bronze/        # Dados originais
│   ├── silver/        # Dados tratados e normalizados
│   └── gold/          # Dados prontos para análise e visualização
│
├── Projeto_02_ADDipynb       # Notebook principal do projeto
│  
│
└── README.md                 # Esse carinha aqui
````
---

## Etapas do Processo

### 1. Ingestão dos Dados

Os dados são carregados a partir de repositório Git (`MathMachado/DSWP`) para garantir reprodutibilidade.

### 2. Tratamento de Dados

* **Valores ausentes:** deveriam ser substituídos pela **mediana** de cada variável numérica, contudo não foram encontrados.
* **Outliers:** identificados via **Z-score**, com limiar de 2.6.

  * Em colunas sem outliers, o limiar foi mantido.
  * Casos discrepantes relevantes foram analisados individualmente.

### 3. Tipos de Dados

* `int64` e `float64`: variáveis numéricas contínuas e discretas.
* Conversões realizadas conforme a necessidade da análise e padronização.

### 4. Análise Exploratória (EDA)

Foram realizadas análises estatísticas e gráficas, incluindo:

* Distribuição de variáveis contínuas;
* Relações entre experiência e acidentes;
* Dispersão;
* Correlações lineares e interpretações contextuais.

---

## Tecnologias Utilizadas

* **Python 3.x**
* **DataBricks**
* **Pandas**, **NumPy**
* **Matplotlib**, **Seaborn**
* **Scikit-learn** 

---

## Como Executar o Projeto

1. **Clonar o repositório:**

   ```bash
   git clone https://github.com/JuflN/projeto-02-arte-dos-dados.git
   ```
2. **Abrir o notebook** no Google Colab:

   ```
   /Projeto_02_ADD.ipynb
   ```
3. **Executar as células** na sequência, garantindo que:

   * O dataset esteja disponível em `data/bronze/`;
   * Os diretórios `silver` e `gold` sejam criados automaticamente ou manualmente antes da execução.

---

## Licença

Este projeto tem fins educacionais e pode ser utilizado para fins de aprendizado, estudo e aprimoramento de práticas de engenharia e ciência de dados.

```

