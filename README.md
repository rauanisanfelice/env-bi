![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/rauanisanfelice/env-bi.svg)
![GitHub top language](https://img.shields.io/github/languages/top/rauanisanfelice/env-bi.svg)
![GitHub pull requests](https://img.shields.io/github/issues-pr/rauanisanfelice/env-bi.svg)
![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/rauanisanfelice/env-bi.svg)
![GitHub contributors](https://img.shields.io/github/contributors/rauanisanfelice/env-bi.svg)
![GitHub last commit](https://img.shields.io/github/last-commit/rauanisanfelice/env-bi.svg)

![GitHub stars](https://img.shields.io/github/stars/rauanisanfelice/env-bi.svg?style=social)
![GitHub followers](https://img.shields.io/github/followers/rauanisanfelice.svg?style=social)
![GitHub forks](https://img.shields.io/github/forks/rauanisanfelice/env-bi.svg?style=social)


# Ambiente de Business Intelligence - Mini Curso Fatec

Criação de um Ambiente para realizar análise de BI.

## Instruções; 

1. Realizar o download do Pentaho Data Integration:

[PDI Download 5.0.1](https://sourceforge.net/projects/pentaho/files/Data%20Integration/5.0.1-stable/pdi-ce-5.0.1-stable.zip/download)

2. Criar os Containers:

```
docker-compose up -d
```

3. Acesar o Banco de Dados:

> localhost

4. Criar Database:

> Servers >> Create >>  Server... 

| Chave | Valor |
|:---|:---:|
| Name | (*)|
| Host Name / address | postgre |
| Port | 5432 |
| Maintenance database | postgres |
| Username | postgres |
| Password | docker123 |

(*) - Nome desejado para o Server.

5. Criando tabelas e importando dados:

Copie o conteudo do arquivo abaixo e execute em uma query.

> conn_tables.sql

## Estrutura do BD;


## Links;

[Transformação que gera Dim Tempo](https://assignittous.com/2018/01/18/generating-date-dimension-table-pentaho-data-integration/)