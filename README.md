# Conhecimento para desenvolvedor

## 1. Estrutura de dados
Estruturas de dados são a base para a análise de complexidade de algoritmos, pois elas definem como os dados são armazenados e manipulados. Ao entender a complexidade das operações de cada estrutura (inserção, busca, remoção, etc.), você pode prever o desempenho geral de um algoritmo e fazer escolhas informadas para resolver problemas de maneira eficiente.

[Saiba mais](https://github.com/JandersonMota/estrutura-de-dados)

## 2. Programação Orientada a Objetos - POO
[Saiba mais](https://github.com/JandersonMota/programacao-orientada-objetos)

## 3. Front-end

### 3.1 Web

#### 3.1.1 Código
- **HTML**: Linguagem de marcação usada para criar a estrutura de uma página web. [+](https://github.com/JandersonMota/ifba-oficina-html_css)
- **CSS**: Linguagem usada para estilizar e layout de uma página web. [+](https://github.com/JandersonMota/ifba-oficina-html_css/tree/main/Formatar%20CSS)
- **JavaScript**: Linguagem de programação usada para adicionar interatividade e funcionalidades dinâmicas às páginas web. [+](https://github.com/JandersonMota/estudando-javascript)

#### 3.1.2 CA SSL - Autoridade de Certificação Secure Sockets Layer
- **Descrição**: Autoridades de certificação que emitem certificados SSL/TLS para segurizar a comunicação entre o cliente e o servidor.

#### 3.1.3 CDN - Content Delivery Network ou Rede de Distribuição de Conteúdo
- **Descrição**: Infraestrutura que distribui conteúdo web de maneira eficiente à escala globalmente.

#### 3.1.4 SaaS - Software as a Service
- **Descrição**: Modeo de software projetado para ser usado como um serviço.

#### 3.1.5 SEO (Otimização para motores de busca)
- **Descrição**: Otimização de páginas web para melhorar a visibilidade em motores de busca.

#### 3.1.6 Interface do Usuário (UI) e à Experiência do Usuário (UX)
- **Descrição**: Desenvolvimento de interfaces de usuário e experiência de usuário para melhorar a interação do usuário com a aplicação.

#### 3.1.7 Psicologia das cores
- **Descrição**: Estudo das emoções e percepivas associadas a cores para melhorar a experiência de usuário.

### 3.2 Livro
- **"Don't Make Me Think" – Steve Krug**:
  Um clássico que aborda usabilidade de forma direta e acessível. Ideal para quem quer entender como os usuários interagem com websites e como simplificar a experiência.
- **"Designing for the Web" – Mark Boulton**:
  Um guia prático sobre design para web, focando em tipografia, cores, e layout. Aborda aspectos fundamentais e técnicas modernas para criar interfaces visualmente atraentes e funcionais.

## 4. Back-end

### 4.1 Web

#### Java Spring
- **Java Spring**: Framework usado para desenvolvimento de aplicações web em Java.
- **Java JPA**: API usada para mapeamento objeto-relacional (ORM) em Java.
- **Java JTE**:

**Saiba mais:**
- [Spring Framework: Documentação Oficial](https://spring.io/projects/spring-framework)
- [Java Persistence API (JPA): Documentação Oficial](https://javaee.github.io/javaee-spec/jpa)
- [Neste GitHub: JPA](https://github.com/JandersonMota/desenvolvedor/blob/main/back-end/README.md)
- [Spring Boot: Java Template Engine (JTE)](https://foojay.io/today/spring-boot-java-template-engine-jte/)

## 5. Banco de dados
- **SQL**: Linguagem usada para gerenciar bancos de dador.
- **ORM (Object-relational mapping)**: Ténica usada para mapear objetos em aplicações orientadas a objetos para tabelas em bancos de dador.

**Saiba mais:**
- [W3Schools: SQL Tutorial](https://www.w3schools.com/sql/)
- [Hibernate: Documentação Oficial](https://hibernate.org/documentaion.html)
- [Neste GitHub: ORM](https://github.com/JandersonMota/desenvolvedor/tree/main/banco-de-dados)

## 6. Engenharia de software
- **Monolito de Software**: Arquitetura de aplicações em que todas as funcionalidades são empacotadas em uma única aplição.
- **Arquitetura Cliente-Servidor**
- **Arquitetura em Camadas**

**Saiba mais:**
- [Martin Fowler: Monolito](https://martinfowler.com/bliogs/anatomy-of-monolith.html)

## 7. Ferramenta interesante

### 7.1 Feature Flags
- **Descrição**: Mecanismo usada para ativar ou desativar funcionalidades dinâmicas sem reiniciar a aplicação inteira.

**Saiba mais:**
- [Neste GitHub](https://github.com/JandersonMota/desenvolvedor/tree/main/front-end)
- [Martin Fowler: Feature Toggles](https://martinfowler.com/articles/feature-toggles.html)

### 7.2 Autenticação a aplicativos
- **Keycloak**: Plaforma de autenticação e autorização open source que suporta autenticação social, SSO, e gerenciamento de identidades.

**Saiba mais:**
- [Keycloak: Documentação Oficial](https://www.keycloak.org/)

## 8. Infraestrutura CI/CD
- Jenkins
- Docker

### 8.1 O que é IaC?
- Infraestrutura como código (IaC) é a prática de gerenciar e provisionar infraestrutura de TI usando arquivos de configuração legíveis por máquinas.
- Substitui processos manuais com código e automação.
- Principais características:
  - Imutabilidade: a infraestrutura é reconstruída em vez de alterada diretamente.
  - Reutilização: códigos reutilizáveis para configurações repetidas.
  - Ex.: utilização de arquivos YAML, JSON ou HCL para definir configurações de servidores e redes.
- Vantagens da IaC:
  - Automatização completa
    - Reduz erros humanos.
    - Diminui o tempo de provisionamento.
  - Consistência
    - Infraestrutura uniforme em diferentes ambientes (desenvolvimento, teste, produção).
  - Auditabilidade
    - Configurações versionadas em sistemas como Git.
  - Escalabilidade e flexibilidade
    - Facilita o crecimento rápido das aplicações e infraestruturas.
  - Custo-benefício
    - Economiza tempo e recursos humanos.
   
**Benefícios com IaC**
- Estudo de caso:
  - Uma empresa X reduziu o tempo de provisionamento de servidores de 2 dias para 20 minutos usando Terraform.
- Dados estatísticos:
  - Adoção de IaC pode reduzir até 90% dos erros de configuração.
 
**Desafios e boas práticas**
- Desafios:
  - Curva de aprendizado inicial.
  - Problemas de compatibilidade entre ferramentas.
- Boas práticas:
  - Versionar sempre: manter controle com Git.
  - Documentar: detalhar configurações para facilitar manutenção.
  - Automatizar testes: validação contínua das configurações.

### 8.2 Ferramentas de IaC
- Terraform
- AWS CloudFormation
- Ansible
- Puppet
- Chef
- SaltStack
- Pulumi
- Kubernetes (Helm)
- Google Cloud Deployment Manager
- Vagrant


- Prometheus
- Grafana
- Alertmanager: gerenciamento de alertas.
- Loki: centralização de logs.
- Tempo: monitoramento de traces.
- Jaeger: rastreamento de transações distribuídas.

### 8.3 Introdução à ELK Stack
- O que é a ELK Stack
  - Elasticsearch: Ferramenta de busca e análise para armazenar logs.
  - Logstash: Pipeline para coleta e processamento de logs.
  - Kibana: Ferramenta de visualização e análise de logs.

- Benefícios da ELK Stack
  - Open-source e altamente customizável.
  - Escalabilidade para grandes volumes de dados.
  - Integração com diversas ferramentas e protocolos.
 
- Cenários de uso
  - Monitoramento de aplicações.
  - Investigação de incidentes de segurança.
  - Otimização de desempenho de sistemas.
