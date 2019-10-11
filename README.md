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

![erp](http://www.plantuml.com/plantuml/png/fLHDRvmm4BtpAwmzLahLIoueYc9XP-Lg5rC3gzuY1zp54HyhOzfAsVxt6ejrQ80kQdr1p1jxdkUzyKEhkT9TLNfUc_5IWDlRJ-27p7Kn-Y-4F1RQyvJ8DA-F9hh1BDg0kxiuAqJ5x-_1g-S1ivhd5vDZuOyC8xm1l0L2dPJ8XSa1m_e02F91B9JavIY8S1mm4a3gWmDNMS6L1NzDpzxHp_1oTjcyy7yxsu4zrQT-6wcrE8enj4z34f28q0a-GojY5AK9lJ0xgIRlTFEVv0AOu2rb14uPJ0YyvRwZad6phL5oHQVCzYtU_vN9LNtIE8MCkEfTst4bLpGYf7iyLvaWYF2SF37-Ejkq2BD7ibles5Gtc-ra4-gRBA-JZMoU3xJugPSQSS0XSaxzBkfyXG1ValwkOLSz_t7L0znHDXD7C85FjeuF4DTY10qcMB1sFqGBaDLldUSl0-B4hhfQPlAqHcw6jsJUzEdZh06j3zwxpv1ogftFDpVdrpVBMSWnScZ_PdZ3rmNxHyhcks4P83V95hKgJX07Z4jCeexMWubsLVaR)

### DW STAGES:

![dwstg](http://www.plantuml.com/plantuml/png/fLHTRziW57tdLw0yJkgqbxv4LLKKQCIK60_RsTugQhEOoXyLnkkaPlzzk87AZaXchNw9SWxtSdpFkRxhZD2choi0kbnK4bvVVu4lgZ3bw7yfrRuq06YP6z7iBRh0tnVmvYR9IrcBsrlu2W2qJ_luP8yCxESaNJzmWia2YWuMBreMqfw2xla4ALx2H6ebgX68IRBYT8NO4kw4pakXtyW_mUuRzXMvxbNx9FwpkoS7hGz36MsCtCinjSqYkg8nPMF-Wh2OCvobp6bxrctHc_Q3ybOe9Ml6AGfe24XuFtuY9XUsiDLgnhHizPfiBsgPurAMP8XJVt_VzKAh6SE8s9Q4xgOOOH8oAI4_WeEB2R-dcpDJ2ma-5dZpfFwfgd_BZT_EBQ6Hlys5OUn8X7rcVyccc673jtHutwYl7oUlkqCRnWCuHYawNhE4M1WvebmIpeHysAOpbBDmPlhzjdZBwxvHkNgUOpedQngEVtOV3A9BmpI5LfOtxd2ukZgyliSEW94SpmtV3d3yyT3miG9Wj2sUSBiCWBFl59_2llK4yrBkBDZNrLy0)

### DW ODS:

![dwods](http://www.plantuml.com/plantuml/png/ZPD1Zzem48Nl_XKMnqfRzR8Nj49OyO1S9N7a6DfRP1AN12K41QSSclxt6XGLKpdGkMM-aVBUc_7oR5Hd-gP6w9ohMkFtzo_uKXMcTBvBNUrBWr2dSwEEUzkTqMyp_F6HvgLkr6A1Vo64RRMxWnsvqi-KHLd8lv8PLcTSN8gggTk3ieDuh4-OqJbETLUfscaAM3F2vtYhkhnKdKCsArytg0fLQ1-Xa0Q21OHd0YZCCJiQlTV-YQlInudVNaU9u7GZ-TtKgMkBthIlVGL4mfeBHdnIRNyDqNCJuw-TeKcLGSWWbd1NcTULjjvUgunv13uPZ19_X2byzouh0R5YOSRelwbYMpxD4gB4oTNevlGVgLAPaPZxX5cIGWIf5321fM1FkOKJX38oGG8U9I58YwaoUc95Ao9vjeMOaj7l3sNQd_fOgDU6nojmWtNezOmdq2tV2JRUout6VRDxW5iISk7shIFhoL4z36zlm_3tZNlHk54FS-xJGvqtXj3IWhwf_m00)

## Links;

[Transformação que gera Dim Tempo](https://assignittous.com/2018/01/18/generating-date-dimension-table-pentaho-data-integration/)