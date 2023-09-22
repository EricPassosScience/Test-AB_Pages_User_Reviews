# Test A/B - Paginas com Avaliações de Usuários Aumentam as Vendas de Produtos Online ? 
********************
<p align="center">
  <img width="900" height="500" src="https://github.com/EricPassosScience/Monte_Carlo_Simulation-Time_Series/assets/97414922/8db39508-4927-48eb-adc3-0d74c1326868">
</p>

**********************

# O que são Testes A/B? 
O marketing é uma disciplina intrincada que exige habilidades e estratégias afiadas para se destacar em um mercado notoriamente competitivo. Para manter uma vantagem sobre a concorrência, é absolutamente imperativo aproveitar todas as oportunidades disponíveis. Neste contexto, os testes A/B desempenham um papel crucial.

O Teste A/B, também conhecido como teste de divisão, é uma estratégia altamente eficaz no campo do Marketing Digital. Essa técnica de otimização é empregada com o objetivo de gradualmente elevar as taxas de conversão em um funil de vendas, seja em relação a contatos gerados ou vendas concretizadas. Além disso, pode ser aplicada para aprimorar outros aspectos nas fases iniciais do processo, como a taxa de cliques ou a taxa de rejeição.

Em um Teste A/B, duas estratégias distintas são testadas em um grupo específico. Para exemplificar, considere uma página de venda de livros online com um botão para os usuários se cadastrarem e receberem e-mails. Este elemento é chamado de controle, ou seja, é a versão existente da página.

Queremos saber se há maneiras de melhorar essa página para atrair mais inscritos. Entre todas as estratégias de marketing, a comunicação via e-mail ainda é a mais eficiente. Portanto, criamos outra versão da página com um botão de inscrição diferente, podendo alterar sua posição, cor, texto de call-to-action, formato, entre outros. Esta nova versão é denominada variável.

Em seguida, exibimos ambas as versões da página para uma divisão igualitária (50/50) de toda a audiência. Isso significa que todos os usuários veem o botão de cadastro, mas alguns veem a página com o botão azul, enquanto outros veem a página com o botão verde, por exemplo.

Dessa forma, coletamos dados analíticos das duas versões, a de controle e a variável, e os usamos como fator decisivo. Qual dessas versões resulta em mais inscritos ou vendas? A versão que obtém melhores resultados é a escolhida.

Esta é apenas a ponta do iceberg! Os Testes A/B podem ser aplicados em diversas plataformas de marketing, como nas redes sociais, marketing visual e muito mais.

Frisa-se que o meu objetivo aqui não é criar o Teste A/B, mas sim analisar os resultados de um Teste A/B.
*******************************

# Análise de Testes A/B
********************************

## Elevação (Lift)

Na análise de Teste A/B, normalmente, avaliamos a diferença entre a versão A e a versão B. Para uma métrica de resultado específica, essa diferença é calculada como xB (versão B) menos xA (versão A). É importante notar que essa diferença, principalmente quando se trata de resultados cumulativos, pode aumentar com o passar do tempo. Tomemos como exemplo o gasto por usuário em um teste. À medida que o teste prossegue, ambos os grupos continuam a fazer compras, acumulando gastos ao longo do tempo. O sucesso da versão B é determinado pelo aumento mais rápido dos gastos no grupo de teste em comparação com o grupo de controle.

Para lidar com essa dinâmica, utilizamos a métrica de elevação, também conhecida como "Lift," que dimensiona a diferença entre os grupos pelo valor de referência, ou seja, o valor da versão A. Para calcular a elevação em relação a uma métrica de resultado x, usamos a fórmula: 
***********************
<p align="center">
  <img width="450" height="150" src="https://github.com/EricPassosScience/Monte_Carlo_Simulation-Time_Series/assets/97414922/91338f64-0e8c-4f66-b1f5-bbdf8493c2b9">
</p>

************************
Essa abordagem nos permite compreender de forma mais precisa como a versão B está performando em relação à versão A, levando em consideração o contexto da linha de base. Assim, podemos determinar se o aumento nas métricas cumulativas é estável ao longo do tempo, o que chamamos de "métricas de elevação" (Lift). A métrica de elevação nos ajuda a avaliar se a versão B está realmente gerando impacto positivo em comparação com a versão A, ajustando para as variações naturais que ocorrem com o tempo.






