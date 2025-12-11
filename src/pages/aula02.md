---
layout: ../layouts/BaseLayout.astro
title: "Aula 02 – Tipos de Dados, Estruturas e Critérios de Projeto de Linguagens"
description: "Resumo otimizado com técnicas de neuroaprendizagem para facilitar memorização."
pubDate: "2025-12-11"
---

# 🌟 Aula 02 – Tipos de Dados, Estruturas e Critérios de Projeto de Linguagens

> ✦ **Frase-âncora geral:**  
> **“Entender tipos de dados é entender como o seu programa pensa e guarda informações.”**

---

## 🟦 1. Por que uma aula inteira só sobre tipos de dados?

### 🔹 1.1. Ideia central

- Tipos de dados são o **alicerce** de qualquer linguagem de programação.
- Eles determinam:
  - 🧠 **Como** a informação é representada na memória.
  - 🧠 **Como** ela pode ser manipulada.
  - 🧠 **Quais** erros são possíveis (ou impossíveis).
  - 🧠 **Quanta** segurança, legibilidade e eficiência o código terá.

> 🧠 **Imagem mental (Dual Coding):**  
> Imagine um **prédio de software**.  
> Os **tipos de dados** são o material de construção (concreto, madeira, vidro).  
> Se você escolhe mal o material, o prédio até fica de pé, mas começa a dar problema com o tempo.

### 🔹 1.2. Programar ≠ Entender tipos

- “Saber programar” não é o mesmo que **entender profundamente**:
  - tipos primitivos,
  - tipos complexos,
  - escopo,
  - tempo de vida,
  - conversões,
  - critérios de projeto da linguagem.
- Quem entende tipos de dados:
  - migra de linguagem com mais facilidade,
  - evita bugs sutis,
  - escreve código mais limpo e profissional.

> ✦ **Frase-âncora:**  
> **“Você não aprende só _Java_ ou _Python_; você aprende _como dados existem_ dentro do computador.”**

---

## 🟦 2. Critérios de projeto de linguagens e relação com tipos

### 🔹 2.1. Principais critérios

1. 🌟 **Legibilidade**

   - Nomes claros.
   - Estruturas simples.
   - Sintaxe consistente.
   - Facilita ler, revisar e manter o código.

2. 🌟 **Facilidade de escrita**

   - Menos regras arbitrárias.
   - Mais fácil transformar ideia em código.

3. 🌟 **Simplicidade e ortogonalidade**

   - Poucas regras, que se combinam bem.
   - Menos exceções estranhas.
   - Mais previsibilidade.

4. 🌟 **Confiabilidade**

   - Verificação de tipos.
   - Tratamento de exceções.
   - Menos bugs silenciosos.

5. 🌟 **Expressividade e abstração**
   - Código mais próximo do domínio do problema.
   - Facilita modelar conceitos reais sem sacrificar desempenho e segurança.

---

## 🟦 3. Ortogonalidade – o “jogo limpo” da linguagem

> 🧠 **Metáfora:**  
> Imagine um jogo de tabuleiro em que **todas as peças seguem regras simples e combináveis**.  
> Linguagens ortogonais são assim: poucas regras, que valem em todo lugar.

### 🔹 3.1. O que é ortogonalidade?

- **Ortogonalidade**: capacidade de combinar recursos da linguagem **sem criar exceções arbitrárias**.
- Em uma linguagem ortogonal:
  - Regras são poucas e previsíveis.
  - Combinações produzem menos “surpresas”.
  - Fica mais fácil **aprender, ler e manter** programas.

> ✦ **Frase-âncora:**  
> **“Ortogonalidade = poucas regras + muitas combinações sem surpresa.”**

---

## 🟦 4. Visão geral dos tipos de dados

### 🔹 4.1. Mapa mental (visão panorâmica)

- 🌟 **Tipos primitivos**
  - Inteiros
  - Reais (ponto flutuante)
  - Caracteres
  - Booleanos
- 🌟 **Estruturas compostas**
  - Strings
  - Vetores e matrizes
  - Registros (structs)
  - Listas, pilhas, filas
  - Coleções
- 🌟 **Endereços / ponteiros**
  - Apontam para posições na memória.
- 🌟 **Arquivos**
  - Dados permanentes fora da memória principal.

> 🧠 **Imagem mental:**  
> Pense em uma **casa de dados**:
>
> - Cada **tipo primitivo** é um cômodo simples.
> - Estruturas compostas são **conjuntos de cômodos** formando ambientes maiores.
> - Ponteiros são **post-its com o endereço do cômodo**.
> - Arquivos são o **arquivo morto no porão**, onde tudo fica guardado para sempre.

---

## 🟦 5. Tipos primitivos

### 🔹 5.1. Inteiros

- Representam números **sem parte fracionária**.
- Ex.: `int`, `short`, `long`, `byte` (dependendo da linguagem).
- Usos típicos:
  - contagem,
  - índices de vetores,
  - quantidades discretas (itens, pessoas, etc.).

### 🔹 5.2. Números de ponto flutuante

- Representam números **com parte fracionária**.
- Ex.: `float`, `double`.
- Usos:
  - medições,
  - cálculos científicos,
  - valores com casas decimais.
- ⚠️ **Cuidado:** possuem **limitações de precisão** (não representam todos os decimais exatamente).

### 🔹 5.3. Caractere e strings

- **Caractere (`char`)**: um único símbolo.  
  Ex.: `'A'`, `'9'`, `'?'`.
- **String**: sequência de caracteres.  
  Ex.: `"Douglas"`, `"Engenharia de Software"`.

> 🧠 **Insight histórico (Java):**  
> No início, trabalhar com texto deixava mais claro que strings são construídas **a partir de tipos primitivos**, mostrando como tipos simples podem gerar estruturas complexas.

### 🔹 5.4. Booleanos (lógicos)

- Representam **verdadeiro** ou **falso**.
- Base de:
  - condições (`if`, `while`),
  - comparações,
  - lógica de fluxo de controle.
- Em algumas linguagens mais antigas ou simples:
  - booleanos eram simulados com `0/1` ou `‘V’/‘F’`.

> ✦ **Frase-âncora:**  
> **“Booleanos são o volante do programa: guiam para onde o fluxo vai.”**

---

## 🟦 6. Declaração, nomes e inicialização de variáveis

### 🔹 6.1. Variáveis como “caixinhas”

- Variáveis são **caixas com etiqueta** onde o programa guarda dados.
- A declaração define:
  - 🧠 **tipo** do conteúdo,
  - 🧠 **nome** da variável,
  - 🧠 opcionalmente o **valor inicial**.

### 🔹 6.2. Boas práticas de nomes

- Evitar:
  - `x`, `y`, `z` (sem contexto),
  - siglas confusas.
- Preferir:
  - nomes semânticos, ex.:
    - `totalVendas`, `dataNascimento`, `quantidadeAlunos`.

> 🧠 **Metáfora:**  
> Etiquetas em caixas de mudança:
>
> - Caixa com a etiqueta **“X”** não ajuda ninguém.
> - Caixa com etiqueta **“Louças da cozinha – frágeis”** evita desastre.

### 🔹 6.3. Inicialização e “lixo de memória”

- Em muitas linguagens, variáveis **não inicializadas** podem conter:
  - **dados aleatórios** (lixo que sobrou na memória).
- Isso gera:
  - comportamento imprevisível,
  - bugs difíceis de rastrear.

**Boas práticas:**

- Sempre inicializar variáveis com:
  - `0`, `""`, `null`, `false` ou algum valor inicial válido **no contexto do problema**.

---

## 🟦 7. Escopo e tempo de vida das variáveis

### 🔹 7.1. Escopo

- **Escopo**: região do código onde a variável é **visível** e pode ser usada.

Tipos comuns de escopo:

- **Local**
  - Declarada dentro de uma função ou bloco.
  - Só existe ali dentro.
- **Global**
  - Visível em todo o programa (ou módulo).

> ✦ **Frase-âncora:**  
> **“Escopo é o ‘raio de visão’ da variável.”**

### 🔹 7.2. Tempo de vida

- Variáveis locais:
  - criadas quando o bloco começa,
  - destruídas quando o bloco termina.
- Variáveis globais ou de longa duração:
  - permanecem durante toda a execução (ou boa parte dela).

### 🔹 7.3. Exemplo clássico de armadilha

- Criar variável de contagem fora do laço `while`.
- Usar essa mesma variável em outros contextos sem redefinir.
- Resultado:
  - comportamento inesperado,
  - valores “contaminados”.

---

## 🟦 8. Atribuição x comparação

> 🧠 **Metáfora:**
>
> - **Atribuição** é “guardar algo na caixa”.
> - **Comparação** é “olhar o que está na caixa e verificar se é igual a outro valor”.

### 🔹 8.1. Diferença crucial

- **Atribuição**:
  - `x = 3` → coloca o valor `3` dentro de `x`.
- **Comparação**:
  - `x == 3` → pergunta “x é igual a 3?”.

Erro clássico:

```c
if (a = 3) {
    // ...
}
```

- Em algumas linguagens, isso:
  - **atribui** 3 a `a`,
  - o resultado da atribuição é considerado **verdadeiro**,
  - o `if` sempre entra.

> ✦ **Frase-âncora:**  
> **“Um igual (=) muda o valor. Dois iguais (==) fazem a pergunta.”**

---

## 🟦 9. Tipos inteiros: short, int, long – e impacto real

### 🔹 9.1. Diferença conceitual

- Todos representam **inteiros**, mas:
  - com **tamanhos de memória diferentes**,
  - e **faixas de valor diferentes**.

### 🔹 9.2. Quando faz diferença?

- Em **notebook moderno** com muito recurso:
  - quase não sente diferença prática.
- Em **dispositivos limitados** (IoT, microcontroladores, sensores, satélites):
  - memória é crítica,
  - energia é crítica,
  - escolhas erradas de tipo:
    - gastam memória à toa,
    - podem gerar sobrecarga de CPU e energia.

> 🧠 **Imagem mental:**  
> Usar um **caminhão** para levar uma única sacola de mercado:  
> funciona? Sim.  
> É eficiente? Não.

---

## 🟦 10. Conversão de tipos (casting e coerção)

### 🔹 10.1. Situações comuns

- Converter:
  - inteiro ↔ texto,
  - inteiro ↔ real,
  - texto → número,
  - etc.

### 🔹 10.2. Formas de conversão

- **Explícita (casting)**  
  Você avisa à linguagem que quer converter:

```java
double x = 10.5;
int y = (int) x; // y = 10 (perde a parte fracionária)
```

- **Implícita (coerção)**
  - A linguagem converte automaticamente quando consegue.

### 🔹 10.3. Riscos

- Perda de precisão (ex.: real → inteiro).
- Conversão inválida de string para número.
- Erros silenciosos em linguagens com muita coerção automática.

> ✦ **Frase-âncora:**  
> **“Sempre que possível, converta de forma explícita para não ter surpresa implícita.”**

---

## 🟦 11. Tipagem forte x tipagem fraca

### 🔹 11.1. Comparação em tabela

| Aspecto              | Tipagem forte           | Tipagem fraca                        |
| -------------------- | ----------------------- | ------------------------------------ |
| Mistura de tipos     | Mais restrita           | Mais flexível                        |
| Erros                | Detectados mais cedo    | Podem aparecer em tempo de execução  |
| Concisão             | Menos “atalhos mágicos” | Mais “atalhos”, mas com risco        |
| Exemplo de linguagem | Java, C#, Haskell       | JavaScript, PHP (em muitos cenários) |

### 🔹 11.2. Ideia central

- **Tipagem forte**:
  - Não deixa misturar tipos perigosamente sem conversão.
- **Tipagem fraca**:
  - Tenta adaptar valores automaticamente,
  - facilita escrever rápido,
  - aumenta risco de bugs sutis.

---

## 🟦 12. Tipagem estática x dinâmica

### 🔹 12.1. Comparação em tabela

| Aspecto              | Tipagem estática         | Tipagem dinâmica         |
| -------------------- | ------------------------ | ------------------------ |
| Momento de definição | Em tempo de compilação   | Em tempo de execução     |
| Detecção de erros    | Mais cedo (compile-time) | Mais tarde (runtime)     |
| Flexibilidade        | Menor                    | Maior                    |
| Exemplo de linguagem | Java, C, C#, Rust        | Python, JavaScript, Ruby |

### 🔹 12.2. Comentário

- Em tipagem dinâmica:
  - o **tipo pode mudar** quando outro valor é atribuído à variável,
  - a linguagem tenta resolver durante a execução.

> ✦ **Frase-âncora:**  
> **“Estática: o compilador te protege cedo. Dinâmica: a linguagem confia mais em você (e cobra em runtime).”**

---

## 🟦 13. Constantes e vinculação

### 🔹 13.1. Constantes

- Valores que **não mudam** durante a execução do programa.
- Protegem:
  - regras de negócio,
  - limites,
  - configurações críticas.

### 🔹 13.2. Boas práticas

- Usar constantes para:
  - limites de repetição,
  - parâmetros de negócio,
  - strings fixas importantes.
- Centralizar essas constantes em um único lugar (configuração).

> 🧠 **Metáfora:**  
> Constantes são **placas de trânsito fixas** no seu sistema.  
> Não é qualquer carro (função) que pode alterar o limite de velocidade.

---

## 🟦 14. Subrotinas: funções e procedimentos

### 🔹 14.1. O que são

- Blocos de código que:
  - executam uma tarefa específica,
  - podem ser reutilizados.
- Podem:
  - receber parâmetros,
  - retornar valores (funções),
  - ou apenas executar ações (procedimentos).

### 🔹 14.2. Contrato da subrotina

- Cabeçalho define:
  - parâmetros (tipos + nomes),
  - tipo de retorno (se houver).
- Esse contrato:
  - garante que quem chama sabe o que enviar e o que receber.

### 🔹 14.3. Pontos importantes

- Um ponto de entrada.
- Pontos de retorno bem definidos.
- Em recursão, cada chamada consome mais memória de pilha (stack).

---

## 🟦 15. Vetores e matrizes

### 🔹 15.1. Vetores

- Coleção **unidimensional** de elementos do mesmo tipo.
- Acesso por **índice numérico**.
- Em muitas linguagens, o tamanho é **fixo**.

### 🔹 15.2. Matrizes

- Vetores de vetores → estrutura **bidimensional**.
- Representadas como “linhas e colunas”.
- Usadas para:
  - tabelas,
  - grids,
  - dados estruturados em 2D.

### 🔹 15.3. Riscos

- Acessar índice fora dos limites:
  - gera erro em tempo de execução,
  - ou sobrescrita de memória (em linguagens de baixo nível).

---

## 🟦 16. Estruturas estáticas x dinâmicas

### 🔹 16.1. Comparação básica

| Estrutura      | Característica principal                                         |
| -------------- | ---------------------------------------------------------------- |
| Vetor estático | Tamanho fixo, acesso rápido, pouca flexibilidade                 |
| Lista dinâmica | Tamanho variável, mais flexível, custo maior em certas operações |

### 🔹 16.2. Exemplo prático

- Vetor estático:
  - ótimo quando você **já sabe** quantos elementos terá.
  - exemplo: leitura de um resultado com tamanho conhecido.
- Lista dinâmica:
  - cresce e diminui conforme inserções e remoções.
  - boa para cenários onde a quantidade varia.

---

## 🟦 17. Listas, filas e pilhas

### 🔹 17.1. Listas

- Coleções lineares que permitem:
  - inserir,
  - remover,
  - percorrer elementos.

### 🔹 17.2. Filas (Queue)

- Disciplina: **FIFO** (First In, First Out).
- 🧠 **Metáfora:** fila de banco.
- Usos:
  - processamento em ordem de chegada,
  - sistemas de atendimento,
  - filas de mensagens.

### 🔹 17.3. Pilhas (Stack)

- Disciplina: **LIFO** (Last In, First Out).
- 🧠 **Metáfora:** pilha de pratos – o último que entra é o primeiro a sair.
- Usos:
  - `Ctrl+Z` (desfazer),
  - histórico de navegação (botão voltar),
  - chamadas de função.

### 🔹 17.4. Tabela comparativa

| Estrutura | Ordem de saída                      | Metáfora        |
| --------- | ----------------------------------- | --------------- |
| Fila      | Primeiro entra, primeiro sai (FIFO) | Fila de banco   |
| Pilha     | Último entra, primeiro sai (LIFO)   | Pilha de pratos |

---

## 🟦 18. Registros (structs) – o “pré-objeto”

### 🔹 18.1. Conceito

- Estrutura que agrupa **campos de tipos diferentes** sob um único nome.
- Exemplo de registro “Pessoa”:
  - `nome: string`
  - `cpf: string`
  - `dataNascimento: data`

### 🔹 18.2. Relação com OO

- Registros são:
  - como um “rascunho” de objeto,
  - possuem **apenas dados** (atributos),
  - sem métodos.
- Orientação a objetos:
  - acrescenta **comportamentos** (métodos) a esses dados.

> ✦ **Frase-âncora:**  
> **“Registro é um objeto sem métodos; objeto é um registro com cérebro.”**

---

## 🟦 19. Arquivos: dados permanentes

### 🔹 19.1. O que são

- Estruturas gravadas em disco ou nuvem.
- Mantidas pelo **sistema operacional**.
- Permitem guardar dados **além** da execução do programa.

### 🔹 19.2. Relação com estruturas em memória

- Combinar:
  - registros,
  - vetores,
  - listas
- com leitura/gravação em arquivos permite:
  - carregar dados,
  - processar em memória,
  - salvar resultados.

---

## 🟦 20. Endereços, referências e ponteiros

### 🔹 20.1. Conceito

- Em vez de guardar o valor diretamente, variáveis podem guardar o **endereço na memória** onde o valor está.
- É assim que:
  - listas encadeadas,
  - árvores,
  - grafos,
  - e muitas estruturas complexas são implementadas.

### 🔹 20.2. Riscos

- Se o objeto apontado:
  - for destruído,
  - sair de escopo,
- a referência fica **inválida** (dangling pointer).
- Isso pode causar:
  - falhas de difícil rastreio,
  - comportamento indefinido.

---

## 🟦 21. Boas práticas com tipos de dados

### 🔹 21.1. Checklist mental

Use esta lista como checklist rápido:

- [ ] **Escolhi o tipo certo** para o domínio (inteiro, real, boolean, string...).
- [ ] **Inicializei** todas as variáveis.
- [ ] Evitei variáveis globais desnecessárias.
- [ ] Usei **constantes** para valores fixos de negócio.
- [ ] Nomeei variáveis e estruturas de forma **semântica**.
- [ ] Evitei conversões implícitas perigosas.
- [ ] Validei entradas externas (formulários, APIs, arquivos).

> ✦ **Frase-âncora final:**  
> **“Tipos certos + nomes claros + escopo bem definido = código confiável.”**

---

## 🟦 22. Erros frequentes relacionados a tipos de dados

- Usar `=` onde deveria ser `==`.
- Acessar índices fora do tamanho do vetor.
- Não inicializar variáveis.
- Misturar tipos em linguagens de tipagem fraca sem validar.
- Confiar cegamente em dados vindos de:
  - formulários,
  - APIs,
  - arquivos externos.

---

## 🟦 23. Resumo final para revisão rápida

> 🌟 **Use este bloco como revisão de véspera de prova.**

- Tipos de dados são **fundamento de toda linguagem**.
- Bons tipos tornam o código:
  - mais legível,
  - mais seguro,
  - mais eficiente.
- **Ortogonalidade** = poucas regras, muitas combinações, poucas surpresas.
- Tipos primitivos:
  - inteiros, reais, caracteres, booleanos.
- Strings = sequência de caracteres.
- Variáveis:
  - são “caixas com etiqueta”,
  - têm **escopo** e **tempo de vida**.
- Diferença crucial:
  - `=` atribui,
  - `==` compara.
- Tipagem:
  - **forte x fraca**,
  - **estática x dinâmica**.
- Constantes:
  - protegem regras fixas.
- Vetores e matrizes:
  - estruturam dados em 1D e 2D.
- Listas, filas e pilhas:
  - modelam ordens de processamento.
- Registros:
  - agrupam dados heterogêneos,
  - são o “pré-objeto”.
- Arquivos:
  - armazenam dados permanentemente.
- Ponteiros/referências:
  - apontam para endereços na memória,
  - exigem cuidado com escopo e tempo de vida.

---

## 🟦 24. Dicas de memorização ativa (Active Recall + Spaced Repetition)

### 🔹 24.1. Active Recall – testar a memória sem olhar

Responda **sem olhar o material** (só depois confira):

1. 🧠 O que é ortogonalidade em linguagens de programação?
2. 🧠 Qual a diferença entre tipagem forte e fraca?
3. 🧠 Explique, com um exemplo, a diferença entre `=` e `==`.
4. 🧠 Em que situação você escolheria vetor estático ao invés de lista dinâmica?
5. 🧠 O que é uma pilha e onde ela aparece no seu dia a dia de usuário?
6. 🧠 O que são registros e como eles se relacionam com orientação a objetos?

### 🔹 24.2. Spaced Repetition – estudar no tempo certo

Sugestão de ciclos:

- **Hoje (Dia 0)** → ler o material completo + responder as perguntas de Active Recall.
- **Daqui 1 dia** → revisar o resumo (Seção 23) + refazer pelo menos 3 perguntas.
- **Daqui 3–4 dias** → revisar os tópicos que você errou nas perguntas.
- **Na véspera da prova** → ler apenas:
  - as frases-âncora ✦,
  - o resumo final 🌟,
  - o checklist de boas práticas (Seção 21).

> 🌟 **Última frase-âncora para guardar:**  
> **“Dominar tipos de dados é sair do modo ‘apertador de botão’ e entrar no modo ‘engenheiro de software’.”**
