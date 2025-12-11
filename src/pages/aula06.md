---
layout: ../layouts/BaseLayout.astro
title: "Aula 06 – Programação Imperativa em C (Tipos, Entrada/Saída e Boas Práticas)"
description: "Revisão em formato de mapa mental: tipos de dados em C, entrada e saída, strings, arquivos, ponteiros, casting, erros e boas práticas."
---

# 🌟 Aula 06 – Programação Imperativa em C

**Paradigma Imperativo Estruturado + Tipos, Entrada/Saída e Boas Práticas**

> 🧠 **Frase-âncora da aula:**  
> **"Dados + Controle bem organizados = programas confiáveis, portáteis e fáceis de testar."**

---

## 🟦 1. Extensão Universitária (Contexto do Curso)

### 🔹 O que é extensão universitária?

- A partir de **2023**, o **MEC** exige que cursos de ensino superior tenham **no mínimo 10% da carga horária** em atividades de **extensão**.
- Exemplo:
  - Curso com **3.400 horas** → você precisa de **340 horas de extensão**.
  - Mesmo aprovado em todas as disciplinas, **sem as horas de extensão não recebe o diploma**.

### 🔹 Como participar?

- A universidade oferece **projetos de extensão** na própria plataforma.
- Caminho típico:
  - Menu lateral → **Extensão**
  - Botão **"Quero participar"** ou **"Inscreva-se"**
- Também é possível:
  - **Sugerir novos projetos** (aba “Faça parte” ou similar).
  - Consultar um **site específico de extensão** com FAQ e orientações.

> ✦ **Frase-âncora:**  
> **"Extensão não é opcional: é parte obrigatória da graduação."**

---

## 🟦 2. Roteiro da Aula 06

🌟 **Foco da aula:**  
Trabalhar, na prática, com **programação imperativa estruturada em C**, revisando:

1. **Fundamentos do paradigma imperativo estruturado**
2. **Tipos de dados em C** (inteiros, ponto flutuante, char, strings)
3. **Arrays e matrizes**
4. **Ponteiros e relação com arrays**
5. **Entrada e saída com `stdio.h`**
6. **Leitura segura: `scanf`, `fgets`, `sscanf`**
7. **Arquivos: `fopen`, `fprintf`, `fscanf`, `fclose`**
8. **Tratamento de erros, overflow e conversões de tipo**
9. **Boas práticas de interação com o usuário**
10. **Gancho para a próxima aula: C++ e orientação a objetos**

> 🧠 **Imagem mental:**  
> Imagine um **painel de controle**:
>
> - de um lado, **dados** (tipos, variáveis, arrays);
> - do outro, **controle** (sequência, seleção, repetição, I/O).  
>   A aula junta esses dois mundos.

---

## 🟦 3. Paradigma Imperativo Estruturado – Recap geral

### 🔹 As 3 estruturas básicas

1. **Sequência**

   - Instruções executadas em **ordem**, linha após linha.
   - 🧠 Pense como uma **receita de bolo**: passo 1, depois passo 2…

2. **Seleção (decisão)**

   - Escolha de caminhos diferentes com base em **condições**.
   - Ex: `if`, `else`, `switch`.
   - 🧠 Visual: um **cruzamento de rua** com placas “se… então…”.

3. **Repetição (laços)**
   - Executar um **bloco de código várias vezes**.
   - Ex: `for`, `while`, `do…while`.
   - 🧠 Visual: uma **roda gigante** passando várias vezes pelo mesmo ponto.

> ✦ **Frase-âncora:**  
> **"Imperativo estruturado = Sequência + Seleção + Repetição bem organizadas."**

### 🔹 Decomposição top-down

- Quebrar um programa grande em **funções menores**, com:
  - **variáveis locais**
  - **escopo bem definido**
- Vantagens:
  - reduz interferência entre partes do código
  - facilita testes
  - deixa o programa mais legível

> 🧠 Pense em um **quebra-cabeça**: você monta peças pequenas (funções) que se unem em uma figura maior (programa).

---

## 🟦 4. Tipos de Dados em C – Tijolos do programa

### 4.1 Inteiros (`int`, `unsigned`, tamanhos fixos)

🔹 **Tipos inteiros básicos:**

- `int` – inteiro “padrão” da implementação
- `unsigned int` – apenas valores **sem sinal** (0, 1, 2, …)
- Podem existir variações: `short`, `long`, `long long`, com ou sem `unsigned`.

🧠 **Ponto chave:**  
O tamanho (em bits) de um `int` **depende do compilador/plataforma**.  
Por isso **não assuma** que `int` tem 32 bits.

---

### 4.2 Tipos de largura fixa (`stdint.h`)

Para **portabilidade** e previsibilidade:

- Use a biblioteca **`<stdint.h>`**:
  - `int32_t` → inteiro **com sinal** de 32 bits
  - `uint32_t` → inteiro **sem sinal** de 32 bits
  - `int64_t`, `uint64_t` etc.

> ✦ **Frase-âncora:**  
> **"`stdint.h` = tipos com tamanho garantido → menos surpresas entre plataformas."**

---

### 4.3 Ponto flutuante (`float` e `double`)

- `float` → precisão simples
- `double` → **dupla precisão** (mais exato, mais memória)

🧠 **Ideia importante:**  
Números de ponto flutuante são **aproximações** → sempre há pequenos erros.

#### ⚠️ Comparação de `float`/`double`

- **Evite** usar `==` diretamente para comparar dois `double`.
- Use uma **tolerância (epsilon)**:

```c
double a, b;
double eps = 0.000001;
if (fabs(a - b) < eps) {
    // Considerar "iguais"
}
```

> 🌟 **Frase-âncora:**  
> **"Ponto flutuante não é exato, é aproximado."**

---

### 4.4 Caracteres e `char`

- `char` representa um **byte**.
- Pode ser **assinado ou não assinado**, dependendo do compilador.
- Usado para:
  - caracteres simples → `'a'`, `'b'`, `'0'`
  - construir **strings** (vetores de `char`).

#### Caracteres de escape (visualize na tela)

- `\n` → quebra de linha
- `\t` → tabulação
- `\\` → barra invertida
- `\'` → aspas simples
- `\"` → aspas duplas

🧠 **Imagem mental:**  
Pense nesses escapes como **atalhos invisíveis** que controlam “como o texto aparece” na tela.

---

### 4.5 Encoding (UTF-8, ISO, ASCII)

- Definem **como bytes são interpretados como caracteres**.
- Padrões comuns:
  - `ASCII`
  - `ISO-8859-1`
  - `UTF-8`
- Em ambientes diferentes:
  - Linux costuma lidar bem com `UTF-8`
  - Windows pode exibir acentos errados se encoding não estiver ajustado

> ✦ **Frase-âncora:**  
> **"Encoding é a legenda dos bytes: sem a legenda certa, os acentos viram bagunça."**

---

## 🟦 5. Strings em C – Arrays de `char` + terminador nulo

### 🔹 Como uma string é representada?

- Em C, **string** = vetor de `char` **terminado por `'\0'`**.
- Exemplo:

```c
char s[6] = "Ola!";  // 'O' 'l' 'a' '!' '\0'
```

🧠 **Regra de ouro:**

- Sempre reserve **1 byte extra** para o `'\0'`.
- Se quer armazenar 5 caracteres, o vetor precisa de **pelo menos 6 posições**.

---

### 🔹 Biblioteca `<string.h>`

Funções úteis (todas dependem do `'\0'` corretamente posicionado):

| Função    | O que faz                             |
| --------- | ------------------------------------- |
| `strlen`  | Tamanho da string (sem contar `'\0'`) |
| `strcpy`  | Copia string origem → destino         |
| `strcat`  | Concatena (anexa) strings             |
| `strcmp`  | Compara strings lexicograficamente    |
| `strncmp` | Compara até N caracteres              |
| `strchr`  | Busca um caractere dentro da string   |
| `strstr`  | Busca substring dentro de outra       |

⚠️ **Risco clássico:**  
Copiar para um buffer **menor que a string de origem** → **overflow de buffer** (corrupção de memória e vulnerabilidades).

> 🌟 **Frase-âncora:**  
> **"String em C = char[] + '\0' + cuidado com o tamanho."**

---

## 🟦 6. Arrays e Matrizes

### 6.1 Arrays (vetores)

- Estrutura para guardar **vários valores do mesmo tipo**, indexados.
- Em C, índices começam em **0**.

```c
int v[10]; // índices de 0 a 9
```

⚠️ **Erro comum:**  
Acessar `v[10]` (ou maior) → acesso fora do array (undefined behavior).

---

### 6.2 Matrizes (arrays multidimensionais)

- Matriz = **array de array**.

```c
int m[3][4]; // 3 linhas, 4 colunas
```

🧠 **Visual:**  
Pense como uma **planilha**: linhas e colunas.

- Em memória, é um grande bloco linear; o compilador faz a “conta” para achar cada célula.

---

### 6.3 Arrays em funções

- Quando passamos um array para uma função, ele vira **ponteiro para o primeiro elemento**.

```c
void processa(int v[], int n);
```

- Por isso é comum passar também o **tamanho** (`n`).

> ✦ **Frase-âncora:**  
> **"Array vira ponteiro quando entra na função."**

---

## 🟦 7. Ponteiros – Endereço de memória

### 🔹 O que é um ponteiro?

- Variável que guarda um **endereço de memória**.
- Sintaxe básica:

```c
int x = 10;
int *px = &x; // px aponta para x
```

- `&x` → “endereço de x”
- `*px` → valor armazenado no endereço apontado por `px`

🧠 **Imagem mental:**  
Ponteiro é um **post-it com o número do apartamento** (endereço).  
Com o post-it, você pode ir até o apartamento e ver/alterar o que tem lá.

---

### 🔹 Ponteiros e `scanf`

- Para que `scanf` escreva dentro da variável, precisamos passar o **endereço**:

```c
int valor;
scanf("%d", &valor); // &valor = ponteiro
```

- Exceção: **strings** (`char[]`) já se comportam como ponteiro, então:

```c
char nome[100];
scanf("%s", nome); // sem &
```

> 🌟 **Frase-âncora:**  
> **"scanf escreve no endereço → passe o & (exceto em strings)."**

---

## 🟦 8. Entrada e Saída com `stdio.h`

### 8.1 Streams padrão

- `stdin` → entrada padrão (teclado)
- `stdout` → saída padrão (console)
- `stderr` → saída de erro (erros e mensagens importantes)

---

### 8.2 `printf` – Saída formatada

- Usado para exibir textos e valores formatados:

```c
printf("Valor: %d\n", x);
```

Principais **especificadores**:

| Especificador | Tipo                                    |
| ------------- | --------------------------------------- |
| `%d`          | `int` com sinal                         |
| `%u`          | `unsigned int`                          |
| `%c`          | `char`                                  |
| `%f`          | `float` / `double`                      |
| `%lf`         | `double` (implementações mais estritas) |
| `%s`          | string (`char*`)                        |

🔹 Controle de casas decimais:

```c
printf("%.2f\n", valor); // 2 casas decimais
```

🔹 Mostrar `%`:

```c
printf("50%% concluído\n"); // imprime 50%
```

---

### 8.3 `scanf` – Entrada formatada

Sintaxe geral:

```c
scanf("formato", &var1, &var2, ...);
```

Exemplos:

```c
int idade;
double altura;
scanf("%d %lf", &idade, &altura);
```

⚠️ **Armadilhas:**

- `scanf` retorna o **número de itens lidos com sucesso**:
  - Sempre que puder, verifique:

```c
if (scanf("%d", &idade) != 1) {
    // entrada inválida
}
```

- Ao misturar leitura numérica com leitura de caracteres, pode sobrar um `'\n'` no buffer e estragar a próxima leitura de `char`.

---

### 8.4 Leitura segura com `fgets` + `sscanf`

🟦 **Padrão robusto:**

1. Ler **uma linha inteira** com `fgets` (evita overflow).
2. Interpretar o conteúdo com `sscanf`.

```c
char linha[100];
if (fgets(linha, sizeof(linha), stdin)) {
    int idade;
    if (sscanf(linha, "%d", &idade) == 1) {
        // idade válida
    } else {
        // erro de conversão
    }
}
```

> 🧠 **Frase-âncora:**  
> **"fgets primeiro, sscanf depois → entrada mais segura e controlada."**

---

## 🟦 9. Arquivos em C – Gravando e lendo dados

### 9.1 Abertura de arquivos (`fopen`)

```c
FILE *f = fopen("dados.txt", "w");
if (f == NULL) {
    // erro ao abrir/criar arquivo
}
```

Principais modos:

| Modo                     | Significado                           |
| ------------------------ | ------------------------------------- |
| `"r"`                    | leitura (arquivo deve existir)        |
| `"w"`                    | escrita (cria ou sobrescreve)         |
| `"a"`                    | append (escrever no final do arquivo) |
| `"r+"` / `"w+"` / `"a+"` | variações leitura+escrita             |

---

### 9.2 Escrita e leitura

🔹 Escrita formatada:

```c
fprintf(f, "Nome: %s - Nota: %.2f\n", nome, nota);
```

🔹 Leitura formatada:

```c
char nome[100];
double nota;
fscanf(f, "%s %lf", nome, &nota);
```

🔹 Leitura de linha com `fgets`:

```c
char linha[128];
while (fgets(linha, sizeof(linha), f)) {
    // processa a linha
}
```

---

### 9.3 Fechando arquivos (`fclose`)

- Sempre feche o arquivo depois de usar:

```c
fclose(f);
```

Motivos:

- liberar recursos
- garantir que o conteúdo do buffer seja realmente gravado no disco
- evitar arquivos “travados” por outro processo

> ✦ **Frase-âncora:**  
> **"Abriu com fopen → feche com fclose."**

---

## 🟦 10. Tratamento de Erros, Overflow e Conversão de Tipos

### 10.1 Overflow

- Acontece quando o **valor ultrapassa o limite** que o tipo consegue armazenar.
- Exemplo:
  - Guardar um valor muito grande em um `int` de 16 bits.
  - Converter um `double` enorme para `int`.

🧠 **Imagem mental:**  
Imagine tentar colocar 20 litros de água em um balde de 10 litros: vai transbordar (overflow).

---

### 10.2 Conversão de tipos (casting)

- **Implícita:** acontece automaticamente (ex: `int` → `double` em operações).
- **Explícita (cast):** você indica o tipo desejado:

```c
int a = 5, b = 2;
double r = (double)a / b; // 2.5
```

- Conversão de `double` para `int` **trunca** o valor.

> 🌟 **Frase-âncora:**  
> **"Casting deixa claro para o compilador (e para quem lê) o tipo de resultado esperado."**

---

### 10.3 Funções para conversão de string em número

- `strtol` → string para `long`
- `strtod` → string para `double`
- Mais antigas: `atoi`, `atof` (menos seguras)

Padrão seguro:

- Analise onde o parse parou para saber se a conversão foi completa.

---

### 10.4 Tratamento de erro com `perror`

- Quando uma função de arquivo falha, você pode chamar:

```c
perror("Erro ao abrir arquivo");
```

- Mostra uma mensagem como:
  - `arquivo não encontrado`
  - `permissão negada`

---

## 🟦 11. Boas Práticas de Interação com o Usuário

### 🔹 Prompts claros

- Antes de `scanf` ou `fgets`, sempre explique **o que o usuário deve digitar**:

```c
printf("Digite sua idade em anos: ");
```

- Evite mensagens vagas.

---

### 🔹 Validação de entrada

- Sempre que possível:
  - verifique retornos de `scanf`, `fgets`, `sscanf`
  - reapresente o prompt em caso de erro
  - explique o problema: “valor inválido”, “faixa permitida”, etc.

---

### 🔹 Saída organizada

- Use quebras de linha (`\n`) e espaçamentos para:

  - alinhar colunas
  - criar tabelas simples
  - facilitar a leitura visual

> 🧠 **Frase-âncora:**  
> **"Programa robusto = entra dados válidos, trata erros, explica o que deu errado."**

---

## 🟦 12. Exercícios da Aula (visão de alto nível)

Na aula, o professor mostrou **exemplos práticos** em C, como:

1. **Somar dois números**

   - Ler dois inteiros com `scanf`
   - Mostrar a soma com `printf`

2. **Ler um inteiro e um caractere**

   - Mostrar entrada inválida se o tipo não bater
   - Exercitar uso de `scanf` e ponteiros

3. **Ler nome completo com `fgets`**

   - Exemplo de limite de tamanho e remoção de `\n`
   - Detecção de nome “muito longo” em relação ao buffer

4. **Calcular média de N números**

   - Ler N
   - Ler N valores em um laço
   - Contar quantos são `< 6` e `>= 6`
   - Calcular média e exibir estatísticas

5. **Registrar nome e notas em arquivo**
   - Abrir arquivo em modo append (`"a"`)
   - `fprintf` para gravar nome + notas
   - Reabrir arquivo e listar registros

> 🌟 **Frase-âncora:**  
> **"Teoria só fixa quando vira código rodando."**

---

## 🟦 13. Gancho para a Próxima Aula – C++ e Orientação a Objetos

- C++ surgiu como uma **evolução de C**, adicionando:
  - suporte a **orientação a objetos** (classes, objetos, métodos)
  - **fluxos** de entrada e saída com `cin` e `cout` (`<iostream>`)
  - `std::getline` para ler linhas completas

🧠 **Imagem mental:**  
Se C é uma **caixa de ferramentas clássica**, C++ adiciona uma **nova camada** com ferramentas para modelar objetos, classes e abstrações maiores.

---

# 🧠 Resumo Final para Revisão Rápida

🌟 **Em 10 linhas:**

1. Extensão universitária é obrigatória: **10% da carga horária** do curso.
2. Paradigma imperativo estruturado = **sequência + seleção + repetição**.
3. Use tipos adequados: inteiros, `float`/`double`, `char`, strings (`char[] + '\0'`).
4. Para portabilidade, prefira tipos de largura fixa de **`stdint.h`** (ex: `int32_t`).
5. Strings precisam de **1 byte extra** para o terminador `'\0'`.
6. Arrays começam em **índice 0**; matrizes são arrays de arrays.
7. Ponteiros guardam **endereços** e são essenciais em `scanf` e manipulação de arrays.
8. `printf` e `scanf` usam **especificadores de formato**: cuidado com o tipo e com o `&`.
9. Para leitura segura, use **`fgets` + `sscanf`**, e verifique retornos de funções.
10. Arquivos: abra com `fopen`, manipule com `fprintf`/`fscanf`/`fgets`, feche com `fclose`.

> ✦ **Frase-chave do resumo:**  
> **"Dominar tipos, I/O e ponteiros em C é construir a base para todo o resto da programação de baixo nível."**

---

# 🔁 Dicas de Memorização Ativa (Active Recall + Spaced Repetition)

### 🧠 Active Recall – Puxe da memória, não só releia

Use perguntas como flashcards:

1. **O que é necessário para uma string ser válida em C?**
2. **Por que não podemos comparar `double` com `==` diretamente?**
3. **Qual a diferença entre `w` e `a` em `fopen`?**
4. **Por que precisamos passar `&` em `scanf`? Quando não precisamos?**
5. **O que `fgets` faz de diferente em relação a `scanf("%s", ...)`?**

Tente responder **sem olhar** o material. Depois confira.

---

### ⏱️ Spaced Repetition – Repetição espaçada

Sugestão de revisão para essa aula:

- **Dia 1 (hoje):**  
  Ler a aula completa, fazer 1 ou 2 exemplos simples em C (somar números, ler nome).
- **Dia 2:**  
  Revisar só o **resumo final** + responder as perguntas de Active Recall.
- **Dia 4:**  
  Focar em **strings, ponteiros e leitura segura (`fgets` + `sscanf`)**.  
  Implementar um mini-programa que lê nome, idade e grava em arquivo.
- **Dia 7:**  
  Revisão geral de tudo (tipos, I/O, arquivos) + exercícios práticos maiores.

> 🌟 **Mantra de estudo:**  
> **"Revisar menos vezes, mas de forma ativa, vale mais do que reler muitas vezes de forma passiva."**

---

✨ Fim da **Aula 06 – Material Premium de Revisão**  
Use este arquivo como seu **mapa mental guiado** antes das provas de Programação em C e Paradigmas Imperativos.
