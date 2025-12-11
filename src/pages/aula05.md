---
layout: ../layouts/BaseLayout.astro
title: "Paradigma Imperativo e Programação Estruturada em C"
description: "Mapa mental premium sobre paradigma imperativo, programação estruturada e fundamentos da linguagem C."
---

# 🌟 Aula 05 — Paradigma Imperativo e Programação Estruturada em C

> 🧠 **Frase-âncora:** _Paradigma é óculos mental; imperativo é receita de passos; estruturado é código organizado em blocos._

---

## 🟦 1. Paradigma de programação — os “óculos mentais” do programador

### 🔹 O que é um paradigma de programação?

- É um **modelo mental** que orienta:
  - como pensamos o problema,
  - como organizamos o código,
  - quais estruturas privilegiamos.

> 🌟 **Metáfora:** Paradigma é um **par de óculos**.  
> Cada óculos muda **como você enxerga entrada, processamento e saída**.

### 🔹 Paradigmas citados na aula

- **Imperativo**
  - Foco no **como fazer** passo a passo.
- **Funcional**
  - Foco em **funções puras** e **imutabilidade**.
- **Lógico**
  - Foco em **regras e inferência lógica**.
- **Orientado a Objetos (OO)**
  - Foco em **classes, objetos, atributos e métodos**.

> 🧠 **Frase-âncora:** _Paradigma não é só sintaxe — é jeito de pensar o código._

---

## 🟦 2. Paradigma imperativo — o mundo das receitas

### 🔹 Ideia central do imperativo

- Descreve **uma sequência de comandos** que:
  - são executados em ordem,
  - alteram o **estado** do programa.

> 🌟 **Metáfora da cozinha:**  
> O programa é uma **receita de bolo**.  
> Cada linha de código é um **passo da receita** mudando o estado dos “ingredientes” (variáveis).

### 🔹 Conceito de estado

- **Estado** = conjunto de **variáveis + valores na memória** em um instante.
- Representa:
  - o que o programa **sabe**,
  - o que está **guardado**,
  - em que **situação** ele está.

Exemplo em C:

```c
int x;
x = 5;
```

- `x` é uma **caixa** na memória.
- `x = 5;` manda colocar o valor **5** nessa caixa.
- O estado “antes” e “depois” do comando é diferente.

> 🧠 **Frase-âncora:** _Estado é foto da memória; comando é ação que muda a foto._

### 🔹 Comandos no imperativo

- Um **comando** é uma instrução que:
  - lê, altera ou usa variáveis,
  - muda o estado do programa.

Exemplos de comandos típicos:

- atribuição: `x = x + 1;`
- leitura: `scanf("%d", &idade);`
- escrita: `printf("Oi\n");`
- controle: `if`, `for`, `while` etc.

> ✦ A maioria das linguagens populares (C, Java, Python, JavaScript, C++, PHP) tem **forte raiz imperativa**.

---

## 🟦 3. Programação estruturada — organizando o imperativo

### 🔹 O problema do “código espaguete”

Antes da programação estruturada:

- Uso intenso de `goto`.
- Saltos de um ponto para outro do código.
- Programas enormes, com um bloco único, difíceis de:
  - entender,
  - testar,
  - manter.

> 🌟 **Metáfora:** Código espaguete = **macarrão todo embolado**: você puxa um lado e tudo vem junto.

### 🔹 A proposta da programação estruturada

Objetivo: tornar o código:

- mais **legível**,
- mais **previsível**,
- mais **modular**.

Como?

- Organizando o código em **blocos lógicos**:
  - cada bloco com **início e fim** claros,
  - cada bloco com **uma função bem definida**.
- Usando apenas **três estruturas de controle básicas**:

1. **Sequência**

   - Instruções executadas uma após a outra.

2. **Decisão (seleção)**

   - `if`, `if...else`, `switch`.
   - Escolhem caminhos distintos.

3. **Repetição (iteração)**
   - `for`, `while`, `do...while`.
   - Executam um bloco várias vezes.

> 🧠 **Frase-âncora:** _Programação estruturada = imperativo com disciplina e blocos claros._

### 🔹 Dijkstra e o “fim do goto”

- Edsger Dijkstra escreveu o artigo **“Go To Statement Considered Harmful”**.
- Argumentou que `goto` torna o código:
  - difícil de seguir,
  - pouco confiável,
  - frágil.
- Defendeu o uso disciplinado de:
  - sequência,
  - seleção,
  - repetição.

> ✦ Resultado: a programação estruturada virou **base do ensino moderno de programação**.

---

## 🟦 4. Imperativo x Estruturado — como se relacionam?

### 🔹 Conceitos diferentes, mas complementares

- **Paradigma imperativo**

  - Diz **como o programa executa**: sequência de comandos e alteração de estado.

- **Programação estruturada**
  - Diz **como organizar** esses comandos: em blocos, funções e estruturas claras.

> 🧠 **Frase-âncora:** _Imperativo é o conteúdo; estruturado é a forma._

### 🔄 Tabela comparativa

| 🧠 Conceito           | Imperativo                  | Estruturado                              |
| --------------------- | --------------------------- | ---------------------------------------- |
| Foco principal        | Como executar passo a passo | Como organizar o código                  |
| Unidade de pensamento | Comando e estado            | Blocos, funções, sub-rotinas             |
| Objetivo              | Descrever o processo        | Aumentar legibilidade e manutenibilidade |
| Problema atacado      | Como realizar a tarefa      | Evitar código espaguete e caos no fluxo  |
| Relação entre eles    | Paradigma geral             | Estilo dentro do paradigma imperativo    |

---

## 🟦 5. Linguagem C como fio condutor

### 🔹 Origem da linguagem C

- Criada por **Dennis Ritchie** por volta de **1972**, nos laboratórios Bell.
- Objetivo:

  - criar uma linguagem que unisse:
    - **eficiência** (próxima do hardware),
    - **legibilidade** (mais próxima do humano).

- Usada, inicialmente, para desenvolver o **sistema operacional Unix**.

### 🔹 Por que C é tão importante?

- Combina:
  - controle de **baixo nível** (memória, ponteiros),
  - sintaxe de **alto nível** (estruturas, funções).
- Serve como base para:

  - sistemas operacionais,
  - compiladores,
  - bibliotecas,
  - drivers,
  - softwares de desempenho crítico.

- Influenciou diretamente:
  - C++, Java, C#, Objective-C, entre outras.

> 🧠 **Frase-âncora:** _Entender C é entender o “esqueleto” de muitas linguagens modernas._

---

## 🟦 6. Estrutura básica de um programa em C

### 🔹 Esqueleto mínimo

```c
#include <stdio.h>

int main() {
    // código aqui
    return 0;
}
```

Componentes:

- `#include <stdio.h>`

  - Inclui a biblioteca padrão de **entrada e saída** (`printf`, `scanf`).

- `int main()`

  - Função principal, **ponto de entrada** do programa.
  - É onde a execução começa.

- `return 0;`
  - Indica que o programa terminou **com sucesso**.

> 🌟 **Metáfora:** `main` é o **palco principal** da peça — é por onde o espetáculo começa.

### 🔹 Olá, mundo em C

```c
#include <stdio.h>

int main() {
    printf("Ola, mundo!\n");
    return 0;
}
```

- `printf` → imprime texto na tela.
- `\n` → quebra de linha.

> 🧠 **Frase-âncora:** _Todo programa em C começa no `main` e termina no `return`._

---

## 🟦 7. Variáveis, tipos e estado em C

### 🔹 Variáveis como “caixinhas” na memória

Exemplo:

```c
int idade;
float altura;
char inicial;
```

- `int` → números inteiros.
- `float` / `double` → números com ponto flutuante.
- `char` → um caractere.

> 🌟 **Imagem mental:**  
> Imagine uma **prateleira com caixas**:
>
> - cada caixa tem um **nome** (`idade`),
> - cada caixa guarda um **tipo de dado** específico.

### 🔹 Vetores (arrays) como “fileiras de caixas”

```c
int notas[10];
```

- `notas` = um **vetor de 10 inteiros**.
- Cada posição é acessada por um **índice**:
  - `notas[0]`, `notas[1]`, ..., `notas[9]`.

> 🧠 **Frase-âncora:** _Array é uma fileira de caixinhas numeradas._

---

## 🟦 8. Entrada e saída: `scanf` e `printf`

### 🔹 `printf` — saída (mostrar algo na tela)

```c
printf("Idade: %d, Altura: %.2f\n", idade, altura);
```

- `%d` → inteiro
- `%f` ou `%.2f` → float (com 2 casas decimais)
- `%s` → string
- `%c` → caractere

### 🔹 `scanf` — entrada (ler algo do usuário)

```c
scanf("%d", &idade);
scanf("%f", &altura);
```

- `&idade` → endereço de memória onde o valor lido será armazenado.
- O formato (`"%d"`, `"%f"`) precisa **combinar com o tipo** da variável.

> 🧠 **Frase-âncora:** _`scanf` coloca valor na caixa; `printf` mostra o que tem na caixa._

---

## 🟦 9. Controle condicional: `if`, `else`

### 🔹 Decisão no código

Permite que o programa **escolha caminhos diferentes** dependendo de uma condição.

Exemplo:

```c
if (idade >= 18) {
    printf("Maior de idade\n");
} else if (idade > 0 && idade < 18) {
    printf("Menor de idade\n");
} else {
    printf("Idade invalida\n");
}
```

- As condições são **expressões lógicas** que retornam verdadeiro ou falso.

> 🌟 **Metáfora:** `if` é uma **encruzilhada**: a condição decide o caminho.

### 🔹 Cuidado: `=` x `==`

- `=` → atribuição (muda o valor).
- `==` → comparação (pergunta se tem aquele valor).

> 🧠 **Frase-âncora:** _`=` muda, `==` pergunta._

---

## 🟦 10. Estruturas de repetição — laços (`for`, `while`, `do...while`)

### 🔹 Por que laços são importantes?

- Evitam reescrever o mesmo código várias vezes.
- Automatizam repetições.

### 🔹 `for` — quando você sabe quantas vezes vai repetir

Exemplo: tabuada

```c
int num;
scanf("%d", &num);

for (int i = 1; i <= 10; i++) {
    printf("%d x %d = %d\n", num, i, num * i);
}
```

- Três partes:
  1. inicialização (`int i = 1;`)
  2. condição (`i <= 10;`)
  3. atualização (`i++;`)

> 🧠 **Frase-âncora:** _Use `for` quando o número de repetições é conhecido._

### 🔹 `while` — repete **enquanto** a condição for verdadeira

```c
int numero;
scanf("%d", &numero);

while (numero != 0) {
    // processa numero
    scanf("%d", &numero);
}
```

- Útil quando a repetição depende de uma **condição externa**.

### 🔹 `do...while` — garante **pelo menos uma execução**

Exemplo: pedir senha até acertar

```c
int senha;

do {
    printf("Digite a senha: ");
    scanf("%d", &senha);
} while (senha != 1234);
```

> 🌟 **Metáfora visual:**
>
> - `while` → checa o crachá **antes** de entrar.
> - `do...while` → deixa entrar **uma vez**, depois confere se continua.

---

## 🟦 11. Funções e sub-rotinas — dividindo o problema

### 🔹 Por que usar funções?

- Para **não** escrever tudo dentro do `main`.
- Para:
  - organizar o código,
  - reaproveitar lógica,
  - facilitar testes e manutenção.

### 🔹 Exemplo de função simples

```c
int somar(int a, int b) {
    return a + b;
}

int main() {
    int x = 4, y = 5;
    int resultado = somar(x, y);
    printf("Resultado: %d\n", resultado);
    return 0;
}
```

- `somar` recebe dois inteiros e devolve um inteiro.
- `main` chama a função e usa o resultado.

> 🧠 **Frase-âncora:** _Função boa faz uma coisa bem definida._

### 🔹 Benefícios da modularização

- **Reutilização**: chama a mesma função em vários lugares.
- **Isolamento de erros**: se algo der errado, você sabe em qual função olhar.
- **Trabalho em equipe**: cada pessoa pode cuidar de funções diferentes.

---

## 🟦 12. Escopo de variáveis — onde a variável “vive”

### 🔹 Escopo local

- Variável declarada **dentro de uma função** ou bloco.

Exemplo:

```c
void exemplo() {
    int x = 10; // x é local à função exemplo
}
```

- Só existe **dentro** de `exemplo`.
- Some quando a função termina.

### 🔹 Escopo global

- Variável declarada **fora de qualquer função**:

```c
int contador_global;

int main() {
    contador_global = 10;
}
```

- Pode ser acessada por várias funções.

### 🔹 Boa prática

- Preferir **variáveis locais**.
- Usar globais apenas quando realmente necessário.

> 🧠 **Frase-âncora:** _Quanto mais local o escopo, mais fácil entender o código._

---

## 🟦 13. Boas práticas e armadilhas em C

### ✅ Boas práticas

- Dar **nomes significativos** às variáveis e funções:
  - `calcularMedia`, `notaAluno`, `imprimirMenu`.
- Manter funções **curtas e coesas**:
  - uma função = uma responsabilidade.
- Usar **indentação** consistente:
  - facilita ver blocos e estruturas.

### ❌ Erros comuns

- Não inicializar variáveis → pode ler **lixo de memória**.
- Criar **loops infinitos** (condição nunca se torna falsa).
- Usar `=` no lugar de `==` nas condições.
- Depender de `goto`, criando **código espaguete**.

> 🌟 **Frase-âncora:** _Código legível hoje = menos sofrimento amanhã._

---

## 🧠 Resumo Final para Revisão Rápida

> Use esta seção como revisão de véspera de prova.

- **Paradigma de programação**

  - É um **modelo mental** para organizar o raciocínio do código.
  - Exemplos: imperativo, funcional, lógico, OO.

- **Paradigma imperativo**

  - Trabalha com **estado + comandos**.
  - Código como **receita passo a passo**.
  - Presente em C, Java, Python, JS, etc.

- **Programação estruturada**

  - Surge como resposta ao **código espaguete** e ao abuso de `goto`.
  - Usa três estruturas básicas:
    - sequência,
    - decisão (`if`),
    - repetição (`for`, `while`, `do...while`).
  - Divide o problema em **funções e blocos lógicos**.

- **Linguagem C**

  - Criada por Dennis Ritchie (anos 70).
  - Ponte entre **hardware** e **linguagens modernas**.
  - Base de muitos sistemas operacionais e linguagens.

- **Conceitos-chave em C**
  - Variáveis e tipos (`int`, `float`, `char`, `double`).
  - Entrada/saída com `scanf` e `printf`.
  - Controle condicional com `if/else`.
  - Laços de repetição (`for`, `while`, `do...while`).
  - Funções e escopo (local x global).
  - Boas práticas: nomes claros, funções curtas, indentação.

---

## 🟦 Dicas de Memorização Ativa (Active Recall + Spaced Repetition)

### 🔁 1. Active Recall (lembrar sem olhar)

Feche o material e tente responder, de cabeça:

1. O que é **paradigma imperativo**?
2. Qual a diferença entre **imperativo** e **estruturado**?
3. Quais são as **três estruturas básicas** da programação estruturada?
4. Como é o **esqueleto mínimo** de um programa em C?
5. Qual a diferença entre `while` e `do...while`?

Se travar em alguma:

- Volte **apenas na seção específica**,
- Releia,
- Tente responder de novo depois de alguns minutos.

### ⏰ 2. Spaced Repetition (repetição espaçada)

Sugestão de revisão:

- **Dia 1 (hoje):**

  - Ler a aula inteira,
  - Rodar mentalmente 1 exemplo de `if` + 1 de `for` + 1 de função.

- **Dia 2:**

  - Revisar só:
    - seções 2 (imperativo), 3 (estruturada) e 6 (estrutura de C),
    - - o **resumo final**.

- **Dia 4:**

  - Tentar explicar em voz alta:
    - sem olhar,
    - a diferença entre `while` e `do...while`,
    - e entre imperativo e estruturado.

- **Dia 7 (véspera de prova):**
  - Ler **apenas o resumo final**,
  - Refazer mentalmente a estrutura de um programa em C (`main`, `printf`, `scanf`).

### 🧠 3. Mini-desafios de fixação

Sem olhar o material, tente:

1. Escrever um `if` que classifica idade em:
   - inválida,
   - menor de idade,
   - maior de idade.
2. Montar um `for` de tabuada de 1 a 10.
3. Explicar em **duas frases**:
   - o que é programação estruturada,
   - por que `goto` é problemático.
4. Escrever o esqueleto mínimo de um programa em C.

> 🌟 **Frase-âncora final:** _Aprender paradigma imperativo e C é aprender a pensar como o computador executa cada passo._
