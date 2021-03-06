
<!-- README.md is generated from README.Rmd. Please edit that file -->

# abjutils <a href='http://abjur.github.io/abjutils/'><img src='man/figures/logo.png' align="right" height="138.5" /></a>

<!-- badges: start -->

[![CRAN\_Status\_Badge](https://www.r-pkg.org/badges/version/abjutils)](https://cran.r-project.org/package=abjutils)
[![R build
status](https://github.com/abjur/abjutils/workflows/R-CMD-check/badge.svg)](https://github.com/abjur/abjutils/actions)
<!-- badges: end -->

## Visão Geral

`{abjutils}` é um Kit de Ferramentas com algumas funções úteis
utilizadas pela [Associação Brasileira de
Jurimetria](https://abj.org.br/).

A maioria das funções ajuda a lidar com a identificação de processos
judiciais numeros (unificados pelo CNPJ, [Conselho Nacional de
Justiça](https://www.cnj.jus.br/programas-e-acoes/numeracao-unica/documentos/):
NNNNNNN-DD.AAAA.J.TR.OOOO).

Enquanto as demais são para ajudar com a conciliação do ASCII e entre
outros problemas de formatação.

## Para Instalar

Você pode instalar a versão mais recente do `{abjutils}` com:

``` r
# Para instalar a versão CRAN
install.packages("abjutils")

# Para instalar a versão GitHub (dev)
install.packages("remotes")
remotes::install_github("abjur/abjutils")
```

## Lista de funções

| Função              | Descrição                                                                 |
|---------------------|---------------------------------------------------------------------------|
| `build_id()`        | Adiciona separadores a IDs de processos                                   |
| `calc_dig()`        | Verifica os números de um processo no fomato estruturado pelo CNJ         |
| `carf_build_id()`   | Adiciona separadores para ações judiciais do CARF                         |
| `carf_calc_dig()`   | Verifica o número CARF com o dígito de verificação                        |
| `carf_check_dig()`  | Verifica se um dígito de verificação CARF está correto                    |
| `check_dig()`       | Verifica se um dígito de verificação CNJ está correto                     |
| `check_dig_vet()`   | Verifica se um vetor de dígito de verificação CNJ está correto            |
| `chrome_to_body()`  | Analisa o fluxo de rede de uma página web                                 |
| `clean_cnj()`       | Remove todos os caracteres não núméricos de uma string                    |
| `clean_id()`        | Remove separadores de IDs de processos judiciais                          |
| `escape_unicode()`  | Substitui caracteres acentuados por seus valores escapados de Unicode     |
| `extract_parts()`   | Extrai partes dos IDs dos processos                                       |
| `file_sans_ext()`   | Extrai o nome do arquivo sem extensão                                     |
| `gather_subjects()` | Reuni os assuntos do esaj automaticamente                                 |
| `lsos()`            | Lista objetos elegantemente em uma sessão R                               |
| `pattern_cnj()`     | Padrão Regex para encontrar números de processos judiciais                |
| `precision()`       | Aplica escala de precisão                                                 |
| `reais()`           | Converter valores da moeda brasileira (texto) em numéricos                |
| `rm_accent()`       | Remove diacríticos de uma string                                          |
| `sample_cnj()`      | Cria uma amostra aleatória de processos judiciais                         |
| `separate_cnj()`    | Divide uma coluna com IDs de processos em 6 colunas com suas partes       |
| `tabela()`          | Produz tabela de contingência dos elementos de um vetor                   |
| `test_fun()`        | Verifica se todos os argumentos de outra função já tem valores atribuídos |
| `verify_cnj()`      | Verifica se a identificação de um processo brasileiro é um número CNJ     |
| `write_data()`      | Atalho para gravar o arquivo no diretório “data /”                        |

## Como Usar

Exemplo 1:

``` r
# Para Remover separadores de IDs de processos judiciais
 abjutils::clean_id(c("1025736-09.2014.8.26.0100","0043877-64.2012.8.26.0100","1013689-61.2018.8.26.0100"))
#> [1] "10257360920148260100" "00438776420128260100" "10136896120188260100"
```

Exemplo 2:

``` r
# Extrair partes dos IDs dos processos
abjutils::extract_parts(c("1025736-09.2014.8.26.0100","0043877-64.2012.8.26.0100","1013689-61.2018.8.26.0100"))
#> [[1]]
#>         N         D         A         J         T         O 
#> "1025736"      "09"    "2014"       "8"      "26"    "0100" 
#> 
#> [[2]]
#>         N         D         A         J         T         O 
#> "0043877"      "64"    "2012"       "8"      "26"    "0100" 
#> 
#> [[3]]
#>         N         D         A         J         T         O 
#> "1013689"      "61"    "2018"       "8"      "26"    "0100"
```

Exemplo 3:

``` r
# Remover diacríticos de uma string
abjutils::rm_accent("acórdão")
#> [1] "acordao"
```

## Requisitos

`{abjutils}` requer uma versão do R superior ou igual a 3.6.

## Licença

O sistema de gerenciamento de conteúdo `{abjutils}` é licenciado sob os
termos da [MIT + file
LICENSE](https://github.com/abjur/abjutils/blob/master/LICENSE)

#### Citations

To cite this package, use `citation("abjutils")`:

    To cite package ‘abjutils’ in publications use:

      Associacao Brasileira de Jurimetria (2020). abjutils:
      Useful Tools for Jurimetrical Analysis Used by the
      Brazilian Jurimetrics Association. R package version
      0.0.1. https://github.com/abjur/abjutils

    A BibTeX entry for LaTeX users is

      @Manual{,
        title = {abjutils: Useful Tools for Jurimetrical Analysis Used by the Brazilian Jurimetrics Association},
        author = {Associacao Brasileira de Jurimetria},
        year = {2020},
        note = {R package version 0.3.0},
        url = {https://github.com/abjur/abjutils},
      }
