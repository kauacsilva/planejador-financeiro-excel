# Planejador Financeiro em Excel | Simulação Patrimonial e Perfil de Investidor

Projeto desenvolvido no **Microsoft Excel** para organizar informações financeiras pessoais, estimar a reserva de emergência e simular a evolução de investimentos com aportes mensais e juros compostos. 

> **Escopo:** ferramenta de planejamento e simulação financeira. Os números apresentados são projeções condicionadas às premissas inseridas na planilha, **não resultados históricos ou garantias de rentabilidade**.

## Sumário

- [Visão geral](#visão-geral)
- [Objetivos e perguntas analíticas](#objetivos-e-perguntas-analíticas)
- [Funcionalidades e organização da planilha](#funcionalidades-e-organização-da-planilha)
- [Ferramentas e metodologia](#ferramentas-e-metodologia)
- [Como utilizar](#como-utilizar)
- [Melhorias futuras](#melhorias-futuras)
- [Autor e contato](#autor-e-contato)

## Visão geral 

O planejamento financeiro exige relacionar **renda, despesas, capacidade de poupança, reserva de emergência e objetivos de investimento**. 

Este projeto reúne essas informações em uma pasta de trabalho do Excel, combinando campos de entrada, cálculos automáticos, indicadores financeiros, comparação entre horizontes de investimento e um gráfico de evolução patrimonial.


## Objetivos e perguntas analíticas

- **Capacidade financeira:** qual é a renda mensal total, quanto é gasto e qual valor permanece disponível?
- **Sugestão de aporte:** quanto corresponderia a um percentual definido da renda total?
- **Segurança financeira:** qual seria a meta de reserva de emergência e quanto falta para alcançá-la?
- **Projeção patrimonial:** quanto pode ser acumulado ao investir um valor mensal durante determinado período, considerando uma taxa fixa de rendimento?
- **Comparação de cenários:** como variam o total aportado e o patrimônio projetado nos prazos de 2, 5, 10, 20 e 30 anos?
- **Perfil de investidor:** como um aporte pode ser distribuído entre categorias de FIIs nos perfis Conservador, Moderado e Agressivo?

## Funcionalidades e organização da planilha

A pasta de trabalho contém **quatro abas**, com funções complementares:

| Aba | Finalidade | Recursos identificados |
| --- | --- | --- |
| `Planilha` | Painel principal de planejamento financeiro | Entradas de renda e despesas, percentual sugerido para investimento, cálculo de reserva, simulação de patrimônio, cenários e gráfico de linhas. |
| `Perfil ` | Distribuição de aportes por perfil | Seleção do perfil em lista suspensa; cálculo automático dos percentuais e valores mensais para seis categorias de FIIs. O nome da aba contém um espaço ao final. |
| `Base do perfil` | Base de referência interna | Matriz com 18 combinações entre três perfis e seis tipos de FIIs, usada nas consultas da aba de perfil. |
| `Evolução` | Base de cálculo do gráfico | Série de apoio com pontos de tempo, total investido, patrimônio projetado e rendimento acumulado; fórmulas vinculadas ao planejamento principal. |

### Recursos disponíveis

- Preenchimento de **salário, renda extra, custo de vida, percentual para investir, reserva atual, aporte mensal, prazo e taxa de rendimento**.
- Cálculo automático de renda total, saldo mensal, valor sugerido para investimento, meta de reserva e valor restante para atingir essa meta.
- Simulação com **aportes mensais e capitalização composta**, utilizando a função de valor futuro do Excel.
- Comparação de cenários de investimento para cinco horizontes temporais predefinidos.
- Gráfico de linhas com três séries: **Patrimônio**, **Total investido** e **Rendimento acumulado**.
- Seleção entre **Conservador**, **Moderado** e **Agressivo**, com consulta à base interna de percentuais de FIIs.

## Ferramentas e metodologia

### Ferramenta utilizada

**Microsoft Excel (`.xlsx`)**, com:

| Recurso | Aplicação no projeto |
| --- | --- |
| Fórmulas aritméticas e referências entre células/abas | Cálculos de orçamento, reserva e projeções. |
| `FV` (valor futuro; `VF` em algumas versões em português) | Simulação de patrimônio com aportes recorrentes e taxa mensal fixa. |
| `PROCV` | Recuperação do percentual de cada categoria de FII a partir do perfil escolhido. |
| `IF` (`SE`) e `MAX` (`MÁXIMO`) | Definição de mensagens e do prazo mínimo exibido no gráfico. |
| Concatenação com `&` e intervalos nomeados | Construção de chaves de consulta e organização das referências das fórmulas. |
| Validação de dados | Lista suspensa para o perfil de investidor e restrição de número inteiro para o prazo de investimento. |
| Gráfico de linhas | Comparação visual entre patrimônio, aportes e rendimento acumulado. |

### Fluxo de cálculo

1. O usuário informa as **informações financeiras** na aba `Planilha`.
2. As fórmulas calculam **disponibilidade mensal** e **necessidade de reserva de emergência**.
3. O valor do aporte, o prazo e a taxa mensal alimentam a **simulação de juros compostos**.
4. A aba `Evolução` organiza as séries utilizadas no gráfico do painel.
5. Na aba `Perfil `, uma seleção é combinada ao tipo de FII para localizar, na `Base do perfil`, o percentual aplicável e calcular o valor correspondente ao aporte.

## Resultados da simulação

Os números abaixo correspondem aos **valores de exemplo presentes no arquivo analisado**. Representam o estado atual da planilha, não dados financeiros de uma pessoa identificada nem retornos efetivamente realizados.

### Premissas preenchidas

| Parâmetro | Valor no arquivo |
| --- | ---: |
| Salário mensal | R$ 3.400,00 |
| Renda extra mensal | R$ 400,00 |
| Renda total calculada | R$ 3.800,00 |
| Custo de vida mensal | R$ 2.500,00 |
| Sobra mensal calculada | R$ 1.300,00 |
| Percentual usado no aporte sugerido | 20% |
| Valor sugerido para investir | R$ 760,00 |
| Aporte mensal utilizado nas projeções | R$ 1.000,00 |
| Prazo da simulação principal | 10 anos |
| Rendimento mensal hipotético | 1% |
| Meta de reserva de emergência | R$ 15.000,00 |
| Reserva atual informada | R$ 3.000,00 |
| Valor restante para a reserva | R$ 12.000,00 |

### Comparação entre prazos

Com aporte de **R$ 1.000,00 por mês** e rendimento constante hipotético de **1% ao mês**:

| Prazo | Total investido | Patrimônio projetado | Rendimento acumulado projetado |
| ---: | ---: | ---: | ---: |
| 2 anos | R$ 24.000,00 | R$ 26.973,46 | R$ 2.973,46 |
| 5 anos | R$ 60.000,00 | R$ 81.669,67 | R$ 21.669,67 |
| **10 anos** | **R$ 120.000,00** | **R$ 230.038,69** | **R$ 110.038,69** |
| 20 anos | R$ 240.000,00 | R$ 989.255,37 | R$ 749.255,37 |
| 30 anos | R$ 360.000,00 | R$ 3.494.964,13 | R$ 3.134.964,13 |


## Como utilizar

1. Faça o download de [Planejador_Financeiro.xlsx](Planejador_Financeiro.xlsx) e abra o arquivo no **Microsoft Excel**.
2. Na aba `Planilha`, preencha os campos de entrada de **salário, renda extra, custo de vida e percentual desejado para investimento**.
3. Informe os dados da **reserva de emergência**: número de meses e valor já reservado.
4. Configure **valor do aporte mensal, prazo em anos e taxa de rendimento mensal** para observar os resultados e cenários calculados.
5. Consulte o **gráfico de evolução** no painel principal e, se necessário, a série de apoio na aba `Evolução`.
6. Na aba `Perfil `, escolha **Conservador, Moderado ou Agressivo** para visualizar a distribuição percentual e monetária do aporte entre as categorias de FIIs.
7. Salve uma cópia do arquivo para preservar os valores originais de exemplo.

**Atenção:** a aba `Base do perfil` contém os percentuais de referência e a aba `Evolução` contém cálculos de apoio. Alterá-las pode modificar a lógica da solução. As fórmulas recalculam os resultados com base nas entradas; não foi identificada integração com uma fonte externa que demande atualização de dados.

## Melhorias futuras

- Adicionar validações para impedir valores incompatíveis, como taxas ou aportes inadequados ao contexto de cálculo.
- Incluir cenários de taxas de rentabilidade variáveis.
- Permitir simulações com inflação, tributos e custos, diferenciando valores nominais, reais, brutos e líquidos.
- Vincular a uma ferramenta de controle de gastos mensais e anuais. 

## Autor e contato

- **Autor:** Kauã Castro
- **LinkedIn:** [https://www.linkedin.com/in/kauã-castro]

---

*Este projeto tem finalidade demonstrativa e educacional. Não constitui recomendação individualizada de investimento.*
