# Análise de Dados do Projeto Final Modulo 1 - 

Este repositório contém a analise de dados do projeto final do módulo 1, seguindo a arquitetura Medallion, preservando o histórico original, limpando a estrutura e transformando os dados brutos em métricas e gráficos claros, respondendo as perguntas de negócio
propostas no desafio.

## Identificação
* **Aluna:** Henrique Luan da Silveira
* **Turma:** Análise de Dados T2
* **Base de dados:** Viagens a Serviço do Portal da Transparência do Governo Federal

---

## 📁 Estrutura do repositório

O projeto está organizado da seguinte forma:

* `data/`: Contém a base de dados utilizada na análise.
* `scripts/`: Arquivos para realização das etapas das camadas RAW / SILVER E GOLD
* `sql/`: Arquivo com script de criação do banco de dados
* `README_HenriqueSilveira_DadosT2.md`: Descrição e instruções para execução do projeto (este arquivo).

---
## Dependências

Antes de começar, certifique-se de ter o Python instalado em sua máquina, o MYSQL e as dependências para execução do projeto

### Dependências principais:
* Python 3.x
* Pandas
* Numpy
* Matplotlib
* Gdown
* Zipfile
* MySql
---

## Executando o Projeto

1. Abra a pasta do projeto no *VS Code*.
2. Abra o terminal e instale todas dependências necessárias.
3. Configure o arquivo `.env` conforme as informações de conexão do seu banco de dados.
4. O script pode fazer o download da base de dados do google drive ou utilizar o arquivo já disponibilizado na pasta `data`

Para testar o download, siga as instruções abaixo:

    * Faça upload do arquivo "viagens.zip", da pasta `data` em uma conta do google drive.
    * Exclua ou recorte o arquivo da pasta `data` para deixar o script realizar o download   
    * Abra o caminho do arquivo no drive
    * Clique em Mais Ações (ALT+A)
    * Clique em Copiar Link
    * Copie SOMENTE a parte do link copiado inidicada abaixo:
      https://drive.google.com/file/d/ `1bT2jlF1_70lV9ixDwTgxc-_bIqW17L_T` view?usp=drive_link
    * Abra o arquivo `config.py` , na linha `56` em `DRIVE_FILE_ID` e COLE o ID do arquivo do seu google drive  

Para rodar sem baixar, siga para o próximo passo.

5. Abra a pasta `sql/` e abra o arquivo `sql/0_criar_banco.sql`.
6. Execute as instruções contidas no arquivo.
7. Acesse a pasta `scripts/` e execute os arquivos:

    * 1.extrair.py  	- Referente camada RAW
    * 2_transformar.py  - Referente camada SILVER
    * 3_analise.ipynb   - Referente camada GOLD


## ANÁLISES OS INSIGHTS OBTIDOS:

Perguntas de negócio respondidas e respectivas camadas:

| Camada     | Pergunta                                  | Gráfico                     
| ---------- | ----------------------------------------- | ----------------------------
| **Silver** | Top 5 órgãos com maior custo total        | 📊 Barras horizontais       
| **Silver** | UF de destino com maior número de trechos | 🍩 Gráfico de rosca         
| **Silver** | Meio de transporte mais utilizado         | 📊 Barras verticais         
| **Gold**   | Top 3 destinos com maior custo médio      | 📊                          
| **Gold**   | Relação entre duração e custo das viagens | 📈                          
| **Gold**   | Tipo de pagamento com maior valor médio   | 📊     



- 💡 Insight: 

- 💡 Insight: 

- 💡 Insight: 

- 💡 Insight: 

- 💡 Insight: 

- 💡 Insight: 

- 💡 Insight: 


                     