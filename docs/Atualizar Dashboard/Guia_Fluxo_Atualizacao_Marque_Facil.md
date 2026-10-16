# MARQUE FÁCIL

## Ordem de preenchimento e relacionamento entre arquivos

## 1. Ordem de preenchimento dos arquivos

A atualização deve seguir esta ordem:

**RELATÓRIO GERAL → AUTO → APRESENTAÇÃO**

[![](https://mermaid.ink/img/pako:eNp9kM1qwkAQgF9lmVMLatdkJSYUIf4VD1WxemnTw5qMGkiyMm6oVTz10FOfpo-QF-smxdJScA_LzPB9M7N7hFBFCB6sEvUSbiRpNu8GFGTMHP8pgBkmUhefFCt2hyST2yXddKaEmIUbJJbKLJdJipnGAJ5Zvd5hXWP5i_mkIv0lxcSQhUkcShOkzNdGiA-SDH8e1K3EXilOZ4OHwXjuF-_F2-QX0quQvkGmkxm7X4xHveJjOvqeMsMQl8jUjkUyKm_Fyg3-6QOjW9yyLj7irzI0ylAmWu7YlXV9UYQarCmOwNOUYw1SpFSWKRzLhgHoDaaG80xIGOX7eqgSZb4hyE5G3crsUan0bJPK1xvwVjLZmSzfRlJjP5ZrkulPlTCLkHoqzzR4wq16gHeEPXjNttUQQvCW47oudx3HqcGrKXPRsFuiKVzBubBtW5xqcKjG8karZfG2cLjtOK7DhTh9AfsbqOI?type=png)](https://mermaid.live/edit#pako:eNp9kLFOwzAQQH_Fugmktripg5MIIaWhIAbaqLQLhMFNjjZSEqOrIwpVJwYmvoZP6I_hBIFASHiw7s7v3dneQqozhADuC_2YrhQZNhsmlFTMrvA2gSkWyuzfKdfsAkkVJws6Oo0JsUpXSKxUVa2KEiuDCdyxbveUDa0VzmeTlgwXlBNDlhZ5qmxQstBYIX9WZPmvQcNWjBoxno6uR-NZuH_dv0x-IFGLnFkknkzZ1Xx8Ge3f4svPKVNMcYFMr1mmsmbXrLnBH31kdYc7zr-P-K2cW-VcFUat2YFz-K8IHVhSnkFgqMYOlEilalLYNg0TMCssLRfYkDCrN91UF9p-Q1LtrPqgqhutyy-bdL1cQXCvirXN6odMGTzL1ZJU-V0lrDKkSNeVgUDItgcEW9hA0PecnhCCu9L3fe5LaU-fbJk7vYEr-i73pOj7A-9414Hndizvua7DPSH5QEpfciF2H_wyqO8)
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