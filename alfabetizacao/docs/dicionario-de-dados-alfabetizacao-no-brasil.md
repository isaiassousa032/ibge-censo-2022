# Dicionário de Dados — Alfabetização no Brasil (Censo 2022)

**Projeto:** Censo 2022 - Retratos do Brasil  
**Módulo:** Alfabetização  
**Fontes principais:**  
- Tabela SIDRA 9542  
- Tabela SIDRA 9543  
- Publicação: *Censo Demográfico 2022: Alfabetização – Resultados do universo* (IBGE, 2024)

---

## 1. Identificação das Tabelas

| Código | Nome oficial | Conteúdo principal | Unidade |
|--------|--------------|--------------------|--------|
| **9542** | Pessoas de 15 anos ou mais de idade, total e as alfabetizadas, por sexo, cor ou raça e grupos de idade | Números absolutos (contagens) | Pessoas |
| **9543** | Taxa de alfabetização das pessoas de 15 anos ou mais de idade por sexo, cor ou raça e grupos de idade | Taxa de alfabetização | % (2 casas decimais) |

**Período:** 2022  
**Tipo de dados:** Universo (não amostra)

---

## 2. População de Referência

- Pessoas residentes no Brasil com **15 anos ou mais de idade**.
- A taxa de alfabetização e os contingentes referem-se exclusivamente a esse grupo etário.
- **Importante:** Não inclui a população de 5 a 14 anos (essa informação será divulgada em outro momento pelo IBGE).

---

## 3. Conceito Oficial de Alfabetização

Segundo o IBGE:

> Considera-se **alfabetizada** a pessoa que sabe ler e escrever pelo menos um bilhete simples ou uma lista de compras, no idioma que conhece (incluindo línguas indígenas), independentemente de estar ou não frequentando escola e de já ter concluído períodos letivos.

A pergunta do questionário básico era:  
**“Sabe ler e escrever?”**

---

## 4. Variáveis Principais

### Tabela 9542 (números absolutos)

| Variável | Descrição | Unidade |
|----------|-----------|--------|
| Pessoas de 15 anos ou mais de idade | Total de pessoas na faixa etária | Pessoas |
| Pessoas de 15 anos ou mais de idade alfabetizadas | Pessoas que sabem ler e escrever | Pessoas |
| Pessoas de 15 anos ou mais de idade não alfabetizadas | Pessoas que não sabem ler e escrever | Pessoas |

> Observação: A variável “Não alfabetizadas” pode ser calculada como:  
> `Total − Alfabetizadas`

### Tabela 9543 (taxa)

| Variável | Descrição | Unidade |
|----------|-----------|--------|
| Taxa de alfabetização das pessoas de 15 anos ou mais de idade | (Alfabetizadas / Total de 15 anos ou mais) × 100 | % |

---

## 5. Dimensões (Classificações)

### 5.1 Sexo

| Categoria | Descrição |
|-----------|-----------|
| Total | Homens + Mulheres |
| Homens | Pessoas do sexo masculino |
| Mulheres | Pessoas do sexo feminino |

### 5.2 Cor ou raça

| Categoria | Descrição |
|-----------|-----------|
| Total | Inclui todas as categorias + ignorados/omitidos |
| Branca | — |
| Preta | — |
| Amarela | — |
| Parda | — |
| Indígena | Ver nota especial abaixo |

**Nota importante sobre Indígena (Censo 2022):**

No Censo 2022, foi considerada indígena:
- A pessoa residente em localidades indígenas que se declarou indígena pelo quesito de cor ou raça **ou** pelo quesito “se considera indígena”;
- A pessoa residente fora de localidades indígenas que se declarou indígena no quesito de cor ou raça.

Por essa razão, o total de pessoas indígenas pode ser superior ao total de pessoas que se declararam apenas como “Indígena” no quesito de cor ou raça.

### 5.3 Grupos de idade

| Categoria | Descrição |
|-----------|-----------|
| Total | 15 anos ou mais |
| 15 a 19 anos | — |
| 20 a 24 anos | — |
| 25 a 34 anos | — |
| 35 a 44 anos | — |
| 45 a 54 anos | — |
| 55 a 64 anos | — |
| 65 anos ou mais | — |

> Observação: As tabelas originais também permitem idades isoladas (15 anos, 16 anos...), mas no recorte atual utilizamos apenas os grupos acima.

### 5.4 Alfabetização (apenas na tabela 9542)

| Categoria | Descrição |
|-----------|-----------|
| Total | Pessoas de 15 anos ou mais |
| Alfabetizadas | Pessoas que sabem ler e escrever |
| Não alfabetizadas | Pessoas que não sabem ler e escrever |

---

## 6. Níveis Territoriais Disponíveis

| Código SIDRA | Nível | Observação |
|--------------|-------|----------|
| N1 | Brasil | 1 unidade |
| N2 | Grande Região | 5 unidades (Norte, Nordeste, Sudeste, Sul, Centro-Oeste) |
| N3 | Unidade da Federação | 27 unidades |
| N6 | Município | 5.570 municípios (não baixado neste momento) |

No recorte atual do projeto estamos usando apenas **Brasil + Grandes Regiões + Unidades da Federação**.

---

## 7. Estrutura dos Arquivos Baixados

### Arquivo 9543 (Taxa)

Formato original (largo):

- Colunas de identificação: `Cód.`, território, `Idade`
- Depois: colunas de taxa para **Sexo × Cor ou raça**
  - Sem sufixo → Sexo = Total
  - Sufixo `.1` → Sexo = Homens
  - Sufixo `.2` → Sexo = Mulheres

### Arquivo 9542 (Absolutos)

Formato original (largo):

- Colunas de identificação: `Cód.`, território, `Cor ou raça`, `Idade`
- Depois: colunas de contagem para **Alfabetização × Sexo**
  - Sem sufixo → Total de pessoas
  - Sufixo `.1` → Alfabetizadas
  - Sufixo `.2` → Não alfabetizadas

---

## 8. Observações Técnicas Importantes

1. Os dados são do **Universo** (não da amostra).
2. A categoria **Total** de cor ou raça inclui os casos ignorados ou omitidos.
3. Os valores de taxa usam **vírgula** como separador decimal nos arquivos CSV originais do SIDRA.
4. Os códigos territoriais seguem o padrão oficial do IBGE (ex: 1 = Brasil, 33 = Rio de Janeiro, 35 = São Paulo etc.).
5. Não existem valores especiais (`-`, `...`, `X`) nos recortes que baixamos (Brasil, Regiões e UFs).

---

## 9. Fontes Oficiais

- SIDRA – Tabela 9542: https://sidra.ibge.gov.br/Tabela/9542  
- SIDRA – Tabela 9543: https://sidra.ibge.gov.br/Tabela/9543  
- Publicação completa: https://biblioteca.ibge.gov.br/visualizacao/periodicos/3108/cd_2022_alfabetizacao.pdf  
- Página da divulgação: https://sidra.ibge.gov.br/pesquisa/censo-demografico/demografico-2022/universo-alfabetizacao  

---

## 10. Histórico de Versões deste Dicionário

| Data | Versão | Alteração |
|------|--------|---------|
| 21/09/2026 | 1.0 | Criação inicial com base nas tabelas 9542 e 9543 (Brasil, Regiões e UFs) |