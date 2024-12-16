# Spring Framework
As anotações fazem parte do conceito de **programação declarativa**, onde você define o que quer fazer, e o framework (Spring) cuida de implementar a lógica necessária. Isso reduz o esforço de escrever código repetitivo e aumenta a legibilidade e manutenção da aplicação.

Os códigos que possuem `@` representam anotações no Java. As **anotações** são uma maneira de fornecer metadados para o compilador ou framework (como o Spring e o JPA), indicando como o código deve ser processado ou executado.


## Status CODE
|CODE	   |Significado			|
|----------|----------------------------|
|2xx	   |Sucesso			|
|4xx	   |Erro do cliente		|
|5xx  	   |Erro no serviço/servidor	|


## Spring Data JPA (JPA = Java Persistence API)
### Explicação das anotações no código:
### `@Entity`
- Declara que a classe é uma **entidade JPA**.
- Isso significa que ela será mapeada para uma tabela no banco de dados.
- Sem essa anotação, o JPA não reconheceria a classe como uma tabela.


### `@Table(name="<NOME-DA-TABELA>")`
- Define o nome da tabela no banco de dados que será usada para mapear essa entidade.
- Por padrão, o JPA usa o nome da classe como o nome da tabela, mas você pode sobrescrever isso com `@Table(name="categoria")` por exemplo.


### `@Id`
- Indica que o atributo codigo é a chave primária da tabela.
- Essa é uma exigência do JPA para identificar de forma única cada linha na tabela.


### `@GeneratedValue(strategy = GenerationType.IDENTITY)`
- Indica que o valor da chave primária será gerado automaticamente pelo banco de dados.
- O parâmetro `strategy = GenerationType.IDENTITY` especifica que o banco de dados usará uma estratégia de auto incremento para gerar os valores da coluna.

```Java
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.Table;

@Entity
@Table(name="categoria")
public class Categoria {
	
	@Id
	@GeneratedValue(strategy = GenerationType.IDENTITY)
	private Long codigo;
	private String nome;
}
```
#### Por que usar essas anotações?
- Elas eliminam a necessidade de escrever SQL manual para definir a estrutura do banco de dados.
- O JPA usa as anotações para gerar automaticamente as tabelas e manipular os dados.
- Isso simplifica o desenvolvimento, deixando o foco na lógica de negócio.


### `@Autowired`
**O que é:**
- Realiza a injeção de dependência de forma automática.
- Informa ao Spring que ele deve gerenciar a criação e a configuração do objeto necessário (no caso, o objeto é chamado de *bean*).

**Principais características:**
- Pode ser usada em atributos, construtores ou métodos.
- Facilita o gerenciamento de dependências, eliminando a necessidade de criar objetos manualmente.

- A anotação `@Autowired` instrui o Spring a procurar automaticamente por um *bean* que corresponda ao tipo do campo ou método anotado.
- Esse *bean* é então injetado no local onde foi declarado.

1. Vantagens do `@Autowired`:
Reduz o acoplamento: O Spring gerencia a criação e o ciclo de vida dos objetos.
Aumenta a testabilidade: Dependências podem ser facilmente substituídas por mocks em testes.

2. Boas práticas:
Prefira usar `@Autowired` em construtores ou métodos em vez de diretamente nos campos. Isso melhora a legibilidade e facilita testes.

3. Configuração necessária:
Certifique-se de que as classes onde `@Autowired` é usado estão marcadas com anotações como `@Component`, `@Service`, `@Repository`, ou configuradas como *beans* no Spring Context.

Com `@Autowired`
``` Java
@Autowired
private CategoriaRepository categoriaRepository;
```

Sem o `@Autowired`: Sem a injeção automática, você teria que instanciar ou gerenciar manualmente esse objeto:
``` Java
private CategoriaRepository categoriaRepository = new CategoriaRepositoryImpl(); // Manual
```

**Exemplo:**

``` Java
@Autowired
private UserRepository userRepository;

@GetMapping("/users")
public List<User> listUsers() {
    return userRepository.findAll();
}
```

**O que acontece:**
- O Spring cria e injeta automaticamente uma instância de `UserRepository` no atributo `userRepository`.
- Você pode usar o `userRepository` diretamente para acessar o banco de dados.


### `@RestController`

**O que é:**
- Marca uma classe como um *controller* RESTful no Spring.
- Um *controller* é responsável por lidar com requisições HTTP, processá-las e retornar respostas.

**Principais características:**
- Combina as funcionalidades de:
	- `@Controller` (usado para indicar uma classe que processa requisições HTTP).
	- `@ResponseBody` (usado para retornar o dado diretamente no corpo da resposta em JSON ou XML).
- É ideal para criar APIs que enviam dados estruturados (como JSON).
**Exemplo:**

``` Java
@RestController
public class MyController {
    @GetMapping("/hello")
    public String sayHello() {
        return "Hello, World!";
    }
}
```


### `@RequestMapping("/<CAMINHO-DA-URL>")`

**O que é:**
- Define a URL base para as requisições que serão processadas por essa classe ou método.

**Principais características:**
- Pode ser usada tanto em classes quanto em métodos.
- Especifica um caminho de URL, e também pode definir:
	- O tipo de requisição HTTP (GET, POST, PUT, DELETE, etc.).
	- Parâmetros adicionais (como cabeçalhos ou mídia aceita).
**Exemplo em uma classe:**

``` Java
@RequestMapping("/api")
public class ApiController {
    @GetMapping("/users")
    public List<String> listUsers() {
        return List.of("User1", "User2");
    }
}
```
**O que acontece:**
- A URL completa para acessar o método seria `/api/users`.


### `@GetMapping`
**O que é:**
- Especifica que o método deve responder apenas a requisições HTTP **GET**.
- É uma alternativa simplificada a `@RequestMapping(method = RequestMethod.GET)`.

**Principais características:**
- Usada principalmente para *buscar dados*.
- Geralmente retorna informações do banco de dados ou configurações de sistema.

**Exemplo:**

``` Java
@GetMapping("/products")
public List<Product> listProducts() {
    return productRepository.findAll();
}
```

**O que acontece:**
- Quando o cliente faz uma requisição GET para a URL `/products`, o método é executado, retornando a lista de produtos.

``` Java
import java.util.List;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

import com.example.algamoney.api.model.Categoria;
import com.example.algamoney.api.repository.CategoriaRepository;

@RestController  // Indica que esta classe é um controlador RESTful
@RequestMapping("/categorias")  // Define que todas as requisições para "/categorias" serão tratadas aqui
public class CategoriaResource {

    @Autowired  // Injeta uma instância de CategoriaRepository
    private CategoriaRepository categoriaRepository;

    @GetMapping  // Responde a requisições HTTP GET na URL "/categorias"
    public List<Categoria> listar() {
        return categoriaRepository.findAll(); // Retorna todas as categorias do banco de dados
    }
}
```
**Fluxo:**
1. O cliente faz uma requisição GET para `/categorias`.
2. O Spring verifica que a URL pertence ao controller `CategoriaResource`.
3. O Spring injeta automaticamente o repositório `CategoriaRepository` no atributo.
4. O método `listar` é chamado, que usa o repositório para buscar todas as categorias no banco de dados.
5. A lista de categorias é retornada em formato JSON.


## Spring Jackson JSON
O Jackson é uma biblioteca de processamento de dados JSON para a linguagem de programação Java, que serve para transformar texto em código.

O Jackson é conhecido por ser eficiente e flexível, permitindo que os desenvolvedores manipulem dados JSON de forma simples e intuitiva.

O Jackson oferece uma série de funcionalidades, como:
- Anotações que personalizam a serialização e deserialização de objetos Java para e de JSON.
- Suporte a vários formatos, além de JSON, como XML e YAML.
- Conjunto robusto de anotações que permitem um controle fino sobre a serialização e desserialização.
