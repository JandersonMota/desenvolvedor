# OAuth 2

O OAuth 2 é uma estrutura de autorização que permite que aplicativos obtenham acesso limitado a contas de usuário em um serviço HTTP.

## Funções do OAuth

O OAuth define quatro funções:

**Proprietário do recurso:** o proprietário do recurso é o usuário que autoriza um aplicativo a acessar sua conta. O acesso do aplicativo à conta do usuário é limitado ao escopo da autorização concedida (por exemplo, acesso de leitura ou gravação)

**Cliente:** O cliente é o aplicativo que deseja acessar a conta do usuário. Antes de fazer isso, ele deve ser autorizado pelo usuário e a autorização deve ser validada pela API.

**Servidor de recursos:** o servidor de recursos hospeda as contas de usuário protegidas.

**Servidor de Autorização:** O servidor de autorização verifica a identidade do usuário e emite tokens de acesso para o aplicativo.


**Saiba mais:**
- [DigitalOcean: introdução ao OAuth 2](https://spring.io/projects/spring-framework)


# JWT - JSON Web Tokens

## O que é JSON Web Token?

Os JSON Web Tokens são um método RFC 7519 aberto e padrão do setor para representar declarações com segurança entre duas partes.

JWT. IO permite decodificar, verificar e gerar JWT.

> **Aviso:** JWTs são credenciais que podem conceder acesso a recursos. Tenha cuidado onde você os cola! Não registra tokens, toda a validação e depuração são feitas no lado do cliente.

Embora os JWTs possam ser criptografados para também fornecer sigilo entre as partes, vamos nos concentrar nos tokens *assinados*. Os tokens assinados podem verificar a *integridade* das declarações contidas nele, enquanto os tokens criptografados *ocultam* essas declarações de outras partes. Quando os tokens são assinados usando pares de chaves pública/privada, a assinatura também certifica que apenas a parte que possui a chave privada é a que a assinou.

## Quando você deve usar JSON Web Tokens?

Aqui estão alguns cenários em que os tokens Web JSON são úteis:

- **Autorização:** esse é o cenário mais comum para usar o JWT. Depois que o usuário estiver conectado, cada solicitação subsequente incluirá o JWT, permitindo que o usuário acesse rotas, serviços e recursos permitidos com esse token. O Single Sign On é um recurso que usa amplamente o JWT hoje em dia, devido à sua pequena sobrecarga e à sua capacidade de ser facilmente usado em diferentes domínios.

- **Troca de informações:** JSON Web Tokens são uma boa maneira de transmitir informações com segurança entre as partes. Como os JWTs podem ser assinados, por exemplo, usando pares de chaves pública/privada, você pode ter certeza de que os remetentes são quem dizem ser. Além disso, como a assinatura é calculada usando o cabeçalho e a carga, você também pode verificar se o conteúdo não foi adulterado.

## Qual é a estrutura do JSON Web Token?

Em sua forma compacta, os JSON Web Tokens consistem em três partes separadas por pontos (.), que são:

- Cabeçalho
- Carga útil
- Assinatura

Portanto, um JWT normalmente se parece com o seguinte.

`xxxxx.yyyyy.zzzzz`

**Saiba mais:**
- [JWT](https://jwt.io/)
