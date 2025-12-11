---
layout: ../layouts/BaseLayout.astro
title: "Aula 07 – Programação Orientada a Objetos (POO)"
description: "Como pensar, modelar e programar usando **Programação Orientada a Objetos (POO)."
---

# Aula 07 – Programação Orientada a Objetos (POO)

🌟 **Tema central da aula:**  
Como pensar, modelar e programar usando **Programação Orientada a Objetos (POO)**, a partir dos conceitos de **classe, objeto, atributo, método, abstração, encapsulamento e modelagem** nas linguagens **C++ e Java**.

> 🧠 **Frase‑âncora geral:**  
> “POO é o paradigma que organiza código em torno de **objetos do mundo real**, com **estado** (atributos) e **comportamento** (métodos).”

---

## 🟦 1. Por que usar Programação Orientada a Objetos?

### 🔹 1.1 O problema a resolver

Antes da POO, já existiam linguagens **estruturadas/procedurais** (como C) baseadas em:

- variáveis soltas
- funções soltas
- controle de fluxo (`if`, `while`, `for`)

Isso funciona, mas em sistemas maiores gera:

- código espalhado
- dificuldade de manutenção
- dificuldade de entender “quem é responsável por quê”

### 🔹 1.2 A ideia da POO

A POO surge como **evolução do paradigma imperativo**, NÃO como substituição.

> ✦ **Frase‑âncora:**  
> “POO = paradigma imperativo organizado em torno de objetos.”

Ela traz:

- **Organização em unidades lógicas** (classes)
- **Relacionamento com o mundo real** (cliente, produto, venda, aluno, jogo…)
- **Encapsulamento** de dados + regras no mesmo lugar
- **Modularidade**: funções menores, especializadas, fáceis de manter
- **Reuso**: classes podem ser reaproveitadas em vários contextos

### 🔹 1.3 Por que é importante profissionalmente?

Linguagens muito usadas no mercado são orientadas a objetos:

- Java
- C++
- C#
- Python (suporta POO)
- PHP moderno, entre outras

> 🧠 **Frase‑âncora:**  
> “Entender POO é entender a base de grande parte dos sistemas usados em empresas hoje.”

---

## 🟦 2. Visão geral da POO – o “quadrilátero” fundamental

Pense em um **mapa mental** com 4 nós principais:

1. **Classe**
2. **Objeto**
3. **Atributo**
4. **Método**

### 🔹 2.1 Classe

- É o **molde**, **forma**, **projeto**.
- Define **que dados** o objeto terá (atributos) e **que ações** poderá realizar (métodos).

> ✦ Metáfora:  
> Classe = **projeto da casa**.

### 🔹 2.2 Objeto

- É a **instância concreta** criada a partir da classe.
- Vive na memória durante a execução.

> ✦ Metáfora:  
> Objeto = **casa construída** usando o projeto.

Exemplo mental:

- Classe: `Animal`
- Objetos: `cachorro`, `gato`

### 🔹 2.3 Atributos

- São os **dados** (estado) associados ao objeto.
- Em POO: costumam ser **variáveis de médio ou longo prazo** para aquele objeto.

Exemplos:

- `nome`, `idade`, `preco`, `cpf`

### 🔹 2.4 Métodos

- São as **ações** (comportamentos) do objeto.
- Acessam e alteram os atributos de forma **controlada**.

Exemplos:

- `caminhar()`, `comer()`, `calcularTotal()`, `aplicarDesconto()`

---

## 🟦 3. Exemplo visual: Classe Animal

Imagine uma caixinha (classe) escrita **Animal**, com três áreas:

1. **Nome da classe**
2. **Atributos**
3. **Métodos**

```text
+----------------------+
|        Animal        |
+----------------------+
| - nome               |
| - idade              |
+----------------------+
| + caminhar()         |
| + comer()            |
+----------------------+
```

Possíveis objetos:

- `perro` (cachorro)
- `gato`

Ambos são **Animal**, mas têm:

- `nome` diferente
- `idade` diferente
- mesmos métodos (`caminhar`, `comer`), com comportamento semelhante aplicado a dados distintos.

> 🧠 **Frase‑âncora:**  
> “Classe define; objeto concretiza.”

---

## 🟦 4. Abstração – focar no essencial

### 🔹 4.1 O que é abstração?

**Abstração** = decidir **quais características importam** para o problema e **ignorar o resto**.

> ✦ Metáfora:  
> Como desenhar um mapa: você não desenha cada tijolo da cidade, só o que importa para se localizar.

### 🔹 4.2 Exemplo: Classe Aluno

Na vida real, uma pessoa pode ter:

- CPF, RG, CNH
- endereço completo
- cor dos olhos, altura, peso
- redes sociais, etc.

Mas, para um **sistema de universidade**, talvez bastem:

- `cpf`
- `nome`
- `dataNascimento`

Tudo o que **não for necessário** para o objetivo do sistema… fica de fora da classe.

> 🧠 **Frase‑âncora:**  
> “Abstração = ignorar o que não é necessário para o problema.”

### 🔹 4.3 Fronteiras entre entidades

Outro exemplo:

- `Aluno` tem um **endereço**.
- Mas **Endereço** também pode pertencer a `Professor`, `Fornecedor`, etc.

Nesse caso, o endereço pode virar **outra classe** (`Endereco`), em vez de “colar” tudo dentro de `Aluno`.

---

## 🟦 5. Atributos x Variáveis locais

Esse é um ponto em que muitos erram. Vamos separar com um quadro mental.

### 🔹 5.1 Diferença principal

| 🧠 Tipo            | Onde é declarado?                      | Duração na memória              | Uso típico                             |
| ------------------ | -------------------------------------- | ------------------------------- | -------------------------------------- |
| **Atributo**       | Dentro da classe, **fora** dos métodos | Enquanto o objeto existir       | Estado permanente (nome, idade, preço) |
| **Variável local** | **Dentro** de um método ou parâmetro   | Só durante a execução do método | Cálculos temporários, respostas, flags |

> ✦ Frase‑âncora:  
> “Atributo = estado duradouro – Variável local = apoio temporário.”

### 🔹 5.2 Riscos comuns

❌ Usar atributo como variável temporária:

- Polui o estado do objeto.
- Pode deixar a classe em um estado **incoerente**.
- Outras partes do código podem ler valores que **não fazem mais sentido**.

✅ Boa prática:

- Use **atributos** apenas para dados que representam a **essência** do objeto.
- Use **variáveis locais** para cálculos intermediários e decisões temporárias.

---

## 🟦 6. Encapsulamento – protegendo o estado do objeto

### 🔹 6.1 Ideia central

**Encapsulamento** = esconder detalhes internos da classe e expor somente o que é necessário por meio de **métodos públicos**.

Na prática:

- Atributos → normalmente **`private`**
- Acesso ao valor → via **getters e setters**

> 🧠 Frase‑âncora:  
> “Ninguém mexe direto no meu atributo; passa pelo método.”

### 🔹 6.2 Modificadores de acesso (Java)

- `private` → só a própria classe vê
- `protected` → classes do mesmo pacote + subclasses
- `public` → qualquer código pode acessar

Em outras linguagens:

- C++ também usa `public`, `private`, `protected`, mas com regras específicas.
- Em Python, usa‑se convenções como `_atributo` (underline) para indicar “não mexa”.

### 🔹 6.3 Por que isso importa?

Exemplo: atributo `idade`.

- Regra da realidade: **idade não pode ser negativa**.

Se o atributo `idade` for `public`:

```java
pessoa.idade = -10; // ninguém impede
```

Se for `private` e existir um `setIdade()`:

```java
public void setIdade(int idade) {
    if (idade >= 0) {
        this.idade = idade;
    } else {
        // regra de erro / tratamento
    }
}
```

Agora:

- Nenhum código externo consegue quebrar a regra.
- Toda modificação passa pelo “porteiro” (o método `set`).

> ✦ Metáfora visual:  
> Atributos são **cofre**; métodos públicos são **porta com senha**.

---

## 🟦 7. Getters e Setters – acesso controlado

### 🔹 7.1 O que são?

São métodos especiais:

- `getX()` → devolve o valor de um atributo.
- `setX()` → altera o valor de um atributo, com regras de validação.

### 🔹 7.2 Funções típicas

- Garantir que **não entre dado inválido** (preço negativo, idade negativa etc.).
- Devolver o dado **formatado** (ex.: preço com 2 casas decimais).
- Manter **invariantes** do sistema (regras que sempre devem ser verdadeiras).

> 🧠 Frase‑âncora:  
> “Getter mostra, setter protege.”

### 🔹 7.3 Integração com frameworks

Muitos frameworks (especialmente em Java) se apoiam fortemente em getters e setters para:

- mapear objetos para banco de dados
- serializar para JSON
- integrar com bibliotecas externas

Então, além de boas práticas, eles se tornam **necessários** em muitos cenários.

---

## 🟦 8. Organização de código: pacotes, namespaces e repositórios

### 🔹 8.1 Por que agrupar classes?

Em sistemas reais, podemos ter **dezenas ou centenas de classes**.

Organização típica:

- Pacotes (Java): `br.unicesumar.sistema`
- Namespaces (C++): `namespace sistema { ... }`

Isso facilita:

- localizar as classes
- separar responsabilidades
- controlar visibilidade entre módulos

### 🔹 8.2 Exemplo visual de pacotes

Imagine a estrutura:

```text
br
 └─ unicesumar
     └─ sistema
         ├─ modelo
         │   ├─ Pessoa
         │   ├─ Produto
         │   └─ Venda
         └─ repositorio
             ├─ PessoaRepositorio
             ├─ ProdutoRepositorio
             └─ VendaRepositorio
```

Separação:

- **modelo/domínio**: classes que representam coisas do mundo real (Pessoa, Produto, Venda…)
- **repositório**: classes responsáveis por **armazenar/buscar** essas entidades (CRUD)

> ✦ Frase‑âncora:  
> “Modelo representa; repositório persiste.”

---

## 🟦 9. Modelagem com classes – do problema ao diagrama

### 🔹 9.1 Objetivo da modelagem

A modelagem com **diagramas de classes UML** ajuda a:

- visualizar as classes
- ver atributos e métodos
- enxergar relacionamentos (associação, agregação, composição, herança)

### 🔹 9.2 Exemplo de domínio: clientes, produtos, vendas

Classes de domínio:

- `Pessoa` (cliente)
- `Produto`
- `Venda`

Classes de apoio:

- `Menu` (interação com usuário)
- `PessoaRepositorio`, `ProdutoRepositorio`, `VendaRepositorio` (armazenamento)

Mapa mental:

- Domínio → **coisas do mundo real**
- Apoio → **controle de tela/fluxo/armazenamento**

### 🔹 9.3 Como modelar passo a passo (checklist prático)

1. **Ler o cenário do problema**
   - Sublinhe os **substantivos** → candidatos a **classes**  
     Ex.: cliente, produto, pedido, venda, endereço…
2. **Escolher atributos essenciais**
   - Para cada classe, pergunte: “O que eu REALMENTE preciso saber sobre isso?”
3. **Identificar verbos** → candidatos a **métodos**
   - Ex.: cadastrar, atualizar, remover, listar, calcular total…
4. **Definir responsabilidades**
   - Cada classe deve ter um **papel claro** (princípio da responsabilidade única).
5. **Desenhar o diagrama de classes inicial**
   - Refinar conforme surgirem novos requisitos.

> 🧠 Frase‑âncora:  
> “Substantivos viram classes; verbos viram métodos.”

---

## 🟦 10. C++ x Java – mesma ideia, sintaxes diferentes

### 🔹 10.1 O que muda?

**C++**:

- Combina programação estruturada com POO.
- Tem controle fino de memória (ponteiros, `new`, `delete`).
- Suporta **herança múltipla** (uma classe com vários “pais”) – poderoso, mas perigoso.
- A visibilidade padrão de membros em classes costuma ser `private`.

**Java**:

- Focado em POO, com sintaxe mais “verbal” e descritiva.
- Gerencia memória via **Garbage Collector** (sem `delete` manual).
- **Não permite herança múltipla de classes.**
- Usa `new` para instanciar objetos.
- Organização forte por **pacotes**.

### 🔹 10.2 O que permanece igual?

Em ambos:

- Você define **classes**.
- Cria **objetos** com **atributos** e **métodos**.
- Usa **encapsulamento** (`private`, `public`, `protected`).
- Trabalha com **instanciação**: `Classe obj = new Classe(...);`

> ✦ Frase‑âncora:  
> “Linguagem muda; ideia da POO permanece.”

---

## 🟦 11. Ciclo de vida de um objeto

### 🔹 11.1 Etapas

1. **Criação**
   - Chamada ao construtor (ex.: `new Pessoa(...)`).
2. **Uso**
   - Método acessa atributos, chama outros métodos, realiza operações.
3. **Desc descarte/liberação**
   - Em C++: pode exigir `delete` ou gerenciamento explícito.
   - Em Java: o Garbage Collector remove o objeto quando ele não é mais referenciado.

### 🔹 11.2 Cuidados

- Não manter referências a objetos **sem necessidade** (vazamento lógico de memória).
- Não misturar responsabilidade: um objeto não deve fazer “tudo ao mesmo tempo”.

---

## 🟦 12. Erros comuns em POO (e como evitar)

### 🔹 12.1 Top 5 erros

1. **Usar atributos como variáveis temporárias**
   - Deixa o estado do objeto incoerente.
2. **Classe “Deus”** – uma classe que faz tudo:
   - Quebra o princípio da responsabilidade única.
3. **Misturar modelo com persistência**
   - Ex.: uma classe `Pessoa` que já salva direto no banco.
   - Melhor separar: `Pessoa` (modelo) e `PessoaRepositorio` (persistência).
4. **Violação de encapsulamento**
   - Atributos `public` expostos sem controle.
5. **Herança mal usada**
   - Colocar herança onde composição seria mais adequada.
   - Em C++, herança múltipla sem necessidade → código frágil.

> 🧠 Frase‑âncora:\*\*  
> “Estado limpo, responsabilidade clara, encapsulamento forte.”

---

## 🟦 13. Checklist para ler um código orientado a objetos

Quando pegar um código desconhecido, siga este mini‑roteiro:

1. **Onde estão as classes?**
   - Liste o nome delas e o que parecem representar.
2. **Quais são os atributos importantes?**
   - O que é essencial? Que tipo eles usam?
3. **Quais são os métodos principais?**
   - Entradas (parâmetros) e saídas (tipo de retorno).
4. **Quem conversa com quem?**
   - Quais classes chamam métodos de outras classes?
5. **Como está o encapsulamento?**
   - Atributos são `private`? Há getters/setters?
6. **Onde está a lógica de negócio?**
   - Está concentrada em classes de domínio ou espalhada em telas, menus, etc.?

> ✦ Frase‑âncora:  
> “Entenda as classes, e você entende o sistema.”

---

## 🟦 14. Resumo final para revisão rápida

Use esta seção como “cola da prova” (sem a cola 😄).

- POO é uma **extensão moderna** do paradigma imperativo, organizada em torno de **objetos**.
- **Classe** = molde/projeto; **Objeto** = instância concreta.
- **Atributos** = estado duradouro do objeto (nome, idade, preço…).
- **Variáveis locais** = dados temporários, usados dentro de métodos.
- **Abstração** = foco no essencial, ignorando detalhes irrelevantes para o problema.
- **Encapsulamento** protege o estado do objeto usando:
  - Atributos `private`
  - Métodos públicos (`get`/`set`) para acesso controlado
- **Pacotes/namespaces** organizam classes em módulos lógicos (modelo, repositório, serviço, interface, etc.).
- **C++ e Java** implementam POO com diferenças de sintaxe e memória, mas com a mesma base conceitual.
- Erros comuns:
  - Atributos usados como variáveis temporárias
  - Classes com responsabilidade demais
  - Quebra de encapsulamento
  - Herança mal aplicada
- Checklist de leitura:
  - Identificar classes, atributos, métodos, relacionamentos, regras de visibilidade.

> 🧠 Macro‑frase‑âncora da aula:  
> “Pensar em POO é pensar em **objetos do mundo real** com **dados bem definidos**, **regras claras** e **fronteiras protegidas**.”

---

## 🟦 15. Dicas de memorização ativa (Active Recall + Spaced Repetition)

### 🔹 15.1 Active Recall – puxar da memória sem olhar

1. Feche o material e responda, de cabeça:
   - O que é **classe**?
   - O que é **objeto**?
   - Diferença entre **atributo** e **variável local**?
   - O que é **encapsulamento**?
   - Como a **abstração** aparece no exemplo de `Aluno`?
2. Depois, confira no resumo se esqueceu algo.
3. Reescreva, em 3 frases, o que é POO.

### 🔹 15.2 Spaced Repetition – revisar em intervalos

Sugestão de calendário:

- **Hoje (D0):**
  - Ler a aula completa.
  - Fazer o checklist de leitura em um exemplo simples de código que você já conheça.
- **Daqui 1 dia (D1):**
  - Revisar só o **Resumo final** e as **frases‑âncora**.
  - Tentar explicar POO em voz alta, como se estivesse dando aula.
- **Daqui 3 dias (D3):**
  - Refazer as perguntas do Active Recall.
  - Modelar um mini‑sistema (ex.: biblioteca ou loja) com 3 classes.
- **Daqui 7 dias (D7):**
  - Revisão rápida + resolver exercícios de modelagem e identificação de atributos/métodos em um novo domínio.

### 🔹 15.3 Gatilhos de memória visuais

Associe mentalmente:

- **Classe** → desenho de um **projeto de casa**.
- **Objeto** → imagem de várias **casas construídas** a partir do mesmo projeto.
- **Encapsulamento** → **cofre fechado** com uma porta (métodos) controlando a entrada/saída de valores.
- **Abstração** → mapa simplificado da cidade, sem cada tijolo.

Sempre que bater a dúvida na prova, puxe essas imagens.

---

✦ **Fechamento da aula 07:**  
Você agora tem o mapa mental para entender POO:  
**Classe, objeto, atributo, método, abstração, encapsulamento, pacotes e modelagem**.  
Com esse kit conceitual, fica muito mais fácil avançar para **herança, polimorfismo e generics** nas próximas etapas do curso.
