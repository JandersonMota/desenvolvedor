# Angular

- Baixe o <a href="https://nodejs.org/en/">Node.js LTS</a>
- **Verificar a versão instalada do Node:** abra o CMD e digite "node -v".
- **Instalar o Angular CLI:** abra o CMD e digite "npm install -g @angular/cli" para instalar.
- **Verificar a versão instalada do Angular:** abra o CMD e digite "ng --version".
- Baixe o VSCode.
  - Extensões:
    - Pesquisar por "loiane" (Angular Extension Pack) ou Angular Language Service.

## Comandos
- Criar projeto: "ng new < nome-do-projeto >"
  - Ex.: "ng new crud-angular"
  - Vai perguntar se quer roteamento e a resposta é SIM.
  - Vai perguntar "qual é o estilo de CSS que quer utilizar?".
🔹 Observação:
  - Este comando cria um projeto Angular com Standalone API ativada por padrão.
  - O Angular não criará `app.module.ts`.
  - Ele usará `bootstrapApplication(AppComponent)` no `main.ts` para inicializar o app.
  - Os componentes são Standalone (usam `standalone: true` em vez de serem declarados em um módulo).
  - Melhor performance e menos código desnecessário.

- Criar projeto: "ng new < nome-do-projeto > --standalone=false"
  - Este comando força o Angular a criar o projeto usando NgModule (arquitetura antiga/tradicional).
🔹 Observação:
  - O Angular criará `app.module.ts`.
  - Os componentes são agrupados dentro de um `NgModule`.
  - O `main.ts` inicializa o app chamando `platformBrowserDynamic().bootstrapModule(AppModule)`.
  - Boa escolha se você quer compatibilidade com projetos mais antigos.

📌 Quando usar cada um?

✔ Modo Standalone (sem `app.module.ts`)

  ✅ Melhor para novos projetos e mais simples de manter.

  ✅ Performance melhor porque elimina a sobrecarga dos módulos.

  ✅ Recomendado pelo próprio Angular para novos projetos.

  ❌ Pode ser mais difícil integrar com bibliotecas mais antigas.

✔ Modo NgModule (com `app.module.ts`)

  ✅ Melhor se você trabalha com projetos antigos que usam módulos.

  ✅ Algumas bibliotecas ainda dependem de módulos.

  ❌ Adiciona mais código e pode ser mais complexo para manutenção.

Se você quer usar a abordagem mais moderna, use o Standalone API. Se precisa de compatibilidade com código legado, use `--standalone=false`. 🚀

- Rodar projeto: "ng serve"
  - Parar o projeto: "Ctrl + c"
  - Caso o erro seja parecido com esse:
    
    ```
    ng : O arquivo C:\Users\Jande\AppData\Roaming\npm\ng.ps1 não pode ser carregado porque a execução de scripts foi desabilitada neste sistema. Para obter mais informações, consulte about_Execution_Policies em https://go.microsoft.com/fwlink/?LinkID=135170.
    No linha:1 caractere:1
    + ng serve
    + ~~
        + CategoryInfo          : ErrodeSegurança: (:) [], PSSecurityException
        + FullyQualifiedErrorId : UnauthorizedAccess
    ```
  
  Esse erro ocorre porque a política de execução do PowerShell está bloqueando a execução do script `ng.ps1`. Para resolver isso, siga estes passos:

**Solução: Alterar a política de execução**
1. Abra o PowerShell como administrador:
  - Pressione `Win + S`, digite `PowerShell`, clique com o botão direito e selecione Executar como administrador.

2. Verifique a política de execução atual digitando:
  ```powershell
  Get-ExecutionPolicy
  ```
  Se o resultado for `Restricted`, significa que scripts não podem ser executados.

3. Altere a política de execução para permitir scripts digitando:
  ```powershell
  Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
  ```
  Se for solicitado, digite `A` (Sim para todos).

4. Tente novamente executar o Angular CLI:
  ```
  ng serve
  ```

- Instalar o <a href="https://material.angular.io/">Angular Material</a>
  - Digite no terminal "ng add @angular/material".
