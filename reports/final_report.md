# Relatório final: análise de engajamento no Instagram

## Objetivo

Identificar quais tipos de conteúdo mais engajam no Instagram de uma empresa, usando a base de postagens analisada nos notebooks existentes.

## Contexto

A base cobre publicações desde o início das postagens da marca até 27 de março. A análise original orienta ignorar `Visualizações` e focar em curtidas, comentários e interações. Tags vazias devem ser tratadas como ausência de tag.

## Metodologia

A análise foi conduzida em dois notebooks:

- `data-analysis-instagram-engagement-part01.ipynb`: análise geral de formatos, pessoas, campanhas e carrossel.
- `data-analysis-instagram-engagement-part02.ipynb`: análise com foco em tags.

As etapas principais foram:

1. Importar a base Excel com pandas.
2. Remover a coluna `Visualizações` da análise.
3. Tratar valores nulos em `Carrossel` como `N`.
4. Avaliar estatísticas descritivas.
5. Visualizar curtidas e comentários ao longo do tempo.
6. Ordenar publicações por curtidas.
7. Agregar métricas com `groupby`.
8. Separar tags compostas com `split` e `explode` para análise específica de tags.

## Principais resultados

Os resultados abaixo foram extraídos dos outputs e conclusões dos notebooks. Nenhum resultado novo foi calculado para este relatório.

| Recorte | Resultado observado |
| --- | --- |
| Curtidas médias com pessoas | `14.664,55` |
| Curtidas médias sem pessoas | `4.256,67` |
| Curtidas médias com campanhas | `18.173,27` |
| Curtidas médias sem campanhas | `7.928,33` |
| Curtidas médias em fotos sem carrossel | `13.776,36` |
| Curtidas médias em fotos com carrossel | `11.817,88` |
| Curtidas médias com pessoas e campanhas | `19.405,35` |
| Curtidas médias da tag `Promoções` | `27.458,33` |
| Curtidas médias da tag `Datas comemorativas` | `20.752,25` |
| Curtidas médias da tag `Trends` | `20.024,00` |

## Insights

- Postagens com pessoas engajam muito mais do que postagens sem pessoas.
- Postagens em campanhas apresentam melhor engajamento.
- Na base analisada, carrossel não foi um diferencial positivo para engajamento.
- Promoções, datas comemorativas e trends foram os destaques na análise por tags.
- Vídeos não devem ser descartados apenas pelo formato; o notebook mostra que vídeos com pessoas, trends ou datas comemorativas tiveram desempenho melhor.
- A tag `Loja` precisa de novos testes antes de ser classificada como ruim, especialmente com pessoas ou campanhas.

## Limitações

- A base tem volume limitado de postagens.
- A análise é exploratória e não demonstra causalidade.
- Algumas combinações têm poucas ocorrências.
- A análise por tags duplica linhas ao usar `explode`; por isso, o notebook recomenda usar a base transformada apenas para análises envolvendo tags.
- O custo de campanhas e promoções não está incorporado às métricas atuais.

## Próximos passos

- Continuar monitorando novas postagens.
- Testar publicações com a tag `Loja` usando pessoas e campanhas.
- Avaliar retorno financeiro das promoções, não apenas engajamento.
- Padronizar caminhos de dados em uma futura revisão técnica, preservando as conclusões.
- Exportar visualizações existentes para `reports/figures/` quando necessário.

## Observações de segurança

Este relatório usa apenas métricas agregadas e conclusões dos notebooks. Ele não inclui linhas individuais do dataset, credenciais, tokens ou informações sensíveis.
