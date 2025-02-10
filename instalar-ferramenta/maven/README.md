# Maven

## Comando

1. Baixar todas as bibliotecas e construir o projeto:
```
mvn clean install
```

2. Limpar o cache do Maven e recompilar o projeto:
```
mvn clean compile -U
```

3. Executar projeto:
- Executa um projeto Java baseado em Maven, desde que um mainClass esteja definido no arquivo pom.xml. Esse comando geralmente é usado para rodar aplicações Java standalone.
```
mvn exec:java
```
4. Iniciar o servidor:
- Executar diretamente o seu aplicativo Spring Boot sem precisar empacotar o projeto em um `.jar`.

📌 Quando usar `mvn spring-boot:run`?

✅ Durante o desenvolvimento, para testar rapidamente a aplicação sem precisar criar um `.jar`.

✅ Quando você quer que o Maven gerencie todas as dependências e execução automaticamente.

❌ Não é recomendado para produção (nesse caso, você gera um `.jar` e roda com `java -jar`).
```
mvn spring-boot:run
```
