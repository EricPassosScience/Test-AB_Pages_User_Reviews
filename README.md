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

# Análise de Potência
Antes de iniciar um teste, é fundamental abordar duas questões essenciais:
- Qual a proporção de usuários que deve participar do teste e quantos devem permanecer no grupo de controle?
- Por quanto tempo o teste deve ser conduzido?

A abordagem estatística para responder a essas perguntas envolve a análise de potência. Para começar, é necessário determinar qual é a menor diferença (ou aumento) que teria relevância para o negócio, conhecida como "tamanho do efeito". Em segundo lugar, é preciso entender o nível de variação normalmente observado na métrica de resultado. A análise de potência realiza cálculos para determinar o tamanho da amostra necessário, ou seja, o número de usuários que deve ser incluído no teste, a fim de identificar o tamanho do efeito com significância estatística.

A análise de potência considera dois componentes importantes para determinar o tamanho da amostra:
- Divisão: A proporção de usuários alocados para o grupo de teste em comparação com o grupo de controle. Essa divisão afeta diretamente o tamanho da amostra. Quanto mais desequilibrada for essa divisão (ou seja, quanto mais distante de uma divisão 50-50), mais longo deverá ser o teste.
- Duração do teste: O período total que será necessário para expor a quantidade planejada de usuários ao teste. Como os usuários podem ser expostos novamente ao longo do tempo, o aumento cumulativo da exposição acontece de forma mais lenta. Matematicamente, quanto mais desequilibrada for a divisão e quanto menor for o tamanho do efeito, mais longa deverá ser a duração do teste.

A fórmula matemática para calcular a potência estatística em um cenário como esse é geralmente expressa como:

<p align="center">
  <img width="200" height="40" src="https://github.com/EricPassosScience/Monte_Carlo_Simulation-Time_Series/assets/97414922/8dd493fd-5a42-4075-9937-2b999fc98247">
</p>

onde P é a potência estatística  que representa a probabilidade de detectar um efeito significativo se ele existir. β é a taxa de erro do tipo II, que indica a probabilidade de não detectar um efeito significativo quando ele realmente existe. A análise de potência desempenha um papel crucial na determinação de como conduzir testes de forma eficiente, otimizando a alocação de usuários e o tempo necessário para obter resultados confiáveis.

É importante destacar que, em muitas situações, a análise de potência não conta toda a história. Um exemplo disso é observado em portais online que seguem um ciclo semanal distintamente marcado, com padrões de comportamento de compra variando consideravelmente nos fins de semana e nos dias úteis. Nesse contexto, é altamente recomendável realizar testes A/B com uma duração mínima de uma semana e, de preferência, em múltiplos de sete dias. Naturalmente, se os resultados parecerem significativamente negativos logo nos primeiros um ou dois dias, é sensato encerrar o teste mais cedo.

Além disso, a escolha do equilíbrio na divisão entre os grupos de teste e controle não apenas afeta a duração do teste, mas também está relacionada ao nível de risco envolvido. Por exemplo, quando uma ampla variedade de produtos está à venda, podemos começar com uma divisão de 90% para o controle e 10% para o teste. Em contraste, quando desejamos garantir que um recurso crítico no site mantenha seu desempenho, podemos optar por uma divisão de 5% para o controle e 95% para o teste. Entretanto, em testes de baixo risco, como pequenas alterações na interface do site, uma divisão equilibrada de 50% para o controle e 50% para o teste pode resultar em uma duração de teste mais curta.

A seleção cuidadosa do equilíbrio entre teste e controle, juntamente com a consideração do contexto sazonal e do comportamento dos usuários, desempenha um papel crucial na execução eficaz de testes A/B, permitindo que as empresas tomem decisões informadas com base em dados confiáveis.

# Em resumo, como analisar testes A/B? 
- 1. Configuramos o experimento
- 2. Executamos o teste de hipótese e registramos a taxa de sucesso de cada grupo.
- 3. Criamos um gráfico de distribuição da diferença entre as duas amostras
- 4. Calculamos o poder estatístico
- 5. Avaliamos como o tamanho da amosta afeta o teste. 

# Fonte de Dados
Usaremos dados fictícios, mas que representam os dados de um cenário real. Abaixo, podemos visualizar um exemplo:

| id | variante | compra | data |
|---|---|---|---|
| 0x6f9421 | A | False | 2019-12-26 |
| 0x6f9421 | A | True | 2019-04-15 |
| 0x6f9421 | B | False | 2019-06-29 |
| 0x6f9421 | A | False | 2019-04-10 |
| 0x6f9421 | B | True | 2019-11-02 |

A coluna "variante" representa se a página que foi acessada possui ou não comentários e avaliações.
- A: representa a página que mostra o número atual de comentários e avaliações de usuários;
- B : representa a página que não mostra os comentários de usuários no site.

A coluna "id" indica qual foi o usuário que acessou a página. A variável "compra" informa se aquele usuário realizou ou não uma compra (True ou False), enquanto que a coluna "data" registra a data de acesso ou da trasação em uma das páginas. 

Obs. Poderiamos ter outras informaçõe como: valor gasto, horário da transação ou do acesso, etc. 

## Fase 1 - Configurando o Experimento
Com base nos registros de data e hora associados a cada evento, é possível realizar um teste de hipótese continuamente à medida que cada evento é observado. No entanto, surge a questão crucial: quando devemos interromper esse processo? Deve ser quando uma variante é considerada significativamente superior à outra ou é necessário que essa superioridade seja consistentemente mantida por um determinado período de tempo? E quanto tempo devemos esperar antes de concluir que nenhuma das variantes é superior à outra? Todas essas decisões precisam ser feitas considerando o contexto específico do negócio em questão. Geralmente, essas são as partes mais desafiadoras dos Testes A/B e da análise em geral.

Se determinarmos que a variante "A" é superior, a menos que a nova variante "B" prove ser definitivamente melhor com uma taxa de erro Tipo I de 5%, nossas hipóteses nula e alternativa devem ser formuladas da seguinte maneira:
- h0: Pb - Pa = 0
- H1: Pb - Pa > 0

H0: diz que a diferença de probabilidade dos dois grupos é igual a zero

H1: diz que a diferença d e probabilidade dos dois grupos é maior que zero


## Pré-Processamento dos Dados
Todo o passo a passo está dentro do script. Mas deixarei qui algumas considerações:
- Por conta da plotagem dos gráficos requerer bastante muita capacidade de processamento, vamos utilizar somente dados referentes a dois meses
- Vamos criar um baseline (linha base) da taxa de conversão antes de executar o teste de hipótese. Assim, saberemos a taxa de conversão base e ou aumento desejado em compras que gostariámos de testar
- Para o nosso exemplo, queremos confirmar que as alterações que fazemos na página retirando as avaliações de usuários resultarão em pelo menos um aumento de 2% em nossa taxa de inscrição (essa definição deve ser alinhada com a área de negócio)
- Lembremos, A será o grupo de controle e B será o grupo de teste


Continua...
  














