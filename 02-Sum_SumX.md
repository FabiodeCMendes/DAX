<!-- Âncora do Índice -->
[◀ Voltar](./README.md#indice)

<!-- Âncora do Ínicio do arquivo -->
## <a id="inicio"></a>

# DAX — Exemplos Práticos de Implementação

## 01 — Função SUM e SUMX
### Exemplo

<!-- titulo e Imagem referencia -->
![exemplo](./imgs/002.jpg)


SUMX é uma "função integrante", refere a uma funções de agregação ou de combinação de tabelas no Power BI.
para cálculos linha a linha, ponderando o resultado.

evita colunas materializadas.

### Fórmulas DAX

```dax
SomaVendas = SUM('fPedidos_Detalhes'[Total])
```

```dax
Valor_Desconto = sumx('Pedidos Detalhes',
'fPedidos_Detalhes'[Preço Unitário]*'fPedidos_Detalhes'[Desconto])
```


### Descrição

| Medida | Função | Comportamento |
|---|---|---|
| `SomaVendas` | `SUM` | Soma simples da coluna `Total` da tabela `fPedidos_Detalhes` || `Valor Desconto` |
| `Valor Desconto` | `SUMX` | Cria uma tabela em memoria para calcular o valor linha a lina da tabela `fPedidos_Detalhes` || `Valor Desconto` |








<!-- Âncora do Índice -->
[◀ Voltar](./README.md#indice)