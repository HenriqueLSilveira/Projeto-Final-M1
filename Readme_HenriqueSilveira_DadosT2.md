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

📈 Resumo das Análises

Após a construção das camadas Silver e Gold, foram realizadas consultas analíticas para responder perguntas de negócio sobre as viagens oficiais do Portal da Transparência.

Cada análise foi desenvolvida utilizando consultas SQL e representada por gráficos adequados ao tipo de informação apresentada.

🥈 Camada Silver

As análises da camada Silver foram realizadas diretamente sobre os dados tratados e normalizados, permitindo explorar informações detalhadas das viagens antes da etapa de agregação.

📌 Análise 1 — Quais são os 5 órgãos com maior custo total?

Identificar quais órgãos públicos concentraram os maiores gastos com viagens oficiais durante o período analisado.
Informações obtidas:

        nome_orgao_superior	                            custo_total
	1   Ministério da Justiça e Segurança Pública	        R$ 486.933.121,65
	2   Ministério da Defesa	                            R$ 156.070.304,49
	3   Ministério da Educação	                        R$ 111.291.349,34
	4   Ministério do Meio Ambiente e Mudança do Clima	R$ 49.697.710,16
	5   Ministério da Previdência Social	                R$ 40.417.309,06

📊 Gráfico de Barras Horizontais
O gráfico de barras horizontais facilita a comparação entre categorias com nomes extensos.

---

📌 Análise 2 — Quais são os 3 destinos com maior custo médio por viagem?
Identificar os destinos que apresentam maior custo médio nas viagens realizadas.
Informações obtidas:

        destino_cidade	qtd_viagens	custo_medio
    1	Tejupá	        1	        115175.00
    2	Chavantes	    1	        114557.01
    3	Teolândia	    1	        109322.50

🍭 Gráfico de Pirulito (Lollipop Chart)
O gráfico de pirulito apresenta uma visualização limpa e objetiva

---

📌 Análise 3 — Qual foi a viagem de maior duração e seu custo total?
Identificar a viagem com maior duração registrada e analisar seu custo total.
Informações obtidas:

    id_viagem	        nome_orgao_superior	                trajeto	                            duracao_dias  valor_total
0	0000000000020699856	Ministério da Previdência Social	São Paulo → São Paulo → São Paulo	383	          0.0 


📊 Gráfico de Barra Vertical
Como apenas uma viagem é destacada, um gráfico de barra única representa o valor gasto de forma simples e objetiva, evidenciando o custo associado à viagem de maior duração.


🥇 Camada Gold

A camada Gold foi construída utilizando JOIN e GROUP BY, consolidando informações provenientes das tabelas da camada Silver para disponibilizar indicadores voltados à tomada de decisão.
Foram criadas tabelas agregadas contendo métricas consolidadas de viagens, pagamentos e trechos, simplificando as consultas analíticas.

📌 Análise 1 — Qual o tipo de pagamento possui maior valor médio?
Identificar qual modalidade de pagamento apresenta o maior valor médio entre todas as viagens registradas.
Informações obtidas:

        tipo_pagamento	            valor_medio
    1	PASSAGEM	                2176.967143
    2	DIÁRIAS	                    2060.436286
    3	Serviço correlato: seguro	479.089429



📊 Gráfico de Barras Horizontais
O gráfico permite comparar facilmente as médias entre as diferentes categorias de pagamento, destacando aquela com maior valor médio.

---

Análise 2 — Qual o meio de transporte mais utilizado nos trechos?
Identificar qual meio de transporte foi utilizado com maior frequência nas viagens oficiais.
Informações obtidas:

    meio_transporte	    total
1	Veículo Oficial	    386424.0
2	Aéreo	            232666.0
3	Rodoviário	        64970.0

🍩 Gráfico de Rosca (Donut Chart)
O gráfico de rosca evidencia a participação percentual de cada categoria em relação ao total de trechos, permitindo identificar rapidamente o meio de transporte predominante.

---

📌 Análise 3 — Qual UF de destino aparece em mais trechos?
Identificar quais estados brasileiros aparecem com maior frequência como destino das viagens oficiais
Informações obtidas:

    destino_uf	        total
0	São Paulo	        82722.0
1	Distrito Federal	79962.0
2	Minas Gerais	    50965.0

🍭 Gráfico de Pirulito (Lollipop Chart)
O gráfico de pirulito proporciona uma comparação clara entre as quantidades de trechos por estado.




                     