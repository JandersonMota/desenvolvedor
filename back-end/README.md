# Spring Framework

Os códigos que possuem `@` representam anotações no Java. As **anotações** são uma maneira de fornecer metadados para o compilador ou framework (como o Spring e o JPA), indicando como o código deve ser processado ou executado.

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
