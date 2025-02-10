# Instalar Ferramenta

## Linguagem
- **Java**: <a href="https://www.azul.com/downloads/?package=jdk#zulu">Zulu</a>

## IDE
- **VSCode**: <a href="https://code.visualstudio.com/download">VSCode</a>
- **Spring Tool Suite**: <a href="https://spring.io/tools">Spring</a>

## Maven
📌 **Opção 2: Instalar Manualmente (Windows, Linux, Mac)**

1️⃣ **Baixe o Maven** no site oficial:

👉 <a href="https://maven.apache.org/download.cgi">Apache Maven - Download</a>

2️⃣ **Extraia o arquivo** para um local do seu sistema (ex: `C:\Program Files\Apache\Maven`).

3️⃣ **Adicione o Maven ao PATH** (Apenas Windows):

- Abra **Variáveis de Ambiente** (`Win + R`, digite `sysdm.cpl` e vá em "Variáveis de Ambiente").
- No campo **Path**, adicione:
```
C:\Program Files\Apache\Maven\bin
```
- Salve e reinicie o VSCode.

4️⃣ Abra o **terminal do VSCode** (ou CMD) e execute:
```
mvn -version
```

### Javalin + Maven
Javalin é um micro framework para desenvolvimento de aplicações web em Java e Kotlin. Ele foi inicialmente um fork do framework SparkJava, mas rapidamente se transformou em uma reescrita baseada em lições aprendidas com SparkJava e o framework JavaScript Koa.js. O Javalin é conhecido por ser leve e fácil de usar, sendo utilizado principalmente para a criação de APIs REST, mas também oferece suporte a WebSockets e a leitura de arquivos estáticos, como HTML.

Além disso, o Javalin tem a capacidade de estender o objeto Context, permitindo que os desenvolvedores adicionem funções personalizadas para facilitar o trabalho com objetos que não são nativamente suportados em Java. Ele também suporta a serialização de objetos e o compartilhamento de informações entre handlers e requests através de um cookie-store-map.

O Javalin é utilizado por grandes empresas como Microsoft e Red Hat e é conhecido por sua documentação clara e pela facilidade em construir REST APIs.

Roda o servidor Javalin.
```
mvn clean compile exec:java
```

### Chocolatey + Maven

Instalar o Maven pelo Chocolatey (Windows)
```
choco install maven
```
Verificar a instalação
```
mvn -version
```

[Chocolatey: o que é e como usar](https://imasters.com.br/back-end/chocolatey-o-que-e-e-como-usar)

## SQL

1️⃣ **SGBD**: sevidor **<a href="https://dev.mysql.com/downloads/installer/">MySQL</a>**.

2️⃣ **Ferramenta visual para controlar SGBD**: **<a href="https://dev.mysql.com/downloads/workbench/?os=33">Workbench</a>**.
