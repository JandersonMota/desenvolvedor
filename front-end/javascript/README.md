# Javascript

## Declarar variáveis
- var
- let
- const

## Operadores
### 🔻 Operadores Aritméticos
| Operador | Descrição |
|----------|-----------|
| + | Adição |
| - | Subtração |
| * | Multiplicação |
| / | Divisão |
| ** | Exponencial |
| % | Módulo |
| ++ | Incremento |
| -- | Decremento |

### 🔻 Operadores de Atribuição
| Operador | Equivale a |
|----------|-----------|
| = | x = y |
| += | x = x + y |
| *= | x = x * y |
| /= | x = x / y |
| %= | x = x % y |

### 🔻 Operadores de Comparação
| Operador | Descrição |
|----------|-----------|
| == | Igual a |
| === | Mesmo valor e tipo |
| != | Diferente |
| !== | Diferente em valor e tipo |
| < | Menor que |
| > | Maior que |
| <= | Menor ou igual a |
| >= | Maior ou igual a |

> `=` é para atribuição; `==` para igualdade; e `===` para identico;

### 🔻 Operadores Lógicos
| Operador | Descrição |
|----------|-----------|
| && | 'e' lógico |
| \|\| | 'ou' lógico |
| ! | 'não' lógico |

### 🔻 Operador Ternário
```
condicao ? código1 : código2

```

```
condicao ? retorna verdadeiro : retorna falso

```

## Estrutura condicional
```
if ( condicao ) {
// códigos que serão executados caso a condição seja verdadeira
} else if ( condicao ) {
// códigos que serão executados caso a condição anterior não seja verdadeira
} else {
// códigos que serão executados caso nenhuma condição anterior não seja verdadeira
}
```

### 🔻 Operador &&

O operador `&&` possui um comportamento chamado curto-circuito que torna possível executar um código de forma similar ao if.

Veja um exemplo:
```
var valor = 650;
if ( valor > 100 ) console.log(“Pode parcelar a compra sem juros”);
// vai imprimir "Pode parcelar a compra sem juros"
```

Esse código pode ser escrito utilizando && da seguinte forma:
```
var valor = 650;
( valor > 100 ) && console.log(“Pode parcelar a compra sem juros”) ;
// vai imprimir "Pode parcelar a compra sem juros"
```

Veja um outro exemplo, onde atribuímos um valor a uma variável, baseado na condição `preco > 100`.
```
var preco = 20;
var permiteParcelar = preco > 100 && true;
console.log(permiteParcelar);
// vai imprimir false
```

## Função

- Uma função é definida com a palavra-chave `function`.
- O **nome** segue as regras de nomenclatura para variáveis.
- Os **parâmetros** opcionais são listados entre parênteses: **(p1, p2, p3)**.
- O **código** a ser executado está listado entre chaves.
- Opcionalmente, as funções podem **retornar** um valor de volta para o "chamador".

```
function name(p1, p2, p3) {
  // code
}
```

> Acessar uma função sem () retorna a função e não o resultado da função:

```
function toCelsius(fahrenheit) {
  return (5/9) * (fahrenheit-32);
}

let value = toCelsius;
```

### 🔻 Funções de seta
As funções de seta nos permitem escrever uma sintaxe de função mais curta

Sem seta:
```
let myFunction = function(a, b) {return a * b}

```

Com seta:
```
let myFunction = (a, b) => a * b;

```

### 🔻 Funções usadas como variáveis
As funções podem ser usadas como variáveis, em todos os tipos de fórmulas, atribuições e cálculos.

Em vez de usar uma variável para armazenar o valor de retorno de uma função:
```
let x = toCelsius(77);
let text = "The temperature is " + x + " Celsius";
```

Você pode usar a função diretamente, como um valor variável:
```
let text = "The temperature is " + toCelsius(77) + " Celsius";

```

### 🔻 Immediately Invoked Function Expression (IIFE)

Uma função que é declarada e executada imediatamente.
```
(function nome() {
    // código
})();
```
Explicação:
1. `function nome() { ... }`
    - Isso é a declaração da função chamada `nome`.

2. Os parênteses ao redor da função: `(function nome() { ... })`
    - Transformam a declaração em uma **expressão de função**.

    - → Em JavaScript, uma *função declarada* (sem parênteses) não pode ser chamada imediatamente — por isso usamos os parênteses para dizer:

    > “Isto é uma expressão de função, não uma declaração.”

3. Os parênteses finais `()`

   Chamam a função **imediatamente após a definição**.

#### 🔹 Em resumo

O código:
```
(function main() {
    console.log("Rodando imediatamente!");
})();
```
1. Criar a função `main`
2. Executá-la logo em seguida

#### 🔹 Para que serve um IIFE?

Ele é usado quando você quer **executar um bloco de código imediatamente, mas sem deixar variáveis ou funções expostas no escopo global**.

Exemplo:
```
(function() {
    const segredo = "12345";
    console.log("Executado e isolado!");
})();

console.log(typeof segredo); // undefined
```
A variável `segredo` só existe **dentro da função** — fora dela, não é acessível.

#### 🔹 Variações

Pode usar arrow functions:
```
(() => {
    console.log("IIFE com arrow function");
})();
```

⚠️ Assim que o script roda, a função é chamada automaticamente — ótimo para configurações, logs, ou inicializações.

## Objeto

- Um **Objeto** é uma variável que pode conter muitas variáveis.
- Objetos são coleções de **pares-chave-valor**, onde cada chave (conhecida como **nomes de propriedades**) tem um valor.

> **Nota:**
> 
> Você deve declarar objetos com a palavra-chave `const`. Quando um objeto é declarado com `const`, você não pode depois reatribuí-lo para apontar para uma variável diferente.
Isso não torna o objeto imutável. Você ainda pode modificar suas propriedades e valores.

### 🔻 Como criar um Objeto

Um **objeto literal** é uma lista de **pares de valor chave** dentro de colchetes **enrolados { }**.
```
// Create an Object
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};
```

Você também pode criar um **objeto vazio** e adicionar as propriedades depois:
```
// Create an Object
const person = {};

// Add Properties
person.firstName = "John";
person.lastName = "Doe";
person.age = 50;
person.eyeColor = "blue";
```

Crie um novo objeto JavaScript usando `new Object()`
```
// Create an Object
const person = new Object({
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
});
```

> Nota:
>
> Todos os exemplos acima fazem exatamente a mesma coisa. Não há necessidade de usar `new Object()`. Para legibilidade, simplicidade e velocidade, use um objeto literal.

### 🔻 Propriedades do Objeto

Você pode acessar as propriedades dos objetos de duas maneiras:
```
person.lastName;
```

```
person["lastName"];
```

### 🔻 Definir de funções

```
const person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,

  fullName : function() {
    return this.firstName + " " + this.lastName;
  }

};
```

### 🔻 Funções construtoras

Às vezes precisamos criar muitos objetos do mesmo **tipo**. Para criar um **tipo de objeto**, usamos uma **função construtora de objetos**. É considerado uma boa prática nomear funções construtoras com uma letra maiúscula.

Tipo Objeto Pessoa:
```
function Person(first, last, age, eye) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eye;
}
```

> Nota:
>
> Na função construtora, não tem valor `this`. O valor de se tornará o novo objeto quando um novo objeto é criado `this`.

Agora podemos usar para criar muitos novos objetos Person `new Person()`:
```
const myFather = new Person("John", "Doe", 50, "blue");
const myMother = new Person("Sally", "Rally", 48, "green");
const mySister = new Person("Anna", "Rally", 18, "green");

const mySelf = new Person("Johnny", "Rally", 22, "green");
```
