Loja Perfeita — Power BI

Painel de execução em loja para operações de trade marketing / merchandising. Transforma as visitas de campo em uma nota de 0 a 10 por loja, quebrada em pilares, comparada com metas e classificada em faixas — do resumo executivo até o detalhe de cada loja.

Os dados são 100% sintéticos. Lojas, pessoas, SKUs e resultados foram gerados para este projeto e não representam nenhuma empresa real. O modelo é genérico e pode ser aplicado a qualquer operação de varejo com a mesma finalidade.

O que o painel responde
Qual é a nota geral da operação no período e como ela se compara com a meta?
Quais pilares puxam a nota para cima ou para baixo?
Quantas lojas estão em cada faixa de nota (excelente → crítica)?
Qual a cobertura de visitas (planejado × realizado)?
Para uma loja específica: quem é o supervisor e o promotor, quando foi a última coleta, quais SKUs estão ausentes e como está o planograma?
Como a nota é calculada

Cada visita avalia 5 pilares. O peso de cada pilar soma 10, então a nota da visita já sai na escala de 0 a 10:

Pilar	Peso	O que mede
Sortimento	5,0	Presença dos SKUs esperados na loja
Ponto extra	2,0	Pontos de exposição adicionais
Planograma	1,5	Aderência ao planograma
MPDV	1,0	Material de ponto de venda
Preço	0,5	Conformidade de preço

Nota da visita = soma de (% atingido do pilar × peso do pilar). Nota do período = média das visitas com coleta completa no período selecionado.

Faixas de classificação: 9–10 · 7–9 · 5–7 · 3–5 · abaixo de 3. Semáforo de metas: verde a partir de 100 % da meta, amarelo a partir de 85 %, vermelho abaixo disso.

Conteúdo do modelo
Fatos (8): bi_f_geral (visita × pilar), bi_f_notas_consolidadas (nota por loja, calculada em Power Query), bi_f_metas, bi_f_sortimento_hist, bi_f_planograma, bi_f_mpdv, bi_f_ponto_extra, bi_f_preco
Dimensões (10): calendário, lojas, hierarquia (rota/supervisor), líderes, pessoas, pilares, SKUs, categorias de MPDV, MPDV e tipos de ponto extra
Tabelas de apoio: faixas de nota, classificações e data da última atualização
Medidas DAX: 70+ medidas organizadas em pastas (Notas Pilares, Metas, Atingimento Meta, Efetividade, Sortimento, Planograma, Informações da Loja, Formatação Condicional, Cards KPI, Metadados)
Páginas: Lojas Perfeita (visão geral) e Detalhamento (visão por loja)
Volume da base sintética: 60 lojas · 144 SKUs · 32 pessoas · visitas de jan a abr/2025

Boas práticas aplicadas: esquema estrela com dimensões conformadas, tabela de medidas separada (_medidas), medidas com DIVIDE, formatação condicional dirigida por medida e cards KPI em HTML/CSS.

Como usar

Requisitos: Power BI Desktop (gratuito, somente Windows).

Baixe este repositório (Code → Download ZIP) e extraia mantendo a estrutura de pastas.
Abra LojaPerfeita_Portfolio.pbix no Power BI Desktop.
Se aparecer erro de fonte de dados, aponte o arquivo Excel para o seu computador: Início → Transformar dados → Configurações da fonte de dados → Alterar origem… e selecione data/Base_Sintetica_LojaPerfeita.xlsx. A troca vale para todas as consultas de uma vez.
Clique em Atualizar.

Para usar com dados próprios, mantenha os nomes das abas e das colunas do Excel (uma aba por tabela do modelo) e substitua o conteúdo.

Estrutura do repositório
Loja_perfeita/
├── LojaPerfeita_Portfolio.pbix     # painel
├── data/
│   └── Base_Sintetica_LojaPerfeita.xlsx   # base sintética
├── prints/                         # capturas de tela
└── README.md
Autor

Alejandro Castor — Analista de BI · São Paulo, SP LinkedIn · GitHub

English summary

Power BI dashboard that turns in-store audit visits into a 0–10 execution score per store, split into five weighted pillars (assortment, extra display, planogram, POS material, price), tracked against targets and grouped into score bands. Built on a star schema with 70+ DAX measures. All data is synthetic and generic, so the model fits any retail trade-marketing operation. Open it with Power BI Desktop and point the data source to data/Base_Sintetica_LojaPerfeita.xlsx.
