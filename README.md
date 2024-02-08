# reviewing-java 💻

## Sumário
1. [Download do Java JDK](#1-passo)
2. [Sobre o Java](#sobre)
3. [Estrutura de uma aplicação](#estrutura-de-uma-aplicaçao)
4. [Desenvolvimento](#desenvolvimento)
    - [Estrutura Sequencial](#estrutura-sequencial)
        - [Expressões aritméticos](#expressoes-aritmeticas)
        - [Operadores aritméticos](#operadores-aritmeticos)
        - [Precedência de Operadores](#precedencia-de-operadores)
        - [Tipos primitivos de váriaveis](#tipos-primitivos-de-variaveis)
        - [Padrões de nome para váriaveis](#padroes-de-nome-para-variaveis)
        - [Casting Explícito](#casting-explicito) 
        - [Funções Matemáticas](#funçoes-matematicas)
    - [Estrutura Condicional](#estrutura-condicional)
        - [Expressoes Comparativas](#expressoes-comparativas)
        - [Operadores Comparativos](#operadores-comparativos)
        - [Operadores Logicos](#operadores-logicos)
        - [Estruturas Condicionais:](#estruturas-condicionais)
            - [If/else](#if-else)
            - [Switch](#switch)
        - [Atribuição Acumulativa](#atribuiçao-acumulativa)
        - [Expressão Condicional Ternária](#expressao-condicional-ternaria)
        - [Escopo e Variáveis](#escopo-e-variaveis)
    - [Estrutura Repetitiva](#estrutura-repetitiva)
        - [Estruturas Repetitivas:](#estruturas-repetitivas)
            - [While](#while)
            - [Do-While](#do-while)
            - [For](#for)

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

    ##

- ### Estrutura Condicional
    - ###  Expressoes Comparativas
    <div align="center">
        <img src="https://media.discordapp.net/attachments/1039503054489255957/1204579221733900298/image.png?ex=65d53ed2&is=65c2c9d2&hm=eca2d2d61d909c21c916422faad8d9ab8bdbc6341495e8cd37e314fec2b22271&=&format=webp&quality=lossless">
    </div>

    ##

    - ### Operadores Comparativos

    | Operador | Descrição                              | Exemplo                 | Resultado  |
    |----------|----------------------------------------|-------------------------|------------|
    | `==`     | Igualdade                              | `5 == 5`                | `true`     |
    | `!=`     | Não igual                              | `5 != 5`                | `false`    |
    | `>`      | Maior que                              | `3 > 5`                 | `false`    |
    | `<`      | Menor que                              | `3 < 5`                 | `true`     |
    | `>=`     | Maior ou igual a                       | `5 >= 5`                | `true`     |
    | `<=`     | Menor ou igual a                       | `3 <= 5`                | `true`     |

    Esses operadores são usados para comparar valores em expressões condicionais e retornam um valor booleano (`true` ou `false`) com base no resultado da comparação.

    ##

    - ### Operadores Logicos


    | Operador | Descrição                                      | Exemplo                   | Resultado  |
    |----------|------------------------------------------------|---------------------------|------------|
    | `&&`     | E lógico (AND)                                | `true && false`           | `false`     |
    | `\|\|`   | OU lógico (OR)                                | `true \|\| false`         | `true`      |
    | `!`      | Negação lógica (NOT)                          | `!true`                   | `false`     |

    Esses operadores são utilizados para realizar operações lógicas em expressões booleanas. O operador `&&` retorna `true` se ambos os operandos forem `true`, o operador `||` retorna `true` se pelo menos um dos operandos for `true`, e o operador `!` nega o valor do operando, ou seja, se o operando for `true`, o resultado será `false`, e vice-versa.

     ##

    - ### Estruturas Condicionais
        - ## If-else
        - Estrutura do If `Simples`:
            ```java
                if ( <condição> ) {
                    // Ativo quando a condição é (TRUE)
                } 
            ```
        - Estrutura do If `Composta`:
            ```java
                if ( <condição> ) {
                    // Ativo quando a condição é (TRUE)
                } else {
                    // Ativo quando a condição é (FALSE)
                }
            ```
        - Encadeamento de Estrutura If:
            ```java
                if ( <condição> ) {
                    // Ativo quando a condição é (TRUE)
                } else {
                    if ( <condição> ) {
                        // Ativo quando a condição é (TRUE)
                    } else {
                        // Ativo quando a condição é (FALSE)
                    }
                }
            ```
        
        ##
         
        - ## Switch
        - Estrutura do `Switch`:
            ```java
                switch (expressao) {
                case valor1:
                    // código a ser executado se a expressão for igual a valor1
                    break;
                case valor2:
                    // código a ser executado se a expressão for igual a valor2
                    break;
                default:
                    // código a ser executado se nenhum dos casos anteriores for correspondido
                }
            ```
            - `expressao`: É o valor que será avaliado para determinar qual caso será executado.
            - `valor1`, `valor2`: Podem ser valores numéricos, caracteres, strings ou até mesmo expressões constantes.
    

    - ### Atribuiçao Acumulativa

    | Operador | Descrição                                    | Exemplo                 | Equivalente a |
    |----------|----------------------------------------------|-------------------------|---------------|
    | `+=`     | Adição acumulativa                           | `a += 5;`               | `a = a + 5;`  |
    | `-=`     | Subtração acumulativa                        | `a -= 3;`               | `a = a - 3;`  |
    | `*=`     | Multiplicação acumulativa                    | `a *= 2;`               | `a = a * 2;`  |
    | `/=`     | Divisão acumulativa                          | `a /= 4;`               | `a = a / 4;`  |
    | `%=`     | Resto da divisão acumulativa                 | `a %= 3;`               | `a = a % 3;`  |

    Esses operadores combinam uma operação aritmética ou lógica com uma atribuição, tornando o código mais conciso e legível.

    ##

    - ### Expressao Condicional Ternaria
    - Estrutura:
    ```java
        variavel = (condicao) ? valorSeVerdadeiro : valorSeFalso;
    ```
    - `condicao`: É a expressão booleana que será avaliada. Se for verdadeira, o valorSeVerdadeiro será atribuído à variável; caso contrário, o valorSeFalso será atribuído.
    - `valorSeVerdadeiro`: Valor atribuído à variável se a condição for verdadeira.
    - `valorSeFalso`: Valor atribuído à variável se a condição for falsa.
    Ex:
    ```java
        String exemploVariavel = (10 < 5) ? "Caso a expressão for (TRUE)" : "Caso a expressão for (FALSE)";
    ```

    ##

    - ### Escopo e Variaveis
    Quando declaramos uma variável dentro de um bloco `if`, ela só é acessível dentro desse bloco e seus blocos filhos, como o bloco `else` ou outros blocos `if` dentro do bloco `if` original. Isso é conhecido como escopo local.

    Exemplo:

    ```java
        if (idade >= 18) {
            String status = "Maior de idade"; // Declaração e inicialização da variável dentro do bloco if
            System.out.println(status); // Imprime o status
        } else {
            String status = "Menor de idade"; // Declaração e inicialização da variável dentro do bloco else
            System.out.println(status); // Imprime o status
        }

        // A variável status não é acessível aqui fora do bloco if-else
        // System.out.println(status); // Isso causaria um erro
    ```

    Para tornar a variável `status` acessível fora do escopo do bloco `if`, devemos declará-la fora do escopo local:

    ```java
        String status; // Declaração da variável fora do escopo local

        if (idade >= 18) {
            status = "Maior de idade"; // Inicialização da variável dentro do bloco if
            System.out.println(status); // Imprime o status
        } else {
            status = "Menor de idade"; // Inicialização da variável dentro do bloco else
            System.out.println(status); // Imprime o status
        }

        // Agora a variável status é acessível fora dos blocos if e else
        System.out.println("Status: " + status);
    ```

    Agora, a variável `status` pode ser acessada fora dos blocos `if` e `else`, permitindo seu uso em outras partes do código."

    ##

- ### Estrutura repetitiva
    - ### Estruturas repetitivas
        - ## While
        - Estrutura do While:
        ```java
            while (expressao) {
                // código a ser executado se a expressão for (TRUE)
            }
        ```
        - `expressao`: O while vai rodar infinitamente até que a expressão seja (FALSE).

        ##

        - ## Do-While
        - Estrutura do Do-While:
        ```java
            do {
                // código a ser executado
            } while (condição);
        ```
        O do-while executa o código pelo menos uma vez, sem verificar a condição. Depois de rodar ele verifica a condição e continua a executar o código enquanto a condição for verdadeira. É útil quando você precisa garantir que um código seja executado pelo menos uma vez, independentemente da condição.

        ##
            
        - ## For
        - Estrutura do For:
        ```java
            for (início; condição; incremento) {
                // código a ser executado
            }
        ```
        - **Início**: Aqui, inicializamos a variável de controle `i` com o valor 1.
        - **Condição**: Esta parte verifica se `i` é menor ou igual a 10. Enquanto essa condição for verdadeira, o loop continuará executando até que a condição se torne falsa.
        - **Incremento**: A cada iteração do loop, incrementamos o valor de `i` em 1. Se quisermos decrementar, podemos usar `i--` em vez de `i++`.

        Obs: O `for` é usado quando sabemos a quantidade de repetições a serem realizadas, em contraste com o `while`, que é mais apropriado quando a condição de término não é conhecida.