<a id="topo"></a>

# Parâmetro de Hipótese (What-if Parameter) no Power BI

## O que é

O **Parâmetro de Hipótese** (em inglês, *What-if Parameter*) é um recurso do Power BI que cria uma tabela de valores numéricos independente do modelo de dados, permitindo simular cenários interativamente. O usuário movimenta um *slider* (controle deslizante) no relatório e todas as medidas que referenciam esse parâmetro recalculam em tempo real.

É muito usado para simulações do tipo:
- "E se o desconto fosse de X%?"
- "E se a taxa de crescimento fosse de Y%?"
- "E se a meta de vendas aumentasse em Z%?"

## Como é criado internamente

Ao criar um Parâmetro de Hipótese pela interface (**Modelagem → Nova Parâmetro → Numérico**), o Power BI gera automaticamente uma tabela calculada usando a função `GENERATESERIES`, e uma medida auxiliar para capturar o valor selecionado.

### Exemplo

```dax
Parâmetro = GENERATESERIES(0.001, 0.09, 0.001)
```

### Explicação dos argumentos

`GENERATESERIES(<start>, <end>, <increment>)`

| Argumento | Valor no exemplo | Significado |
|---|---|---|
| `start` | `0.001` | Valor inicial da série (0,1%) |
| `end` | `0.09` | Valor final da série (9%) |
| `increment` | `0.001` | Incremento entre cada valor (0,1%) |

Essa fórmula gera uma tabela de uma única coluna (`[Value]`) com **90 valores**, de 0,1% a 9%, em passos de 0,1% — típica de um cenário de simulação de **taxa** ou **percentual** (ex.: taxa de juros, desconto, margem).

### Tabela gerada (resumo)

| Value |
|---|
| 0,001 |
| 0,002 |
| 0,003 |
| ... |
| 0,089 |
| 0,090 |

## Medida auxiliar gerada automaticamente

Junto com a tabela, o Power BI cria uma medida para capturar o valor atualmente selecionado no slicer:

```dax
Parâmetro Value = SELECTEDVALUE('Parâmetro'[Parâmetro], 0.045)
```

- `SELECTEDVALUE` retorna o valor único selecionado na segmentação de dados (slicer).
- O segundo argumento (`0.045`) é o valor padrão, usado quando **múltiplos valores** estão selecionados ou nenhum filtro é aplicado — nesse exemplo, o ponto médio da série.

## Usando o parâmetro em uma medida de simulação

O objetivo do parâmetro é ser referenciado dentro de outras medidas para simular o impacto de diferentes percentuais:

```dax
Venda_Com_Ajuste = 
[SomaVendas] * (1 + [Parâmetro Value])
```

Nesse caso, ao mover o slider entre 0,1% e 9%, o visual conectado à medida `Venda_Com_Ajuste` recalcula automaticamente, simulando um aumento percentual sobre o total de vendas.

## Passo a passo na interface do Power BI

1. Vá em **Modelagem** → **Nova Parâmetro** → **Numérico**
2. Defina:
   - **Tipo de dados**: Número decimal
   - **Mínimo**: `0.001`
   - **Máximo**: `0.09`
   - **Incremento**: `0.001`
   - **Valor padrão**: (opcional) ponto de partida do slider
3. Marque **"Adicionar segmentação de dados a esta página"** para inserir o slider automaticamente
4. Use a medida `Parâmetro Value` gerada em qualquer outra medida do modelo

## Boas práticas

- Prefira incrementos pequenos (`0.001`) quando o parâmetro representar **taxas ou percentuais**, para permitir ajuste fino no slider.
- Nomeie o parâmetro de forma descritiva (ex.: `Parâmetro Taxa Desconto`), especialmente em modelos com múltiplos parâmetros de hipótese.
- Sempre defina um **valor padrão coerente** em `SELECTEDVALUE`, evitando que a medida retorne `BLANK()` quando nenhum valor estiver selecionado.
- Documente a unidade do parâmetro (percentual, valor monetário, etc.) próximo ao slicer, para orientar quem usa o relatório.

[🔝 Voltar ao início](#topo)
