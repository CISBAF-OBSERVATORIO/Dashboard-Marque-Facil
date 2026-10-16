# Documentação do Dashboard Marque Fácil

## Visão geral

O Marque Fácil é um relatório Power BI do CISBAF que acompanha procedimentos realizados, atendimentos e faltas (absenteísmo) de municípios credenciados ao CISBAF, de 2018 em diante. Os dados vêm de uma única planilha Excel em rede; não há API nem banco de dados.

| Item | Detalhe |
| --- | --- |
| Arquivo | Marque\_Facil.pbix (5,3 MB) |
| Modelo | 4 tabelas importadas, 1 relacionamento, 4 medidas DAX |
| Páginas | 12 (5 de desktop, 3 de celular, 4 ocultas) |

## Fontes de dados

Todas as tabelas vêm de quatro abas da mesma planilha Excel, lida pelo Power Query com `Excel.Workbook(File.Contents(...))`. O arquivo não contém nenhuma chamada a API, banco de dados ou serviço web; planilha é preenchida manualmente através dos relatórios financeiros puxados diretamente do sistema do E-Client ou através dos dados capturados pela API, que se encontra no repositório [CISBAF-OBSERVATORIO/api-hygia](https://github.com/CISBAF-OBSERVATORIO/api-hygia)&#32;

- Arquivo: `S:\OBSERVATORIO\PROJETOS\BI e Afins\MARQUE FACIL\apresentação.xlsx`
- Tipo: pasta de rede (unidade S:), caminho absoluto fixo nas quatro consultas
- Modo: importação (os dados ficam dentro do .pbix e só mudam com a atualização)

| Tabela no modelo | Aba do Excel | Linhas | Transformações no Power Query |
| --- | --- | --- | --- |
| 2022 | 2022 | 98 | Promove cabeçalhos; tipa Competência 2021 e Competência como texto, Indice e TOTAL como inteiro |
| POR MUNICIPIO | POR MUNICIPIO | 880 | Promove cabeçalhos; tipa PROCEDIMENTOS, MUNICIPIO e ANO como texto, TOTAL como inteiro; passo "Linhas Filtradas" com `each true`, que não filtra nada |
| Faltas (2) | Faltas (2) | 519 | Promove cabeçalhos; tipa Municipio, Ano e Competencia como texto, Atendimento e Falta&#32; como inteiro, Indice como qualquer tipo |

### O que cada tabela guarda

- **POR MUNICIPIO** traz o total de procedimentos realizados por procedimento, município e ano.
- **Faltas (2)** traz, por município e competência, quantos atendimentos aconteceram e quantas faltas houve. Os nomes de município aparecem com maiúsculas e acentos diferentes dos de POR MUNICIPIO (por exemplo, "Itaguai" e "ITAGUAI").
- **2022** ordena as competências no gráfico; `TOTAL` é o total de procedimentos do mês.

## Medidas DAX

As quatro medidas ficam na tabela Faltas (2) e alimentam as páginas de absenteísmo (Página 3 e Pág 3 - Cel). Nenhuma tem pasta de exibição ou descrição.

| Medida | Para que serve | Expressão |
| --- | --- | --- |
| Agendamento | Total agendado: atendimentos mais faltas | `SUM('Faltas (2)'[Falta]) + SUM('Faltas (2)'[Atendimento])` |
| Taxa Atendimento | Parcela dos agendamentos que foi atendida | `SUM('Faltas (2)'[Atendimento])/[Agendamento]` |
| Taxa Faltas | Parcela dos agendamentos em que o paciente faltou (absenteísmo) | `SUM('Faltas (2)'[Falta])/[Agendamento]` |
| MensagemAusenciaDados | Texto de aviso quando não há faltas registradas no filtro atual | ver abaixo |

```dax
MensagemAusenciaDados =
VAR SomaFaltas = SUM('Faltas (2)'[Falta])
RETURN
    IF(
        SomaFaltas = 0,
        "Os dados referentes ao número de faltas nesta competência não foram registrados no banco de dados do sistema. Por esse motivo, as informações não serão exibidas",
        ""
    )
```

O aviso aparece em um cartão na base das páginas de faltas. Ele evita que uma competência com atendimentos e zero faltas

## Como atualizar e reproduzir

O relatório só muda quando a planilha muda e a atualização é feita. Os passos abaixo valem para o .pbix atual,

Relatórios localizados na pasta: `S:\OBSERVATORIO\PROJETOS\BI e Afins\MARQUE FACIL`

1. Atualize a planilha  `RELATORIO GERAL CONSOLIDADO MARQUE FACIL 2025 - Atalho`, apenas as abas referente ao ano no qual deseja atualizar
2. Abre a planilha `Aut``o` abra a pagina de dados e clique em  **"Atualizar tudo" **
3. Abra a `apresentação` abra a pagina de dados e clique em  **"Atualizar tudo"**** **em seguida, preencha as abas `2022` e `Falta``s``(2``)`&#32;&#32;
4. Abra o Marque\_Facil.pbix no Power BI Desktop
5. Clique em Atualizar. Se o arquivo mudou de pasta, use Transformar dados e troque o caminho em cada uma das quatro consultas.
6. Confira se o índice (`Indice`) e as competências novas aparecem na Página 2 e se os totais da Página 1 e da Página 4 estão coerentes.
7. Publique no serviço Power BI
