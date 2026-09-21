# Censo 2022 — Retratos do Brasil

## Visão Geral

Projeto de portfólio de **Análise de Dados** utilizando dados oficiais do **Censo Demográfico 2022 do IBGE**.

O projeto é organizado de forma modular (guarda-chuva). O primeiro módulo desenvolvido é:

> **Alfabetização no Brasil — Censo 2022**

---

## Objetivo

Analisar como a alfabetização se distribui pelo território brasileiro e quais desigualdades demográficas e regionais o Censo 2022 revela, utilizando dados oficiais do IBGE.

### Pergunta analítica central

> Como a alfabetização se distribui pelo território brasileiro e quais desigualdades demográficas e regionais o Censo 2022 revela?

---

## Escopo Atual (Módulo Alfabetização)

### População de referência
- Pessoas de **15 anos ou mais** de idade

### Abrangência geográfica (neste momento)
- Brasil
- Grandes Regiões
- Unidades da Federação

> Municípios serão incluídos em etapa posterior.

### Dimensões analisadas
- Sexo
- Cor ou raça
- Grupos de idade

### Indicadores principais
- Taxa de alfabetização (%)
- Contingente de pessoas alfabetizadas e não alfabetizadas (números absolutos)

---

## Fonte dos Dados

Dados oficiais do **IBGE – Censo Demográfico 2022 (Resultados do Universo)**.

| Tabela SIDRA | Conteúdo | Formato baixado |
|--------------|----------|-----------------|
| **9542** | Pessoas de 15 anos ou mais de idade, total e as alfabetizadas, por sexo, cor ou raça e grupos de idade | CSV (BR) |
| **9543** | Taxa de alfabetização das pessoas de 15 anos ou mais de idade por sexo, cor ou raça e grupos de idade | CSV (BR) |

**Links oficiais:**
- [Tabela 9542](https://sidra.ibge.gov.br/Tabela/9542)
- [Tabela 9543](https://sidra.ibge.gov.br/Tabela/9543)
- [Página da divulgação – Alfabetização](https://sidra.ibge.gov.br/pesquisa/censo-demografico/demografico-2022/universo-alfabetizacao)
- [Publicação completa (PDF)](https://biblioteca.ibge.gov.br/visualizacao/periodicos/3108/cd_2022_alfabetizacao.pdf)

---

## Arquitetura Atual

```text
SIDRA / IBGE
      ↓
 Download manual (CSV)
      ↓
 pandas + numpy
      ↓
 Dados processados
      ↓
 Power BI
```

**Tecnologias utilizadas até o momento:**
- Python (pandas, numpy)
- Jupyter Notebook
- Power BI (previsto)
- Git / GitHub
---

## Status Atual do Projeto

### Concluído
- [x] Definição do objetivo e escopo do módulo de Alfabetização
- [x] Identificação das tabelas oficiais do SIDRA (9542 e 9543)
- [x] Download dos dados (Brasil + Grandes Regiões + UFs)
- [x] Exploração inicial da estrutura dos arquivos CSV
- [x] Criação do dicionário de dados

### Em andamento
- [ ] Limpeza e transformação dos dados com pandas (formato tidy)
- [ ] Análise exploratória inicial

### Próximos passos
1. Transformar os arquivos de formato largo para formato longo (tidy)
2. Criar base processada limpa e documentada
3. Análise exploratória (taxas, diferenças regionais, desigualdades por sexo, cor/raça e idade)
4. Modelagem e construção do dashboard no Power BI
5. Documentação final do módulo

---

## Decisões Técnicas Importantes

- Os dados brutos **não são alterados**. Toda transformação é feita de forma reproduzível.
- Iniciamos apenas com Brasil, Regiões e UFs para manter o volume de dados gerenciável.
- Municípios serão adicionados posteriormente.
- Preferência por soluções simples (YAGNI).
- Documentação é atualizada continuamente.

---

## Como Executar (estado atual)

1. Clone o repositório
2. Crie um ambiente virtual e instale as dependências:
   ```bash
   pip install pandas numpy jupyter
   ```
3. Os arquivos brutos estão em `alfabetizacao/dados/brutos/`
4. A limpeza e análise serão desenvolvidas nos notebooks

---

## Limitações Atuais

- Ainda não inclui dados municipais
- Ainda não possui análise exploratória nem visualizações
- Ainda não possui dashboard
- A limpeza dos dados ainda está em andamento

---

## Referências

- IBGE. Censo Demográfico 2022: Alfabetização – Resultados do universo. Rio de Janeiro, 2024.
- SIDRA – Sistema IBGE de Recuperação Automática

---

**Última atualização:** 21/09/2026

---

Este README reflete exatamente o ponto em que estamos.  
Quer que eu ajuste alguma seção ou já partimos para a limpeza dos dados?