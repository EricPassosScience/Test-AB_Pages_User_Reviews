# Prueba A/B - ¿Las páginas con reseñas de usuarios aumentan las ventas de productos en línea?

********************
<p align="center">
  <img width="900" height="500" src="https://github.com/EricPassosScience/Monte_Carlo_Simulation-Time_Series/assets/97414922/8db39508-4927-48eb-adc3-0d74c1326868">
</p>

**********************
# Consideraciones iniciales:
La guía paso a paso para resolver el problema se encuentra en el script Python.

Sin embargo, en este README proporcionaré el contexto del problema, algunas de las técnicas utilizadas y los datos.

***************************
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

## Configurando el experimento
Según las marcas de tiempo asociadas con cada evento, puede realizar una prueba de hipótesis continuamente a medida que se observa cada evento. Sin embargo, surge la pregunta crucial: ¿cuándo deberíamos detener este proceso? ¿Debería serlo cuando una variante se considera significativamente superior a la otra, o es necesario que esta superioridad se mantenga consistentemente durante un cierto período de tiempo? ¿Y cuánto tiempo deberíamos esperar antes de concluir que ninguna variante es superior a la otra? Todas estas decisiones deben tomarse considerando el contexto específico del negocio en cuestión. Estas suelen ser las partes más desafiantes de las pruebas A/B y del análisis en general.

Si determinamos que la variante "A" es superior, a menos que la nueva variante "B" demuestre ser definitivamente mejor con una tasa de error Tipo I del 5%, nuestras hipótesis nula y alternativa deberían formularse de la siguiente manera:
- h0: Pb - Pa = 0
- H1: Pb - Pa > 0

H0: dice que la diferencia de probabilidad de los dos grupos es igual a cero

H1: dice que la diferencia de probabilidad de los dos grupos es mayor que cero

## Preprocesamiento y algunos comentarios.
Todo el paso a paso está dentro del script. Pero te dejo con algunas consideraciones:
- Debido a que trazar los gráficos requiere mucha capacidad de procesamiento, solo usaremos datos durante dos meses.
- Creemos una línea de base de la tasa de conversión antes de ejecutar la prueba de hipótesis. De esta manera sabremos la tasa de conversión base y/o aumento deseado de compras que nos gustaría probar.
- Para nuestro ejemplo, queremos confirmar que los cambios que hacemos en la página eliminando las reseñas de los usuarios resultarán en al menos un aumento del 2% en nuestra tasa de suscripción (esta definición debe estar alineada con el área de negocio)
- Trabajaremos con el Efecto Mínimo Detectable (Minimum Detectable Effect)
- Recuerde, A será el grupo de control y B será el grupo de prueba

## Distribución de Bernoulli y el teorema del límite central

***¿Cómo interpretar la diferencia en la probabilidad máxima? (Ver script en Python)***

Es fundamental dirigir nuestra atención a la tasa de conversión para garantizar una comparación justa entre términos equivalentes. Para calcular esto con precisión, es imperativo estandarizar los datos y comparar las probabilidades de éxito (representadas por 'p') en cada grupo.

Inicialmente debemos analizar la distribución de Bernoulli en el grupo control. La fórmula para esto es: ![imagem_2023-10-06_232903456](https://github.com/EricPassosScience/Test-AB_Pages_User_Reviews/assets/97414922/9643946f-b209-4d3a-9509-8833fb2efa58)

donde $P(X=k)$ es la probabilidad de obtener $k$ éxitos en un solo experimento de Bernoulli; $p$ es la probabilidad de éxito (por ejemplo, la tasa de conversión); $1-p$ es la probabilidad de fracaso; $k$ es 1 para éxito y 0 para fracaso.

Según las propiedades de la distribución de Bernoulli, la media y la varianza son las siguientes: 
$E(X) = p$ y $Var(X) = p(1 - p)$. 

Según el teorema del límite central, al calcular varias medias muestrales, podemos aproximarnos a la media verdadera μ de la población, de la cual se obtuvieron los datos para el grupo de control. La distribución de las medias muestrales se distribuirá normalmente alrededor de la media verdadera, con una desviación estándar igual al error estándar de la media. La ecuación para esto viene dada como:

<p align="center">
  <img width="250" height="100" src="https://github.com/EricPassosScience/Test-AB_Pages_User_Reviews/assets/97414922/254fca72-e950-4de1-a852-9c3e8a8c08da/imagem_2023-10-07_002250176.png">
</p>

Por tanto, podemos representar ambos grupos como una distribución normal con las siguientes propiedades:

<p align="center">
  <img width="250" height="100" src="https://github.com/EricPassosScience/Test-AB_Pages_User_Reviews/assets/97414922/889c6b64-b8ad-4c85-99a1-5e1eabe07741/imagem_2023-10-07_161558848.png">
</p>

Lo mismo se puede hacer para el grupo de prueba. Por tanto, tendremos dos distribuciones normales para p_A y p_B. Y con distribuciones normales, nuestro trabajo de comparación será más sencillo.Obs: p_A y p_B están definidos en Python scrypt.

# Variación de Suma
Otro punto importante para comprender lo que se hace en Python scrypt es la variación de la suma.
Una propiedad básica de la varianza es que la varianza de la suma de dos variables aleatorias independientes es la suma de las varianzas. Algo obvio, pero hay que decir lo obvio: 
- $Var(X+Y) = Var(X) + Var(Y)$

- $Var(X+Y) = Var(X) + Var(Y)$

Esto significa que las hipótesis nula y alternativa tendrán la misma varianza que será la suma de las varianzas para el grupo de control y de prueba:

<p align="center">
  <img width="700" height="100" src="https://github.com/EricPassosScience/Test-AB_Pages_User_Reviews/assets/97414922/3725a919-108c-4fd3-8814-b8b127733e7e.imagem_2023-10-07_180125501.png">
</p>

Entonces la desviación estándar se puede calcular como:

<p align="center">
  <img width="600" height="100" src="https://github.com/EricPassosScience/Test-AB_Pages_User_Reviews/assets/97414922/1c019dfb-58cc-434a-8ae0-d8e46c09f3e8.imagem_2023-10-07_182351012.png">
</p>

Si expresamos esta ecuación en relación con la desviación estándar de la distribución de Bernoulli, obtenemos:

<p align="center">
  <img width="250" height="100" src="https://github.com/EricPassosScience/Test-AB_Pages_User_Reviews/assets/97414922/252a072f-0d4b-4f45-a3ff-0a6cdb4b4df2.imagem_2023-10-07_183418952.png">
</p>

Y así obtenemos la aproximación de Satterthwaite para el error estándar agrupado. Cuando calculamos la probabilidad combinada y usamos este valor para determinar la desviación estándar de ambos grupos, llegamos a:

![imagem_2023-10-07_185824302](https://github.com/EricPassosScience/Test-AB_Pages_User_Reviews/assets/97414922/80249f02-9f01-491a-9388-972f184ca43e)

Dónde: 

<p align="center">
  <img width="250" height="100" src="https://github.com/EricPassosScience/Test-AB_Pages_User_Reviews/assets/97414922/9d6a8774-6362-4bcd-bbd7-7838753ffa74.imagem_2023-10-07_190516970.png">
</p>

Las dos ecuaciones para el error estándar combinado producirán resultados muy similares. Esto nos proporcionará datos adecuados para crear las distribuciones relacionadas con la hipótesis nula y la hipótesis alternativa.

# Influencia del tamaño de la muestra y Conclusiones:
Del siguiente gráfico podemos sacar algunas conclusiones:

Visualmente, el gráfico de las hipótesis nula y alternativa es muy similar a los otros gráficos que se encuentran en el script Python. Afortunadamente, las dos curvas tienen forma idéntica (hicimos algunas transformaciones a los datos), por lo que podemos simplemente comparar la distancia entre las medias de las dos distribuciones. ***Podemos ver que la curva de hipótesis alternativa sugiere que el grupo de prueba tiene una tasa de conversión más alta que el grupo de control.*** En otras palabras, la página que no tiene reseñas tiene una tasa de conversión de clientes más alta.

Este gráfico también se puede utilizar para determinar directamente el poder estadístico. Es más fácil definir el poder estadístico y el nivel de significancia mostrando primero cómo se representan en el gráfico de hipótesis nula y alternativa. Podemos devolver una visualización del poder estadístico agregando el parámetro show_power = True.

El área sombreada en verde representa la potencia estadística y el valor calculado de la potencia también se muestra en el gráfico. Las líneas discontinuas grises en el gráfico representan el intervalo de confianza (95%) para la hipótesis nula. El poder estadístico se calcula encontrando el área bajo la distribución de la hipótesis alternativa y fuera del intervalo de confianza de la hipótesis nula.

Después de ejecutar nuestro experimento, obtenemos una tasa de conversión resultante para ambos grupos. Si calculamos la diferencia entre las tasas de conversión, terminamos con un resultado, la diferencia o el efecto de cambiar el diseño de la página web, sin mostrar las opiniones de los usuarios. Nuestra tarea es determinar de qué población proviene este resultado, la hipótesis nula o la hipótesis alternativa.

El área bajo la curva de la hipótesis alternativa es igual a 1. Si el diseño alternativo (sin evaluaciones) es realmente mejor, la potencia es la probabilidad de que aceptemos la hipótesis alternativa y rechacemos la hipótesis nula y es igual al área sombreada en verde (verdadero positivo). El área opuesta bajo la curva alternativa es la probabilidad de no rechazar la hipótesis nula y rechazar la hipótesis alternativa (falso negativo). Esto se conoce como beta en las pruebas A/B o pruebas de hipótesis y se muestra a continuación.

Si la hipótesis nula es verdadera y realmente no hay diferencia entre los grupos de control y de prueba, el nivel de significancia es la probabilidad de que rechacemos la hipótesis nula y aceptemos la hipótesis alternativa (falso positivo). Un falso positivo es cuando concluimos erróneamente que el nuevo diseño es mejor. Este valor es bajo porque queremos limitar esta probabilidad.

A menudo, a un problema se le proporcionará un nivel de confianza deseado en lugar del nivel de significancia. Un nivel de confianza típico del 95 % para una prueba A/B corresponde a un nivel de significancia de 0,05.

![imagem_2023-10-08_180455953](https://github.com/EricPassosScience/Test-AB_Pages_User_Reviews/assets/97414922/16cb0236-37f6-442c-8828-235b867171e7)

Cabe señalar que lo que queremos es el mejor resultado lo más rápido posible con la menor cantidad de datos posible, por eso el poder estadístico es importante. A través del poder estadístico podemos determinar la cantidad mínima de datos necesarios para que la prueba tenga una potencia de al menos el 80%. Al calcular el tamaño mínimo de muestra que necesitamos antes del experimento, podemos determinar cuánto tiempo llevará obtener los resultados para que la empresa pueda tomar una decisión final.

El secreto del Test A/B no está en realizar la prueba de hipótesis en sí, sino en poder obtener el poder estadístico necesario para confirmar si los cambios tuvieron efecto o no en la tasa de conversión. **Para nuestro ejemplo, con 1249 muestras podemos decir que sí, eliminar las reseñas de los usuarios de la página aumenta la tasa de conversión.**

Todo esto se explicó en el archivo de Python, asegúrese de consultarlo.

Fin






