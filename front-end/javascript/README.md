# Javascript

## Declarar variáveis
- var
- let
- const

## Operadores
### Operadores Aritméticos
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

### Operadores de Atribuição
| Operador | Equivale a |
|----------|-----------|
| = | x = y |
| += | x = x + y |
| *= | x = x * y |
| /= | x = x / y |
| %= | x = x % y |

### Operadores de Comparação
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

### Operadores Lógicos
| Operador | Descrição |
|----------|-----------|
| && | 'e' lógico |
| \|\| | 'ou' lógico |
| ! | 'não' lógico |

### Operador Ternário
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

### Operador &&

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
