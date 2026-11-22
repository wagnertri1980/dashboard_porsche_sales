# Porsche Vendas — Dashboard Interativa de Receita, Quilometragem & Logística

Dashboard executiva interativa desenvolvida em **HTML5**, **Tailwind CSS** e **Chart.js** a partir da base sanitizada `Porsche_Database_Sanitized.xlsx` (100 registros de vendas).

## Visão Geral do Projeto

O objetivo deste painel é transformar os dados de vendas de veículos Porsche em uma leitura prática para tomada de decisão comercial, operacional e financeira, conectando cada visualização a perguntas de negócio específicas e permitindo filtragem dinâmica em tempo real.

## Perguntas de Negócio & Por Que Elas Importam

### 1. Qual família de modelos lidera o faturamento e como a quilometragem média se comporta em relação ao preço?
* **Por que perguntar:** Ajuda a identificar o motor de receita do portfólio (se o faturamento vem de linhas de ticket elevado ou maior volume) e a entender a relação entre uso do veículo (milhas) e precificação/depreciação.
* **Visualizações escolhidas:**
  * **Barras Horizontais:** Compara o faturamento total e a participação percentual entre as famílias (`911`, `Taycan`, `Cayenne`, `Panamera`, `Macan`, `718`) sem truncar rótulos.
  * **Gráfico de Dispersão (Scatter Plot):** Cruza quilometragem (eixo X) e preço (eixo Y) para evidenciar a correlação negativa geral (`-0,55`) e o posicionamento de cada família.

### 2. Qual percentual das vendas já foi efetivamente entregue e quanto está parado em etapas pendentes/em trânsito ou perdido por cancelamento?
* **Por que perguntar:** Venda registrada não equivale imediatamente a receita concluída. Medir o que foi entregue, o que está em aprovação/revisão/trânsito e o que foi cancelado ajuda a enxergar gargalos operacionais, capital represado e perdas evitáveis.
* **Visualizações escolhidas:**
  * **Gráfico de Rosca (Donut):** Exibe a distribuição percentual das unidades entre `Entregue (Delivered)`, `Pendente / Aprovação / Revisão`, `Em Trânsito / Aguardando Logística` e `Cancelado (Cancelled)`.
  * **Cards de KPI:** Destacam percentuais, contagem de unidades e valores financeiros (`USD`) para cada etapa.

### 3. Como a situação operacional se desdobra em valor financeiro por família de modelos?
* **Por que perguntar:** Complementa a visão percentual mostrando *onde* o dinheiro está concentrado, retido ou perdido quando segmentamos por família de veículos.
* **Visualização escolhida:**
  * **Barras Empilhadas:** Compara a receita de cada família dividida pelas etapas operacionais, facilitando a identificação de gargalos e cancelamentos por linha de produto.

## Qualidade e Sanitização dos Dados

* A base analisada contém **100 registros** e **0 valores nulos** nas regras estruturais avaliadas na aba de qualidade da planilha.
* Registros com datas inválidas no calendário original (`INVALID`) são preservados na base para análises de preço, quilometragem, família e status, e isolados em análises temporais para não distorcer séries cronológicas.

## Filtros e Interatividade

* **Filtro por Família de Modelos:** `ALL`, `911`, `Taycan`, `Cayenne`, `Panamera`, `Macan`, `718`.
* **Filtro por Etapa Logística:** `ALL`, `Entregue (Delivered)`, `Pendente / Aprovação / Revisão`, `Em Trânsito / Aguardando Logística`, `Cancelado (Cancelled)`.
* **Filtro por Método de Pagamento:** `Wire Transfer`, `Credit Card`, `Financing`, `Cash`, `Lease`, `Crypto Payment`, `Bank Transfer`, `ACH Payment`, `Debit Card`.
* **Tabela Dinâmica:** Atualiza automaticamente conforme os filtros selecionados e conta com botão de reset.

## Como Executar

1. Faça o download ou clone este repositório.
2. Abra o arquivo `.html` da dashboard diretamente em qualquer navegador moderno (Chrome, Edge, Firefox, Safari) — não é necessário instalar dependências locais ou subir servidor.
