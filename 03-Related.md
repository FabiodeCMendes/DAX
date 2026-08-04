<!-- Âncora do Índice -->
[◀ Voltar](./README.md#indice)

<!-- Âncora do Ínicio do arquivo -->
## <a id="inicio"></a>

# DAX — Exemplos Práticos de Implementação

## Função SUMX e RELETED
### Exemplo

<!-- titulo e Imagem referencia -->
![exemplo](./imgs/003.jpg)

https://learn.microsoft.com/pt-br/dax/related-function-dax

Releted  - A função RELATED no Power BI serve para buscar e trazer um valor de outra tabela que já possui uma relação configurada, funcionando de forma parecida com o PROCV do Excel

* permitindo executar calculos entre tabelas. 

### Fórmulas DAX

```dax
Custo = SUMX('Pedidos Detalhes',
'Pedidos Detalhes'[Quantidade]*
RELATED(Produtos[Custo Padrão]))
```



<!-- Âncora do Índice -->
[◀ Voltar](./README.md#indice)