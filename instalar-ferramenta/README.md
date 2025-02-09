# Instalar Ferramenta

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
