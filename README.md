# reviewing-java 💻

## Sumário
1. [Download do Java JDK](#1-passo)
2. [Sobre o Java](#sobre)
3. [Estrutura de uma aplicação](#estrutura-de-uma-aplicaçao)
4. [Desenvolvimento](#desenvolvimento)
    - [Estrutura Sequencial](#estrutura-sequencial)
        - [Expressoes aritméticos](#expressoes-aritmeticas)
        - [Operadores aritméticos](#operadores-aritmeticos)
        - [Precedência de Operadores](#precedencia-de-operadores)
        - [Tipos primitivos de váriaveis](#tipos-primitivos-de-variaveis)
        - [Padrões de nome para váriaveis](#padroes-de-nome-para-variaveis)
        - [Casting Explícito](#casting-explicito) 
        - [Funções Matemáticas](#funçoes-matematicas)
##

### 1. Passo
Para iniciar o desenvolvimento em Java, o primeiro passo é baixar o [Java JDK](https://www.azul.com/downloads/?package=jdk#zulu). Vamos escolher a versão LTS (Long-Term Support), pois muitas empresas preferem essa versão devido à estabilidade e suporte.

##

## Sobre
O Java foi criado na década de 1990 por James Gosling e sua equipe na Sun Microsystems. Eles buscavam uma linguagem de programação que fosse independente de plataforma, ou seja, que pudesse ser executada em diferentes sistemas operacionais sem a necessidade de recompilação.

A grande sacada do Java foi a introdução da Máquina Virtual Java (JVM). Em vez de compilar o código diretamente para o código de máquina da CPU, o Java compila seu código em bytecode, uma linguagem de máquina virtual. Isso significa que, ao invés de escrever um programa específico para cada sistema operacional, você escreve um programa em Java uma vez e pode executá-lo em qualquer lugar que tenha uma JVM compatível.

Essa abordagem "write once, run anywhere" (escreva uma vez, execute em qualquer lugar) foi um dos grandes diferenciais do Java. A portabilidade e a independência de plataforma fizeram com que a linguagem ganhasse popularidade rapidamente, especialmente em ambientes empresariais onde a interoperabilidade entre diferentes sistemas é crucial.

<div align="center">
    <img src="https://media.discordapp.net/attachments/1039503054489255957/1203485264723582987/image.png?ex=65d143fe&is=65becefe&hm=f5d5798c531b22b02434cb3240d268b706225093eb44794b7c77ecbee0d9a5dc&=&format=webp&quality=lossless&width=839&height=465">
</div>

##

## Estrutura de uma aplicaçao
```scss
MeuProjeto
│
├── src
│   ├── module-info.java (arquivo de módulo)
│   │
│   ├── com
│   │   ├── meuprojeto
│   │   │   ├── package1
│   │   │   │   ├── Classe1.java
│   │   │   │   └── Classe2.java
│   │   │   │
│   │   │   ├── package2
│   │   │       ├── Classe3.java
│   │   │       └── Classe4.java
│   │   │
│   │   └── outroprojeto
│   │       └── OutraClasse.java
│   │
└── out
    └── (arquivos compilados e outros artefatos)
```

##

## Desenvolvimento
- ### Estrutura Sequencial
    - ### Expressoes aritmeticas
    <div align="center">
        <img src="https://media.discordapp.net/attachments/1039503054489255957/1203822142836449291/image.png?ex=65d27dbc&is=65c008bc&hm=214af6d2878242568dba29f23e25685108575c00aec0986a601e8f9a96b48f46&=&format=webp&quality=lossless">
    </div>

    ##

    - ### Operadores Aritmeticos

    | Operador | Descrição           | Exemplo        |
    |----------|---------------------|----------------|
    | `+`      | Adição              | `a + b`        |
    | `-`      | Subtração           | `a - b`        |
    | `*`      | Multiplicação       | `a * b`        |
    | `/`      | Divisão             | `a / b`        |
    | `%`      | Resto da Divisão    | `a % b`        |
    | `++`     | Incremento          | `a++` ou `++a` |
    | `--`     | Decremento          | `a--` ou `--a` |

    ##

    - ### Precedencia de Operadores

    | Ordem   | Operador              | Descrição                       |
    |---------|-----------------------|---------------------------------|
    | 1 Lugar | `*`, `/`, `%`         | Multiplicação, Divisão e Resto  |
    | 2 Lugar | `+`, `-`              | Positivo e Negativo             |

    ##

    - ### Tipos primitivos de variaveis

    | Tipo      | Tamanho (em bits) | Faixa de Valores                                   | Exemplo    |
    |-----------|---------------------|----------------------------------------------------|------------|
    | `byte`    | 8                   | -128 a 127                                         | `byte b = 42;` |
    | `short`   | 16                  | -32,768 a 32,767                                   | `short s = 1000;` |
    | `int`     | 32                  | -2^31 a 2^31 - 1                                   | `int i = 12345;` |
    | `long`    | 64                  | -2^63 a 2^63 - 1                                   | `long l = 123456789L;` |
    | `float`   | 32                  | Aproximadamente ±3.40282347E+38F                  | `float f = 3.14f;` |
    | `double`  | 64                  | Aproximadamente ±1.79769313486231570E+308D       | `double d = 3.14;` |
    | `boolean` | -                   | `true` ou `false`                                  | `boolean flag = true;` |
    | `char`    | 16                  | Unicode de 0 a 65,535 (ou '\u0000' a '\uffff')    | `char c = 'A';` |

    ##

    - ### Padroes de nome para variaveis
        - Não pode começar com dígito: Use sempre letras ou _
        - Não pode ter espaços.
        - Não usar nenhuma acentuação.
        - Sempre começamos nomes de váriaveis com a letra minúscula.
        - Sempre utilize o padrão camelCase. Ex: `int exemploAssim` = 0;

    ##

    - ### Casting Explicito  

    Casting em Java é o processo de converter um valor de um tipo de dado para outro. No entanto, é essencial garantir que não ocorra perda de dados ao reduzir o tamanho de um tipo de dado.

    - Isso ocorre quando você está convertendo um tipo de dado maior em um tipo de dado menor.

    - Pode haver perda de dados se o valor não puder ser representado no tipo de dado alvo.

    - É necessário prestar atenção, pois às vezes estamos dividindo dois valores do tipo `int`, o que nos devolverá um valor do tipo `double`. Por exemplo:

    ```java
        int a = 5;
        int b = 2;

        double resultado;

        resultado = a / b;

        System.out.println(resultado);
    ```

    O resultado correto deveria ser: 2.5. No entanto, ele nos retorna 2.0 porque as variáveis são do tipo `int`, então o compilador corta as casas decimais, nos retornando um inteiro. Mas dessa forma não está correto o valor, por isso, devemos utilizar o casting. Por exemplo:

    ```java
        int a = 5;
        int b = 2;

        double resultado;
        
        // Declaramos que o resultado da divisão é um valor double.
        resultado = (double) a / b; 

        System.out.println(resultado);
    ```

    ##

    - ### Funçoes Matematicas


    | Função                          | Descrição                                                                                                                                                                            |
    |---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | `Math.abs(double a)`            | Retorna o valor absoluto de um número.                                                                                                                                               |
    | `Math.pow(double base, double exponent)` | Retorna a potência de um número.                                                                                                                                            |
    | `Math.sqrt(double a)`           | Retorna a raiz quadrada de um número.                                                                                                                                              |
    | `Math.floor(double a)`          | Retorna o maior número inteiro menor ou igual a um número.                                                                                                                           |
    | `Math.ceil(double a)`           | Retorna o menor número inteiro maior ou igual a um número.                                                                                                                           |
    | `Math.round(double a)`          | Retorna o valor inteiro mais próximo de um número.                                                                                                                                   |
    | `Math.sin(double a)`            | Retorna o seno de um ângulo em radianos.                                                                                                                                            |
    | `Math.cos(double a)`            | Retorna o cosseno de um ângulo em radianos.                                                                                                                                         |
    | `Math.tan(double a)`            | Retorna a tangente de um ângulo em radianos.                                                                                                                                        |
    | `Math.min(double a, double b)`  | Retorna o menor dos dois números.                                                                                                                                                   |
    | `Math.max(double a, double b)`  | Retorna o maior dos dois números.                                                                                                                                                   |
    | `Math.random()`                 | Retorna um número aleatório entre 0 (inclusive) e 1 (exclusivo).                                                                                                                     |
    | `Math.PI`                       | Retorna o valor de pi (π), uma constante matemática.                                                                                                                                 |

    Essas funções da classe `Math` em Java são úteis para uma ampla variedade de tarefas matemáticas em programação.