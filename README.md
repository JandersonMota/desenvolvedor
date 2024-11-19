# Conhecimento para desenvolvedor

## 1. Estrutura de dados
Estruturas de dados são a base para a análise de complexidade de algoritmos, pois elas definem como os dados são armazenados e manipulados. Ao entender a complexidade das operações de cada estrutura (inserção, busca, remoção, etc.), você pode prever o desempenho geral de um algoritmo e fazer escolhas informadas para resolver problemas de maneira eficiente.

[Saiba mais](https://github.com/JandersonMota/estrutura-de-dados)

## 2. Programação Orientada a Objetos - POO
[Saiba mais](https://github.com/JandersonMota/programacao-orientada-objetos)

## 3. Front-end
### 3.1 Web
#### 3.1.1 Código
- HTML [+](https://github.com/JandersonMota/ifba-oficina-html_css)
- CSS [+](https://github.com/JandersonMota/ifba-oficina-html_css)
- Javascript

#### 3.1.2 CA SSL - Autoridade de Certificação Secure Sockets Layer
#### 3.1.3 CDN - Content Delivery Network ou Rede de Distribuição de Conteúdo
#### 3.1.4 SaaS - Software as a Service
#### 3.1.5 SEO (Otimização para motores de busca)

### 3.2 Feature Flags
#### Razões para sua importância:

1. **Testes em produção**: As feature flags permitem testar novos recursos diretamente no ambiente de produção, utilizando dados reais, mas sem afetar a experiência de todos os usuários. Isso reduz riscos e possibilita validar funcionalidades em situações reais. Outras técnicas, como *canary deployment*, também podem ser usadas para esse propósito.
2. **Entrega contínua de recursos**: Com feature flags, é possível implementar um recurso de forma parcial, colocá-lo em produção e controlá-lo sem expor imediatamente aos usuários. Assim, você pode disponibilizá-lo gradualmente ou ativá-lo apenas quando o desenvolvimento estiver 100% concluído, promovendo uma estratégia de entrega contínua e mais eficiente.
3. **Personalização**: As feature flags permitem habilitar ou desabilitar recursos de forma segmentada, adaptando funcionalidades de acordo com as preferências ou necessidades de grupos específicos de usuários. Essa flexibilidade aumenta a satisfação do cliente e otimiza a usabilidade do sistema.

#### Vantagens significativas, especialmente em ambientes de desenvolvimento ágil, onde a entrega contínua e a experimentação são prioridades.

1. **Testes em produção com segurança**

   As feature flags permitem testar novos recursos diretamente no ambiente de produção com usuários reais, mas sem impactar todos os usuários. Isso ajuda a:
- Validar o comportamento de funcionalidades em condições reais.
- Reduzir riscos de falhas catastróficas.
- Reverter rapidamente uma funcionalidade problemática, desativando a flag sem a necessidade de realizar um rollback completo.

2. **Entrega contínua e incremental**

   Com feature flags, equipes podem lançar funcionalidades em produção antes que estejam totalmente concluídas, mantendo-as ocultas dos usuários finais até que estejam prontas. Isso facilita:
- Implementações graduais (progressive rollout), ativando recursos para um subconjunto de usuários antes de disponibilizá-los para todos.
- Colaboração entre equipes de desenvolvimento, QA e marketing ao sincronizar lançamentos de novos recursos.

3. **Experimentos e A/B Testing**

   As feature flags são ferramentas ideais para experimentação e análise de impacto, permitindo:
- Executar testes A/B para comparar diferentes versões de uma funcionalidade.
- Coletar métricas e feedback antes de decidir qual versão implementar permanentemente.

4. **Personalização da experiência do usuário**

   Com feature flags, é possível personalizar a interface ou os recursos para diferentes grupos de usuários com base em:
- Função ou permissão no sistema (ex.: administradores vs. usuários regulares).
- Região geográfica ou idioma.
- Preferências ou comportamento do usuário.

5. **Facilidade na reversão de mudanças**

   Caso um novo recurso cause problemas, as feature flags permitem desativá-lo imediatamente, sem a necessidade de:
- Reverter código no repositório.
- Realizar um novo ciclo de deploy.

6. **Colaboração entre equipes**

   As feature flags ajudam equipes multidisciplinares a trabalharem juntas com mais eficiência:
- Desenvolvedores podem lançar recursos técnicos gradualmente.
- Equipes de produto ou marketing podem decidir quando ativar os recursos para os usuários finais.

7. **Redução de risco em grandes mudanças**

   Ao introduzir mudanças significativas, as feature flags permitem:
- Implementações parciais ou isoladas, minimizando impactos em sistemas críticos.
- Monitorar o comportamento dos sistemas antes de escalar as alterações.

8. **Suporte ao desenvolvimento ágil**

   As feature flags são fundamentais para práticas como Continuous Integration (CI) e Continuous Delivery (CD), permitindo:
- Ciclos de entrega mais rápidos.
- Lançamentos frequentes com menos interrupções.

9. **Aumento da flexibilidade em decisões**

   Permitem que decisões importantes, como ativar ou desativar um recurso, sejam tomadas com base em dados e não apenas em suposições. Isso é especialmente útil para:
- Validar hipóteses antes de um lançamento completo.
- Ajustar estratégias rapidamente com base no feedback do usuário.

#### Desvantagens e desafios que devem ser considerados durante sua implementação e manutenção:

1. **Complexidade no código**:
O uso excessivo de feature flags pode tornar o código mais complexo e difícil de manter. Condicionais baseadas em flags podem se espalhar pelo código, criando situações conhecidas como *flag debt* (dívida técnica associada às flags). Isso dificulta a legibilidade e aumenta a chance de erros.
2. **Necessidade de gerenciamento**:
As feature flags precisam ser monitoradas e removidas após seu propósito ser cumprido. Flags que permanecem no código sem necessidade aumentam o risco de confusão e acúmulo de lixo técnico, tornando a base de código mais difícil de gerenciar ao longo do tempo.
3. **Risco de erros na configuração**:
Um erro ao configurar uma flag pode causar problemas em produção, como ativar funcionalidades incompletas ou desativar recursos importantes. Para minimizar esse risco, é essencial implementar controles rigorosos e testes para a gestão das flags.
4. **Dificuldade de testes**:
Ambientes com muitas flags podem gerar um número significativo de combinações possíveis de estados (ativadas ou desativadas). Testar todas essas combinações para garantir que o sistema funcione corretamente em todos os cenários pode ser desafiador e demorado.
5. **Impacto no desempenho**:
A lógica adicional necessária para avaliar o estado das feature flags pode impactar o desempenho do sistema, especialmente se muitas flags forem avaliadas em tempo de execução ou em operações críticas.
6. **Dependência de ferramentas externas**:
Se as flags forem gerenciadas por ferramentas de terceiros, pode haver dependência dessas plataformas. Problemas na integração ou na própria ferramenta podem afetar a capacidade de ativar ou desativar recursos.
7. **Risco de exposição indevida**:
Em alguns casos, recursos controlados por feature flags podem ser acessados ou descobertos por usuários avançados (ex.: por meio de inspeção de código ou URLs). Isso pode levar à ativação de funcionalidades ainda em desenvolvimento de forma não intencional.

### 3.3 Livro
- **"Don't Make Me Think" – Steve Krug**:
  Um clássico que aborda usabilidade de forma direta e acessível. Ideal para quem quer entender como os usuários interagem com websites e como simplificar a experiência.
- **"Designing for the Web" – Mark Boulton**:
  Um guia prático sobre design para web, focando em tipografia, cores, e layout. Aborda aspectos fundamentais e técnicas modernas para criar interfaces visualmente atraentes e funcionais.


## 4. Back-end
### 4.1 Web
#### Java Spring
- Java JTE [+](https://foojay.io/today/spring-boot-java-template-engine-jte/)

## 5. Banco de dados
### SQL

## 6. Engenheiro de software
- Monolito de software
