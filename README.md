# Calculadora de Mecânica dos Solos

Aplicativo web (um único arquivo HTML, sem dependências) para cálculos de mecânica dos solos, baseado na tabela "Fórmulas de correlação para Índices Físicos".

Você escolhe **o que quer calcular**, informa **o que tem**, e o programa:

- encontra automaticamente o caminho de cálculo (encadeando fórmulas quando necessário);
- mostra o **resultado**;
- mostra o **passo a passo** com a fórmula e a substituição numérica;
- lista as **fórmulas alternativas** que também servem e avisa se os resultados divergem;
- indica o que falta preencher quando os dados ainda não bastam.

## Como usar

Abra o `index.html` no navegador. Não precisa instalar nada.

Se o GitHub Pages estiver ativado no repositório, o app também fica disponível online.

## Assuntos cobertos

| Grupo | Exemplos |
|---|---|
| Índices físicos | e, η, Sr, ω, γ, γd, γsat, γ′, γs, Gs, DR |
| Plasticidade | IP, IL, IA, LL, LP |
| Granulometria | Cu, Cc, D10 |
| Permeabilidade | Darcy, Hazen, permeâmetros de carga constante e variável |
| Tensões e empuxos | σv, σ′v, u, K0, Ka, Kp, Ea, Ep, E0, τf |
| Adensamento | Cc, Cs, mv, av, recalque, Tv, U, Cv (Taylor e Casagrande) |

## Convenções

- Unidades coerentes (kN, m, kPa). Ângulos em graus.
- γw padrão = 10 kN/m³ (editável).
- ω, η, Sr, DR e U são digitados em % e tratados internamente como decimal.

## Como adicionar uma fórmula

Em `index.html`, cada fórmula é uma linha na constante `R`, no formato:

```
alvo|expressão|descrição|condição (opcional)
```

Exemplo: `gd|gs/(1+e)|por γs e e`

Variáveis novas entram no objeto `C` (símbolo, nome, unidade; 4º item `1` se for percentual). O motor usa as variáveis da expressão para decidir sozinho quando a fórmula é aplicável.

## Aviso

Ferramenta de apoio ao estudo e ao pré-dimensionamento. Confira os resultados e a aplicabilidade de cada correlação empírica antes de usar em projeto.
