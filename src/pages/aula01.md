---
layout: ../layouts/BaseLayout.astro
title: "Aula 01 – Paradigmas de Linguagens de Programação"
description: "Revisão estruturada da aula 01 de Paradigmas de Linguagens de Programação: vocabulário, sintaxe, semântica, gramática formal (BNF), paradigmas imperativo, estruturado, orientado a objetos, funcional e lógico."
pubDate: "2025-12-11"
---

# Aula 01 – Paradigmas de Linguagens de Programação (Visão Geral)

> **Frase-âncora da aula:**  
> _“Paradigma é o **jeito de pensar** o problema. Linguagem é só a **ferramenta** para implementar esse jeito de pensar.”_

---

## 1. Abertura da disciplina

- Disciplina: **Paradigmas de Linguagens de Programação**
- Objetivo geral:
  - Ir **além do “como programar”** em uma linguagem específica
  - Entender **por que** as linguagens são diferentes
  - Desenvolver um **arsenal mental** de formas de pensar problemas
- Mesmo quem **não quer ser desenvolvedor full-time** se beneficia:
  - Entender melhor o que pedir de um time técnico
  - Saber escolher tecnologias com **critério técnico**, não só por modinha

---

## 2. Por que estudar paradigmas em vez de focar só em uma linguagem?

Muita gente pensa:

> “Por que não focar só em *uma linguagem* (a mais popular ou a que o mercado está pedindo) e pronto?”

O professor responde com duas ideias principais:

1. **Profundidade e adaptação**
   - Estudar **paradigmas** (jeitos de pensar) aumenta sua capacidade de:
     - Resolver problemas de formas diferentes
     - Se adaptar a novas linguagens com mais facilidade
2. **Escolha consciente de ferramentas**
   - Em vez de “Java porque é o que todo mundo usa”, pensar:
     - Que tipo de problema eu tenho?
     - Qual paradigma atende melhor?
     - Qual linguagem implementa bem esse paradigma?

> 💡 **Insight:**  
> “A melhor linguagem é a que **melhor resolve o problema** que você tem na mão, não a que está mais na moda.”

---

## 3. O que define uma linguagem de programação?

Uma linguagem de programação pode ser vista como um **idioma**, com:

1. **Vocabulário (tokens)**
   - Símbolos, palavras reservadas, operadores
   - Exemplos:
     - `if`, `while`, `for`
     - `+`, `-`, `=`, `==`

2. **Sintaxe (gramática)**
   - **Como escrever** corretamente
   - Regras de formatação e estrutura
   - Erro de sintaxe = erro de gramática → o compilador reclama

3. **Semântica (significado)**
   - **O que o código quer dizer / faz de verdade**
   - Um programa pode:
     - Compilar sem erros (sintaxe correta)
     - Mas ainda assim estar **semânticamente errado** (lógica errada)

4. **Ortogonalidade**
   - Medida de **consistência** da linguagem
   - Quanto **menos exceções e regras especiais**, mais previsível e simples de aprender
   - Linguagem pouco ortogonal:
     - Vários casos especiais
     - Mesmo recurso se comporta de jeitos diferentes dependendo do contexto
   - Linguagem mais ortogonal:
     - Combinar recursos é mais previsível
     - Menos “pegadinhas” de linguagem

---

## 4. Sintaxe x Semântica – por que isso cai tanto em prova e dá tanto bug?

### 4.1 Sintaxe

- Sintaxe = **como escrever**
- Exemplo de erro de sintaxe:
  - Esquecer `;`
  - Deixar parêntese ou chave sem fechar
- O compilador costuma acusar rápido:
  - “Unexpected token”
  - “Missing `;`”
  - Etc.

**Analogia com português:**

- Frase sintaticamente errada:
  - “Eu ir no mercado ontem”
- O sentido é até compreensível, mas a **gramática está errada**

### 4.2 Semântica

- Semântica = **o que o código significa / faz**
- Exemplo de erro semântico:
  - Usar `+` quando queria `-`
  - Fazer uma condição que **nunca** será verdadeira
  - Inverter `<` por `>` em uma comparação
- O compilador **não vê** a intenção, só vê se é válido sintaticamente

> ⚠️ **Perigo:**  
> Erros semânticos não impedem o código de compilar, mas podem **quebrar o negócio** em produção.

---

## 5. Gramática formal (BNF) e árvore sintática

Para descrever a sintaxe de uma linguagem **sem ambiguidade**, usamos **gramáticas formais**.

### 5.1 O que é BNF?

- BNF = **Backus–Naur Form**
- É uma **metalinguagem**:
  - Uma linguagem usada para **descrever outra linguagem**
- Serve para:
  - Definir todas as regras sintáticas de uma linguagem
  - Ser base para **compiladores** e **interpretadores**

### 5.2 Componentes básicos da BNF

- **Símbolos não terminais**:
  - Representam partes abstratas da linguagem
  - Geralmente escritos entre `<>`, por exemplo:
    - `<expr>`, `<var>`, `<stmt>`
- **Produções (regras)**:
  - Definem como um símbolo não terminal pode ser formado
  - Exemplo (forma genérica):
    ```bnf
    <assign> ::= <var> "=" <expr>
    ```
- **Símbolo inicial**:
  - Ponto de partida da gramática
  - Ex.: `<program>`

### 5.3 Árvores sintáticas

- Dada uma gramática em BNF, podemos construir uma **árvore sintática** para um comando concreto
- Ela mostra:
  - Como uma instrução é derivada da gramática
  - A estrutura **hierárquica** do código (do geral → para o específico)

Exemplo conceitual para:

```txt
x = x + y
```

- No topo: um nó que representa **atribuição**
- Nos ramos:
  - Nó para a variável `x` (lado esquerdo)
  - Nó para a expressão `x + y` (lado direito)
- Isso ajuda:
  - Compiladores a gerarem código
  - A gente a entender **ordem de avaliação**, precedência etc.

---

## 6. Visão geral dos paradigmas de programação

O professor apresenta primeiro uma **separação macro**:

- Paradigmas que tendem ao **procedural / imperativo**
- Paradigmas que tendem ao **declarativo**

Depois entra nos principais:

1. **Imperativo**
2. **Estruturado**
3. **Orientado a Objetos (OO)**
4. **Funcional**
5. **Lógico**

### 6.1 Paradigma imperativo

- Essência:
  - Dar **comandos diretos** ao computador, passo a passo
- Foco:
  - **Comandos** e **estado mutável**
  - Variáveis mudam de valor ao longo da execução
- Fluxo típico:
  - Sequência de instruções
  - Desvios (`if`)
  - Laços (`for`, `while`)
- Exemplos de linguagens:
  - C, BASIC, Pascal (e muitas outras)

**Analogia visual:**

- É fácil desenhar um programa imperativo como um **fluxograma**:
  - Começo → decisões → laços → fim

### 6.2 Programação estruturada (dentro do imperativo)

- Surge como uma **evolução** do paradigma imperativo
- Ideia central:
  - Organizar o código em partes menores:
    - **Funções**
    - **Procedures**
  - Reaproveitar código
  - Melhorar legibilidade e manutenção

Antes: muito uso de `GOTO` (principalmente em linguagens antigas como COBOL, Clipper etc.)

Depois:
- Divisão em **sub-rotinas**
- Conceitos de:
  - Variáveis **globais** x **locais**
  - Escopo
  - Passagem de parâmetros

> 💡 **Resumo:**  
> Programação estruturada ainda é imperativa, mas com **organização e modularização**.

### 6.3 Programação Orientada a Objetos (OO)

- Também uma **evolução** do paradigma imperativo
- Muda o foco:
  - De **procedimentos isolados** → para **objetos**
- Objeto:
  - Abstração de algo do **mundo real**
  - Junta:
    - **Dados** (atributos)
    - **Comportamentos** (métodos)

Exemplo:
- Classe `Pessoa`
  - Atributos: `nome`, `cpf`, `dataNascimento`
  - Métodos: `validarDataNascimento()`, `calcularIdade()`

#### Conceitos centrais de OO

- **Classe**: “molde” para criar objetos
- **Objeto**: instância de uma classe
- **Atributos**: dados do objeto
- **Métodos**: comportamentos do objeto
- **Encapsulamento**: esconder detalhes internos (visibilidade)
- **Herança**: reuso de comportamentos de uma classe base
- **Polimorfismo**: objetos diferentes se comportam de forma diferente usando a mesma “interface” de métodos

> ⚠️ Importante:  
> OO **não substitui** o imperativo; ela se apoia nele.  
> Dentro de um método, ainda escrevemos **if, for, while** de forma sequencial.

### 6.4 Paradigma funcional

- Muda o foco do “como” para o **“o que calcular”**
- Programa visto como **composição de funções matemáticas puras**
- Conceitos-chave:
  1. **Funções puras**
     - Mesma entrada → mesma saída
     - Sem efeitos colaterais (não mexem em variáveis globais, não alteram estado externo)
  2. **Imutabilidade**
     - Dados não são modificados
     - Em vez de “mudar um objeto”, criamos **uma nova versão** com o valor atualizado

- Linguagens clássicas:
  - Haskell, Scheme
- Linguagens multiparadigma com recursos funcionais:
  - Python, Java (streams, lambdas), JavaScript, etc.

### 6.5 Paradigma lógico

- É um paradigma **declarativo**
- Baseado em:
  - **Lógica formal**
  - Fatos
  - Regras
- Em vez de escrever passo a passo, você escreve:
  - **O que é verdade** no seu domínio
  - O programa responde a perguntas (**queries**) com base nisso

- Exemplo clássico:
  - **Prolog**
  - Usado em:
    - Inteligência Artificial
    - Sistemas especialistas
    - Bases de conhecimento

---

## 7. Declarativo x Procedural (imperativo)

O professor propõe uma divisão geral:

### 7.1 Paradigmas que tendem ao declarativo

- Focam em dizer **o que** deve ser verdade ou qual resultado queremos
- O “como chegar lá” fica a cargo do **sistema**
- Exemplos:
  - Funcional
  - Lógico
  - (e vários DSLs, linguagens de consulta, etc.)

### 7.2 Paradigmas que tendem ao procedural / imperativo

- Focam em dizer **como executar** passo a passo
- O programador define:
  - Sequência de comandos
  - Fluxo de controle
  - Mudanças de estado
- Exemplos:
  - Imperativo
  - Estruturado
  - Orientado a Objetos (por baixo, ainda imperativo)

---

## 8. Operadores, precedência, associatividade e tipagem

### 8.1 Precedência de operadores

- Define **a ordem** em que as operações são avaliadas
- Em aritmética:
  - `*` e `/` antes de `+` e `-`
- Em expressões lógicas:
  - Operadores relacionais (`>`, `<`, `==`) antes de
  - Operadores lógicos (`&&`, `||`)

### 8.2 Associatividade

Resolve ambiguidades quando operadores têm **mesma precedência**.

Exemplo:

```txt
5 - 3 + 2
```

Se a associatividade é da **esquerda para a direita**:

```txt
(5 - 3) + 2 = 4
```

> ✅ Regra prática:  
> Quando tiver dúvida, use **parênteses** para deixar a intenção explícita.

### 8.3 Ortogonalidade e sobrecarga de operadores

- Ortogonalidade baixa → muitas exceções
- Exemplo de sobrecarga de operador problemático:

```js
1 + 1      // 2 (número)
"1" + "1"  // "11" (string)
```

Isso pode gerar bugs se você **não souber** com quais tipos está lidando.

### 8.4 Tipagem: forte x fraca

- **Tipagem forte** (ex.: C, Java):
  - Conversões de tipo geralmente precisam ser **explícitas**
  - Compilador reclama mais rápido
- **Tipagem fraca** (ex.: JavaScript, PHP):
  - A linguagem converte tipos automaticamente em várias situações
  - Mais flexível, porém mais sujeita a “magias” inesperadas

> 💡 Boa prática:  
> Sempre validar os dados antes de converter,  
> e ter cuidado com **perda de informação** (ex.: float → int).

---

## 9. “Erros clássicos” comentados pelo professor

Alguns riscos conceituais que aparecem muito:

1. **Confundir “compilar” com “estar correto”**
   - “Compilou” ≠ “Está certo”
   - Compilar só garante:
     - Sintaxe correta
     - Tipos (mais ou menos) compatíveis
   - A lógica pode estar completamente errada

2. **Esquecer parênteses em expressões complexas**
   - Pode mudar a ordem da avaliação
   - Resultados numéricos ou lógicos errados

3. **Confiar demais em operadores sobrecarregados**
   - Ex.: `+` ser soma ou concatenação
   - Em tipagem fraca, isso piora

4. **Ignorar escopo e tipagem**
   - Variável global alterada por engano
   - Sombra de variáveis (mesmo nome em escopos diferentes)

---

## 10. Como isso conversa com sua formação de engenheiro de software?

A disciplina não é “só teoria chata”:

- Ajuda você a:
  - Ler códigos em linguagens diferentes sem entrar em pânico
  - Avaliar tecnologias para um projeto real
  - Evitar bugs por confusão de sintaxe/semântica
- Cria base para matérias futuras:
  - Compiladores
  - Arquitetura de software
  - Linguagens específicas (Java, C#, JS, etc.)

---

## 11. Dicas extra de estudo (neuroaprendizagem)

Sugestões alinhadas com a fala do professor (tornar o conteúdo menos “denso”):

1. **Estude fazendo paralelos com português**
   - Sintaxe da linguagem ↔ gramática da língua
   - Semântica ↔ significado da frase

2. **Monte pequenos exemplos próprios**
   - Ex.: escrever um `if` sintaticamente correto, mas semanticamente errado
   - Rodar e ver o resultado inesperado

3. **Desenhe mini árvores sintáticas**
   - Para expressões tipo `x = a + b * c`
   - Isso ajuda a fixar precedência

4. **Compare paradigmas em um quadro**
   - Imperativo x OO x Funcional x Lógico
   - Colunas: foco, estado, estilo mental, exemplos de linguagem

---

## 12. Para a próxima aula

Tarefas sugeridas:

- Tente:
  1. Escrever 3 exemplos de **erros de sintaxe**
  2. Escrever 3 exemplos de **erros de semântica**
- Em cada exemplo, anotar:
  - Se o código compila ou não
  - Por que o resultado está errado (no caso semântico)

> 💡 Dica:  
> Guardar esses exemplos em um repositório ou caderno digital.  
> Eles viram um “catálogo de bugs clássicos” para revisar antes da prova.

---

## Fim da Revisão da Aula 01

Esta página resume a **aula 01** de Paradigmas de Linguagens de Programação, baseada na fala do professor:
- Conceitos de **vocabulário, sintaxe, semântica, BNF e árvores sintáticas**
- Visão geral dos principais **paradigmas** (imperativo, estruturado, OO, funcional, lógico)
- Discussão sobre **precedência, associatividade, tipagem e ortogonalidade**
- Dicas práticas para **prova** e para a vida real como engenheiro de software.
