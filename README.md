# Animación del Sistema Solar

El propósito del proyecto es realizar una animación del sistema solar por medio de aproximaciones numéricas que nos permiten hacer uso del problema de los tres cuerpos, así que solo se tienen en cuenta las interacciones con los 2 cuerpos más masivos del sistema solar disponibles (Sol y Júpiter o Saturno) y aproximar así el movimiento de los 8 planetas del sistema solar con respecto al Sol. Esto se logra haciendo uso de la Ley de la Gravitación Universal de Newton para cada cuerpo presente en la interacción y usando la herramienta scipy.integrate.odeint para resolver las ecuaciones diferenciales ordinarias de movimiento acopladas con sus respectivas condiciones iniciales

![](AMaJ.PNG)

## Consideraciones

Para hacer uso de este código, es necesario tener una versión de Matplotlib que permita hacer uso de la función anim.save en caso de que se quiera guardar la animación, ya que algunas versiones como la 3.1 no lo permiten. Además, el código está escrito para ejecutarse en la consola de Jupyter. El código como está escrito, anima una pequeña sección de vídeo para evitar tiempos elevados en la ejecución del programa. Queda a la disposición del usuario escoger la cantidad de frames a animar dependiendo de cuánto quiera observar en la animación y cuánto tiempo esté dispuesto a dejar corriendo el programa. De igual forma, por facillidad para el usuario, todos los pasos están comentados en el código para que el usuario entienda qué se hace con cada sección.

## Instalación

Descargar el archivo ASS.ipynb y correrlo en la consola de Jupyter Notebook. En caso de no poder hacer uso de la función anim.save, se puede descargar FFmpeg desde [acá](https://ffmpeg.zeranoe.com/builds/) o descargar una versión de matplotlib que no presente fallas con esa función (como la 3.0), tal como se indicó en las consideraciones.

## Física del código

[Teoría](https://github.com/JuanCastro36/Sistema-Solar/blob/patch-1/Teor%C3%ADa) 

## Resumen del código

La primera parte del código consiste en importar las librerías y funciones necesarias para el código, como matplotlib para las gráficas, scipy para solucionar las ecuaciones diferenciales de movimiento y HTML para las animaciones. Después asignamos las constantes físicas necesarias para las ecuaciones como la constante de la gravitación universal G y valores de referencia como la masa del Sol, la velocidad orbital de la Tierra respecto al Sol, el período de la órbita de la Tierra alrededor del Sol y la distancia media de la Tierra al Sol en m, para después utilizar por comodidad las unidades astronómicas UA.

Posteriormente ingresamos las 7 funciones necesarias para definir el problema de los 8 planetas. Para calcular los movimientos del Sol, Júpiter y Saturno; se usa la misma ecuación ya que al ser los 3 cuerpos más masivos del sistema solar, son los que más se afectarán entre sí según la aproximación de los 3 cuerpos. Cada función consiste en definir inicialmente los valores iniciales de la posición y la velocidad, ya que tratamos con ecuaciones diferenciales ordinarias de segundo orden e incluimos estos valores junto con los de los otros dos cuerpos con los que interactuará el planeta, dentro de un arreglo "a" de 18 entradas. Además se definen las ecuaciones de la posición y la velocidad del centro de masas del sistema de 3 cuerpos.

A continuación ingresamos las distancias entre cuerpos e introducimos las ecuaciones diferenciales de movimiento de aceleración y velocidad con ayuda de la Ley de la Gravitación Universal de Newton. Posteriormente ingresamos los parámetros iniciales y con ayuda de la libería scipy, solucionamos numericamente las EDOs y obtenemos las soluciones para los 3 cuerpos y dependiendo del objetivo, definimos qué solución queremos mostrar. Respecto a eso último, en todas las funciones (menos en la de Júpiter) se definen las respectivas funciones del planeta. En la de Júpiter se define la solución para el Sol, Júpiter y Saturno.

Para la tercera parte del código, definimos la animación y la graficación de las soluciones expresadas en la segunda parte. Usamos plot y scatter para obtener las gráficas de los planetas y sus órbitas, e introducimos los valores para el color y el tamaño de los planetas. En esta sección también creamos la función Animar en la que se añaden comandos para alivianar la carga de procesamiento de la animación y los cálculos. Con las variables orbita y traza definimos los valores necesarios en cada punto que se anime.

Para finalizar, configuramos ciertos detalles referentes a la presentación de la animación y las gráficas. Por gusto, eliminamos la marcación de los ejes y las mallas y adicionalmente, dejamos el fondo completamente negro para dar la impresión del espacio. Ya para ultimar, usamos FuncAnimation para generar la animación haciendo uso de los parámetros definidos en la función Animar y escogiendo la cantidad de frames a animar y con ayuda de HTMl, generamos una animación que nos brinda la posibilidada de pausar, adelantar o retroceder y se incluye anim.save para guardar un vídeo mp4 con el contenido de la animación.

## Resultados

Los resultados dependerán de qué tanto se quiera abarcar, un resultado que se puede obtener en poco tiempo de ejecución del código, es la simulación de Mercurio, Venus, Tierra, Marte y Júpiter como se ve en la animación a continuación. Hay que tener en cuenta que el código se puede editar para agregar más cuerpos si se quiere con sus posiciones y velocidades definidas, pero entre más se quiera agregar, mayor va a ser el tiempo de ejecución del programa.

![](Problema3C1250.gif)

Adicional a la animación, obtendremos una gráfica con los ejes coordenados con su respectiva leyenda y una imagen de la animación. A continuación se muestran ejemplos de ambas.

![](Captura.PNG)

Estas simulaciones tienen las formas mostradas, debido a que entre más cuerpos lejanos se agreguen, los planetas más cercanos al Sol ya habrán girado muchas veces con órbitas que no son iguales. También cabe aclarar que entre más espacio se quiera abarcar, menos se van a ver los cuerpos y para propósitos de imagen, no es muy conveniente. Por eso se muestran imágenes de simulaciones sin todos los planetas del Sistema Solar.

![](Animación_Sistema_Solar2.gif)


## Autores

 * Juan Pablo Castro Rodríguez

 * Luis Felipe De La Ossa Mayorga

## Licencia

[GNU General Public License V3.0](https://github.com/JuanCastro36/Sistema-Solar/blob/patch-1/LICENSE)
