# Funções DAX por Tema

As principais funções da linguagem **DAX (Data Analysis Expressions)** no Power BI organizadas com links diretos para a documentação oficial da Microsoft (Microsoft Learn):

### Text (Texto)
Funções utilizadas para manipular cadeias de caracteres (strings), limpar dados textuais ou concatenar colunas:
* [`CONCATENATE`](https://learn.microsoft.com/pt-br/dax/concatenate-function-dax): Une duas sequências de texto em uma única string.
* [`CONCATENATEX`](https://learn.microsoft.com/pt-br/dax): Avalia uma expressão para cada linha de uma tabela e concatena os resultados.
* [`FORMAT`](https://learn.microsoft.com/pt-br/dax): Converte um valor em texto usando um formato de exibição especificado.
* [`LEFT`](https://learn.microsoft.com/pt-br/dax) / [`RIGHT`](https://learn.microsoft.com/pt-br/dax) / [`MID`](https://learn.microsoft.com/pt-br/dax): Extraem partes de um texto com base em posições.
* [`LEN`](https://learn.microsoft.com/pt-br/dax): Retorna o número de caracteres de uma string.
* [`LOWER`](https://learn.microsoft.com/pt-br/dax) / [`UPPER`](https://learn.microsoft.com/pt-br/dax): Convertem todas as letras para minúsculas ou maiúsculas.
* [`SUBSTITUTE`](https://learn.microsoft.com/pt-br/dax) / [`REPLACE`](https://learn.microsoft.com/pt-br/dax): Substituem partes de um texto por um novo valor.
* [`TRIM`](https://learn.microsoft.com/pt-br/dax): Remove espaços em branco extras no início e fim do texto.

### Aggregate (Agregação Geral)
Calculam valores escalares globais resumindo os dados de uma coluna inteira ou tabela:
* [`SUM`](https://learn.microsoft.com/pt-br/dax): Soma todos os números de uma coluna específica.
* [`AVERAGE`](https://learn.microsoft.com/pt-br/dax): Calcula a média aritmética dos valores de uma coluna.
* [`PRODUCT`](https://learn.microsoft.com/pt-br/dax): Multiplica todos os números de uma coluna.
* [`SUMX`](https://learn.microsoft.com/pt-br/dax) / [`AVERAGEX`](https://learn.microsoft.com/pt-br/dax) / [`PRODUCTX`](https://learn.microsoft.com/pt-br/dax): Funções iteradoras que calculam uma expressão linha por linha antes de agregá-la.

### MIN (Mínimo)
Localizam o menor valor possível dentro de um conjunto de dados:
* [`MIN`](https://learn.microsoft.com/pt-br/dax): Retorna o menor valor numérico, de data ou string de uma coluna.
* [`MINA`](https://learn.microsoft.com/pt-br/dax): Retorna o menor valor de uma coluna, incluindo valores lógicos e texto.
* [`MINX`](https://learn.microsoft.com/pt-br/dax): Avalia uma expressão para cada linha de uma tabela e retorna o menor resultado encontrado.

### MAX (Máximo)
Localizam o maior valor possível dentro de um conjunto de dados:
* [`MAX`](https://learn.microsoft.com/pt-br/dax): Retorna o maior valor numérico, de data ou string de uma coluna.
* [`MAXA`](https://learn.microsoft.com/pt-br/dax): Retorna o maior valor de uma coluna, incluindo valores lógicos e texto.
* [`MAXX`](https://learn.microsoft.com/pt-br/dax): Avalia uma expressão para cada linha de uma tabela e retorna o maior resultado encontrado.

### Date (Data e Hora)
Funções que realizam cálculos temporais simples ou manipulam componentes de calendário:
* [`DATE`](https://learn.microsoft.com/pt-br/dax): Retorna uma data no formato padrão a partir de ano, mês e dia numéricos.
* [`DATEDIFF`](https://learn.microsoft.com/pt-br/dax): Calcula a diferença (em dias, meses, anos, etc.) entre duas datas.
* [`YEAR`](https://learn.microsoft.com/pt-br/dax) / [`MONTH`](https://learn.microsoft.com/pt-br/dax) / [`DAY`](https://learn.microsoft.com/pt-br/dax): Extraem respectivamente o ano, mês ou dia de uma data informada.
* [`TODAY`](https://learn.microsoft.com/pt-br/dax) / [`NOW`](https://learn.microsoft.com/pt-br/dax): Retornam a data atual ou a data e hora atual do sistema.
* [`EDATE`](https://learn.microsoft.com/pt-br/dax) / [`EOMONTH`](https://learn.microsoft.com/pt-br/dax): Calculam datas somando meses ou encontrando o último dia de um mês.

### Filter (Filtro e Contexto)
Essenciais para alterar o contexto de avaliação dos cálculos dinâmicos no relatório:
* [`CALCULATE`](https://learn.microsoft.com/pt-br/dax): Modifica o contexto de filtro original de uma medida de forma totalmente customizada.
* [`FILTER`](https://learn.microsoft.com/pt-br/dax): Retorna uma tabela contendo um subconjunto filtrado baseado em condições lógicas.
* [`KEEPFILTERS`](https://learn.microsoft.com/pt-br/dax): Mantém os filtros existentes no contexto visual sem substituí-los por novos filtros.
* [`CALCULATETABLE`](https://learn.microsoft.com/pt-br/dax): Avalia uma expressão de tabela em um contexto de filtro modificado.

### Related (Relacionamento)
Permitem navegar entre tabelas que possuem relacionamentos ativos no modelo de dados:
* [`RELATED`](https://learn.microsoft.com/pt-br/dax): Copia ou puxa um valor de uma tabela relacionada (lado "1") para a tabela atual (lado "Muitos").
* [`RELATEDTABLE`](https://learn.microsoft.com/pt-br/dax): Avalia uma expressão de tabela e retorna apenas as linhas relacionadas à linha corrente.
* [`USERELATIONSHIP`](https://learn.microsoft.com/pt-br/dax): Ativa temporariamente um relacionamento inativo durante o cálculo de uma medida.

### Counting (Contagem)
Dedicadas a computar o volume e a frequência de registros presentes nas tabelas:
* [`COUNT`](https://learn.microsoft.com/pt-br/dax): Conta as células de uma coluna que contêm valores numéricos.
* [`COUNTA`](https://learn.microsoft.com/pt-br/dax): Conta qualquer célula não vazia em uma coluna (aceita texto e lógica).
* [`COUNTROWS`](https://learn.microsoft.com/pt-br/dax): Conta a quantidade exata de linhas totais dentro de uma tabela.
* [`COUNTBLANK`](https://learn.microsoft.com/pt-br/dax): Conta o número de valores vazios (blanks) presentes em uma coluna.
* [`DISTINCTCOUNT`](https://learn.microsoft.com/pt-br/dax): Conta a quantidade de valores únicos (sem repetição) em uma coluna.
* [`COUNTX`](https://learn.microsoft.com/pt-br/dax) / [`COUNTAX`](https://learn.microsoft.com/pt-br/dax): Iteradores que executam uma expressão em cada linha e contam os resultados.

### ALL (Limpeza de Filtros)
Ignoram as seleções feitas pelo usuário nos relatórios para gerar totais e percentuais precisos:
* [`ALL`](https://learn.microsoft.com/pt-br/dax): Limpa todos os filtros aplicados a uma tabela ou coluna específica.
* [`ALLEXCEPT`](https://learn.microsoft.com/pt-br/dax): Remove filtros de uma tabela inteira, exceto das colunas especificadas.
* [`ALLSELECTED`](https://learn.microsoft.com/pt-br/dax): Mantém os filtros externos (como segmentadores), mas limpa os filtros internos da própria matriz ou gráfico.
* [`REMOVEFILTERS`](https://learn.microsoft.com/pt-br/dax): Uma alternativa explícita à função ALL usada unicamente para limpar filtros dentro de uma `CALCULATE`.

### Calendar (Inteligência de Tempo / Tabelas Calendário)
Utilizadas principalmente para a criação nativa e dinâmica da dimensão dCalendário:
* [`CALENDAR`](https://learn.microsoft.com/pt-br/dax): Retorna uma tabela com uma única coluna de datas contínuas entre uma data inicial e final.
* [`CALENDARAUTO`](https://learn.microsoft.com/pt-br/dax): Cria uma tabela calendário automaticamente buscando o menor e maior ano contidos em todo o seu modelo.
* [`DATESYTD`](https://learn.microsoft.com/pt-br/dax) / [`DATESMTD`](https://learn.microsoft.com/pt-br/dax) / [`DATESQTD`](https://learn.microsoft.com/pt-br/dax): Filtram datas desde o início do ano, mês ou trimestre atual.
* [`DATEADD`](https://learn.microsoft.com/pt-br/dax): Desloca um conjunto de datas para frente ou para trás no tempo por um intervalo definido.
