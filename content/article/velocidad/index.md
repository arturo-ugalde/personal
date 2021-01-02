---
title: "Estimar la Velocidad"
date: 2020-12-20T16:01:38-06:00

tags: ['Scrum', 'Estimación']
categories: ['Scrum']
author: "Geiber"

---

 Sea que el proyecto inicia pronto o en unos meses una de las preguntas más importantes que responderemos cuando nos encargan un proyecto es: ¿Cuándo finalizará?.  En el mundo del agilismo una de las técnicas que nos apoya en esta labor es la estimación de la velocidad.  A continuación en este artículo mostraremos los pasos a seguir según el libro "Agile Estimating and Planning" de Mike Cohen, uno de los gurus de Scrum.

<!--more-->
{{< highlight html>}}{{< /highlight >}} 
Antes de realizar estimaciones Mike Cohen [1] enseña la importancia de la curva de esfuerzo vs. exactitud.  Esta curva muestra que es innecesario dedicar mucho esfuerzo a estimaciones porque a partir de cierto punto la exactitud de los valores estimados empieza a decrecer generando estimaciones poco precisas.  Por el contrario sólo se necesita un poco de esfuerzo para generar valores adecuados de estimación. Por ejemplo, apróximadamente un 10% de esfuerzo generaría estimaciones con un 50% de exactitud.  Cohen advierte sobre la idea equivocada que una planificación exhaustiva de todas las tareas y la búsqueda de la firma contractual de todos los requerimientos **no implican** que un proyecto sea más preciso y por el contrario estas ideas tomarían un mayor esfuerzo de estimación.  Al mismo tiempo recuerda que el agilismo abraza la idea que esfuerzos pequeños son recompensados con grandes ganancias y la incertidumbre jamás puede ser eliminada de la estimación.
{{< figure src="curva.png">}}
> __Figura 6.1__ en [1] 
{{< highlight html>}}{{< /highlight >}} 

Considerando la curva anterior, una receta para estimar la duración de un proyecto con Scrum es conocer primero el tamaño de los features o items del backlog y luego la velocidad del equipo.  Con ambas variables se realiza una simple división entre el tamaño estimado y la velocidad para obtener la cantidad de iteraciones o sprints.   Finalmente el número de sprints se multiplica por el tamaño del sprint para determinar una fecha estimada de finalización.  Más adelante veremos que es preferible ofrecer un rango de fechas de finalización.

{{< highlight html>}}{{< /highlight >}} 

### Cómo estimar la velocidad? ###
Cohen [2] presenta 3 formas de estimar la velocidad:
- Usar datos históricos.
- Iterar al menos una vez.
- Predecir la velocidad.

La estimación de la velocidad es el tema de este artículo pero iniciamos un breve recorrido por los dos primeros.  Usar valores históricos para estimar la velocidad es una opción para proyectos sinónimos; un contexto difícil de tener.
Los proyectos son únicos y cada línea de código es hecha a mano.  Es poco probable conseguir al menos dos proyectos con los mismos requerimientos, el mismo equipo Scrum, negocio, restricciones, prioridades y la misma tecnología.  Si encuentra proyectos con atributos similares entonces puede considerarlo.


La segunda opción es observar la velocidad de los desarrolladores ejecutando al menos un sprint.  Cohen sugiere hasta 3 sprints y ofrece como ejemplo la experiencia de un director de TI que indicó cómo en su compañía para proyectos de 1 año de duración les toma hasta 2 meses de planificación para definir *deadlines*, pero aún con este esfuerzo sus planes se desvíaban de la realidad en más del 50%.  
Definitivamente una mejor estrategía sería llevar a cabo al menos un sprint para observar la velocidad del equipo, en lugar de tomarnos tanto esfuerzo en la planificación del proyecto que al final tampoco logra una exactitud aceptable.
{{< highlight html>}}{{< /highlight >}}

Sin embargo cuando no es rentable correr iteraciones sea porque el proyecto aún no inicia o quizás nunca comience se debe recurrir a los siguientes pasos para **predecir la velocidad**:
1) Estimar la capacidad de cada desarrollador:
Un desarrollador generalmente no usa el 100% de su tiempo en el proyecto, frecuentemente tendrá tareas fuera del proyecto que son también su responsabilidad (reuniones, llamadas telefónicas, correos, etc).  Por lo tanto, es sensato realizar una estimación de la capacidad de cada desarrollador antes de creer que van a dedicar el 100% de su día al proyecto. Cohen muestra la experiencia de la famosa compañía Toyota donde, aún con su eficiente proceso Lean, un ingeniero usa un 80% del tiempo en su proyecto.  Si utilizamos esta experiencia u otra como punto de comparación podríamos estimar mejor la capacidad.

2) Determine las horas/hombre disponibles para el sprint:
Realice la sumatoria de las horas disponibles por día (según su capacidad)  que tiene cada desarrollador.  Por ejemplo, para un sprint de dos semanas (10 días), con un equipo de 3 desarrolladores con capacidad de 6 horas al días para cada uno, se contaría con 18 horas por día y 180 horas totales para el sprint.

3) Expanda las historias de usuario:
Seleccione un conjunto de historias o items significativos, lo más aleatorio posible. Expanda una historia en las tareas que necesite para finalizarla.  Estime las horas necesaria para completar todas sus tareas y sustraigalas del total de horas disponibles que calculó en el paso anterior.  Continúe con la siguientes historia y repita este paso hasta que haya consumido todas las horas disponibles para el sprint. 

4) Contabilice los puntos de historia:  
A partir de las historias de usuario ocupadas en el paso anterior, cuantifique los puntos de historia correspondientes.  De esta manera calculamos la velocidad estimada.  Por ejemplo, velocidad igual a 20 puntos.

5) Convierta la velocidad en un rango:
Cohen recomienda que se debe asignar un rango de incertidumbre a la velocidad calculada utilizando alguna técnica como por ejemplo el "Cono de Incertidumbre". 

El cono de incertidumbre fue presentado por Barry Boehm en [3] y es propuesto como una técnica para:
* Disminuir ambiguedades
* Determinar estimaciones más precisas
* Calcular un rango de probabilidades
* Determinar cuanto riesgo esta dispuesto a tomar.
[4] 

El cono de incertidumbre de Boehm expone que la duración, el alcance o el esfuerzo real de un proyecto estará probablemente entre 1/4 o 4 veces las estimaciones iniciales.

Por el contrario, Mike Cohen utiliza un cono con una variabilidad reducida.  Los sprints son iteraciones de corta duración, no superan 1 mes, y producen rápidamente avances o incrementos del proyecto que ayudan a reducir la incertidumbre. De esta manera la variabilidad se reduce de un factor de 4 , según Boehm, a un 60% por encima o por debajo de las estimaciones (es decir se reduce de 4x a 1.6x).  Así obtenemos un cono como se muestra en la siguiente figura: 

{{< figure src="cono.png">}}
> __Figura 1.1__ en [5] 
{{< highlight html>}}{{< /highlight >}} 

El cono de incertidumbre es una herramienta que se aplica para cualquiera de las 3 formas de estimación de velocidad mencionadas anteriormente. Por ejemplo, cuando se estima con valores reales al ejecutar algunos sprints se puede usar el cono como multiplicador de ajuste a partir del número de sprints terminados.  A continuación se muestra la tabla para generar los rangos [2]:

| [Sprint] | [Multiplicador inferior] | [Multiplicador superior] |
| ------ | ----------- | ---------|
| 1   | 0.6 |1.6 |
| 2 | 0.8 | 1.25|
| 3    | 0.85 | 1.15 |
| 4 o más.  | 0.90 |1.10 |

{{< highlight html>}}{{< /highlight >}} 
Si ha finalizado dos sprints y tiene una velocidad promedio de 12 entonces el rango a utilizar estaría entre 80% y 125%.  Esto ajusta la velocidad promedio y predice que la velocidad real al final del proyecto probablemente se encuentre en el rango de 16-25.

De forma similar, si aplica los 5 pasos para predecir la velocidad entonces calcule su rango usando 60% y 160%, la parte más ancha del cono de incertidumbre.  Por ejemplo si la velocidad calculada fue 10 entonces podríamos predecir que la velocidad al final del proyecto se encontrará en el rango de 6-16.

{{< highlight html>}}{{< /highlight >}} 
Finalmente, Cohe recomienda aprovechar los valores reales de velocidad que obtiene en los sprints finalizados.  Utilícelos junto al cono de incertidumbre cuando discuta el proyecto y requiera dar rangos de fechas de finalización.


{{< highlight html>}}{{< /highlight >}} 
__Referencias__

[1] Mike Cohn, "Techinques for Estimating" in *Agile Estimating and Planning*, Prentice Hall Professional Technical Reference, 2006, fig. 6.1 [Online]. Available: https://www.mountaingoatsoftware.com/uploads/articles/aep_sample.pdf. [Accessed: Oct 25, 2020].

[2] Mike Cohn, "Estimating velocity" in *Agile Estimating and Planning*, Prentice Hall Professional Technical Reference, 2006, pp. 175-184.

[3] Boehm, B. “Software Engineering Economics”. PrenticeHall, 1981. 

[4] Thaisa Fernandes, "Learn About the Cone of Uncertainty Framework", 2020,  [Online]. Available: https://medium.com/pm101/cone-of-uncertainty-framework-78927c1840f. [Accessed: Dec 01, 2020].

[5] Mike Cohn, "The Purpose of Planning" in *Agile Estimating and Planning*, Prentice Hall Professional Technical Reference, 2006, fig. 1.1. 

