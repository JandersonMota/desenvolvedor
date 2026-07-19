# DOCKER
<img width="1000" height="418" alt="image" src="https://github.com/user-attachments/assets/ac499249-ba3c-48df-88da-ffe7864815da" />

## Fundamentos

### Modelo Cliente-Servidor
O modelo cliente-servidor é uma estrutura de aplicação que distribui as tarefas e cargas de trabalho entre os fornecedores de um recurso ou serviço, designados como servidores, e os requerentes dos serviços, designados como clientes.

<img width="461" height="222" alt="image" src="https://github.com/user-attachments/assets/75f224c8-e457-402a-9d2a-ac78b6991467" />

### Cloud
A cloud computing é o acesso sob demanda, via internet, a recursos de computação - aplicativos, servidores (físicos e virtuais), armazenamento de dados, ferramentas de desenvolvimento, recursos de rede e muito mais - hospedados em um data center remoto gerenciado por um provedor de serviços em cloud (Cloud Solution Provider). O CSP disponibiliza esses recursos por uma assinatura mensal ou por um valor **cobrado conforme o uso**.

### Virtualização
A virtualização utiliza software para criar uma camada de abstração sobre o hardware do computador, permitindo que os recursos de hardware de um único computador (processadores, memória, armazenamento, etc) sejam divididos em vários computadores virtuais.

<img width="428" height="409" alt="image" src="https://github.com/user-attachments/assets/2d3654cc-abf8-475c-a22e-a95a569d2088" />

### Microserviços
Microserviços são uma abordagem arquitetônica e organizacional do desenvolvimento de software na qual o software consiste em pequenos serviços independentes que se comunicam usando APIs bem definidas. Esses serviços pertencem a pequenas equipes autossuficientes.

As arquiteturas de microserviços facilitam a escalabilidade e agilizam o desenvolvimento de aplicativos, habilitando a inovação e acelerando o tempo de introdução de novos recursos no mercado.

Hoje, gigantes do mercado como Netflix e Spotify, divulgam a receita do scesso ao transformar suas aplicações monolíticas em mais de 500 microsserviços.

Quando quebramos uma aplicação monolítica em várias pequenas partes, conseguindo escalá-las de forma separada. Supondo que um serviço de autenticação seja chamado várias vezes durante a sessão de um usuário, com certeza o stress sobre ele é maior.

### O que é um container
Os contêineres são uma tecnologia usada para reunir um aplicativo e todos os seus arquivos necessários em um ambiente de tempo de execução. Como uma unidade, o contêiner pode ser facilmente movido e executado em qualquer sistema operacional, em qualquer contexto.

[IBM - contêineres](https://www.ibm.com/br-pt/cloud/learn/containers)
[Red Hat - contêineres](https://www.redhat.com/pt-br/topics/containers)

### O que é Docker?
Com o Docker, é possível lidar com os containers como se fossem máquinas virtuais modulares e extremamente leves. Além disso, os containers oferecem maior flexibilidade para você criar, implantar, copiar e migrar um container de um ambiente para outro. Isso otimiza as aplicações em nuvem (privada e pública).

<img width="517" height="494" alt="image" src="https://github.com/user-attachments/assets/2f9719a9-7eba-4435-8f22-a7319d21ce8d" />

[Red Hat](https://www.redhat.com/pt-br/topics/containers/what-is-docker)
[Microsoft](https://docs.microsoft.com/pt-br/dotnet/architecture/microservices/container-docker-introduction/docker-defined)

### Qual é a diferença entre virtualização e os containers?
As duas tecnologias são distintas porém complementares. Veja uma maneira fácil de distinguir ambas:
- Com a virtualização, é possível executar sistemas operacionais (Windows ou Linux) simultaneamente em um único sistema de hardware.
- Os containers compartilham o mesmo kernel do sistema operacional e isolam os processos da aplicação do restante do sistema. Os containers Linux são extremamente portáteis, mas devem ser compatíveis com sistema subjacente.

[Red Hat - Containers e VMs](https://www.redhat.com/pt-br/topics/containers/containers-vs-vms)

### Comandos essenciais
[Medium](https://medium.com/xp-inc/principais-comandos-docker-f9b02e6944cd)
[Docker](https://docs.docker.com/engine/reference/commandline/docker/)
[Dev](https://dev.to/soutoigor/docker-imagens-containers-e-seus-principais-comandos-23p6)
