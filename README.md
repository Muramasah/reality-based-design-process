# Reality Based Design Process

## Tabla de contenidos
- [Reality Based Design Process](#reality-based-design-process)
  - [Tabla de contenidos](#tabla-de-contenidos)
  - [Introducción](#introducci%c3%b3n)
    - [¿Qué resuelve este material?](#%c2%bfqu%c3%a9-resuelve-este-material)
    - [¿Para qué escenarios está pensado?](#%c2%bfpara-qu%c3%a9-escenarios-est%c3%a1-pensado)
  - [Descarte cero](#descarte-cero)
    - [Mindset](#mindset)
    - [Setting](#setting)
    - [Mis herramientas](#mis-herramientas)
  - [Prioridad de desarrollo](#prioridad-de-desarrollo)
    - [¿Qué necesitamos medir?](#%c2%bfqu%c3%a9-necesitamos-medir)
  - [Conceptos](#conceptos)
    - [Análisis](#an%c3%a1lisis)
    - [Diseño](#dise%c3%b1o)
    - [Fast Delivery](#fast-delivery)
    - [User Engagement](#user-engagement)
    - [Technical Debt](#technical-debt)
  - [Fuentes](#fuentes)

## Introducción
Aquí proponemos introducir un pequeño conjunto de conceptos que nos ayuden a organizar el lanzamiento de nuevas features en un producto. Estos conceptos no los inventé yo y son interpretaciones personales tomadas de [agile](https://es.wikipedia.org/wiki/Desarrollo_%C3%A1gil_de_software) y [fast delivery](#fast-delivery), basadas en la experiencia personal de la implementación de librerías y otras herramientas para diseñar software basado en datos reales. ¿Datos de quienes? Del objetivo de todo lo que hacemos, los usuarios.

### ¿Qué resuelve este material?
Los desafíos que se abarcan son:
- ¿Cómo mantenerse creativo? No cortar el chorro de creatividad en las etapas de [análisis](#análisis) y [diseño](#diseño).
- ¿Qué desarrollo agrega más valor al producto? Features reales basadas en métricas y feedback de los usuarios.
- ¿Hasta donde tengo que diseñar y desarrollar? Balance entre deuda técnica, release de features, etapas de producción y de refactorización.

### ¿Para qué escenarios está pensado?
Este conjunto de herramientas, teóricas y pŕacticas, está pensado para alguno de los siguientes escenarios:
- Rediseño de un [producto mínimo viable](https://es.wikipedia.org/wiki/Producto_viable_m%C3%ADnimo) (MVP).
- Extensión de un **MPV**.
- Necesidad de reorientar el desarrollo de una aplicación existente para aumentar el engagement de los usuarios.

## Descarte cero
Si bien los tres escenarios en los que podemos utilizar estos conceptos son muy distintos, todos comparten que en algún momento vamos a tener que sentarnos a analizar qué está hecho y qué hay que hacer, tanto para resolver los problemas que tengamos en el desarrollo hasta el momento, como para planificar las funcionalidades nuevas. Para eso es importante darle lugar a todas las ideas, tanto a las pequeñas, que luego se pueden agrandar, como las grandes, que se pueden achicar o atomizar.

Nuestro objetivo en esta etapa es **acumular valor creativo** generando una lista de funcionalidades para la próxima etapa, por lo que necesitamos llevar un registro de todas estas ideas en el formato que más rápido nos permita explayarnos, ya que nos puede pasar que si cambiamos en qué estamos pensando por un instante podemos llegar a perder una buena idea. Por eso es muy importante nuestro _mindset_, es decir, cómo estamos mentalmente predispuestos para la situación creativa, y el _setting_, el cómo preparamos nuestro entorno para esa situación.

### Mindset
En este momento es muy importante olvidarnos de aquello que nos pueden restringir el mar de ideas que puede surgir en un ambiente creativo, los **olvidables** son:
- Tiempo de entregas.
- Complejidad de las soluciones propuestas.
- Otro tipo de falta de recursos.

También tenemos que estar descansados, bien alimentados, hidratados, etc. Lo que suele pasar más un lunes que un viernes por al tarde, o al comenzar un [sprint](https://proyectosagiles.org/ejecucion-iteracion-sprint/) más que al finalizarlo, de todas formas esto varía según el equipo. Hablando del equipo, este también influye en la limitación de la creatividad de los miembros del mismo, según cómo percibe el miembro que es valorado. Lo que nos lleva a lo siguiente.

### Setting
El entorno en el que desarrollamos el acto creativo de resolver un problema lógico es fundamental, al trabajar en equipos, lo primero que tenemos que asegurarnos es un entorno ameno para todos los integrantes. Para esto es recomendable:
- Lugares silenciosos, tranquilos y bien iluminados para evitar distracciones.
- Buena preparación previa de los participantes para evitar el desgaste de explicar los problemas lógicos en lugar de las soluciones propuestas.
- Normas claras y prácticas que permitan la exposición de todos los que quieran proponer algo.
- Herramientas listas para ser usadas, pizarras, cuadernos, lápices con punta, lo que sea que usen lo tienen que tener a mano.

### Mis herramientas
En lo personal, que trabajo de forma remota hace unos 5 años, prefiero una pizarra para marcadores y una de corcho. Mi proceso es sencillo, escribo los conceptos principales en la pizarra y los voy conectado de forma gráfica de ser posible. Una vez que desarrollé el concepto, saco una foto con el celular, y lo vuelvo a escribir en limpio. Por ahí hago este ciclo un par de veces hasta que quedo conforme, muchas veces me pasa de tener varias ideas al mismo tiempo, por eso nunca borro la pizarra sin sacar fotos.

Una vez hecho esto hago fichas basadas en las imágenes separando el problema en partes más pequeñas, estas fichas las fijo con pines a la pizarra y las conecto con hilos de distinto color dependiendo el tipo de lógica envuelto en la resolución del problema. A esto también le saco fotos en el proceso.

Las fotos las suelo compartir con mis colegas cuando explico la resolución del problema, si esta es aceptada, hago una documentación escrita basada en la documentación gráfica.

## Prioridad de desarrollo
Si estamos siguiendo esta propuesta metodológica vamos a tener como prioridad que nuestra aplicación que esta pueda capturar datos de nuestros usuarios y enviarlos a una base de datos o a una aplicación que los procese.

### ¿Qué necesitamos medir?
Para marketing digital se suelen necesitar muchas métricas, pero nosotros nos vamos a centrar en las acciones del usuario, lo que nos va a permitir hacer algo similar a [A/B testing](https://es.wikipedia.org/wiki/Prueba_A/B). Los datos entonces son obtenidos de [eventos globales del DOM](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers): 
  - Utilizamos los eventos tipo _onload_ para medir páginas o secciones visitadas.
  - Los eventos de ejecución de acciones como los _onclick_ para saber dónde intenta realizar acciones el usuario.
  - Los eventos de navegación tipo _onmousewheel_ para saber cómo navega nuestro usuario.

También se pueden tomar métricas end-to-end, es decir de funcionalidades completas, pero pueden llegar a ser un poco más complejas de implementar y sobrepasan el espectro de contenidos de este material.

Cabe aclarar la simulación de eventos del DOM por parte de nuestro código nos va a dar falsos positivos, por lo cual se deben evitar.

## Conceptos

### Análisis
El análisis refiere a la etapa en la que se cuantifica cuáles van a ser las problemáticas particulares que tiene o va a tener una aplicación.

### Diseño
La etapa de diseño en el desarrollo de software se refiere al momento en el que planificamos soluciones para las problemáticas específicas de nuestra app. Cuantificadas en la etapa de análisis.

### Fast Delivery
Este concepto no es nada del otro mundo, se refiere al ajuste de técnicas **agile** para entregar rápido nuevas funcionalidades al usuario.

Tiene un _pro_ muy grande que es que podemos tener feedback rápido de los usuarios, lo que le permite al modelo de negocios reaccionar y organizar las siguientes entregas basado en lo que piden los usuarios.

Pero también tiene una _contra_ bastante fuerte que es la acumulación de [deuda técnica](#deuda-técnica) mientras se mantenga esta logística de entregas.

### User Engagement
El User Engagement es la capacidad de mantener usuarios utilizando nuestra página o aplicación y la podemos medir de varias maneras, pero aquí nos centraremos en medir las acciones del usuario.

Como usuarios sabemos que el uso de las aplicaciones muchas veces es un poco distinto a como viene planteada la app en sí. Cómo desarrolladores lo sabemos más y los que tienen un poco de experiencia en el área de producto también saben que los usuarios, de determinado rango etario, se cansan de las aplicaciones por más que sean eficientes en el problema que resuelven.

Esto nos lleva a necesitar mantener un  flujo de lanzamiento de nuevas features a medida que pasa el tiempo para adaptarnos a esto, el problema está que si no lanzamos la siguiente

### Technical Debt
La siguiente es una división utilizada en el libro [Refactoring for Software Design Smells](https://books.google.com.ar/books?id=1SaOAwAAQBAJ&lpg=PA3&hl=es&pg=PA2#v=onepage&q&f=false).

1) Deuda de estilo (_code debt_).
2) Deuda de diseño (_design debt_).
3) Deuda de pruebas (_test debt_).

## Fuentes
1) [Comparative Study on Agile software development methodologies](https://www.researchgate.net/publication/249011841_Comparative_Study_on_Agile_software_development_methodologies) (_paper_).
2) [Technical debt 101](https://medium.com/@joaomilho/festina-lente-e29070811b84).
3) [Tutorial on Online User Engagement: Metrics and Optimization](https://dl.acm.org/citation.cfm?id=3320087) (_paper_).
4) [User Engagement en la web: estrategias de implementación y métricas de seguimiento](http://www.nosolousabilidad.com/articulos/user_engagement.htm).
5) [Ejecución de la iteración (Sprint)](https://proyectosagiles.org/ejecucion-iteracion-sprint/).
6) [Desarrollo ágil de software](https://es.wikipedia.org/wiki/Desarrollo_%C3%A1gil_de_software).
7) [Producto mínimo viable](https://es.wikipedia.org/wiki/Producto_viable_m%C3%ADnimo)
8) [Set and setting](https://en.wikipedia.org/wiki/Set_and_setting).
9) [Prueba A/B](https://es.wikipedia.org/wiki/Prueba_A/B).
10) [GlobalEventHandlers](https://developer.mozilla.org/es/docs/Web/API/GlobalEventHandlers).
11) [Using Touch Events](https://developer.mozilla.org/en-US/docs/Web/API/Touch_events/Using_Touch_Events).
12) [Refactoring for Software Design Smells](https://books.google.com.ar/books?id=1SaOAwAAQBAJ&lpg=PA3&hl=es&pg=PA2#v=onepage&q&f=false) (_libro_)
13) [GUI Performance Metrics Framework: Monitoring performance of web clients to improve user experience](http://www.diva-portal.org/smash/record.jsf?pid=diva2%3A1299788&dswid=-4694) (_paper_).
14) [El MVP ha muerto, larga vida al MAP. (Minimum Awesome Product)](https://medium.com/productea/el-mvp-ha-muerto-larga-vida-al-map-596987f37de4).