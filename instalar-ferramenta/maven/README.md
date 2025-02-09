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
