# Monólito
## Quando o monólito (modular) é a melhor maneira de construir software
- [Rahul Garg: When (‌modular) monolith is the better way to build software](https://www.thoughtworks.com/en-br/insights/blog/microservices/modular-monolith-better-way-build-software)

# Microsserviço

# Padrões de Projetos
- Livro: Design Patterns - GoF 

[YouTube: Padrões de Projetos](https://www.youtube.com/watch?v=MqddY6Ochkc&list=PLbIBj8vQhvm0VY5YrMrafWaQY2EnJ3j8H)

## SOLID

## Tipos de Padrões de Projetos
Os padrões de projetos são divididos em três categorias, e em cada um possui os tipos de padrões de projetos:
- Criação;
- Estrutural;
- Comportamental.

| Categoria           | Padrão                         | Tipo         | Explicação Resumida |
|---------------------|--------------------------------|--------------|---------------------|
| **Criacional**      | Abstract Factory               | Classe/Objeto| Cria famílias de objetos relacionados sem especificar suas                                                                               classes concretas. |
|                     | Builder                        | Objeto       | Separa a construção de um objeto complexo da sua representação                                                                           final. |
|                     | Factory Method                 | Classe       | Define um método para criar objetos, permitindo que subclasses                                                                           decidam qual instância retornar. |
|                     | Prototype                      | Objeto       | Cria novos objetos copiando um protótipo existente. |
|                     | Singleton                      | Objeto       | Garante que exista apenas uma instância de uma classe e fornece                                                                          um ponto global de acesso a ela. |
| **Estrutural**      | Adapter                        | Classe/Objeto| Converte a interface de uma classe em outra esperada pelos                                                                               clientes. |
|                     | Bridge                         | Objeto       | Separa a abstração da implementação para que possam variar                                                                               independentemente. |
|                     | Composite                      | Objeto       | Permite tratar objetos individuais e composições de forma                                                                                uniforme. |
|                     | Decorator                      | Objeto       | Adiciona responsabilidades a um objeto dinamicamente. |
|                     | Facade                         | Objeto       | Fornece uma interface simplificada para um subsistema complexo. |
|                     | Flyweight                      | Objeto       | Compartilha objetos para economizar memória quando existem                                                                               muitos semelhantes. |
|                     | Proxy                          | Objeto       | Controla o acesso a outro objeto, podendo adicionar                                                                                      comportamentos extras. |
| **Comportamental**  | Chain of Responsibility        | Objeto       | Passa uma solicitação por uma cadeia de manipuladores até que                                                                            seja tratada. |
|                     | Command                        | Objeto       | Encapsula uma solicitação como um objeto, permitindo                                                                                     desfazer/refazer e filas de execução. |
|                     | Interpreter                    | Classe       | Define uma gramática e um interpretador para interpretar                                                                                 sentenças nessa linguagem. |
|                     | Iterator                       | Objeto       | Fornece uma maneira de percorrer elementos de uma coleção sem                                                                            expor sua estrutura interna. |
|                     | Mediator                       | Objeto       | Centraliza a comunicação entre objetos para reduzir o                                                                                    acoplamento. |
|                     | Memento                        | Objeto       | Captura e restaura o estado interno de um objeto sem violar o                                                                            encapsulamento. |
|                     | Observer                       | Objeto       | Define dependência um-para-muitos entre objetos, notificando                                                                             automaticamente as mudanças. |
|                     | State                          | Objeto       | Permite que um objeto altere seu comportamento quando seu estado                                                                         interno muda. |
|                     | Strategy                       | Objeto       | Define uma família de algoritmos e encapsula cada um, tornando-                                                                          os intercambiáveis. |
|                     | Template Method                | Classe       | Define o esqueleto de um algoritmo, permitindo que subclasses                                                                            definam alguns passos. |
|                     | Visitor                        | Objeto       | Separa um algoritmo da estrutura de objetos sobre a qual ele                                                                             opera. |

No livro do GoF, a coluna "Tipo" que coloquei na tabela se refere à forma de implementação do padrão — se ele é implementado principalmente usando **herança (classe)** ou **composição/instâncias (objeto)**.

💡 Em outras palavras:

- **Classe** → foco na herança e definido em tempo de compilação.
- **Objeto** → foco na composição e definido em tempo de execução.

Por exemplo:
- **Factory Method** é um padrão **criacional de classe**, pois envolve herança para criar objetos.
- **Singleton** é um padrão **criacional de objeto**, pois o controle é feito sobre uma instância única.
- **Adapter** pode ser tanto **de classe** quanto **de objeto**, dependendo de como é implementado.

### 🧠 Mapa Mental
<img width="1225" height="816" alt="image" src="https://github.com/user-attachments/assets/2e94d91d-9787-4b0a-b505-37c971c0879d" />

