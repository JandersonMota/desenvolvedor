# Spring Framework
As anotações fazem parte do conceito de **programação declarativa**, onde você define o que quer fazer, e o framework (Spring) cuida de implementar a lógica necessária. Isso reduz o esforço de escrever código repetitivo e aumenta a legibilidade e manutenção da aplicação.

Os códigos que possuem `@` representam anotações no Java. As **anotações** são uma maneira de fornecer metadados para o compilador ou framework (como o Spring e o JPA), indicando como o código deve ser processado ou executado.


## Status CODE
|CODE	   |Significado			|
|----------|----------------------------|
|2xx	   |Sucesso			|
|4xx	   |Erro do cliente		|
|5xx  	   |Erro no serviço/servidor	|


---
### @RestController
`@RestController` é uma anotação do Spring Framework usada em aplicações web baseadas em Spring. Essa anotação combina as funcionalidades de `@Controller` e `@ResponseBody`, tornando-a muito útil para criar controladores RESTful. Vamos explorar mais detalhadamente o que `@RestController` faz e como ele é usado.

**Funcionalidades do `@RestController`**

1. @Controller:

- `@Controller` é uma anotação que indica que uma classe é um controlador, ou seja, ela lida com requisições HTTP e retorna um modelo e uma visão (model-view) para ser renderizada.

2. @ResponseBody:

- `@ResponseBody` é uma anotação que indica que o método anotado deve retornar um objeto que será serializado e enviado no corpo da resposta HTTP. Isso é útil para APIs RESTful, onde o objetivo é retornar dados em formatos como JSON ou XML, em vez de uma página HTML.

3. Combinação:

- `@RestController` combina essas duas anotações, tornando a classe um controlador que automaticamente converte os dados de retorno dos métodos em uma resposta HTTP. Isso elimina a necessidade de anotar cada método com `@ResponseBody`.

**Exemplo de Uso**

Vamos ver um exemplo simples de um controlador RESTful usando `@RestController`.

**Classe `UsuarioController`**

``` Java
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RestController;
import java.util.Arrays;
import java.util.List;

@RestController
public class UsuarioController {

    @GetMapping("/usuarios")
    public List<Usuario> listarUsuarios() {
        // Retorna uma lista de usuários
        return Arrays.asList(
            new Usuario(1L, "João", "joao@example.com"),
            new Usuario(2L, "Maria", "maria@example.com")
        );
    }

    @GetMapping("/usuarios/{id}")
    public Usuario obterUsuario(@PathVariable Long id) {
        // Simula a busca de um usuário por ID
        if (id == 1L) {
            return new Usuario(1L, "João", "joao@example.com");
        } else if (id == 2L) {
            return new Usuario(2L, "Maria", "maria@example.com");
        } else {
            return null;
        }
    }
}

// Classe de modelo Usuario
class Usuario {
    private Long id;
    private String nome;
    private String email;

    public Usuario(Long id, String nome, String email) {
        this.id = id;
        this.nome = nome;
        this.email = email;
    }

    // Getters e setters
    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }
}
```

**Explicação do Exemplo**

**1. Anotação `@RestController`:**

- A classe `UsuarioController` é anotada com `@RestController`, indicando que é um controlador RESTful.

**2. Métodos de Mapeamento:**

- `@GetMapping("/usuarios")`: Mapeia a requisição GET para o endpoint `/usuarios` e retorna uma lista de usuários.
- `@GetMapping("/usuarios/{id}")`: Mapeia a requisição GET para o endpoint `/usuarios/{id}` e retorna um usuário específico com base no ID fornecido.

**3. Retorno de Dados:**

- Os métodos `listarUsuarios` e `obterUsuario` retornam objetos `List<Usuario>` e `Usuario`, respectivamente. Devido à anotação `@RestController`, esses objetos são automaticamente convertidos em JSON e enviados no corpo da resposta HTTP.

**Conclusão**

`@RestController` é uma anotação muito útil para criar APIs RESTful no Spring Framework. Ele simplifica a criação de controladores RESTful, combinando as funcionalidades de `@Controller` e `@ResponseBody`. Isso torna o código mais limpo e fácil de entender e manter.

---
### @Autowired
`@Autowired` é uma anotação do Spring Framework usada para injetar dependências automaticamente em beans gerenciados por Spring. Essa anotação é muito útil para simplificar a injeção de beans em aplicações Spring, especialmente em aplicações web e de serviços.

**Funcionalidades do `@Autowired`**

**1. Injeção Automática:**

- Quando uma propriedade de uma classe é anotada com `@Autowired`, o Spring Framework injeta automaticamente uma instância de um bean correspondente no contêiner durante a criação do contexto de aplicação.
- Isso elimina a necessidade de criar um getter ou setter para a propriedade, pois o Spring injeta a instância diretamente.

**2. Flexibilidade:**

- `@Autowired` pode ser usado em campos, métodos, e construtores. Isso torna a injet automatica muito flexível e adaptável a diferentes estruturas de aplicação.

**3. Tipos de Uso:**

- Em campos:

```
@Autowired
private MeuService meuService;
```

- Em métodos:

```
@Autowired
public void setMeuService(MeuService meuService) {
    this.meuService = meuService;
}
```

- Em construtores:

```
@Autowired
public MeuController(MeuService meuService) {
    this.meuService = meuService;
}
```

**Exemplo de Uso**

Vamos ver um exemplo simples de como usar `@Autowired` em uma aplicação Spring.

**Classe `MeuService`**

``` Java
import org.springframework.stereotype.Service;

@Service
public class MeuService {

    public String obterMensagem() {
        return "Olá, bem-vindo ao MeuService!";
    }
}
```

**Classe `MeuController`**

``` Java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class MeuController {

    @Autowired
    private MeuService meuService;

    @GetMapping("/mensagem")
    public String obterMensagem() {
        return meuService.obterMensagem();
    }
}
```

**Explicação do Exemplo**

**1. Classe MeuService:**

- É anotada com `@Service`, tornando-a um bean gerenciado por Spring.
- Contém um método `obterMensagem` que retorna uma string.

**2. Classe MeuController:**

- É anotada com `@RestController`, tornando-a um controlador RESTful.
- Contém um campo `meuService` anotado com `@Autowired`, que é injetado com uma instância de MeuService durante a criação do contexto de aplicação.
- Contém um método `obterMensagem` que chama o método `obterMensagem` do `MeuService` e retorna a mensagem.

**Conclusão**

`@Autowired` é uma anotação poderosa que simplifica a injeção de dependências em aplicações Spring. Ela permite que os beans gerenciados por Spring sejam injetados automaticamente, eliminando a necessidade de criar e gerenciar manualmente essas dependências. Isso torna o desenvolvimento de aplicações mais limpo, flexível e fácil de manter.

---
### @PostMapping
`@PostMapping` é uma anotação do Spring Framework usada para mapear requisições HTTP POST a métodos específicos em controladores. Essa anotação é muito útil para lidar com ações que envolvem a criação ou atualização de recursos, como o envio de formulários ou a criação de novos registros no banco de dados.

**Funcionalidades do `@PostMapping`**

**1. Mapeamento de Requisições POST:**

- `@PostMapping` é usada para indicar que um método deve ser chamado quando uma requisição HTTP POST é feita para um determinado endpoint (URL).

**2. Flexibilidade:**

- Você pode especificar detalhes adicionais sobre o mapeamento, como parâmetros de consulta, cabeçalhos, e tipos de conteúdo.

**Sintaxe**
A anotação `@PostMapping` pode ser usada de várias maneiras, incluindo:

- URL Simples:
```
@PostMapping("/caminho")

```

- URL com Parâmetros:
```
@PostMapping(value = "/caminho", params = "parametro=valor")

```

- URL com Cabeçalhos:
```
@PostMapping(value = "/caminho", headers = "X-API-Version=2")

```

- URL com Tipo de Conteúdo:
```
@PostMapping(value = "/caminho", consumes = "application/json")

```

**Exemplo de Uso**

Vamos ver um exemplo simples de como usar `@PostMapping` em um controlador Spring.

**Classe `UsuarioController`**

``` Java
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class UsuarioController {

    @PostMapping("/usuarios")
    public String criarUsuario(@RequestBody Usuario usuario) {
        // Lida com a criação do usuário
        // Por exemplo, salva o usuário no banco de dados
        return "Usuário criado com sucesso: " + usuario.getNome();
    }
}

// Classe de modelo Usuario
class Usuario {
    private String nome;
    private String email;

    // Construtor
    public Usuario() {}

    // Getters e setters
    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }
}
```

**Explicação do Exemplo**

**1. Classe `UsuarioController`:**

- É anotada com `@RestController`, indicando que é um controlador RESTful.
- Contém um método `criarUsuario` anotado com `@PostMapping("/usuarios")`, que é chamado quando uma requisição POST é feita para o endpoint `/usuarios`.

**2. Método `criarUsuario`:**

- O método aceita um objeto `Usuario` no corpo da requisição, anotado com `@RequestBody`.
- O objeto `Usuario` é deserializado automaticamente do corpo da requisição JSON.
- O método retorna uma string indicando que o usuário foi criado com sucesso.

**Conclusão**

`@PostMapping` é uma anotação útil do Spring Framework para mapear requisições HTTP POST a métodos específicos em controladores. Isso facilita o desenvolvimento de APIs RESTful e a lidar com ações que envolvem a criação ou atualização de recursos. A anotação é flexível e pode ser personalizada para atender a diferentes requisitos de mapeamento.


---
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
