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

de acordo com o video abaixo, coloque o nome dos municipios correspondentes aos dados e municipio no cabeçalho

Antes de seguir para o próximo arquivo, confira se a aba do ano correto
contém os dados atualizados e se o período/competência desejado está
correto.

[▶️ Assistir ao tutorial](./geral-auto.mp4)

## 3. Auto → Apresentação

Depois de atualizar o Auto a partir do Relatório Geral, atualize as
fórmulas ou conexões do arquivo Auto, quando aplicável. O Auto é a fonte
de dados utilizada pelo arquivo **Apresentação**.

No arquivo **Apresentação**, a aba **POR MUNICIPIO** deve receber
automaticamente os dados do Auto. Ao abrir o arquivo, utilize o comando
**Atualizar**, caso essa seja a etapa configurada na planilha.

## 4. Abas que precisam ser preenchidas automaticamente

As abas abaixo, no arquivo **Apresentação**, também precisam ser
preenchidas automaticamente, sem depender de cópia e colagem manual:

-   **2022** --- deve receber os dados correspondentes do Relatório
    Geral, por meio do fluxo de atualização definido.
-   **Faltas (2)** --- deve receber automaticamente os dados de faltas
    da fonte correspondente no Relatório Geral.

A automação dessas duas abas deve respeitar o mesmo fluxo de origem dos
dados: **Relatório Geral → Auto → Apresentação**. A fonte exata, os
intervalos e as colunas de cada aba devem ser conferidos nas planilhas
para configurar corretamente as fórmulas ou conexões.

## 5. Conferência final

-   [ ] Confirmar que a aba do ano correto foi atualizada no Relatório
    Geral.
-   [ ] Verificar se o Auto recebeu os dados esperados.
-   [ ] Atualizar a aba **POR MUNICIPIO** no arquivo Apresentação.
-   [ ] Confirmar que as abas **2022** e **Faltas (2)** são preenchidas
    automaticamente.
-   [ ] Conferir se os totais e as competências estão coerentes entre os
    arquivos antes de atualizar ou usar o Power BI.

------------------------------------------------------------------------

**Fluxo resumido:** Relatório Geral → Auto → Apresentação

> **Observação:** este guia descreve o fluxo desejado. A necessidade de
> automatizar as abas **2022** e **Faltas (2)** está registrada aqui,
> mas a automação precisa ser configurada e validada nas planilhas.
