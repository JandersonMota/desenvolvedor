# Angular

- Baixe o <a href="https://nodejs.org/en/">Node.js LTS</a>
- **Verificar a versão instalada do Node:** abra o CMD e digite "node -v".
- **Instalar o Angular CLI:** abra o CMD e digite "npm install -g @angular/cli" para instalar.
- **Verificar a versão instalada do Angular:** abra o CMD e digite "ng --version".
- Baixe o VSCode.
  - Extensões:
    - Pesquisar por "loiane" (Angular Extension Pack) ou Angular Language Service.

## Comandos
- Criar projeto: "ng new crud-angular"
  - Vai perguntar se quer roteamento e a resposta é SIM.
  - Vai perguntar "qual é o estilo de CSS que quer utilizar?".
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
