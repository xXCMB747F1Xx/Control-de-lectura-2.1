# Control-de-lectura-2
A partir del video, describa la arquitectura de Big Data mostrada, la naturaleza (o tipo) de los datos y flujo general de procesamiento de los mismos al interior de Netflix.
# Cándido Méndez Baltazar
<H2> Introducción: </H2>

<p>Netflix fue creado en 1997 y durante 20 años de recorrido a logrado alcanzar una cifra de cien millones de miembros en todo el mundo, han logrado invertir durante varios años dinero en contenido original y claramente la audiencia disfruta de dicho contenido, de igual forma esto se ve reflejado en la cantidad de horas que visualizan los usuarios de la plataforma al día.</p>

<p>Se encuentran a rededor de cuatro mil dispositivos diferentes ahora hay una razón, teniendo todo esto en cuenta, creo que es muy obvio decir que la cantidad de datos que se llegan a manejar en la plataforma es inmensa, y por ello suena a algo muy difícil de controlar o manejar, alcanzo incluso un pico de un billón de estos datos, todos estos datos son procesados y almacenados en una base, la cual se logra construir con la tecnología de BIG DATA.</p>

<p>Llevan alrededor de 60 petabytes en su almacén de datos, una tasa de 300 terabyte al día de DW de escritura y en promedio realizan de 5 patabytes de lectura.
Hablaremos de los eventos dentro de la plataforma o en si del servicio, con esto se hace referencia a cada acción que realiza una persona dentro de la plataforma, como la autentificación, el catálogo principal, lo que se recomienda que vea el usuario en base a sus gustos, todo visto desde un algoritmo, cuando hace clic en un contenido o le pone pausa, todos estos eventos registrados y almacenados en el hosting, es decir estos datos se escriben dentro de esta, respaldada por Kafka(Plataforma completa de Streaming y de procesamiento de datos en tiempo real) y logra aterrizar en una capa de ingesta sin procesar dentro de su almacén de datos, en resumen, todo este complejo sistema esta basado en la nube, para ser en específicos en la AWS de Amazon.</p>

<p>Cuentan con una capa sin procesar, utilizando una variedad de tecnologías de procesamiento de BigData, cuando este es encendido logra procesar esos datos, transformarlos y enviarlos al almacén de datos, posterior a ello se logran agregar, normalizarlos y resumirlos, y ponerlos en una capa de informes.</p>

<p>Por otro lado, encontramos los subconjuntos de datos, lo cuales se mueven a una variedad de almacenamiento de acceso rápido donde esos datos están disponibles para las herramientas de visualización de datos Tableau (Empresa estadounidense de software de visualización de datos interactivos centrada en la inteligencia empresarial.) siendo la mas utiliza para la plataforma, pero de igual forma utilizan una variedad de otros casos de usos, esto permite más interacción con otras herramientas de visualización.</p>

<p>Otro aspecto importante es que cada integrante de la empresa tiene acceso a los informes y sus datos, aspecto que de igual forma trae ciertos problemas, por la variedad de datos que maneja la empresa y para lograr controlar todo el trafico que logra ingresar al servicio.</p>

<H2>Desarrollo:</H2>
<P>La herramienta Vizceral se encarga de manejar el trafico la cual interpreta como pequeños puntos la API que se utilizan mientras que los puntos mas grandes representan varias regiones, cuando una región (representada por un círculo) es color rojo, en ciertas secciones significa que hay un problema con esa API, esto significa que estamos recibiendo la mayor parte de los datos, pero es posible que no estemos recibiendo todo los datos, es posible que no estemos recibiendo un tipo de evento, por lo regular esto debido a una mala interacción o ejecución ya sea del usuario o otras personas, este problema se ve afectado a la hora de generar informes.</P>

<p>Al igual que otras empresas, Netflix trabaja mediante roles en su empresa, como lo son los ingenieros de datos, el cual logra entender los sistemas distribuidos y logran procesar millones de eventos dentro de la plataforma, logrando fabricar varios consumibles para el resto de la empresa.</p>

<p>Ingenieros analíticos; continúan donde lo dejo el ingeniero de datos, agregando o creando algunas tablas de resumen, creando visualizaciones e incluso podrían hacer algunas ad hoc y análisis, siendo considerados una pieza fundamental.</p>

<p>También se encuentran los analistas de negocios, analistas científicos y analistas cuantitativos encargados de responder las preguntas que sean realmente grandes y difícil, por otro lado, encontramos al científico de datos y el científico de aprendizaje automático, los cuales se encargan de crear modelos para ayudar a predecir comportamientos o tomar mejores decisiones, fungiendo como los consumidores viéndose afectados por los datos incorrectos.</p>

<p>En la capa superior es donde realmente se comienza a ver el impacto provocado por aquellos datos incorrectos, es donde entran los ejecutivos, otro rol importante que analiza los datos para tomar decisiones, los gerentes de productos se encuentran en la función vertical de la empresa, también se encuentran los ingeniero de algoritmo decidiendo cual es el contenido correcto para mostrarla en el sitio y por ultimo y no menos importante, el ingeniero de software, el cual esta experimentado con cosas, reducir, optimizar, funciones que visualmente no logra captar el usuario, pero que realmente ayuda mucho a la empresa.</p>

<H4>Detección de problemas de calidad de datos:</H4>

<P>La mayor parte de estos problemas se ve reflejado en la estructura del código, se puede trabajar con tablas estadísticas, las cuales te ayudan a profundizar mejor en la estructura, en la mayoría de los métodos implícitos dentro del sistema.</P>
  
<P>Como es que se escriben los datos, como habilitar cosas que pueden ser mas poderosas, con estas estadísticas ahora lo que se puede hacer es enfocarlas de forma aislada, ya que de cierta forma los errores son más difíciles de encontrar, por ello resulta mas factible tomas cada uno de estos datos en un gráfico, donde se podrá visualizar los picos y valles que se han generado por el tiempo, por lo que se notaran las diferencias que se han logrado registrar durante cada día de la semana, entonces se encuentran los datos que se localicen fuera de la distribución.</P>

<H4>Minimizar el impacto desafortunado;</H4>
  
<P>Aquí la pregunta que uno debe hacerse es si realmente si uno ¿Puede confiar en estos informes?, ¿Puedo confiar en estos datos que tengo?, para ello la empresa a logrado crear un proceso que verifica si toda esta información o datos realmente viene errónea y evitar su visualización con posterioridad, antes de llagar a la capa de información se realiza un análisis en su distribución de desviación, esto se debe realizar de esta manera ya que uno como empresa no pude dejar que los usuarios finales vean estos errores, se perdería la confianza con la plataforma y en si con la empresa, por ello la importancia de este proceso.</p>

<p>Para ello es importante mostrar los datos, mostrar la información, cuando fue que se fueron los datos, cuando es que se cargaron por última vez, ¿Cuándo se revisó la ultima vez que se validó?</p>

<p>También somos una vista de nuestro portal de BigData, es una herramienta interna que hemos desarrollado, aunque se plantea agregar visibilidad a las fallas reales y alertar para que los usuarios comerciales puedan verlas.</p>

<h4>Corrección de datos desafortunados rápidamente:</h4>

<p>Deben de visualizar estos errores las personas que necesitan comprender cual es el problema y necesitan solucionarlo, entre las soluciones plateadas se encuentra la de mostrar la información y trabajar con el tiempo de ejecución, el por qué se recibió muchos más datos. Esto facilita y agiliza al usuario para solucionar los problemas que se presenten en el sistema.</p>

<p>Sacando datos:</p>

<p>Aquí encontramos los eventos sin procesar, se trata de programar y sondear en lugar de impulsar, se trabaja con el detallado de la programación o tabla detallada que se encuentre limpia, agregar, a la hora de ejecutar a otro trabajo y va a aumentar, rehacer todos esos datos que se agendan en ciertas horas.
Va a realizar otro proceso que se ejecuta y se normalizará para tener por completo todo el informe, copiarlo en la carpeta en la capa de acceso rápido y antes de la hora de entrega el informe deberá estar listo en un sistema basado en push.</p>

<h4>Cierre:</h4>

<p>Como se logró comprender, la plataforma Netflix realmente tiene una estructura funcional y útil en cuánto sus procesos y metodologías que logran idear, sus roles que manejan ayudan mucho a como realizar cada proceso, sin mencionar que los métodos utilizados para llegar a una solución son factibles y llegan a la misma conclusión, las tecnologías de BigData realmente lograron brindar una excelente dirección a la empresa, en cuestión de la información que reciben así como al gran banco de datos que operan y manejan.</p>
