# Guia Completo de Estatística e Análise Combinatória

Um guia didático para estudantes com explicações, fórmulas e exemplos práticos.

## Índice

1. [Medidas de Dispersão](#medidas-de-dispersão)
2. [Análise Combinatória](#análise-combinatória)
3. [Probabilidade](#probabilidade)
4. [Resumo de Fórmulas](#resumo-de-fórmulas)
5. [Exercícios Resolvidos](#exercícios-resolvidos)
6. [Recursos Adicionais](#recursos-adicionais)

## Medidas de Dispersão

As medidas de dispersão nos mostram o quanto os dados estão "espalhados" em relação à média.

### 🔍 Amplitude

**O que é?** A diferença entre o maior e o menor valor do conjunto de dados.

**Fórmula:** Amplitude = Valor máximo - Valor mínimo

**Exemplo visual:**
```
Dados: 5, 7, 10, 12, 15
       ^            ^
     Mínimo       Máximo
Amplitude = 15 - 5 = 10
```

### 📊 Variância

**O que é?** Mede o quanto cada valor do conjunto de dados se afasta da média.

**Fórmulas:**
- Populacional: σ² = Σ(x_i - μ)²/N
- Amostral: s² = Σ(x_i - x̄)²/(n-1)

**Dica para memorizar:** A variância é a "média dos quadrados dos desvios".

**Exemplo passo a passo:**
```
Dados: 4, 6, 8, 10

1. Média: (4+6+8+10)/4 = 7
2. Desvios: (4-7)=-3, (6-7)=-1, (8-7)=1, (10-7)=3
3. Quadrados: 9, 1, 1, 9
4. Soma dos quadrados: 20
5. Variância populacional: 20/4 = 5
6. Variância amostral: 20/3 ≈ 6,67
```

### 📏 Desvio Padrão

**O que é?** Raiz quadrada da variância. Tem a mesma unidade dos dados originais.

**Fórmulas:**
- Populacional: σ = √σ²
- Amostral: s = √s²

**Interpretação prática:**
- Em distribuições normais, aproximadamente 68% dos dados estão a 1 desvio padrão da média
- Aproximadamente 95% dos dados estão a 2 desvios padrão da média
- Aproximadamente 99,7% dos dados estão a 3 desvios padrão da média

![Regra 68-95-99.7](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8c/Standard_deviation_diagram.svg/500px-Standard_deviation_diagram.svg.png)

### 📈 Coeficiente de Variação

**O que é?** Medida relativa de dispersão que permite comparar a variabilidade de diferentes conjuntos.

**Fórmula:** CV = (Desvio Padrão/Média) × 100%

**Interpretação:**
- CV < 15%: Baixa dispersão (dados homogêneos)
- 15% ≤ CV < 30%: Média dispersão
- CV ≥ 30%: Alta dispersão (dados heterogêneos)

### 📦 Quartis e Amplitude Interquartílica

**O que são quartis?** Valores que dividem os dados ordenados em quatro partes iguais.

**Amplitude Interquartílica (AIQ):** Q3 - Q1

**Vantagem:** Menos sensível a valores extremos (outliers)

**Box Plot:** Representação visual dos quartis
```
    |---------|     |-----------|
Q1 -|         |---- Q2 ---------|--- Q3
    |---------|     |-----------|
```

## Análise Combinatória

A arte de contar possibilidades sem precisar enumerá-las.

### 🧮 Princípio Fundamental da Contagem

**O que é?** Se uma escolha A pode ser feita de m maneiras, e para cada uma dessas, uma escolha B pode ser feita de n maneiras, então há m × n maneiras de fazer as escolhas A e B em sequência.

**Exemplo visual:**
```
       Calças      ×     Camisas     =     Combinações
       (3 opções)        (4 opções)        (12 possibilidades)
       
       Jeans            Branca             Jeans + Branca
       Preta            Azul               Jeans + Azul
       Bege             Vermelha           Jeans + Vermelha
                        Verde              ...e assim por diante
```

### 🔄 Arranjo Simples

**O que é?** Agrupamentos ordenados onde a ordem importa e não há repetição.

**Fórmula:** A(n,p) = n!/(n-p)!

**Pergunta chave:** "De quantas maneiras diferentes posso ordenar p elementos dentre n elementos?"

**Exemplo prático:** Pódio com 1º, 2º e 3º lugares entre 10 competidores
```
A(10,3) = 10!/(10-3)! = 10!/7! = 10×9×8×7!/7! = 10×9×8 = 720
```

### 🔄 Permutação Simples

**O que é?** Caso especial de arranjo onde todos os elementos são utilizados (p = n).

**Fórmula:** P(n) = n!

**Exemplo prático:** Anagramas da palavra "AMOR"
```
P(4) = 4! = 4×3×2×1 = 24 anagramas possíveis
```

### 🔄 Permutação com Repetição

**O que é?** Permutação onde alguns elementos são repetidos.

**Fórmula:** P(n; a,b,...) = n!/(a!×b!×...)

**Exemplo prático:** Anagramas da palavra "CASA"
```
Total: 4 letras
C: aparece 1 vez
A: aparece 2 vezes
S: aparece 1 vez

P(4; 1,2,1) = 4!/(1!×2!×1!) = 24/2 = 12 anagramas possíveis
```

### 🔄 Combinação Simples

**O que é?** Agrupamentos não ordenados onde a ordem não importa e não há repetição.

**Fórmula:** C(n,p) = n!/(p!×(n-p)!)

**Pergunta chave:** "De quantas maneiras diferentes posso escolher p elementos dentre n elementos?"

**Exemplo prático:** Formar uma comissão de 3 pessoas dentre 7 funcionários
```
C(7,3) = 7!/(3!×4!) = 35 comissões possíveis
```

**Dica para não confundir arranjo e combinação:**
- Arranjo: **A**rranjo - **A** ordem é importante (**A**BC ≠ CBA)
- Combinação: **C**ombinação - **C**onjunto, a ordem não importa (ABC = CBA)

## Probabilidade

### 🎲 Conceitos Básicos

**Probabilidade clássica:** P(E) = Número de casos favoráveis / Número total de casos possíveis

**Exemplos:**
- Probabilidade de tirar uma carta de copas em um baralho: 13/52 = 1/4 = 25%
- Probabilidade de obter cara ao lançar uma moeda: 1/2 = 50%

### 🌐 Espaço Amostral e Eventos

**Espaço amostral (Ω):** Conjunto de todos os resultados possíveis
**Evento (E):** Subconjunto do espaço amostral

**Exemplo:** Lançamento de um dado
```
Espaço amostral: Ω = {1, 2, 3, 4, 5, 6}
Evento "número par": E = {2, 4, 6}
P(E) = 3/6 = 1/2 = 50%
```

### 🔄 Probabilidade Condicional

**O que é?** Probabilidade de um evento A ocorrer, sabendo que B já ocorreu.

**Fórmula:** P(A|B) = P(A ∩ B) / P(B)

**Exemplo visual:**
```
             ┌───────────┐
             │           │
             │     A     │
             │     ┌─────┼───┐
             │     │     │   │
             └─────┼─────┘   │
                   │      B  │
                   │         │
                   └─────────┘

P(A|B) = Área de interseção / Área de B
```

### 🔀 Teorema de Bayes

**Fórmula:** P(A|B) = [P(B|A) × P(A)] / P(B)

**Aplicação prática:** Muito usado em diagnósticos médicos, sistemas de spam, etc.

### 🔗 Eventos Independentes

**Definição:** A ocorrência de um evento não afeta a probabilidade de ocorrência do outro.

**Fórmula:** P(A ∩ B) = P(A) × P(B)

**Exemplo:** Lançar dois dados
```
P(primeiro dado = 6 e segundo dado = 5) = P(primeiro = 6) × P(segundo = 5) = 1/6 × 1/6 = 1/36
```

## Resumo de Fórmulas

| Conceito | Fórmula | Exemplo Prático |
|----------|---------|-----------------|
| Amplitude | Max - Min | Diferença entre maior e menor nota em uma turma |
| Variância populacional | σ² = Σ(x_i - μ)²/N | Dispersão dos salários em uma empresa |
| Desvio padrão | σ = √σ² | Variação média das temperaturas diárias |
| Coeficiente de variação | CV = (s/x̄) × 100% | Comparar variabilidade entre classes |
| Arranjo | A(n,p) = n!/(n-p)! | Formação de pódio em competição |
| Permutação | P(n) = n! | Diferentes formas de ordenar livros |
| Permutação com repetição | P(n; a,b,...) = n!/(a!×b!×...) | Anagramas de palavras com letras repetidas |
| Combinação | C(n,p) = n!/(p!×(n-p)!) | Formação de comissões |
| Probabilidade | P(E) = #casos favoráveis / #casos possíveis | Chance de acertar na loteria |
| Probabilidade condicional | P(A\|B) = P(A∩B)/P(B) | Probabilidade de chover dado que está nublado |
| Eventos independentes | P(A∩B) = P(A)×P(B) | Resultado de dois lançamentos de moeda |

## Exercícios Resolvidos

### Exercício 1: Medidas de Dispersão

**Problema:** Calcule média, variância e desvio padrão do conjunto {10, 12, 15, 18, 20}.

**Solução:**
1. Média: (10+12+15+18+20)/5 = 75/5 = 15
2. Desvios: -5, -3, 0, 3, 5
3. Quadrados dos desvios: 25, 9, 0, 9, 25
4. Soma dos quadrados: 68
5. Variância populacional: 68/5 = 13,6
6. Desvio padrão populacional: √13,6 ≈ 3,69

### Exercício 2: Análise Combinatória

**Problema:** Uma senha tem 5 dígitos, sem repetição. Quantas senhas possíveis existem com:
a) Qualquer dígito
b) Apenas dígitos pares

**Solução:**
a) A(10,5) = 10!/(10-5)! = 10!/5! = 30.240
b) Dígitos pares: {0, 2, 4, 6, 8} → 5 dígitos
   A(5,5) = 5! = 120

### Exercício 3: Probabilidade

**Problema:** Em uma sala com 25 pessoas, qual a probabilidade de pelo menos duas pessoas fazerem aniversário no mesmo dia?

**Solução:**
É mais fácil calcular o complemento: a probabilidade de todas as pessoas fazerem aniversário em dias diferentes.

P(diferentes) = 365/365 × 364/365 × 363/365 × ... × 341/365 ≈ 0,43

Então, P(pelo menos duas iguais) = 1 - 0,43 = 0,57 = 57%

## Recursos Adicionais

### 📚 Livros Recomendados
- "Estatística Básica" - Morettin e Bussab
- "Análise Combinatória e Probabilidade" - Morgado et al.

### 🔗 Sites Úteis
- [Khan Academy - Estatística](https://pt.khanacademy.org/math/statistics-probability)
- [Portal Action - Estatística](http://www.portalaction.com.br/)

### 📱 Aplicativos
- GeoGebra (para visualização de conceitos)
- Probability Calculator (para cálculos de probabilidade)

### 🎯 Dicas de Estudo
1. Pratique muitos exercícios diferentes
2. Crie flashcards com as fórmulas
3. Estude em grupo para discutir soluções de problemas
4. Busque aplicações práticas dos conceitos

---

### ⚠️ Erros Comuns a Evitar

1. Confundir arranjo e combinação
2. Esquecer de usar (n-1) no denominador da variância amostral
3. Não verificar se eventos são independentes antes de multiplicar probabilidades
4. Aplicar permutação quando há repetição sem considerar os elementos repetidos

---

*Este material é apenas um guia de estudo. Para um aprendizado completo, consulte seu professor e livros didáticos recomendados.* 