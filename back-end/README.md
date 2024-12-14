# Spring Framework

## Spring Data JPA
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
