# Modelo Relacional — MobiData SP

## 1. Objetivo

Documentar o modelo relacional desenvolvido na Etapa 3 do projeto MobiData SP, utilizando Excel, Power Pivot e DAX para análise de viagens, demanda de passageiros, ocupação e desempenho operacional.

## 2. Tabelas do modelo

| Tabela | Tipo | Descrição |
|---|---|---|
| TfViagens | Fato | Registros das viagens realizadas |
| TfMetas | Fato | Metas operacionais por linha e mês |
| TdLinha | Dimensão | Cadastro das linhas de transporte |
| TdEmpresa | Dimensão | Cadastro das concessionárias |
| TdVeiculo | Dimensão | Cadastro dos veículos |
| TdCalendario | Dimensão | Calendário de janeiro a junho de 2026 |
| TdMes | Dimensão | Referência dos meses |
| TRejeitados | Auditoria | Registros rejeitados no tratamento dos dados |

## 3. Relacionamentos

| Tabela fato | Campo | Tabela dimensão | Campo |
|---|---|---|---|
| TfViagens | Cod_Linha | TdLinha | Cod_Linha |
| TfViagens | Cod_Empresa | TdEmpresa | Cod_Empresa |
| TfViagens | Cod_Veiculo | TdVeiculo | Cod_Veiculo |
| TfViagens | Data | TdCalendario | Data |
| TfMetas | Cod_Linha | TdLinha | Cod_Linha |
| TfMetas | Mes_Inicio | TdMes | Mes_Inicio |
| TdCalendario | Mes_Inicio | TdMes | Mes_Inicio |

Os relacionamentos utilizam cardinalidade muitos-para-um (N:1), conectando registros operacionais às respectivas dimensões.

## 4. Indicadores

O modelo contém medidas DAX para analisar:

- Total de viagens e passageiros.
- Média de passageiros por viagem.
- Intervalo médio e ocupação média.
- Comparação entre resultados e metas.
- Quantidade de registros rejeitados.
- Reconciliação e integridade das chaves.

## 5. Conferência dos dados

- Registros lidos na Etapa 2: 100.
- Viagens aceitas: 71.
- Viagens rejeitadas: 29.
- Diferença de reconciliação: 0.
- Registros de metas: 90.
- Problemas de integridade de chaves identificados: 0.

## 6. Origem dos dados

A origem dos dados tratados é o arquivo MobiData_02_PowerQuery_novo.xlsx.

O arquivo da Etapa 3 possui consultas Power Query conectadas à Etapa 2. O modelo relacional original utiliza tabelas locais do Excel; a integração automática dessas consultas ao modelo permanece pendente.

## 7. Diagrama

![Diagrama do modelo](diagrama_modelo.png)
