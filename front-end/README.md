# Curso

- Angular
   - <a href="https://www.youtube.com/watch?v=qJnjz8FIs6Q&list=PLGxZ4Rq3BOBpwaVgAPxTxhdX_TfSVlTcY">Loiane Groner</a>
   - <a href="https://www.youtube.com/watch?v=zXL0hmil964&list=PLWXw8Gu52TRKj3tFWHlkheh8rLQRqQ1__">Ralf Lima</a>

# Feature Flags

## Razões para sua importância

1. **Testes em produção**:  
   Permitem testar novos recursos diretamente no ambiente de produção, utilizando dados reais, mas sem afetar a experiência de todos os usuários. Isso reduz riscos e possibilita validar funcionalidades em situações reais. Outras técnicas, como *canary deployment*, também podem ser usadas para esse propósito.

2. **Entrega contínua de recursos**:  
   Possibilitam implementar um recurso de forma parcial, colocá-lo em produção e controlá-lo sem expor imediatamente aos usuários. Assim, é possível disponibilizá-lo gradualmente ou ativá-lo apenas quando o desenvolvimento estiver 100% concluído, promovendo uma estratégia de entrega contínua e eficiente.

3. **Personalização**:  
   Permitem habilitar ou desabilitar recursos de forma segmentada, adaptando funcionalidades de acordo com as preferências ou necessidades de grupos específicos de usuários. Essa flexibilidade aumenta a satisfação do cliente e otimiza a usabilidade do sistema.

## Vantagens significativas

1. **Testes em produção com segurança**  
   As feature flags permitem:  
   - Validar o comportamento de funcionalidades em condições reais.  
   - Reduzir riscos de falhas catastróficas.  
   - Reverter rapidamente uma funcionalidade problemática, desativando a flag sem a necessidade de rollback completo.

2. **Entrega contínua e incremental**  
   Facilita:  
   - Implementações graduais (*progressive rollout*), ativando recursos para um subconjunto de usuários antes de disponibilizá-los a todos.  
   - Colaboração entre equipes de desenvolvimento, QA e marketing ao sincronizar lançamentos de novos recursos.

3. **Experimentos e A/B Testing**  
   Ideais para:  
   - Executar testes A/B para comparar diferentes versões de uma funcionalidade.  
   - Coletar métricas e feedback antes de decidir qual versão implementar permanentemente.

4. **Personalização da experiência do usuário**  
   Adaptam funcionalidades com base em:  
   - Função ou permissão no sistema (ex.: administradores vs. usuários regulares).  
   - Região geográfica ou idioma.  
   - Preferências ou comportamento do usuário.

5. **Facilidade na reversão de mudanças**  
   Caso um recurso cause problemas, é possível desativá-lo imediatamente, sem a necessidade de:  
   - Reverter código no repositório.  
   - Realizar um novo ciclo de deploy.

6. **Colaboração entre equipes**  
   Equipes multidisciplinares podem trabalhar de forma integrada:  
   - Desenvolvedores podem lançar recursos técnicos gradualmente.  
   - Equipes de produto ou marketing decidem quando ativar os recursos para os usuários finais.

7. **Redução de risco em grandes mudanças**  
   Permitem:  
   - Implementações parciais ou isoladas, minimizando impactos em sistemas críticos.  
   - Monitorar o comportamento dos sistemas antes de escalar alterações.

8. **Suporte ao desenvolvimento ágil**  
   Fundamentais para práticas como Continuous Integration (CI) e Continuous Delivery (CD):  
   - Promovem ciclos de entrega mais rápidos.  
   - Permitem lançamentos frequentes com menos interrupções.

9. **Aumento da flexibilidade em decisões**  
   Decisões como ativar ou desativar recursos podem ser tomadas com base em dados reais, validando hipóteses e ajustando estratégias com rapidez.

## Desvantagens e desafios

1. **Complexidade no código**  
   O uso excessivo pode tornar o código mais difícil de manter, criando situações conhecidas como *flag debt*. Isso dificulta a legibilidade e aumenta a chance de erros.

2. **Necessidade de gerenciamento**  
   Feature flags precisam ser monitoradas e removidas após seu propósito ser cumprido. Flags desnecessárias aumentam o risco de confusão e dívida técnica.

3. **Risco de erros na configuração**  
   Um erro na configuração pode ativar funcionalidades incompletas ou desativar recursos importantes. Controles rigorosos são essenciais.

4. **Dificuldade de testes**  
   Muitas flags geram diversas combinações possíveis de estados. Testar todas as combinações para garantir a funcionalidade correta pode ser desafiador.

5. **Impacto no desempenho**  
   Avaliar o estado das flags em tempo de execução pode impactar o desempenho, especialmente em operações críticas.

6. **Dependência de ferramentas externas**  
   Problemas em ferramentas de terceiros podem afetar a capacidade de gerenciar as flags.

7. **Risco de exposição indevida**  
   Recursos controlados por feature flags podem ser acessados indevidamente por usuários avançados, expondo funcionalidades em desenvolvimento.

A utilização eficaz das feature flags depende de uma boa estratégia de gerenciamento, alinhamento entre equipes e controle rigoroso para evitar desafios comuns.


# CORS - Cross-Origin Resource Sharing

CORS (Cross-origin Resource Sharing) é um mecanismo que permite que aplicativos web acessem recursos de outros domínios. Ele funciona transmitindo cabeçalhos HTTP que informam aos navegadores se devem permitir que uma aplicação acesse recursos de outra origem.

## O CORS é útil porque: 
- Permite que páginas web integrem recursos de diferentes origens, como imagens, vídeos, scripts, folhas de estilo e iframes.
- Garante a navegação segura ao usuário, evitando o acesso de websites maliciosos e a ação de crackers.
- Permite que o navegador do cliente verifique com os servidores de terceiros se a solicitação foi autorizada antes de qualquer transferência de dados.

## Os cabeçalhos CORS incluem: 
- Access-Control-Allow-Origin
- Access-Control-Allow-Credentials
- Access-Control-Allow-Headers
- Access-Control-Allow-Methods
- Access-Control-Expose-Headers
- Access-Control-Max-Age
- Access-Control-Request-Headers
- Access-Control-Request-Method
- Origin

A especificação que define o CORS é o Fetch Living Standard do WHATWG.

**Saiba mais:**
- [mmdn web docs: CORS](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/CORS)
- [Spring: Habilitando CORS](https://spring.io/guides/gs/rest-service-cors)
