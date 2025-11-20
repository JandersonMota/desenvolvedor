# Javascript

## Índice
- [Declarar variáveis](#declarar-variaveis)
- [Operadores](#operadores)
- [Estrutura condicional](#estrutura-condicional)
- [Função](#funcao)
- [Objeto](#objeto)
- [Classe](#classe)

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

## Array
- Um Array é um tipo de objeto projetado para armazenar coleções de dados.
- No JavaScript, os arrays usam índices numerados.
- No JavaScript, os objetos usam índices nomeados.

> Nota:
>
> É prática comum declarar arrays com a palavra-chave `const`.

Exemplo:
```
const cars = ["Saab", "Volvo", "BMW"];
```

Você também pode criar um array vazio e fornecer elementos depois:
```
const cars = [];
cars[0]= "Saab";
cars[1]= "Volvo";
cars[2]= "BMW";
```

O exemplo a seguir também cria um Array e atribui valores a ele:
```
const cars = new Array("Saab", "Volvo", "BMW");
```

> Nota:
>
> Os dois exemplos acima fazem exatamente a mesma coisa. Não há necessidade de usar `new Array()`. Para simplicidade, legibilidade e velocidade de execução, use o método literal do array.

Você acessa um elemento do array consultando o número do índice:
```
const cars = ["Saab", "Volvo", "BMW"];
let car = cars[0];
```

O método `toString()` JavaScript converte um array em um Cadeia de valores de array (separados por vírgula).
Exemplo:
```
const fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.toString();
```

Com JavaScript, o array completo pode ser acessado consultando o array nome:
```
const cars = ["Saab", "Volvo", "BMW"];
document.getElementById("demo").innerHTML = cars;
```

A maneira mais fácil de adicionar um novo elemento a um array é usando o método `push()`:
```
const fruits = ["Banana", "Orange", "Apple"];
fruits.push("Lemon");  // Adds a new element (Lemon) to fruits
```

Novos elementos também podem ser adicionados a um array usando a propriedade `length`:
```
const fruits = ["Banana", "Orange", "Apple"];
fruits[fruits.length] = "Lemon";  // Adds "Lemon" to fruits
```

### 🔻 Quando usar matrizes. Quando usar Objetos.
- JavaScript não suporta arrays associativos.
- Você deve usar objetos quando quiser que os nomes dos elementos sejam strings (texto).
- Você deve usar arrays quando quiser que os nomes dos elementos sejam números.

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

## Classe

Use a palavra-chave para criar uma classe `class`.
Sempre adicione um método chamado `constructor()`:

Sintaxe:
```
class ClassName {
  constructor() { ... }
}
```

Exemplo:
```
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
}
```

> Nota:
>
> Uma classe JavaScript **não** é um objeto. É um **modelo** para objetos JavaScript.

Quando você tem uma classe, pode usá-la para criar objetos:
```
const myCar1 = new Car("Ford", 2014);
const myCar2 = new Car("Audi", 2019);
```

> Nota:
>
> O método construtor é chamado automaticamente quando um novo objeto é criado.

O método construtor é um método especial:

- Ele precisa ter o nome exato "constructor", ou seja, sempre adicione um método `constructor()`.
- Ele é executado automaticamente quando um novo objeto é criado
- É usado para inicializar propriedades de objetos

Se você não definir um método construtor, JavaScript vai adicionar um método construtor vazio.
