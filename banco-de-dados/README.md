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

**Conclusão**

`@Entity` é uma ferramenta poderosa para mapear objetos Java para tabelas de banco de dados, facilitando a persistência de dados e a gestão de entidades em aplicações de software que usam frameworks ORM.

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
