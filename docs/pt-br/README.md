# Análise de engajamento no Instagram

## Visão geral

Este projeto organiza uma análise exploratória de engajamento no Instagram de uma empresa. A análise parte dos notebooks existentes no repositório e busca responder qual tipo de conteúdo mais engaja nas postagens da marca.

As fontes analíticas originais foram preservadas:

- `data-analysis-instagram-engagement-part01.ipynb`
- `data-analysis-instagram-engagement-part02.ipynb`
- `08. Analisando o engajamento no Instagram.xlsx`

Nenhuma conclusão analítica foi alterada, nenhum gráfico novo foi inventado e o dataset não foi modificado.

## Contexto do problema

A empresa possui uma base de postagens do Instagram desde o início das publicações da marca até 27 de março. A pergunta central registrada nos notebooks é:

> Qual tipo de conteúdo mais engaja no Instagram da minha empresa?

Os direcionamentos da análise original são:

- Ignorar a coluna `Visualizações`.
- Considerar curtidas, comentários e interações.
- Tratar tags vazias como postagens sem tag.

## Dataset

O arquivo Excel original permanece na raiz do repositório para preservar a execução dos notebooks existentes, que carregam o arquivo pelo nome:

```python
pd.read_excel("08. Analisando o engajamento no Instagram.xlsx")
```

Metadados observados sem exposição de linhas do dataset:

- Arquivo: `08. Analisando o engajamento no Instagram.xlsx`
- Abas: `Base` e `Planilha Dinamica`
- A aba `Base` possui 53 linhas, incluindo cabeçalho, e 10 colunas.
- Colunas da aba `Base`: `Tipo`, `Data`, `Curtidas`, `Comentários`, `Visualizações`, `Tags`, `Pessoas`, `Campanhas`, `Carrossel`, `Interacoes`

## Metodologia

A análise foi conduzida em duas partes:

1. Análise geral de engajamento por formato, presença de pessoas, campanhas e carrossel.
2. Análise específica de tags, incluindo separação de tags combinadas com `split` e `explode`.

Principais etapas:

- Importação do dataset em Excel com pandas.
- Remoção analítica da coluna `Visualizações`, conforme orientação do notebook.
- Tratamento de valores nulos em `Carrossel`, interpretando nulos como `N`.
- Estatísticas descritivas de curtidas, comentários e interações.
- Gráficos de dispersão para visualizar curtidas e comentários ao longo do tempo.
- Ordenação de posts por curtidas para observar melhores e piores desempenhos.
- Agrupamentos com `groupby` por `Tipo`, `Pessoas`, `Campanhas`, `Carrossel` e `Tags`.
- Explosão da coluna `Tags` para analisar tags compostas separadamente.

## Principais insights

Os insights abaixo foram extraídos dos notebooks existentes:

- Postagens com pessoas engajam muito mais para a marca.
- Postagens em campanhas também apresentam melhor engajamento.
- No recorte analisado, carrossel não foi um diferencial para melhorar o engajamento.
- O top 5 de curtidas observado no notebook tinha pessoas e era composto por fotos de campanha.
- As 5 piores postagens observadas não tinham pessoas e não eram de campanha.
- Promoções foram as tags com maior engajamento médio na análise por tags.
- Datas comemorativas e trends também apresentaram ótimo engajamento.
- Vídeos sem pessoas tiveram desempenho baixo; vídeos com pessoas, trends ou datas comemorativas tiveram resultado melhor.
- A tag `Loja` não deve ser considerada ruim sem novos testes envolvendo pessoas ou campanhas.
- A continuidade do monitoramento foi indicada como necessária porque a base ainda tem poucas informações.

Alguns resultados numéricos já presentes nos outputs dos notebooks:

- Média de curtidas com pessoas: `14.664,55`.
- Média de curtidas sem pessoas: `4.256,67`.
- Média de curtidas com campanhas: `18.173,27`.
- Média de curtidas sem campanhas: `7.928,33`.
- Média de curtidas em fotos sem carrossel: `13.776,36`.
- Média de curtidas em fotos com carrossel: `11.817,88`.
- Média de curtidas com pessoas e campanhas: `19.405,35`.
- Média de curtidas da tag `Promoções`: `27.458,33`.
- Média de curtidas da tag `Datas comemorativas`: `20.752,25`.
- Média de curtidas da tag `Trends`: `20.024,00`.

## Limitações

- A análise é exploratória e baseada no histórico disponível no dataset.
- A base analisada possui volume limitado de postagens.
- Algumas combinações de formato, pessoas e campanhas têm poucas ocorrências.
- A análise por tags exige cuidado porque `explode` duplica linhas para tags compostas; após essa etapa, o próprio notebook orienta analisar apenas relações envolvendo tags.
- Promoções podem ter custo para a loja, ponto que precisa ser analisado fora das métricas atuais.
- Não há inferência causal; os resultados indicam padrões observados na base.

## Próximos passos

- Continuar monitorando novas postagens para ampliar a base.
- Testar a tag `Loja` com presença de pessoas ou campanhas.
- Avaliar custo e retorno de campanhas promocionais.
- Exportar figuras dos notebooks para `reports/figures/` somente quando forem geradas a partir da análise existente.
- Criar uma versão futura dos notebooks com caminhos padronizados para `data/raw/`, sem alterar conclusões.

## Estrutura do projeto

```text
.
├── assets/
│   └── screenshots/
├── data/
│   ├── raw/
│   ├── processed/
│   └── README.md
├── docs/
│   ├── en/
│   ├── es/
│   ├── fr/
│   └── pt-br/
├── notebooks/
├── reports/
│   ├── figures/
│   └── final_report.md
├── data-analysis-instagram-engagement-part01.ipynb
├── data-analysis-instagram-engagement-part02.ipynb
├── 08. Analisando o engajamento no Instagram.xlsx
└── requirements.txt
```

## Como executar

1. Crie e ative um ambiente Python.
2. Instale as dependências:

```bash
pip install -r requirements.txt
```

3. Abra os notebooks:

```bash
jupyter notebook
```

4. Execute a partir da raiz do repositório para preservar o caminho atual do arquivo Excel usado nos notebooks.

## Segurança e privacidade

- Não publique dados sensíveis, credenciais, tokens ou informações pessoais.
- Não inclua prints com dados privados em `assets/screenshots/`.
- Não altere o dataset original sem uma tarefa específica para isso.
- Ao compartilhar resultados, use métricas agregadas e conclusões já presentes nos notebooks.

## Relatório

Consulte o relatório em [reports/final_report.md](../../reports/final_report.md).
