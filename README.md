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

6. Abra o arquivo **Date Dimension Generator.kjb** no PDI e execute, esta etapa não é necessário executar nas próximas vezes.

7. Abra o arquivo **job_etl.kjb** no PDI e edite os dois *Steps Mail* os campos:

Aba *Addresses*
- Destination address: "Destinatário"
- Sender Name:  "Nome do Remetente"
- Sender address: "Remetente"

Aba *Server*
- Authentication user: "Conta do remetente"
- Authentication password: "Senha da conta"


8. Realizar o Download da biblioteca abaixo, para que o Power BI acesse o Postgre:

[Npgsql 3.2.7](https://github.com/npgsql/npgsql/releases/tag/v3.2.7)

9. Crie seu Dashboard !!!

## Estrutura do BD;

### ERP:

![](http://localhost:8080/png/fLHTRu8m57tdLpG-Bd7PYo_6c3IqcYuAh8ZPcwdG2KR15DYMwFxxIWVrWphDrXV2FRUzf_USspna6mvwlIVmaKH5RENwF-R9AYuiI_2mOEbAHZkOUXqm6FXXpBTiE0Hxom9oPSkrp57m8yK8Tm3B0HSxmICkSq2z7W11VU1paR3DIH1XtwR4XcuVp9a8OoOK-DK-U-8-m-RiJRPcVpxx1woeBgfj92tuYfz2qy0XDl68sy8Dj3pgec3cDins8elA8lidEHlEyDYb11eON18uvbvG2PdSbicojyd8xMCy_PN9JNq2Fu2KwEfbNZAHtD48nvrYKsM28C8cUNpyQcoQX-c8JAvqhAsRojQoSV6MR6wJzLHU7nJyixZMY3bsa7RgEq-ZEmHucLLtTShjykogSpXngI6Eu0mkL9q-G5BcKuO_9hXYxMg8ha2rVlTuNWz8SyjjcIPXihj7Reh7n6pwO6GqOEs3S_T9Kbgrmw7RFUoFbbEGPgJHwismwgyELe-KojV3eg5waXMgL6mXBQ0fSHwjQNq3)

### DW STAGES:

![](http://localhost:8080/png/fLJHRi8W57tlLn0VbxZinHTZJ4X1mwBYQElsPh1bjaQjmNOkqVtxmD9E7MgpyTBqddilXtiER4E-5A3LUWAx9CfYPrlznoAPnvdZI15cV3rNqGPwRO1EnmjZiUBTBjWx3b0hdIrKYaOVFRy_PHZX1k1R4EsaY8JA0cOz08BQm1CouSkJ8CAUouWBQHjCk0nZBe_WbxNxW3v3qtsPBlYVknUWvZhLPMITYRauXOR1YBXaJEWlt4vip2WAV6guRMGQvLdwJtekz76VCW8j72mKVjBFoOHS5QPgu_jqL7KV3szogQDIu0MGaNB_V9jpcTGOneWEiMrlWY32Df4y_6OTt1Yp7XbScPfLlMD1APwGxydoFjtnCQyDCl6PtHZ618zGwTaFiOvgoF3Yw_EEyjNixBWJEA3C4aVGXyKsRO2KsASS2oTSCRc-JLSW8s5DzrUtnPnpbQ-JCDdK4PtXFh7RF-XPZMZSSEv2HQiKxd1eDW_xodOQgEYKc7uxdE9JXlHZfNEhsr82vYvhx2ZVPVmYR5gVnGoLRm00)

### DW ODS:

![](http://localhost:8080/png/ZPDFQy8m6CRl_HJ1uy2nYnSH8JIlaj4s9StSRYMscQrOAxNEm_IxBtMTMfQeEGJo_bx8yxn_jebSAJGOlA1zdjQPips_CvKlijfnAfNKShtGqHvvxw7HA4eoLSZn67qx3jAdd2zrIaEV2VLZZxtY7f9RbExJl5YLIwaJKNkU42L35Aagbwkh88SfnMo8Ph9ACbbTaRU9AUhcgKoLYH28N4vTp68E18Q8hckrKEQCHcatusXq5796tWIxcDfKPRgho_k-N2nWoZZ59gawFWN_jedswswIMQNhKGW4N5GcgrnfR_TL1im7amnAiBc44NmOcnK2dr0lRZxfLhMvJPe5-E5LNMjLR1weAX4n3fYnjoAEm8T8SB1WmUbDhg6548ejn6L-w87GcCXQMLeqmOB5CmZ8tt9yohhyKklqWVLef-1VONzfCyOMTAglXRNpSgB1hfXtu0nxZ7VYHqTxkb9zEFJxXyDvnoter54BQ-VJGjiT-m40)

## Links;

[Transformação que gera Dim Tempo](https://assignittous.com/2018/01/18/generating-date-dimension-table-pentaho-data-integration/)