# MobiData SP — Etapa 3: Power Pivot e DAX

## Objetivo

Desenvolver um modelo de dados para análise do transporte coletivo, utilizando Excel, Power Query, Power Pivot e medidas DAX.

O projeto permite analisar viagens, demanda estimada de passageiros, ocupação dos veículos, intervalos operacionais e cumprimento de metas.

## Ferramentas utilizadas

- Microsoft Excel
- Power Query
- Power Pivot
- DAX

## Estrutura do projeto

- `MobiData_03_PowerPivot.xlsx`: arquivo principal do modelo.
- `dax/medidas_preliminares.dax`: documentação das medidas DAX.
- `docs/modelo_relacional.md`: descrição das tabelas e relacionamentos.
- `docs/diagrama_modelo.png`: diagrama do modelo relacional.
- `scripts_m/`: códigos M das consultas Power Query.
- `evidencias/`: capturas de tela das validações.

## Modelo de dados

O modelo contém tabelas fato de viagens e metas, dimensões de linhas, empresas, veículos e calendário, além de uma tabela de auditoria de registros rejeitados.

Os relacionamentos permitem analisar os indicadores por diferentes dimensões.

## Indicadores desenvolvidos

- Total de viagens.
- Total de passageiros.
- Média de passageiros por viagem.
- Intervalo médio.
- Ocupação média.
- Metas operacionais e respectivos desvios.
- Total de registros rejeitados.
- Reconciliação e integridade das chaves.

## Resultados da validação

| Indicador | Resultado |
|---|---:|
| Registros lidos | 100 |
| Viagens aceitas | 71 |
| Viagens rejeitadas | 29 |
| Passageiros estimados | 3342 |
| Registros de metas | 90 |
| Diferença de reconciliação | 0 |
| Problemas de integridade das chaves | 0 |

## Como abrir e atualizar

1. Abrir o arquivo principal no Excel Desktop com Power Pivot habilitado.
2. Consultar as abas `Validacao` e `Conferencia`.
3. Abrir Power Pivot → Gerenciar para visualizar as tabelas, os relacionamentos e as medidas DAX.
4. Para atualizar as consultas vinculadas à Etapa 2, verificar o parâmetro `pArquivoEtapa2` e utilizar Dados → Atualizar Tudo.

**Limitação atual:** as novas consultas importadas da Etapa 2 ainda não alimentam automaticamente o modelo relacional original. A integração completa e o teste de propagação das atualizações permanecem pendentes.

## Pendências

- Integrar as consultas da Etapa 2 ao modelo relacional utilizado pelas medidas.
- Validar a propagação de alterações entre as etapas.
- Concluir a documentação dos códigos M e de todas as medidas DAX.
