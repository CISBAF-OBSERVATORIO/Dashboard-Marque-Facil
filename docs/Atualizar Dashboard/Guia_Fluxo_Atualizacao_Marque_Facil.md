# MARQUE FÁCIL

## Ordem de preenchimento e relacionamento entre arquivos

## 1. Ordem de preenchimento dos arquivos

A atualização deve seguir esta ordem:

**RELATÓRIO GERAL → AUTO → APRESENTAÇÃO**

``` mermaid
flowchart TD
    A[Relatório Geral<br/>Preencher manualmente] --> B[AUTO<br/>Recebe os dados do relatório geral, basta abrir e clicar em atualizar]
    B --> C[APRESENTAÇÃO]
    C --> D[POR MUNICIPIO<br/>Recebe os dados do AUTO]
    C --> E[2022 <br/>Preencher manualmente]
    C --> F[Faltas (2)<br/>Preencher manualmente]
```

A ordem é importante porque cada arquivo utiliza informações do arquivo
anterior. Primeiro, os dados são atualizados no **Relatório Geral**;
depois, são transferidos para o **Auto**; por fim, o arquivo
**Apresentação** utiliza os dados do Auto.

## 2. Relatório Geral → Auto

No arquivo **Relatório Geral**, acesse a aba correspondente ao ano que
deseja atualizar. Essa aba é a origem dos dados que devem alimentar o
arquivo **Auto**.

de acordo com o video abaixo, coloque o nome dos municipios correspondentes aos dados, uma funcao de soma para os valores e atualiza a celula na qual faz a some de cada competencia


[▶️ Assistir ao tutorial](./Videos/geral-auto.mp4)

## 3. Auto → Apresentação

Depois de atualizar o Auto a partir do Relatório Geral, atualize as
fórmulas ou conexões do arquivo Auto, quando aplicável. O Auto é a fonte
de dados utilizada pelo arquivo **Apresentação**.

No arquivo **Apresentação**, a aba **POR MUNICIPIO** deve receber
automaticamente os dados do Auto. Ao abrir o arquivo, utilize o comando
**Atualizar**, caso essa seja a etapa configurada na planilha.

[▶️ Assistir ao tutorial](./Videos/auto.mp4)

## 4. Abas que precisam ser preenchidas manualmente

As abas abaixo, no arquivo **Apresentação**, precisam ser
preenchidas manualmente:

-   **2022**
-   **Faltas (2)**


------------------------------------------------------------------------

**Fluxo resumido:** Relatório Geral → Auto → Apresentação