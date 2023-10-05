# Prueba A/B - ¿Las páginas con reseñas de usuarios aumentan las ventas de productos en línea?

********************
<p align="center">
  <img width="900" height="500" src="https://github.com/EricPassosScience/Monte_Carlo_Simulation-Time_Series/assets/97414922/8db39508-4927-48eb-adc3-0d74c1326868">
</p>

**********************
# ¿Qué son las Pruebas A/B?
Los Test A/B, también conocidos como pruebas de división, son una estrategia altamente efectiva en el campo del Marketing Digital. Esta técnica de optimización se emplea con el objetivo de elevar gradualmente las tasas de conversión en un embudo de ventas, ya sea en relación con los contactos generados o las ventas concretadas. Además, se puede aplicar para mejorar otros aspectos en las fases iniciales del proceso, como la tasa de clics o la tasa de rebote.

En un Test A/B, se prueban dos estrategias distintas en un grupo específico. Por ejemplo, consideremos una página de venta de libros en línea con un botón para que los usuarios se suscriban y reciban correos electrónicos. Este elemento se llama control, es decir, es la versión existente de la página.

Queremos saber si hay formas de mejorar esta página para atraer más suscriptores. Entre todas las estrategias de marketing, la comunicación por correo electrónico sigue siendo la más eficiente. Por lo tanto, creamos otra versión de la página con un botón de suscripción diferente, que puede cambiar su posición, color, texto de llamada a la acción, formato, entre otros. Esta nueva versión se denomina variable.

A continuación, mostramos ambas versiones de la página a una división equitativa (50/50) de toda la audiencia. Esto significa que todos los usuarios ven el botón de registro, pero algunos ven la página con el botón azul, mientras que otros ven la página con el botón verde, por ejemplo.

De esta manera, recopilamos datos analíticos de las dos versiones, la de control y la variable, y los utilizamos como factor decisivo. ¿Cuál de estas versiones resulta en más suscriptores o ventas? La versión que obtiene mejores resultados es la elegida.

¡Esto es solo la punta del iceberg! Los Tests A/B se pueden aplicar en diversas plataformas de marketing, como en redes sociales, marketing visual y mucho más.

Cabe destacar que mi objetivo aquí no es crear el Test A/B, sino analizar los resultados de un Test A/B.
*******************************

# Análisis de Pruebas A/B
********************************

## Elevación (Lift)

En el análisis de Pruebas A/B, normalmente evaluamos la diferencia entre la versión A y la versión B. Para una métrica de resultado específica, esta diferencia se calcula como xB (versión B) menos xA (versión A). Es importante notar que esta diferencia, especialmente cuando se trata de resultados acumulativos, puede aumentar con el tiempo. Tomemos como ejemplo el gasto por usuario en una prueba. A medida que la prueba avanza, ambos grupos continúan haciendo compras, acumulando gastos con el tiempo. El éxito de la versión B se determina por el aumento más rápido en los gastos del grupo de prueba en comparación con el grupo de control.

Para abordar esta dinámica, utilizamos la métrica de elevación, también conocida como "Lift," que escala la diferencia entre los grupos por el valor de referencia, es decir, el valor de la versión A. Para calcular la elevación en relación con una métrica de resultado x, utilizamos la siguiente fórmula:

***********************
<p align="center">
  <img width="450" height="150" src="https://github.com/EricPassosScience/Monte_Carlo_Simulation-Time_Series/assets/97414922/91338f64-0e8c-4f66-b1f5-bbdf8493c2b9">
</p>

************************
ste enfoque nos permite comprender de manera más precisa cómo se está desempeñando la versión B en comparación con la versión A, teniendo en cuenta el contexto de la línea base. De esta manera, podemos determinar si el aumento en las métricas acumulativas es estable con el tiempo, lo que llamamos "métricas de elevación" (Lift). La métrica de elevación nos ayuda a evaluar si la versión B realmente está generando un impacto positivo en comparación con la versión A, ajustando las variaciones naturales que ocurren con el tiempo.

# Análisis de Potencia
Antes de iniciar una prueba, es fundamental abordar dos cuestiones esenciales:
- ¿Cuál debe ser la proporción de usuarios que participarán en la prueba y cuántos deben permanecer en el grupo de control?
-¿Por cuánto tiempo debe ser conducida la prueba

El enfoque estadístico para responder a estas preguntas implica el análisis de potencia. En primer lugar, es necesario determinar cuál es la diferencia más pequeña (o aumento) que sería relevante para el negocio, conocida como "tamaño del efecto". En segundo lugar, es necesario comprender el nivel de variación normalmente observado en la métrica de resultado. La análisis de potencia realiza cálculos para determinar el tamaño de la muestra necesario, es decir, el número de usuarios que deben ser incluidos en la prueba, con el fin de identificar el tamaño del efecto con significancia estadística.

El análisis de potencia considera dos componentes importantes para determinar el tamaño de la muestra:

División: La proporción de usuarios asignados al grupo de prueba en comparación con el grupo de control. Esta división afecta directamente el tamaño de la muestra. Cuanto más desequilibrada sea esta división (es decir, cuanto más alejada de una división 50-50), más largo deberá ser el test.

Duración del test: El período total que será necesario para exponer la cantidad planeada de usuarios al test. Dado que los usuarios pueden ser expuestos nuevamente a lo largo del tiempo, el aumento acumulativo de la exposición ocurre de forma más lenta. Matemáticamente, cuanto más desequilibrada sea la división y cuanto menor sea el tamaño del efecto, más larga deberá ser la duración del test.

La fórmula matemática para calcular la potencia estadística en un escenario como este generalmente se expresa como:

<p align="center">
  <img width="200" height="40" src="https://github.com/EricPassosScience/Monte_Carlo_Simulation-Time_Series/assets/97414922/8dd493fd-5a42-4075-9937-2b999fc98247">
</p>

Donde P es la potencia estadística, que representa la probabilidad de detectar un efecto significativo si realmente existe. β es la tasa de error tipo II, que indica la probabilidad de no detectar un efecto significativo cuando realmente existe. El análisis de potencia juega un papel crucial en la determinación de cómo llevar a cabo pruebas de manera eficiente, optimizando la asignación de usuarios y el tiempo necesario para obtener resultados confiables.

Es importante destacar que, en muchas situaciones, el análisis de potencia no cuenta toda la historia. Un ejemplo de esto se observa en portales en línea que siguen un ciclo semanal claramente marcado, con patrones de comportamiento de compra que varían considerablemente los fines de semana y los días laborables. En este contexto, es altamente recomendable realizar pruebas A/B con una duración mínima de una semana y, de preferencia, en múltiplos de siete días. Naturalmente, si los resultados parecen significativamente negativos en los primeros uno o dos días, es sensato terminar la prueba más temprano.

Además, la elección del equilibrio en la división entre los grupos de prueba y control no solo afecta la duración de la prueba, sino que también está relacionada con el nivel de riesgo involucrado. Por ejemplo, cuando hay una amplia variedad de productos en venta, podemos comenzar con una división del 90% para el control y el 10% para el test. En contraste, cuando queremos asegurar que una característica crítica en el sitio web mantenga su rendimiento, podemos optar por una división del 5% para el control y el 95% para el test. Sin embargo, en pruebas de bajo riesgo, como pequeños cambios en la interfaz del sitio, una división equilibrada del 50% para el control y el 50% para el test puede resultar en una duración de prueba más corta.

La cuidadosa selección del equilibrio entre prueba y control, junto con la consideración del contexto estacional y del comportamiento de los usuarios, desempeña un papel crucial en la ejecución efectiva de pruebas A/B, permitiendo que las empresas tomen decisiones informadas basadas en datos confiables.

# En resumen, cómo analizar pruebas A/B:
1. Configuramos el experimento
2. Ejecutamos la prueba de hipótesis y registramos la tasa de éxito de cada grupo
3. Creamos un gráfico de distribución de la diferencia entre las dos muestras
4. Calculamos la potencia estadística
5. Evaluamos cómo el tamaño de la muestra afecta la prueba

# Fuente de Datos
Utilizaremos datos ficticios, pero que representan los datos de un escenario real. A continuación, podemos ver un ejemplo:

| id | variante | compra | data |
|---|---|---|---|
| 0x6f9421 | A | False | 2019-12-26 |
| 0x6f9421 | A | True | 2019-04-15 |
| 0x6f9421 | B | False | 2019-06-29 |
| 0x6f9421 | A | False | 2019-04-10 |
| 0x6f9421 | B | True | 2019-11-02 |

La columna "variante" representa si la página que se ha visitado tiene o no comentarios y evaluaciones.
- A: representa la página que muestra el número actual de comentarios y evaluaciones de usuarios
- B: representa la página que no muestra los comentarios de usuarios en el sitio

La columna "id" indica qué usuario ha visitado la página. La variable "compra" indica si ese usuario ha realizado o no una compra (True o False), mientras que la columna "fecha" registra la fecha de acceso o de la transacción en una de las páginas.

Nota: Podríamos tener otras informaciones como: valor gastado, horario de la transacción o del acceso, etc.

## Configurando o Experimento
Com base nos registros de data e hora associados a cada evento, é possível realizar um teste de hipótese continuamente à medida que cada evento é observado. No entanto, surge a questão crucial: quando devemos interromper esse processo? Deve ser quando uma variante é considerada significativamente superior à outra ou é necessário que essa superioridade seja consistentemente mantida por um determinado período de tempo? E quanto tempo devemos esperar antes de concluir que nenhuma das variantes é superior à outra? Todas essas decisões precisam ser feitas considerando o contexto específico do negócio em questão. Geralmente, essas são as partes mais desafiadoras dos Testes A/B e da análise em geral.

Se determinarmos que a variante "A" é superior, a menos que a nova variante "B" prove ser definitivamente melhor com uma taxa de erro Tipo I de 5%, nossas hipóteses nula e alternativa devem ser formuladas da seguinte maneira:
- h0: Pb - Pa = 0
- H1: Pb - Pa > 0

H0: diz que a diferença de probabilidade dos dois grupos é igual a zero

H1: diz que a diferença d e probabilidade dos dois grupos é maior que zero

## Pré-Processamento e alguns comentários
Todo o passo a passo está dentro do script. Mas deixarei qui algumas considerações:
- Por conta da plotagem dos gráficos requerer bastante muita capacidade de processamento, vamos utilizar somente dados referentes a dois meses
- Vamos criar um baseline (linha base) da taxa de conversão antes de executar o teste de hipótese. Assim, saberemos a taxa de conversão base e ou aumento desejado em compras que gostariámos de testar
- Para o nosso exemplo, queremos confirmar que as alterações que fazemos na página retirando as avaliações de usuários resultarão em pelo menos um aumento de 2% em nossa taxa de inscrição (essa definição deve ser alinhada com a área de negócio)
- Trabalharemos com o Efeito Mínimo Detectável (Minimum Detectable Effect)
- Lembremos, A será o grupo de controle e B será o grupo de teste















