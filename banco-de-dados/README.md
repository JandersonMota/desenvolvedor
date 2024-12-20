# ORM (*Object-relational mapping* ou mapeamento objeto-relacional)

## Anotação

### @Entity
`@Entity` é uma anotação usada em Java, principalmente no contexto de frameworks de mapeamento objeto-relacional (ORM), como o Hibernate e o JPA (Java Persistence API). Essa anotação é utilizada para indicar que uma classe Java representa uma tabela em um banco de dados. Cada instância dessa classe é considerada uma linha (ou registro) na tabela correspondente.

Aqui estão alguns pontos importantes sobre o uso de `@Entity`:

**1. Definição da Tabela:**

- Quando você anota uma classe com `@Entity`, você está dizendo ao ORM que essa classe deve ser mapeada para uma tabela no banco de dados.
- Por padrão, o nome da tabela no banco de dados será o mesmo nome da classe, mas você pode personalizar o nome da tabela usando a anotação `@Table`.

**2. Atributos e Colunas:**

- Os campos (ou propriedades) da classe correspondem às colunas da tabela. Você pode usar anotações como `@Id` para indicar a chave primária, `@Column` para especificar detalhes da coluna, `@GeneratedValue` para gerar valores automaticamente, entre outras.

**3. Relacionamentos:**

- Classes anotadas com `@Entity` podem representar entidades que têm relacionamentos com outras entidades. Você pode usar anotações como `@ManyToOne`, `@OneToMany`, `@OneToOne`, e `@ManyToMany` para definir esses relacionamentos.

**4. Persistência:**

- As operações de CRUD (Create, Read, Update, Delete) podem ser realizadas nas entidades usando o EntityManager, que é uma interface fornecida pelo JPA.

**Exemplo de Uso**
Aqui está um exemplo simples de uma classe anotada com `@Entity`:

``` Java
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.Table;

@Entity
@Table(name = "usuarios")
public class Usuario {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(name = "nome")
    private String nome;

    @Column(name = "email")
    private String email;

    // Construtores, getters e setters
}
```

Neste exemplo:

- A classe `Usuario` é mapeada para a tabela `usuarios`.
- O campo `id` é a chave primária e é gerado automaticamente.
- Os campos `nome` e `email` correspondem às colunas `nome` e `email` na tabela.

Algumas anotações de @Entity
- \`@Table\`
    - Exemplo: `@Table(name="usuarios")`
    - Definição: atribui nome a tabela.
      
- \`@Id\`
    - Exemplo: `@Id`
    - Definição: indicar a chave primária.
      
- \`@GeneratedValue\`
    - Exemplo: `@GeneratedValue(strategy = GenerationType.IDENTITY)` // Indica que o valor da chave primária será gerado automaticamente pelo banco de dados.</span>
    - Definição: para gerar valores automaticamente.
      
- \`@Column\`
    - Exemplo: `@Column(name = "cpf", nullable = false, unique = true, length = 11)`
    - Definição: é usada para especificar como um campo de uma classe Java deve ser mapeado para uma coluna em uma tabela de banco de dados, ou seja, especifica detalhes da coluna.
    - Atributos da anotação:
      
        | **Atributos**    | **Exemplo**                                    | **Definição**                                 |
        |------------------|------------------------------------------------|-----------------------------------------------|
        | name             | `@Column(name = "id_cliente")`                 | Especifica o nome da coluna no banco de dados.|
        | nullable         | `@Column(nullable = false)`                    | Indica se a coluna pode conter valores nulos. |
        | unique           | `@Column(unique = true)`                       | Indica se a coluna deve conter valores únicos.|
        | length           | `@Column(length = 100)`                        | Especifica o comprimento máximo da coluna (útil para tipos de dados de caracteres). |
        | precision        | `@Column(precision = 10)`                      | Especifica a precisão para tipos numéricos.   |
        | scale            | `@Column(scale = 2)`                           | Especifica a escala para tipos numéricos.     |
        | updatable        | `@Column(updatable = false)`                   | Indica se a coluna pode ser atualizada.       |
        | insertable       | `@Column(insertable = false)`                  | Indica se a coluna pode ser inserida.         |
        | columnDefinition | `@Column(columnDefinition = "cp(var) varchar")`| Permite especificar a definição da coluna no banco de dados (útil para tipos de dados específicos do banco de dados).|

**Conclusão**

`@Entity` é uma ferramenta poderosa para mapear objetos Java para tabelas de banco de dados, facilitando a persistência de dados e a gestão de entidades em aplicações de software que usam frameworks ORM.

> **Relacionamentos**

As anotações \`@ManyToOne\`, \`@OneToMany\`, \`@OneToOne\`, e \`@ManyToMany\` são usadas no JPA (Java Persistence API) para definir os relacionamentos entre entidades em um mapeamento objeto-relacional (ORM). Vamos explorar cada uma delas com detalhes e exemplos.

**1. @ManyToOne**
- **Descrição**: Indica um relacionamento onde muitas instâncias de uma entidade podem estar associadas a uma única instância de outra entidade.
- **Uso**: Geralmente usado no lado "muitos" do relacionamento.
- **Exemplo**: Um `Pedido` pode ter muitas `Itens`, mas cada `Item` pertence a um único `Pedido`.

``` Java
@Entity
public class Item {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String nome;
    private double preco;

    @ManyToOne
    @JoinColumn(name = "pedido_id")
    private Pedido pedido;
}
```

**2. @OneToMany**
- **Descrição**: Indica um relacionamento onde uma instância de uma entidade pode estar associada a muitas instâncias de outra entidade.
- **Uso**: Geralmente usado no lado "um" do relacionamento.
- **Exemplo**: Um `Pedido` pode ter muitos `Itens`.

``` Java
@Entity
public class Pedido {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String numero;

    @OneToMany(mappedBy = "pedido")
    private List<Item> itens;
}
```

**3. @OneToOne**
- **Descrição**: Indica um relacionamento onde uma instância de uma entidade está associada a uma única instância de outra entidade.
- **Uso**: Usado quando há uma relação de um-para-um.
- **Exemplo**: Um `Usuario` pode ter um único `Perfil`.

``` Java
@Entity
public class Usuario {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String nome;

    @OneToOne(cascade = CascadeType.ALL)
    @JoinColumn(name = "perfil_id", referencedColumnName = "id")
    private Perfil perfil;
}

@Entity
public class Perfil {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String descricao;
}
```

**4. @ManyToMany**
- **Descrição**: Indica um relacionamento onde muitas instâncias de uma entidade podem estar associadas a muitas instâncias de outra entidade.
- **Uso**: Usado quando há uma relação muitos-para-muitos.
- **Exemplo**: Um `Curso` pode ter muitos `Alunos`, e um `Aluno` pode estar matriculado em muitos `Cursos`.

``` Java
@Entity
public class Curso {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String nome;

    @ManyToMany
    @JoinTable(
        name = "curso_aluno",
        joinColumns = @JoinColumn(name = "curso_id"),
        inverseJoinColumns = @JoinColumn(name = "aluno_id")
    )
    private List<Aluno> alunos;
}

@Entity
public class Aluno {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String nome;

    @ManyToMany(mappedBy = "alunos")
    private List<Curso> cursos;
}
```

**Explicação dos Atributos**

1. `@JoinColumn`:

- **Uso**: Especifica a coluna que faz a ligação entre as tabelas.
- **Atributos**:
    - `name`: Nome da coluna na tabela.
    - `referencedColumnName`: Nome da coluna na tabela referenciada.

2. `mappedBy`:

- **Uso**: Indica o campo no lado oposto do relacionamento que possui a propriedade `@JoinColumn`.
- **Exemplo**: No relacionamento `@OneToMany`, o campo `mappedBy` aponta para o campo `@ManyToOne` na entidade relacionada.

3. `cascade`:

- **Uso**: Especifica as operações que devem ser cascadas para a entidade relacionada.
- **Atributos**:
    - `CascadeType.ALL`: Todas as operações (persist, merge, remove, etc.).
    - `CascadeType.PERSIST`: Persistência.
    - `CascadeType.MERGE`: Mesclagem.
    - `CascadeType.REMOVE`: Remoção.

4. `@JoinTable`:

- **Uso**: Usado em relacionamentos @ManyToMany para especificar a tabela de junção.
- **Atributos**:
    - `name`: Nome da tabela de junção.
    - `joinColumns`: Colunas na tabela de junção que fazem referência à tabela principal.
    - `inverseJoinColumns`: Colunas na tabela de junção que fazem referência à tabela relacionada.

**Exemplos Completos**

**1. @ManyToOne e @OneToMany**

``` Java
@Entity
public class Pedido {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String numero;

    @OneToMany(mappedBy = "pedido")
    private List<Item> itens;
}

@Entity
public class Item {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String nome;
    private double preco;

    @ManyToOne
    @JoinColumn(name = "pedido_id")
    private Pedido pedido;
}
```

**2. @OneToOne**

``` Java
@Entity
public class Usuario {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String nome;

    @OneToOne(cascade = CascadeType.ALL)
    @JoinColumn(name = "perfil_id", referencedColumnName = "id")
    private Perfil perfil;
}

@Entity
public class Perfil {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String descricao;
}
```

**3. @ManyToMany**

``` Java
@Entity
public class Curso {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String nome;

    @ManyToMany
    @JoinTable(
        name = "curso_aluno",
        joinColumns = @JoinColumn(name = "curso_id"),
        inverseJoinColumns = @JoinColumn(name = "aluno_id")
    )
    private List<Aluno> alunos;
}

@Entity
public class Aluno {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String nome;

    @ManyToMany(mappedBy = "alunos")
    private List<Curso> cursos;
}
```

**Conclusão**

As anotações `@ManyToOne`, `@OneToMany`, `@OneToOne`, e `@ManyToMany` são essenciais para definir relacionamentos entre entidades em um mapeamento objeto-relacional (ORM) com JPA. Elas permitem que você modele de maneira clara e eficiente os relacionamentos entre as tabelas do seu banco de dados, facilitando a manipulação e consulta dos dados.

---
### @Embeddable
`@Embeddable` é uma anotação do JPA (Java Persistence API) usada para indicar que uma classe Java pode ser incorporada (embedded) dentro de outra entidade. Isso significa que os campos da classe anotada com `@Embeddable` serão mapeados diretamente na tabela da entidade que a incorpora, em vez de ter sua própria tabela separada.

**Características do `@Embeddable`**

**1. Sem Tabela Própria:**

- A classe anotada com `@Embeddable` não terá sua própria tabela no banco de dados. Seus campos serão incorporados na tabela da entidade que a usa.

**2. Reutilização de Componentes:**

- `@Embeddable` é útil para reutilizar conjuntos de campos que aparecem em várias entidades. Por exemplo, um endereço pode ser um componente comum em várias entidades, como `Cliente`, `Fornecedor`, etc.

**3. Anotações de Mapeamento:**

- Você pode usar anotações como `@Column` em campos de classes `@Embeddable` para especificar detalhes de mapeamento, como nomes de colunas.

**Exemplo de Uso**

Vamos ver um exemplo para ilustrar o uso de `@Embeddable`.

**Classe \`Endereco\` (anotada com \`@Embeddable\`)**

``` Java
import javax.persistence.Embeddable;
import javax.persistence.Column;

@Embeddable
public class Endereco {

    @Column(name = "rua")
    private String rua;

    @Column(name = "cidade")
    private String cidade;

    @Column(name = "estado")
    private String estado;

    @Column(name = "cep")
    private String cep;

    // Construtores, getters e setters
}
```

\####-classe `Cliente` (anotada com `@Entity`)

``` Java
import javax.persistence.Entity;
import javax.persistence.Id;
import javax.persistence.Embedded;
import javax.persistence.Table;

@Entity
@Table(name = "clientes")
public class Cliente {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(name = "nome")
    private String nome;

    @Embedded
    private Endereco endereco;

    // Construtores, getters e setters
}
```

####-classe `Fornecedor` (anotada com `@Entity`)

``` Java
import javax.persistence.Entity;
import javax.persistence.Id;
import javax.persistence.Embedded;
import javax.persistence.Table;

@Entity
@Table(name = "fornecedores")
public class Fornecedor {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(name = "nome_empresa")
    private String nomeEmpresa;

    @Embedded
    private Endereco endereco;

    // Construtores, getters e setters
}
```

**Tabela Resultante**

No banco de dados, as tabelas clientes e fornecedores terão colunas para os campos do Endereco:

- Tabela `clientes`:

  - `id`
  - `nome`
  - `rua`
  - `cidade`
  - `estado`
  - `cep`

- Tabela `fornecedores`:

  - `id`
  - `nome_empresa`
  - `rua`
  - `cidade`
  - `estado`
  - `cep`

**Conclusão**

`@Embeddable` é uma anotação útil para reutilizar conjuntos de campos em várias entidades, evitando a redundância de código e simplificando o mapeamento de objetos para tabelas de banco de dados. Isso torna o código mais limpo e manutenível.
