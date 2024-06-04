Arquitecturas de sistemas paralelos

Las arquitecturas de sistemas paralelos son fundamentales para mejorar
el

rendimiento de las aplicaciones mediante la ejecución simultánea de
múltiples

operaciones. Estas arquitecturas se dividen en varias categorías, cada
una

adecuada para diferentes tipos de tareas y aplicaciones. En general, las

arquitecturas paralelas se clasiﬁcan en función de la organización de la
memoria y

la interconexión de los procesadores.

En el ámbito de la computación paralela, las arquitecturas de sistemas
pueden

clasiﬁcarse en dos categorías principales basadas en cómo gestionan la
memoria:

arquitecturas de memoria compartida y arquitecturas de memoria
distribuida.

Ambas tienen sus ventajas y desventajas, y son adecuadas para diferentes
tipos de

aplicaciones y entornos de ejecución.

**Arquitectura** **de** **memoria** **compartida**

En una arquitectura de memoria compartida, todos los procesadores
acceden a un

único espacio de memoria global. Esta conﬁguración es intuitiva y
facilita la

programación, ya que los procesos pueden comunicarse y sincronizarse a
través de

variables compartidas.

Tipos de memoria compartida

> ● Memoria compartida uniforme (UMA): En UMA (Uniform Memory Access),
> todos los procesadores tienen igual tiempo de acceso a la memoria
> principal. Esto signiﬁca que la latencia de acceso a la memoria es la
> misma para todos los procesadores.
>
> ○ Ejemplos: Estaciones de trabajo multiprocesador, servidores de gama
> media.
>
> ○ Ventajas: Simplicidad en la programación debido a la uniformidad en
> el acceso a la memoria. Facilita la coherencia de la caché y la
> sincronización entre procesadores.
>
> ○ Desventajas: No escala bien a un gran número de procesadores debido
> a la contención de memoria y los cuellos de botella en el bus de
> memoria.
>
> ● Memoria compartida no uniforme (NUMA): En NUMA (Non-Uniform Memory
> Access), cada procesador tiene su memoria local, y el tiempo de acceso
> a la memoria varía dependiendo de si se accede a la memoria local o a
> la memoria de otro procesador.
>
> ○ Ejemplos: Servidores de alto rendimiento, sistemas NUMA basados en
> arquitecturas como AMD EPYC e Intel Xeon.
>
> ○ Ventajas: Mejora la escalabilidad al reducir la contención de
> memoria y permite un acceso más rápido a la memoria local.
>
> ○ Desventajas: Mayor complejidad en la programación, ya que se debe
> gestionar la latencia variable en el acceso a la memoria.

Ventajas y desventajas de la memoria compartida

Ventajas:

> ● Facilidad de programación: La memoria compartida es más intuitiva
> para los programadores, ya que se puede usar una única dirección de
> memoria para la comunicación entre hilos.
>
> ● Rendimiento: En sistemas UMA, el acceso uniforme a la memoria puede
> simpliﬁcar la optimización del rendimiento.
>
> ● Coherencia de caché: Los sistemas NUMA y UMA gestionan la coherencia
> de la caché, lo que puede reducir errores en la programación.

Desventajas:

> ● Escalabilidad: Los sistemas UMA enfrentan limitaciones en la
> escalabilidad debido a la contención del bus de memoria.
>
> ● Complejidad en NUMA: Aunque NUMA mejora la escalabilidad, introduce
> complejidad en la programación debido a las diferencias en la latencia
> de acceso a la memoria.
>
> ● Costos: Los sistemas de memoria compartida pueden ser más costosos
> debido a la necesidad de hardware más soﬁsticado para gestionar la
> coherencia de la caché y el acceso a la memoria.

**Arquitectura** **de** **memoria** **distribuida**

En una arquitectura de memoria distribuida, cada procesador tiene su
propia

memoria local. Los procesadores no pueden acceder directamente a la
memoria de

otros procesadores. La comunicación entre procesadores se realiza
mediante el

paso de mensajes.

Tipos de arquitecturas de memoria distribuida

Multicomputadores: Sistemas compuestos por varios nodos de computación,
cada

uno con su propia CPU y memoria. Los nodos están interconectados
mediante una

red de alta velocidad.

> ● Ejemplos: Supercomputadoras, clústeres de computadoras.
>
> ● Ventajas: Alta escalabilidad, ya que no hay contención de memoria
> compartida. Mejor tolerancia a fallos, ya que cada nodo es
> independiente.
>
> ● Desventajas: Programación más compleja debido a la necesidad de
> gestionar la comunicación y sincronización entre nodos mediante el
> paso de mensajes.

Clústeres de computadoras: Un tipo especíﬁco de multicomputador donde
varios

sistemas completos (nodos) están conectados a través de una red para
trabajar

juntos como un solo sistema.

> ● Ejemplos: Clústeres de alto rendimiento (HPC), clústeres de alta
> disponibilidad (HA).
>
> ● Ventajas: Coste-efectividad al utilizar hardware convencional.
> Capacidad de combinar recursos de diferentes sistemas para tareas
> especíﬁcas.
>
> ● Desventajas: Dependencia de la red para la comunicación, lo que
> puede introducir latencias signiﬁcativas.

Ventajas y desventajas de la memoria distribuida

Ventajas:

> ● Escalabilidad: Permite construir sistemas con un gran número de
> nodos sin problemas signiﬁcativos de contención.
>
> ● Tolerancia a fallos: La falla de un nodo no afecta necesariamente a
> los demás, mejorando la ﬁabilidad del sistema.
>
> ● Flexibilidad: Los nodos pueden ser heterogéneos, permitiendo la
> integración de diferentes tipos de hardware según sea necesario.

Desventajas:

> ● Complejidad en la programación: Requiere un manejo explícito de la
> comunicación y sincronización entre nodos, lo que aumenta la
> complejidad del desarrollo de software.
>
> ● Latencia de comunicación: La comunicación entre nodos puede ser
> lenta debido a la latencia de la red, afectando el rendimiento de las
> aplicaciones que requieren alta interactividad.

La elección entre una arquitectura de memoria compartida y una de
memoria

distribuida depende de las características de la aplicación y de los
requisitos

especíﬁcos del sistema.

**Aplicaciones** **adecuadas** **para** **memoria** **compartida**:

> ● Aplicaciones con alta interactividad entre procesos.
>
> ● Sistemas donde la facilidad de programación es una prioridad.
>
> ● Entornos donde la coherencia de la caché y la sincronización son
> críticas.

**Aplicaciones** **adecuadas** **para** **memoria** **distribuida**:

> ● Aplicaciones que requieren alta escalabilidad, como simulaciones
> cientíﬁcas y análisis de big data.
>
> ● Sistemas distribuidos y clústeres donde la tolerancia a fallos es
> crucial. ● Aplicaciones que pueden tolerar latencias de comunicación
> más altas y
>
> donde la programación paralela se puede manejar mediante el paso de
> mensajes.

**Arquitecturas** **paralelas** **híbridas** Las arquitecturas paralelas
híbridas combinan

elementos de arquitecturas de memoria compartida y memoria distribuida
para

aprovechar las ventajas de ambas y mitigar sus desventajas. Estas
arquitecturas se

utilizan en sistemas que requieren alta escalabilidad y rendimiento, y
son comunes

en aplicaciones cientíﬁcas, de ingeniería y de análisis de datos
masivos.

Las arquitecturas híbridas están diseñadas para mejorar la eﬁciencia y
el

rendimiento combinando características de sistemas de memoria compartida

(como UMA y NUMA) y sistemas de memoria distribuida (como
multicomputadores

y clústeres). En una arquitectura híbrida, los nodos individuales pueden
ser sistemas

de memoria compartida que están interconectados mediante una red de alta

velocidad para formar un sistema de memoria distribuida.

Un ejemplo típico de una arquitectura híbrida es un clúster de nodos
NUMA. Cada

nodo es un sistema NUMA, donde múltiples procesadores comparten una
memoria

local. Los nodos están conectados a través de una red, formando un
sistema de

memoria distribuida. Este enfoque permite que cada nodo NUMA opere de
manera

eﬁciente con baja latencia de memoria local, mientras que la red de
interconexión

permite la comunicación entre nodos para tareas de gran escala.

Ventajas de las arquitecturas híbridas

> ● Escalabilidad mejorada: La combinación de memoria compartida y
> distribuida permite escalar el sistema a un gran número de
> procesadores sin los problemas de contención de memoria asociados con
> UMA. La memoria distribuida entre nodos reduce la carga en el bus de
> memoria y mejora la escalabilidad.
>
> ● Flexibilidad: Las arquitecturas híbridas pueden adaptarse a una
> amplia variedad de aplicaciones, desde tareas intensivas en cálculo
> hasta aplicaciones que requieren gran ancho de banda de memoria. Los
> desarrolladores pueden optimizar las aplicaciones utilizando la
> memoria local para datos de acceso frecuente y la memoria distribuida
> para datos que no requieren acceso inmediato.
>
> ● Rendimiento: Los nodos NUMA dentro de una arquitectura híbrida
> permiten un acceso rápido a la memoria local, mejorando el rendimiento
> de las aplicaciones. La interconexión de alta velocidad entre nodos
> permite una comunicación eﬁciente para tareas que requieren
> intercambio de datos.
>
> ● Tolerancia a fallos: La naturaleza distribuida de la memoria permite
> que el sistema continúe operando incluso si uno o varios nodos fallan.
> Las arquitecturas híbridas pueden incluir mecanismos de redundancia y
> recuperación para mejorar la ﬁabilidad del sistema.

Desventajas de las arquitecturas híbridas

> ● Complejidad de programación: Los desarrolladores deben gestionar
> tanto la memoria compartida como la distribuida, lo que aumenta la
> complejidad del desarrollo de software. La programación paralela en
> arquitecturas híbridas requiere un profundo conocimiento de los
> modelos de memoria y las técnicas de sincronización.
>
> ● Latencia de comunicación: Aunque la red de interconexión es rápida,
> la comunicación entre nodos aún puede introducir latencia, afectando
> el rendimiento de aplicaciones altamente interactivas. Las estrategias
> de
>
> minimización de latencia deben ser cuidadosamente diseñadas y
> optimizadas.
>
> ● Costos: La implementación de arquitecturas híbridas puede ser
> costosa debido a la necesidad de hardware soﬁsticado y redes de alta
> velocidad. Los costos operativos y de mantenimiento también pueden ser
> altos debido a la complejidad del sistema.

Modelos de programación en arquitecturas híbridas

Para aprovechar las arquitecturas híbridas, se utilizan diversos modelos
de

programación que combinan técnicas de memoria compartida y distribuida:

> ● Modelo MPI+OpenMP: Este modelo combina el paso de mensajes (MPI)
> para la comunicación entre nodos y la memoria compartida (OpenMP) para
> la paralelización dentro de cada nodo.
>
> ○ Ejemplo: En una simulación de dinámica de ﬂuidos, MPI se puede usar
> para distribuir diferentes regiones del dominio de simulación entre
> nodos, mientras que OpenMP se usa para paralelizar los cálculos dentro
> de cada región.
>
> ● Modelo UPC (Uniﬁed Parallel C): UPC es un modelo de programación
> paralela que extiende C para incluir tanto memoria compartida como
> distribuida.
>
> ○ Permite a los desarrolladores escribir programas que pueden
> aprovechar las arquitecturas híbridas sin tener que gestionar
> explícitamente la comunicación entre nodos.
>
> ● Modelo GASNet (Global Address Space Networking): GASNet es una API
> de comunicaciones diseñada para soportar modelos de programación con
> espacio de direcciones global.
>
> ○ Proporciona una abstracción de comunicación eﬁciente que permite a
> los desarrolladores escribir aplicaciones paralelas que pueden escalar
> en arquitecturas híbridas.

Aplicaciones de las arquitecturas híbridas

Las arquitecturas híbridas son particularmente adecuadas para una amplia
gama de

aplicaciones cientíﬁcas y de ingeniería:

Simulaciones cientíﬁcas:

> ● Aplicaciones como simulaciones de dinámica molecular, modelado
> climático y simulaciones de física de alta energía se beneﬁcian de la
> combinación de memoria compartida y distribuida para manejar grandes
> volúmenes de datos y cálculos intensivos.

Análisis de datos masivos:

> ● En el análisis de big data, las arquitecturas híbridas permiten
> procesar grandes conjuntos de datos de manera eﬁciente mediante la
> distribución de tareas y datos entre nodos y el uso de memoria
> compartida para cálculos intensivos.

Inteligencia artiﬁcial y aprendizaje automático:

> ● Los entrenamientos de modelos de aprendizaje profundo pueden
> aprovechar arquitecturas híbridas para distribuir datos y tareas de
> entrenamiento entre múltiples nodos, mientras que los cálculos
> intensivos se realizan dentro de los nodos utilizando memoria
> compartida.

Ingeniería y diseño asistido por computadora (CAE/CAD):

Las aplicaciones de CAE y CAD, que requieren simulaciones precisas y
detalladas,

pueden utilizar arquitecturas híbridas para manejar las demandas
computacionales

y de memoria.

Ejemplos

Un ejemplo real de arquitectura híbrida es un clúster de alto
rendimiento (HPC) que

utiliza nodos NUMA interconectados mediante una red InﬁniBand de alta
velocidad.

Cada nodo NUMA tiene múltiples procesadores con memoria local
compartida, y los

nodos están conectados para formar una memoria distribuida global. Este
tipo de

clúster se utiliza en centros de supercomputación para tareas como la
simulación

de fenómenos físicos complejos y el análisis de grandes conjuntos de
datos.

Características del clúster HPC híbrido:

> ● Interconexión de alta velocidad:
>
> ○ La red InﬁniBand proporciona una latencia baja y un alto ancho de
> banda para la comunicación entre nodos, mejorando el rendimiento
> global del sistema.
>
> ● Gestión de memoria eﬁciente:
>
> ○ Los desarrolladores pueden aprovechar la memoria local de los nodos
> NUMA para datos de acceso frecuente y utilizar la memoria distribuida
> para datos menos críticos.

Soporte para diversos modelos de programación:

> ● El clúster puede soportar modelos de programación como MPI+OpenMP,
> UPC y GASNet, proporcionando ﬂexibilidad para los desarrolladores.
> Escalabilidad y Rendimiento:

La arquitectura híbrida permite escalar el clúster a miles de nodos,
proporcionando

un rendimiento sustancial para aplicaciones de gran escala.

Técnicas orientadas a computación paralela y distribuida

**Paralelismo** **de** **datos**

El paralelismo de datos implica dividir grandes conjuntos de datos en
partes más

pequeñas y procesarlas simultáneamente en diferentes procesadores. Esta
técnica

es efectiva en aplicaciones como el procesamiento de imágenes,
simulaciones

cientíﬁcas, y análisis de grandes volúmenes de datos.

**Paralelismo** **de** **tareas**

El paralelismo de tareas divide un programa en tareas o hilos que se
ejecutan en

paralelo. Cada tarea puede realizar una operación diferente, permitiendo
la

ejecución concurrente de múltiples operaciones. Esta técnica es útil en
aplicaciones

como servidores web y procesamiento en tiempo real.

**Modelos** **de** **programación** **paralela**

> ● Modelo de paso de mensajes (MPI): Utilizado en sistemas de memoria
> distribuida, donde los procesadores se comunican enviando y recibiendo
>
> mensajes. MPI es un estándar ampliamente utilizado en aplicaciones de
> HPC.
>
> ● Modelo de memoria compartida (OpenMP): Utilizado en sistemas de
> memoria compartida, permite la creación de aplicaciones paralelas
> mediante directivas en el código fuente. OpenMP simpliﬁca la
> programación paralela en sistemas SMP y multinúcleo.
>
> ● Modelo híbrido: Combina MPI y OpenMP para aprovechar las ventajas de
> ambos modelos en sistemas NUMA o clústeres heterogéneos.

keyboard_arrow_down

> Ejercicios
>
> **●** **Explica** **la** **diferencia** **entre** **UMA** **(Uniform**
> **Memory** **Access)** **y** **NUMA** **(Non-Uniform** **Memory**
> **Access).**
>
> UMA (Uniform Memory Access) y NUMA (Non-Uniform Memory Access) son
> arquitecturas de memoria utilizadas en sistemas multiprocesadores,
> diferenciándose principalmente en cómo acceden a la memoria.
>
> UMA (Uniform Memory Access):
>
> ● En UMA, todos los procesadores comparten la memoria física de manera
> uniforme.
>
> ● La latencia de acceso a la memoria es la misma para todos los
> procesadores. ● Es común en sistemas SMP (Symmetric Multiprocessing).
>
> ● Ejemplo: Sistemas con un bus de memoria centralizado donde todos los
> procesadores tienen acceso equitativo a la memoria.
>
> NUMA (Non-Uniform Memory Access):
>
> ● En NUMA, la memoria está distribuida entre nodos de procesadores, y
> cada nodo tiene su propia memoria local.
>
> ● La latencia de acceso a la memoria varía según la proximidad de la
> memoria al procesador. Acceder a la memoria local es más rápido que
> acceder a la memoria remota.
>
> ● Mejora la escalabilidad y el rendimiento en sistemas grandes y
> complejos. ● Ejemplo: Sistemas donde cada procesador tiene su propia
> memoria y un
>
> interconexión de alta velocidad entre nodos permite el acceso a la
> memoria de otros nodos.

Por tanto, la principal diferencia radica en la latencia de acceso a la
memoria y la disposición física de la memoria respecto a los
procesadores: UMA ofrece acceso uniforme con la misma latencia, mientras
que NUMA ofrece acceso no uniforme, optimizando la latencia según la
proximidad de la memoria al procesador.

> **●** **Describe** **las** **ventajas** **y** **desventajas** **de**
> **la** **memoria** **compartida** **en** **comparación** **con**
> **la** **memoria** **distribuida.**

La memoria compartida y la memoria distribuida son dos enfoques
diferentes para la gestión de memoria en sistemas multiprocesadores. A
continuación, se presentan las ventajas y desventajas de cada uno de
estos enfoques de manera breve y técnica.

Memoria Compartida:

*Ventajas:*

> 1\. Simplicidad en la programación: Los procesos pueden comunicarse
> directamente a través de variables compartidas, lo que simpliﬁca el
> desarrollo de software.
>
> 2\. Rendimiento en acceso a datos comunes: El acceso a los datos
> compartidos puede ser más rápido, ya que no hay necesidad de
> transferir datos entre nodos.
>
> 3\. Facilidad en la sincronización: Las primitivas de sincronización
> (como semáforos y mutexes) son más fáciles de implementar en un
> entorno de memoria compartida.

*Desventajas:*

> 1\. Escalabilidad limitada: A medida que aumenta el número de
> procesadores, el bus de memoria puede convertirse en un cuello de
> botella, limitando el rendimiento.
>
> 2\. Contención y coherencia de caché: Los múltiples accesos
> concurrentes a las mismas ubicaciones de memoria pueden causar
> contención y problemas de coherencia de caché, lo que reduce la
> eﬁciencia.
>
> 3\. Complejidad del hardware: La implementación de mecanismos para
> mantener la coherencia de la memoria caché en sistemas grandes es
> compleja y costosa.

Memoria Distribuida:

*Ventajas:*

> 1\. Escalabilidad: Cada nodo tiene su propia memoria, lo que reduce la
> contención y permite escalar el sistema añadiendo más nodos.
>
> 2\. Mejor rendimiento local: El acceso a la memoria local es rápido, y
> las cargas de trabajo pueden ser distribuidas de manera eﬁciente para
> aprovechar esta ventaja.
>
> 3\. Reducción de cuello de botella: La ausencia de un bus de memoria
> centralizado elimina el cuello de botella asociado a la memoria
> compartida.

*Desventajas:*

> 1\. Complejidad en la programación: Los desarrolladores deben manejar
> explícitamente la comunicación entre nodos, lo que puede complicar el
> desarrollo de software.
>
> 2\. Latencia de comunicación: La comunicación entre nodos puede ser
> lenta debido a la latencia de la red, afectando el rendimiento de
> aplicaciones que requieren alta interacción entre nodos.
>
> 3\. Diﬁcultad en la sincronización: La sincronización entre nodos es
> más compleja y puede requerir mecanismos adicionales para garantizar
> la coherencia de datos.

Es decir, la memoria compartida simpliﬁca la programación y la
sincronización, pero sufre de problemas de escalabilidad y contención.
La memoria distribuida, por otro lado, ofrece mejor escalabilidad y
rendimiento local, a costa de una mayor complejidad en la programación y
la sincronización entre nodos.

> **●** **¿Qué** **es** **la** **coherencia** **de** **caché** **y**
> **por** **qué** **es** **importante** **en** **sistemas** **de**
> **memoria** **compartida?**

La coherencia de caché es un principio que garantiza que múltiples
copias de datos almacenadas en las cachés de diferentes procesadores de
un sistema multiprocesador sean consistentes entre sí. En otras
palabras, asegura que todas las cachés reﬂejan el mismo valor para una
misma ubicación de memoria compartida.

Importancia en sistemas de memoria compartida:

> 1\. Consistencia de datos: Sin coherencia de caché, los procesadores
> podrían trabajar con versiones diferentes de los mismos datos, lo que
> llevaría a resultados incorrectos y comportamientos impredecibles en
> las aplicaciones.
>
> 2\. Sincronización: La coherencia de caché facilita la sincronización
> entre procesadores, ya que los mecanismos de sincronización (como
> semáforos y mutexes) dependen de la visibilidad de cambios en los
> datos compartidos.
>
> 3\. Rendimiento: Mantener la coherencia de caché minimiza la necesidad
> de acceder a la memoria principal para obtener datos actualizados, lo
> que mejora el rendimiento al reducir la latencia de acceso.
>
> 4\. Correctitud: Garantiza que las operaciones concurrentes sobre los
> datos compartidos sigan el orden esperado por los desarrolladores,
> preservando la correctitud de los programas.

Por lo tanto, la coherencia de caché es crucial en sistemas de memoria
compartida para asegurar la consistencia de datos, facilitar la
sincronización entre procesadores, mejorar el rendimiento y garantizar
la correctitud de las aplicaciones.

> **●** **Describe** **el** **proceso** **de** **comunicación**
> **entre** **nodos** **en** **un** **sistema** **de** **memoria**
> **distribuida.**

En un sistema de memoria distribuida, cada nodo posee su propia memoria
local y los nodos se comunican entre sí a través de una red de
interconexión. El proceso de comunicación entre nodos generalmente sigue
estos pasos:

> 1\. Inicio de comunicación: Un nodo fuente (emisor) decide que
> necesita enviar datos a otro nodo destino (receptor).
>
> 2\. Serialización de datos: Los datos a ser transferidos se serializan
> en un formato adecuado para su transmisión a través de la red.
>
> 3\. Envio de datos: El nodo fuente utiliza una interfaz de red, como
> MPI (Message Passing Interface), sockets, o RDMA (Remote Direct Memory
> Access), para enviar los datos serializados al nodo destino.
>
> 4\. Transmisión: Los datos se transmiten a través de la red de
> interconexión, que puede ser Ethernet, InﬁniBand u otra tecnología de
> red de alta velocidad.
>
> 5\. Recepción: El nodo destino recibe los datos a través de su
> interfaz de red.
>
> 6\. Deserialización de datos: El nodo destino deserializa los datos
> recibidos para convertirlos de nuevo a su formato original.
>
> 7\. Procesamiento: El nodo destino procesa los datos recibidos según
> sea necesario para la aplicación.

Importancia de la comunicación entre nodos:

> ● Escalabilidad: Permite que sistemas distribuidos escalen añadiendo
> más nodos, cada uno con su propia memoria.
>
> ● Eﬁciencia: Los nodos pueden procesar tareas localmente y solo
> comunicar los resultados necesarios, optimizando el uso de la red.
>
> ● Distribución de cargas: Facilita la distribución de cargas de
> trabajo entre nodos, mejorando el rendimiento global del sistema.

En este caso, la comunicación entre nodos en un sistema de memoria
distribuida implica la serialización, transmisión y deserialización de
datos a través de una red de interconexión, permitiendo la colaboración
eﬁciente entre nodos y la escalabilidad del sistema.

> **●** **Explica** **las** **técnicas** **comunes** **para**
> **optimizar** **la** **comunicación** **en** **sistemas** **de**
> **memoria** **distribuida.**

En sistemas de memoria distribuida, optimizar la comunicación entre
nodos es crucial para mejorar el rendimiento y la eﬁciencia. Aquí se
describen algunas técnicas comunes:

> 1\. Agrupamiento de mensajes (Message Aggregation):
>
> ● Combina múltiples mensajes pequeños en un mensaje más grande para
> reducir la sobrecarga de la comunicación.
>
> ● Minimiza el número de envíos y recibos, disminuyendo el tiempo total
> de comunicación.
>
> 2\. Comunicación asincrónica:
>
> ● Permite que los nodos continúen procesando otras tareas mientras
> esperan que los datos se transmitan.
>
> ● Reduce el tiempo de espera ocioso y mejora la utilización de
> recursos. 3. RDMA (Remote Direct Memory Access):
>
> ● Permite el acceso directo a la memoria de otro nodo sin involucrar
> al procesador del nodo remoto.
>
> ● Aumenta la velocidad de transferencia y reduce la latencia, ya que
> se evita la sobrecarga del sistema operativo.
>
> 4\. Compresión de datos:
>
> ● Comprime los datos antes de enviarlos y los descomprime al
> recibirlos.
>
> ● Disminuye el volumen de datos transmitidos, reduciendo el tiempo de
> transferencia y el uso de ancho de banda.
>
> 5\. Uso de topologías eﬁcientes:
>
> ● Implementa topologías de red optimizadas, como topologías de malla o
> hipercubo, que minimizan la latencia y maximizan el ancho de banda.
>
> ● Reduce la cantidad de saltos necesarios para la transmisión de datos
> entre nodos.
>
> 6\. Algoritmos de balanceo de carga:
>
> ● Distribuye equitativamente las tareas entre los nodos para evitar
> sobrecargas en nodos especíﬁcos.
>
> ● Optimiza el uso de recursos y mejora el rendimiento global del
> sistema. 7. Caching de datos remotos:
>
> ● Almacena en caché los datos frecuentemente accedidos de nodos
> remotos localmente.
>
> ● Reduce la necesidad de comunicaciones repetidas para los mismos
> datos, mejorando la velocidad de acceso.
>
> 8\. Protocolo de comunicación eﬁciente:
>
> ● Utiliza protocolos de comunicación diseñados para reducir la
> latencia y aumentar el rendimiento, como MPI (Message Passing
> Interface) optimizado.
>
> ● Mejora la eﬁciencia de las comunicaciones inter-nodo mediante
> optimizaciones especíﬁcas del protocolo.

Es decir, las técnicas comunes para optimizar la comunicación en
sistemas de memoria distribuida incluyen la agrupación de mensajes, la
comunicación asincrónica, el uso de RDMA, la compresión de datos,
topologías de red eﬁcientes, algoritmos de balanceo de carga, el caching
de datos remotos y el uso de protocolos de comunicación eﬁcientes. Estas
técnicas ayudan a reducir la latencia, mejorar el rendimiento y aumentar
la eﬁciencia global del sistema.

> **●** **Discute** **los** **desafíos** **de** **programación** **en**
> **sistemas** **de** **memoria** **distribuida.**

La programación en sistemas de memoria distribuida presenta una serie de
desafíos que los desarrolladores deben enfrentar para crear aplicaciones
eﬁcientes y robustas. Algunos de estos desafíos incluyen:

> 1\. Gestión explícita de la comunicación: Los desarrolladores deben
> manejar explícitamente la comunicación entre nodos, incluida la
> serialización y deserialización de datos, así como la coordinación de
> la transferencia de datos entre nodos.
>
> 2\. Sincronización y coherencia de datos: La sincronización de
> operaciones entre nodos y la garantía de la coherencia de los datos
> distribuidos pueden ser complejas y propensas a errores. Los
> desarrolladores deben implementar
>
> mecanismos de sincronización adecuados para evitar condiciones de
> carrera y garantizar la integridad de los datos.
>
> 3\. Detección y manejo de fallas: Los sistemas distribuidos pueden ser
> propensos a fallas de red, nodos caídos o fallos de comunicación. Los
> desarrolladores deben implementar estrategias de detección de fallas y
> mecanismos de recuperación para mantener la disponibilidad y la
> consistencia de las aplicaciones.
>
> 4\. Desarrollo de algoritmos distribuidos: La creación de algoritmos
> eﬁcientes y escalables para operar en un entorno distribuido puede ser
> desaﬁante debido a la necesidad de coordinar el procesamiento entre
> múltiples nodos y minimizar la sobrecarga de comunicación.
>
> 5\. Depuración y pruebas: La depuración de aplicaciones distribuidas
> puede ser más compleja que en sistemas centralizados debido a la
> naturaleza distribuida de los errores y la necesidad de comprender el
> comportamiento del sistema en un entorno distribuido.
>
> 6\. Rendimiento y escalabilidad: Optimizar el rendimiento y la
> escalabilidad de las aplicaciones distribuidas puede requerir un
> análisis cuidadoso del tráﬁco de red, el equilibrio de carga entre
> nodos y la optimización de algoritmos para minimizar la comunicación
> entre nodos.

En resumen, la programación en sistemas de memoria distribuida presenta
desafíos únicos relacionados con la gestión de la comunicación, la
sincronización de datos, la detección de fallas, el desarrollo de
algoritmos distribuidos, la depuración y pruebas, así como la
optimización del rendimiento y la escalabilidad. Los desarrolladores
deben abordar estos desafíos de manera efectiva para crear aplicaciones
distribuidas robustas y eﬁcientes.

> **●** **Deﬁne** **qué** **es** **una** **arquitectura** **de**
> **memoria** **híbrida** **y** **da** **ejemplos** **de** **sistemas**
> **que** **la** **utilizan.**

Una arquitectura de memoria híbrida es un diseño que combina
características de la memoria compartida y la memoria distribuida en un
sistema. En este enfoque, los recursos de memoria se distribuyen entre
múltiples nodos, pero algunos de estos nodos pueden compartir ciertas
porciones de memoria, mientras que otras áreas permanecen distribuidas.

En una arquitectura híbrida, algunos nodos pueden acceder a la memoria
compartida para mejorar la coherencia de datos y reducir la latencia en
operaciones que requieren alta comunicación entre nodos, mientras que
otros nodos pueden mantener su propia memoria local para maximizar el
rendimiento local y la escalabilidad.

Ejemplos de sistemas que utilizan arquitecturas de memoria híbrida
incluyen:

> 1\. Clústeres de computación de alto rendimiento (HPC): Algunos
> clústeres HPC utilizan una combinación de nodos con memoria compartida
> y nodos con memoria distribuida para satisfacer las demandas de
> aplicaciones que requieren tanto alta comunicación entre nodos como
> rendimiento local.
>
> 2\. Supercomputadoras: Algunas supercomputadoras adoptan arquitecturas
> híbridas para equilibrar la comunicación entre nodos y el rendimiento
> local, optimizando así el rendimiento general de la aplicación.
>
> 3\. Sistemas de análisis de datos distribuidos: En entornos de
> análisis de datos distribuidos, como Apache Hadoop o Apache Spark, se
> pueden utilizar arquitecturas de memoria híbrida para equilibrar el
> procesamiento distribuido de grandes conjuntos de datos con la
> necesidad de compartir datos entre nodos para tareas de análisis
> complejas.

Por tanto, una arquitectura de memoria híbrida combina elementos de la
memoria compartida y la memoria distribuida para optimizar el
rendimiento y la escalabilidad en sistemas que requieren una combinación
de comunicación entre nodos y procesamiento local.

> **●** **Explica** **cómo** **se** **puede** **combinar** **MPI** **y**
> **OpenMP** **en** **una** **arquitectura** **híbrida** **para**
> **mejorar** **el** **rendimiento.**

En una arquitectura híbrida, MPI y OpenMP se pueden combinar para
aprovechar

tanto el paralelismo a nivel de nodo como la comunicación entre nodos,
mejorando

así el rendimiento en sistemas distribuidos con nodos de memoria
compartida.

> 1\. Paralelismo a nivel de nodo con OpenMP:
>
> ● OpenMP permite la creación de hilos dentro de un nodo de memoria
>
> compartida, aprovechando los múltiples núcleos de la CPU para
>
> ejecutar tareas en paralelo.
>
> ● Los hilos pueden acceder eﬁcientemente a la memoria compartida del
>
> nodo, lo que minimiza la latencia en el acceso a los datos locales y
>
> optimiza el rendimiento.
>
> 2\. Comunicación entre nodos con MPI:
>
> ● MPI se utiliza para la comunicación entre nodos en un sistema
>
> distribuido, permitiendo que los procesos en diferentes nodos
>
> intercambien datos y coordinen su trabajo.
>
> ● MPI facilita la distribución de tareas entre nodos y la
> sincronización de
>
> operaciones, lo que es esencial para aplicaciones que requieren
>
> colaboración entre múltiples nodos.
>
> 3\. Coordinación entre OpenMP y MPI:
>
> ● Los nodos pueden dividir su carga de trabajo en tareas
> paralelizables
>
> utilizando OpenMP para ejecutar múltiples hilos en cada nodo.
>
> ● Luego, utilizando MPI, los nodos pueden comunicarse entre sí para
>
> intercambiar datos y coordinar el procesamiento de tareas entre
>
> nodos, aprovechando la eﬁciencia del paralelismo a nivel de nodo y la
>
> comunicación entre nodos.
>
> 4\. Optimización del rendimiento y escalabilidad:
>
> ● La combinación de MPI y OpenMP permite un mejor balance de carga
>
> entre los nodos y una mayor escalabilidad, ya que cada nodo puede
>
> paralelizar eﬁcientemente su carga de trabajo utilizando OpenMP,
>
> mientras que MPI coordina la comunicación y la sincronización entre
>
> los nodos para trabajar en conjunto de manera eﬁciente.

En resumen, la combinación de MPI y OpenMP en una arquitectura híbrida
permite

aprovechar el paralelismo a nivel de nodo con OpenMP y la comunicación
entre

nodos con MPI, mejorando así el rendimiento y la escalabilidad en
sistemas

distribuidos con nodos de memoria compartida.

> **●** **Discute** **las** **consideraciones** **de** **diseño** **al**
> **desarrollar** **aplicaciones** **para** **arquitecturas**
> **híbridas.**

Al desarrollar aplicaciones para arquitecturas híbridas que combinan MPI
y OpenMP, es importante tener en cuenta varias consideraciones de
diseño:

> 1\. Granularidad del paralelismo:
>
> ● Es fundamental seleccionar el nivel adecuado de granularidad para el
> paralelismo tanto a nivel de nodo (utilizando OpenMP) como entre nodos
> (utilizando MPI).
>
> ● La granularidad demasiado ﬁna puede aumentar la sobrecarga de
> comunicación entre nodos, mientras que la granularidad demasiado
> gruesa puede subutilizar los recursos disponibles.
>
> 2\. Balance de carga:
>
> ● Se debe garantizar un equilibrio de carga adecuado entre los hilos
> OpenMP en cada nodo y entre los diferentes nodos en el clúster.
>
> ● La distribución desigual de la carga de trabajo puede generar
> cuellos de botella y reducir el rendimiento global de la aplicación.
>
> 3\. Minimización de la comunicación entre nodos:
>
> ● Es importante minimizar la cantidad de comunicación entre nodos para
> reducir la sobrecarga de red y optimizar el rendimiento.
>
> ● Se deben utilizar algoritmos y técnicas que minimicen la necesidad
> de intercambiar datos entre nodos siempre que sea posible.
>
> 4\. Sincronización y barreras de comunicación:
>
> ● Se deben utilizar de manera eﬁciente las funciones de sincronización
> y barreras tanto en OpenMP como en MPI para garantizar que los nodos y
> los hilos cooperen de manera sincronizada en la ejecución de tareas.
>
> ● La sincronización excesiva puede generar bloqueos y reducir la
> escalabilidad, por lo que se debe minimizar su uso cuando no sea
> necesario.
>
> 5\. Optimización del rendimiento:
>
> ● Se deben aplicar técnicas de optimización de rendimiento, como la
> localidad de datos, la reducción de la sobrecarga de comunicación y la
> minimización de la sincronización, para maximizar la eﬁciencia del
> sistema híbrido.
>
> ● Se puede considerar el uso de herramientas de análisis de
> rendimiento para identiﬁcar cuellos de botella y áreas de mejora en la
> aplicación.

Es decir, al desarrollar aplicaciones para arquitecturas híbridas, es
esencial considerar la granularidad del paralelismo, el equilibrio de
carga, la minimización de la comunicación entre nodos, la sincronización
y las barreras de comunicación, así como la optimización del rendimiento
para garantizar un rendimiento óptimo y una escalabilidad eﬁciente.

> **1** **.** **Escribe** **un** **programa** **en** **Python** **que**
> **use** **la** **librería** **multiprocessing** **para** **simular**
>
> **múltiples** **procesos** **accediendo** **y** **modiﬁcando** **una**
> **variable** **compartida.** **Usa** **un**
>
> **Manager** **para** **manejar** **el** **acceso** **seguro** **a**
> **la** **variable** **compartida.**
>
> \[ \]
>
> from multiprocessing import Process, Manager
>
> def increment(shared_dict, key):
>
> for \_ in range(1000):
>
> shared_dict\[key\] += 1
>
> if \_\_name\_\_ == "\_\_main\_\_":
>
> manager = Manager()
>
> shared_dict = manager.dict()
>
> shared_dict\["counter"\] = 0
>
> processes = \[\]
>
> for \_ in range(4):
>
> p = Process(target=increment, args=(shared_dict, "counter"))
>
> processes.append(p)
>
> p.start()
>
> for p in processes:
>
> p.join()
>
> print(f"Final counter value: {shared_dict\['counter'\]}")

2 . Usa la librería mpi4py para simular la comunicación entre nodos en
un sistema

de memoria distribuida. Crea un programa que envíe y reciba mensajes
entre

múltiples procesos.

\[ \]

> from mpi4py import MPI
>
> comm = MPI.COMM_WORLD
>
> rank = comm.Get_rank()
>
> size = comm.Get_size()
>
> if rank == 0:
>
> data = "Hello from rank 0"
>
> for i in range(1, size):
>
> comm.send(data, dest=i)
>
> else:
>
> data = comm.recv(source=0)
>
> print(f"Rank {rank} received data: {data}")

3 . Combina MPI y OpenMP en un programa Python utilizando mpi4py y
threading.

Simula una tarea que se distribuye entre nodos y luego se paraleliza
dentro de cada

nodo.

\[ \]

> from mpi4py import MPI
>
> from threading import Thread
>
> def thread_task(rank):
>
> print(f"Thread in rank {rank} is running")
>
> comm = MPI.COMM_WORLD
>
> rank = comm.Get_rank()
>
> size = comm.Get_size()
>
> threads = \[\]
>
> for \_ in range(4):
>
> t = Thread(target=thread_task, args=(rank,))
>
> threads.append(t)
>
> t.start()
>
> for t in threads:
>
> t.join()
>
> if rank == 0:
>
> print("All threads completed.")

4 . Escribe un programa en C que use pthread para crear múltiples hilos
que

accedan y modiﬁquen una variable global compartida de manera segura
usando

mutex.

\[ \]

> \#include \<pthread.h\>
>
> \#include \<stdio.h\>
>
> int counter = 0;
>
> pthread_mutex_t lock;
>
> void\* increment(void\* arg) {
>
> for (int i = 0; i \< 1000; i++) {
>
> pthread_mutex_lock(&lock);
>
> counter++;
>
> pthread_mutex_unlock(&lock);
>
> }
>
> return NULL;

}

int main() {

> pthread_t threads\[4\];
>
> pthread_mutex_init(&lock, NULL);
>
> for (int i = 0; i \< 4; i++) {
>
> pthread_create(&threads\[i\], NULL, increment, NULL);
>
> }
>
> for (int i = 0; i \< 4; i++) {
>
> pthread_join(threads\[i\], NULL);
>
> }
>
> pthread_mutex_destroy(&lock);
>
> printf("Final counter value: %d\n", counter);
>
> return 0;

}

5 . Usa MPI en C para crear un programa que envíe y reciba mensajes
entre

múltiples procesos.

\[ \]

> \#include \<mpi.h\>
>
> \#include \<stdio.h\>
>
> int main(int argc, char\*\* argv) {
>
> MPI_Init(&argc, &argv);
>
> int rank, size;
>
> MPI_Comm_rank(MPI_COMM_WORLD, &rank);
>
> MPI_Comm_size(MPI_COMM_WORLD, &size);
>
> if (rank == 0) {
>
> char message\[\] = "Hello from rank 0";
>
> for (int i = 1; i \< size; i++) {
>
> MPI_Send(message, sizeof(message), MPI_CHAR, i, 0, MPI_COMM_WORLD);
>
> }
>
> } else {
>
> char message\[20\];
>
> MPI_Recv(message, 20, MPI_CHAR, 0, 0, MPI_COMM_WORLD,
> MPI_STATUS_IGNORE);
>
> printf("Rank %d received message: %s\n", rank, message);
>
> }
>
> MPI_Finalize();
>
> return 0;
>
> }

6 . Escribe un programa en Python que use multiprocessing.Pool para
sumar los

elementos de una lista en paralelo. Divide la lista en partes iguales y
asigna cada

parte a un proceso.

\[ \]

> from multiprocessing import Pool
>
> def sum_segment(segment):
>
> return sum(segment)
>
> if \_\_name\_\_ == "\_\_main\_\_":
>
> data = list(range(1000000)) \# Lista de un millón de elementos
>
> num_processes = 4
>
> segment_size = len(data) // num_processes
>
> segments = \[data\[i \* segment_size:(i + 1) \* segment_size\] for i
> in range(num_processes)\]
>
> with Pool(num_processes) as pool:
>
> results = pool.map(sum_segment, segments)
>
> total_sum = sum(results)
>
> print(f"Total sum: {total_sum}")

7 . Implementa un patrón productor-consumidor usando
multiprocessing.Queue en

Python. Crea varios procesos productores que pongan datos en la cola y
varios

procesos consumidores que lean y procesen esos datos.

\[ \]

> from multiprocessing import Process, Queue
>
> import time
>
> import random
>
> def producer(queue):
>
> for \_ in range(10):
>
> item = random.randint(1, 100)
>
> queue.put(item)
>
> print(f"Produced {item}")
>
> time.sleep(random.random())
>
> def consumer(queue):
>
> while True:
>
> item = queue.get()
>
> if item is None: \# Sentinel value to indicate end of processing
>
> break
>
> print(f"Consumed {item}")
>
> time.sleep(random.random())

if \_\_name\_\_ == "\_\_main\_\_":

> queue = Queue()
>
> producers = \[Process(target=producer, args=(queue,)) for \_ in
> range(2)\]
>
> consumers = \[Process(target=consumer, args=(queue,)) for \_ in
> range(2)\]
>
> for p in producers:
>
> p.start()
>
> for c in consumers:
>
> c.start()
>
> for p in producers:
>
> p.join()
>
> \# Add sentinel values to the queue to signal consumers to exit
>
> for \_ in consumers:
>
> queue.put(None)
>
> for c in consumers:
>
> c.join()

8 . Usa mpi4py para implementar un broadcast donde un proceso envía
datos a

todos los demás procesos en el comunicador.

\[ \]

> from mpi4py import MPI
>
> comm = MPI.COMM_WORLD
>
> rank = comm.Get_rank()
>
> if rank == 0:
>
> data = {'key1': 'value1', 'key2': 'value2'}
>
> else:
>
> data = None
>
> data = comm.bcast(data, root=0)
>
> print(f"Rank {rank} received data: {data}")

9 . Implementa una reducción (reduce) con mpi4py para sumar números

distribuidos entre varios procesos.

\[ \]

> from mpi4py import MPI
>
> comm = MPI.COMM_WORLD
>
> rank = comm.Get_rank()
>
> \# Cada proceso tiene un número diferente
>
> number = rank + 1
>
> total_sum = comm.reduce(number, op=MPI.SUM, root=0)
>
> if rank == 0:
>
> print(f"Total sum: {total_sum}")

10 . Combina MPI y threading para distribuir una lista de datos entre
nodos y luego

procesarla en paralelo dentro de cada nodo.

\[ \]

> from mpi4py import MPI
>
> from threading import Thread

def process_data(data_segment):

> result = \[x \*\* 2 for x in data_segment\]
>
> print(f"Processed segment: {result}")

comm = MPI.COMM_WORLD

rank = comm.Get_rank()

size = comm.Get_size()

data = None

if rank == 0:

> data = list(range(100))
>
> segment_size = len(data) // size
>
> data_segments = \[data\[i \* segment_size:(i + 1) \* segment_size\]
> for i in range(size)\]

else:

> data_segments = None

data_segment = comm.scatter(data_segments, root=0)

threads = \[\]

for i in range(4):

> t = Thread(target=process_data, args=(data_segment\[i::4\],))
>
> threads.append(t)
>
> t.start()
>
> for t in threads:
>
> t.join()
>
> comm.Barrier()
>
> if rank == 0:
>
> print("All data processed.")

11 . Usa MPI para recolectar y combinar los resultados de datos
procesados en

paralelo utilizando OpenMP en cada nodo.

\[ \]

> from mpi4py import MPI
>
> from threading import Thread
>
> def compute_square(value, result_list, index):
>
> result_list\[index\] = value \*\* 2
>
> comm = MPI.COMM_WORLD
>
> rank = comm.Get_rank()
>
> size = comm.Get_size()

data = None

if rank == 0:

> data = list(range(1, 101))
>
> segment_size = len(data) // size
>
> data_segments = \[data\[i \* segment_size:(i + 1) \* segment_size\]
> for i in range(size)\]

else:

> data_segments = None

data_segment = comm.scatter(data_segments, root=0)

results = \[0\] \* len(data_segment)

threads = \[\]

for i in range(len(data_segment)):

> t = Thread(target=compute_square, args=(data_segment\[i\], results,
> i))
>
> threads.append(t)
>
> t.start()

for t in threads:

> t.join()

gathered_results = comm.gather(results, root=0)

> if rank == 0:
>
> ﬁnal_results = \[item for sublist in gathered_results for item in
> sublist\]
>
> print(f"Final results: {ﬁnal_results}")

\[ \]

> \### Tus respuestas

Multiprocesadores

Los multiprocesadores son sistemas que utilizan múltiples CPUs en un
solo sistema

de memoria compartida. Estas CPUs pueden estar en un solo chip
(multinúcleo) o

en varios chips (multiprocesador). Los multiprocesadores pueden mejorar

signiﬁcativamente el rendimiento de las aplicaciones mediante el
paralelismo a nivel

de tarea o de hilo.

Tipos de multiprocesadores

> ● Sistemas simétricos de multiprocesamiento (SMP): En SMP, todos los
> procesadores son iguales y comparten la memoria principal de manera
> equitativa. Cada procesador tiene acceso directo a toda la memoria y a
> los dispositivos de E/S. Los sistemas SMP son ideales para
> aplicaciones que requieren alta interactividad entre procesos.
>
> ● Sistemas asimétricos de multiprocesamiento (AMP): En AMP, los
> procesadores no son iguales. Un procesador principal controla el
> sistema y asigna tareas a los procesadores secundarios. Este modelo es
> menos común y se utiliza en sistemas embebidos o en aplicaciones
> especíﬁcas.

Ventajas de los Multiprocesadores

> ● Mejoran el rendimiento general al ejecutar múltiples tareas
> simultáneamente. ● Simpliﬁcan la programación comparado con sistemas
> de memoria
>
> distribuida.
>
> ● Buena escalabilidad en sistemas NUMA.

Multicomputadores

Los multicomputadores, también conocidos como sistemas de memoria
distribuida,

consisten en múltiples nodos de computación, cada uno con su propia CPU
y

memoria, interconectados por una red de alta velocidad. Estos sistemas
son

altamente escalables y se utilizan en aplicaciones que requieren un gran
poder de

cómputo, como simulaciones cientíﬁcas y análisis de big data.

Ventajas de los multicomputadores

> ● Alta escalabilidad debido a la naturaleza independiente de los
> nodos.
>
> ● Mayor tolerancia a fallos, ya que la falla de un nodo no afecta a
> los demás.

Desventajas de los multicomputadores

> ● Programación compleja debido a la necesidad de gestionar la
> comunicación entre nodos.
>
> ● Latencias de comunicación más altas comparadas con sistemas de
> memoria compartida.

Clústeres

Los clústeres son un tipo de arquitectura de multicomputador donde
varios

sistemas completos (nodos) están conectados a través de una red para
trabajar

juntos como un solo sistema. Los clústeres pueden ser homogéneos (todos
los

nodos son iguales) o heterogéneos (nodos con diferentes capacidades).

Tipos de clústeres

> ● Clústeres de alto rendimiento (HPC): Diseñados para maximizar el
> rendimiento y son utilizados en simulaciones cientíﬁcas, análisis de
> datos, y otras aplicaciones que requieren gran poder de cómputo.
>
> ● Clústeres de alta disponibilidad (HA): Enfocados en proporcionar
> alta disponibilidad y tolerancia a fallos. Se utilizan en aplicaciones
> críticas donde el tiempo de inactividad debe minimizarse.
>
> ● Clústeres de balanceo de carga: Distribuyen la carga de trabajo
> entre varios nodos para mejorar el rendimiento y la disponibilidad de
> servicios web y aplicaciones empresariales.
>
> Ventajas de los clústeres
>
> ● Alta escalabilidad y ﬂexibilidad.
>
> ● Costo-efectividad al utilizar hardware convencional.
>
> ● Capacidad de combinar recursos de diferentes sistemas para tareas
> especíﬁcas. Desventajas de los Clústeres Complejidad en la
> conﬁguración y gestión. Dependencia de la red para la comunicación
> entre nodos, lo que puede introducir latencias.
>
> Ejercicios
>
> **●** **Explica** **las** **diferencias** **fundamentales** **entre**
> **un** **multiprocesador** **y** **un** **multicomputador** **en**
> **términos** **de** **arquitectura,** **comunicación** **entre**
> **procesadores** **y** **aplicaciones** **típicas.**

En términos técnicos, un multiprocesador se reﬁere a un sistema en el
cual múltiples unidades de procesamiento comparten recursos físicos,
como memoria y dispositivos de entrada/salida, dentro de un único
sistema computacional. Por otro lado, un multicomputador es un sistema
compuesto por múltiples computadoras independientes conectadas a través
de una red de comunicación.

Las diferencias fundamentales entre ambos sistemas radican en:

> 1\. Arquitectura:
>
> ● Multiprocesador: Los procesadores comparten un espacio de memoria
> común y están interconectados a través de un bus de comunicación o un
> sistema de interconexión de alta velocidad.
>
> ● Multicomputador: Cada computadora tiene su propia memoria y
> recursos, y están conectadas a través de una red de comunicación, como
> Ethernet o InﬁniBand.
>
> 2\. Comunicación entre procesadores:
>
> ● Multiprocesador: La comunicación entre procesadores se realiza a
> través de la memoria compartida o mediante interrupciones de hardware.
>
> ● Multicomputador: La comunicación entre computadoras se lleva a cabo
> mediante el intercambio de mensajes a través de la red de
> comunicación.
>
> 3\. Aplicaciones típicas:
>
> ● Multiprocesador: Se utiliza principalmente para aplicaciones que
> requieren un alto grado de paralelismo y coordinación entre
>
> procesadores, como bases de datos de alto rendimiento, servidores web
> y sistemas de computación cientíﬁca.
>
> ● Multicomputador: Se emplea en aplicaciones distribuidas donde cada
> computadora puede trabajar de manera independiente en diferentes
> tareas, como la computación distribuida, la simulación de redes y el
> procesamiento de grandes volúmenes de datos.

Es decir, mientras que un multiprocesador centraliza recursos y requiere
una alta coordinación entre los procesadores, un multicomputador
distribuye recursos entre computadoras independientes que se comunican a
través de una red, lo que permite una mayor escalabilidad y ﬂexibilidad
en aplicaciones distribuidas.

> **●** **Discute** **los** **diferentes** **modelos** **de**
> **consistencia** **de** **memoria** **en** **sistemas** **de**
> **multiprocesadores.** **Compara** **y** **contrasta** **la**
> **consistencia** **secuencial,** **la** **consistencia** **causal**
> **y** **la** **consistencia** **eventual,** **proporcionando**
> **ejemplos** **de** **situaciones** **en** **las** **que** **cada**
> **uno** **podría** **ser** **adecuado.**

En sistemas de multiprocesadores, los modelos de consistencia de memoria
deﬁnen cómo los diferentes procesadores ven y acceden a los datos
compartidos en la memoria compartida. Aquí hay una breve discusión sobre
tres modelos comunes:

> 1\. Consistencia Secuencial:
>
> ● En este modelo, las operaciones de escritura y lectura se ven en el
> mismo orden por todos los procesadores.
>
> ● Cada operación se completa antes de que comience la siguiente
> operación.
>
> ● Ejemplo: En un sistema bancario en línea, donde es crucial que todas
> las transacciones se vean en el mismo orden para evitar
> inconsistencias en los saldos de las cuentas.
>
> 2\. Consistencia Causal:
>
> ● Este modelo garantiza que todas las operaciones que están
> relacionadas causalmente se vean en el mismo orden por todos los
> procesadores.
>
> ● No requiere que todas las operaciones se vean en el mismo orden.
>
> ● Ejemplo: En una aplicación de mensajería en línea, donde los
> mensajes enviados deben ser vistos en el mismo orden por todos los
> destinatarios, pero los mensajes de diferentes conversaciones pueden
> aparecer en orden diferente para diferentes usuarios.
>
> 3\. Consistencia Eventual:
>
> ● En este modelo, no hay garantía sobre el orden en el que las
> operaciones se ven entre diferentes procesadores, pero eventualmente
> todas las vistas convergen a un estado consistente.
>
> ● Puede haber brechas de tiempo durante las cuales los procesadores
> ven diferentes estados.
>
> ● Ejemplo: En una red social donde la secuencia exacta en la que se
> ven las actualizaciones de estado de los amigos no es crítica, siempre
> que eventualmente todos los usuarios vean el mismo conjunto de
> actualizaciones.

Por lo tanto, la consistencia secuencial asegura un orden estricto para
todas las operaciones, la consistencia causal garantiza un orden
relacionado con la causalidad, mientras que la consistencia eventual
permite que las vistas sean diferentes en diferentes momentos, siempre
que eventualmente converjan a un estado consistente. La elección del
modelo depende de las necesidades especíﬁcas de la aplicación y el
equilibrio entre la coherencia y el rendimiento.

> **●** **Deﬁne** **el** **problema** **de** **coherencia** **de**
> **caché** **en** **sistemas** **multiprocesadores** **y** **describe**
> **al** **menos** **dos** **protocolos** **de** **coherencia** **de**
> **caché** **(como** **MESI** **y** **MOESI).** **Explica** **cómo**
> **estos** **protocolos** **ayudan** **a** **mantener** **la**
> **coherencia** **y** **los** **posibles** **problemas** **de**
> **rendimiento** **asociados.** **Paralelismo** **a** **Nivel** **de**
> **Instrucción** **(ILP)**

El problema de coherencia de caché en sistemas multiprocesadores se
reﬁere a la necesidad de garantizar que los datos almacenados en las
cachés de los diferentes procesadores estén actualizados y sean
consistentes entre sí. Dos protocolos comunes para abordar este problema
son MESI (Modiﬁed, Exclusive, Shared, Invalid) y MOESI (Modiﬁed, Owned,
Exclusive, Shared, Invalid).

El protocolo MESI deﬁne cuatro estados posibles para un bloque de caché:
Modiﬁcado, Exclusivo, Compartido e Inválido. Mientras tanto, el
protocolo MOESI añade un estado adicional llamado Propiedad. Estos
protocolos ayudan a mantener la coherencia de caché mediante la
actualización de los estados de los bloques de caché y el uso de señales
de control para coordinar las operaciones de lectura y escritura entre
las cachés.

Sin embargo, estos protocolos pueden introducir problemas de rendimiento
debido a la sobrecarga de tráﬁco de caché y la latencia asociada con las
operaciones de invalidación y actualización de caché. Además, una
implementación ineﬁciente puede limitar el paralelismo a nivel de
instrucción al introducir retardos en la

ejecución de instrucciones debido a conﬂictos de caché y esperas por la
coherencia de caché. Es esencial optimizar el diseño y la gestión de
estos protocolos para minimizar los impactos negativos en el
rendimiento.

> ● Describe el concepto de paralelismo a nivel de instrucción (ILP) y
> cómo los multiprocesadores pueden explotarlo. Discute técnicas como la
> ejecución fuera de orden y la predicción de saltos, y cómo estas
> técnicas afectan el rendimiento.

El paralelismo a nivel de instrucción (ILP) es la capacidad de ejecutar
múltiples instrucciones de manera simultánea en un procesador. Los
multiprocesadores pueden aprovechar el ILP mediante técnicas como la
ejecución fuera de orden y la predicción de saltos.

> 1\. Ejecución fuera de orden:
>
> ● En esta técnica, el procesador reorganiza dinámicamente las
> instrucciones para ejecutarlas en un orden diferente al especiﬁcado en
> el programa.
>
> ● Esto se logra mediante el uso de buffers de instrucciones y unidades
> de ejecución especulativa que permiten ejecutar instrucciones
> independientes mientras se esperan resultados de instrucciones
> anteriores.
>
> ● La ejecución fuera de orden puede mejorar signiﬁcativamente el
> rendimiento al permitir que el procesador utilice eﬁcazmente los
> recursos de hardware disponibles.
>
> 2\. Predicción de saltos:
>
> ● Los saltos condicionales en el código pueden diﬁcultar la predicción
> del ﬂujo de ejecución del programa.
>
> ● Los procesadores utilizan técnicas de predicción de saltos para
> predecir la dirección del ﬂujo de ejecución y especular sobre la
> ejecución de instrucciones futuras.
>
> ● Si la predicción es correcta, se pueden cargar y ejecutar
> instrucciones en paralelo con el ﬂujo de ejecución especulado, lo que
> aumenta el ILP y mejora el rendimiento.
>
> ● Sin embargo, las predicciones incorrectas pueden llevar a la
> ejecución de instrucciones innecesarias, lo que resulta en una pérdida
> de rendimiento debido a la necesidad de deshacer y rehacer las
> operaciones incorrectas.

Es decir, el paralelismo a nivel de instrucción (ILP) permite a los
multiprocesadores ejecutar múltiples instrucciones simultáneamente para
mejorar el rendimiento. Técnicas como la ejecución fuera de orden y la
predicción de saltos son fundamentales para explotar el ILP, aunque su
efectividad puede verse afectada por la complejidad del código y la
precisión de las predicciones.

> ● Describe las diferentes topologías de red utilizadas en
> multicomputadores (como malla, hipercubo, anillo y estrella). Analiza
> las ventajas y desventajas de cada topología en términos de latencia,
> ancho de banda y tolerancia a fallos.

Las topologías de red en multicomputadores se reﬁeren a cómo están
conectadas físicamente las diferentes unidades de procesamiento. Aquí
están algunas de las topologías comunes:

> 1\. Malla:
>
> ● En una topología de malla, cada nodo está conectado directamente a
> varios de sus vecinos más cercanos.
>
> ● Ventajas: Proporciona una alta redundancia de ruta y es escalable,
> ya que agregar más nodos es relativamente fácil.
>
> ● Desventajas: Puede haber una alta latencia debido a múltiples saltos
> entre nodos, y el ancho de banda puede verse afectado por cuellos de
> botella en los enlaces entre nodos.
>
> 2\. Hipercubo:
>
> ● En una topología de hipercubo, cada nodo está conectado a un número
> ﬁjo de otros nodos, formando una estructura en forma de cubo.
>
> ● Ventajas: Proporciona una latencia baja y un alto grado de
> conectividad, lo que facilita la comunicación entre nodos.
>
> ● Desventajas: Requiere una gran cantidad de enlaces físicos, lo que
> puede hacer que sea costoso de implementar, y la complejidad aumenta
> con el tamaño del hipercubo.
>
> 3\. Anillo:
>
> ● En una topología de anillo, cada nodo está conectado directamente a
> dos nodos vecinos, formando un bucle cerrado.
>
> ● Ventajas: La latencia es baja ya que cada nodo solo tiene que pasar
> por un máximo de dos nodos para comunicarse con cualquier otro nodo en
> el anillo.
>
> ● Desventajas: La capacidad de expansión está limitada ya que agregar
> nodos adicionales puede requerir la reconﬁguración de la topología, y
> la tolerancia a fallos es baja ya que la falla de un nodo puede
> interrumpir la comunicación en todo el anillo.
>
> 4\. Estrella:
>
> ● En una topología de estrella, todos los nodos están conectados a un
> nodo central, formando una estructura en forma de estrella.
>
> ● Ventajas: La latencia es baja ya que todas las comunicaciones pasan
> a través del nodo central, y es fácil de administrar y expandir.
>
> ● Desventajas: La tolerancia a fallos es baja ya que la falla del nodo
> central puede dejar inaccesibles a todos los demás nodos, y el ancho
> de banda puede ser limitado por la capacidad de enlace del nodo
> central.

Por lo tanto, cada topología de red en multicomputadores tiene sus
propias ventajas y desventajas en términos de latencia, ancho de banda y
tolerancia a fallos. La elección de una topología especíﬁca dependerá de
los requisitos de la aplicación y las consideraciones de costos y
escalabilidad.

> **●** **Compara** **y** **contrasta** **los** **protocolos** **de**
> **comunicación** **punto** **a** **punto** **y** **basados** **en**
> **mensajes** **en** **multicomputadores.** **Proporciona**
> **ejemplos** **de** **situaciones** **en** **las** **que** **uno**
> **podría** **ser** **más** **adecuado** **que** **el** **otro.**

Los protocolos de comunicación en multicomputadores pueden ser punto a
punto o basados en mensajes. Aquí hay una comparación y contraste entre
ambos:

> 1\. Comunicación punto a punto:
>
> ● En este enfoque, cada nodo está directamente conectado a uno o más
> nodos especíﬁcos para la comunicación.
>
> ● La comunicación se establece mediante operaciones de lectura y
> escritura en las direcciones de memoria de los nodos conectados.
>
> ● Ventajas: Es eﬁciente para comunicaciones rápidas y predecibles
> entre nodos especíﬁcos sin sobrecarga adicional de administración de
> mensajes.
>
> ● Desventajas: Puede ser menos ﬂexible y escalable, especialmente
> cuando se necesitan comunicaciones entre un gran número de nodos.
>
> 2\. Comunicación basada en mensajes:
>
> ● En este enfoque, los nodos se comunican enviando y recibiendo
> mensajes a través de una red de comunicación compartida.
>
> ● Los mensajes contienen información sobre el remitente, el
> destinatario y los datos a transmitir.
>
> ● Ventajas: Ofrece mayor ﬂexibilidad y escalabilidad, ya que cualquier
> nodo puede comunicarse con cualquier otro nodo en la red sin
> restricciones de conexión ﬁja.
>
> ● Desventajas: Puede introducir sobrecarga adicional debido al
> encapsulamiento y enrutamiento de mensajes, lo que puede aumentar la
> latencia y reducir el rendimiento en comparación con la comunicación
> punto a punto en casos especíﬁcos.

En situaciones donde la comunicación es entre un número limitado de
nodos y requiere baja latencia y alto rendimiento, la comunicación punto
a punto puede ser más adecuada. Por ejemplo, en aplicaciones de
computación de alto rendimiento donde los nodos están sincronizados y
cooperan estrechamente en tareas especíﬁcas.

Por otro lado, en situaciones donde la comunicación es entre un gran
número de nodos y se necesita ﬂexibilidad para la comunicación entre
cualquier par de nodos, la comunicación basada en mensajes puede ser
preferible. Por ejemplo, en aplicaciones distribuidas donde los nodos
necesitan intercambiar datos de manera dinámica y descentralizada, como
en sistemas de almacenamiento distribuido o procesamiento de datos en la
nube.

> **●** **Deﬁne** **el** **concepto** **de** **escalabilidad** **en**
> **el** **contexto** **de** **multicomputadores** **y** **discute**
> **los** **factores** **que** **afectan** **la** **escalabilidad,**
> **como** **la** **latencia** **de** **comunicación,** **el** **ancho**
> **de** **banda** **y** **el** **balance** **de** **carga.**
> **Proporciona** **ejemplos** **de** **cómo** **diseñar** **un**
> **sistema** **multicomputador** **escalable.**

La escalabilidad en el contexto de multicomputadores se reﬁere a la
capacidad del sistema para manejar un aumento en la carga de trabajo o
el número de nodos de manera eﬁciente sin comprometer el rendimiento.
Esto implica que el sistema puede crecer en tamaño o capacidad de
procesamiento sin necesidad de cambios drásticos en su diseño o
arquitectura.

Los factores que afectan la escalabilidad en multicomputadores incluyen:

> 1\. Latencia de comunicación:
>
> ● Una baja latencia de comunicación entre nodos es crucial para la
> escalabilidad, ya que permite una rápida transferencia de datos entre
> los componentes del sistema.
>
> ● Las redes de interconexión de alta velocidad, como InﬁniBand o
> Ethernet de baja latencia, son fundamentales para garantizar una
> comunicación eﬁciente entre los nodos.
>
> 2\. Ancho de banda:
>
> ● Un alto ancho de banda de comunicación es esencial para permitir la
> transferencia rápida de grandes volúmenes de datos entre los nodos.
>
> ● Redes de alta velocidad y con ancho de banda amplio garantizan que
> el sistema pueda escalar adecuadamente para manejar grandes ﬂujos de
> datos.
>
> 3\. Balance de carga:
>
> ● Distribuir uniformemente la carga de trabajo entre los nodos del
> sistema es esencial para una escalabilidad efectiva.
>
> ● Técnicas como el enrutamiento inteligente de mensajes y la
> asignación dinámica de tareas aseguran que ningún nodo se sobrecargue
> mientras otros permanecen inactivos.

Para diseñar un sistema multicomputador escalable, se deben considerar
varios aspectos:

> 1\. Arquitectura modular:
>
> ● Diseñar el sistema de manera modular para permitir la adición o
> eliminación de nodos de manera fácil y eﬁciente.
>
> 2\. Redes de interconexión de alto rendimiento:
>
> ● Emplear redes de interconexión de alta velocidad y baja latencia
> para garantizar una comunicación eﬁciente entre los nodos del sistema.
>
> 3\. Algoritmos de balance de carga eﬁcientes:
>
> ● Implementar algoritmos inteligentes de balance de carga que
> distribuyan uniformemente la carga de trabajo entre los nodos para
> evitar cuellos de botella y maximizar la utilización del sistema.
>
> 4\. Escalado horizontal y vertical:
>
> ● Permitir tanto el escalado horizontal (agregar más nodos) como el
> escalado vertical (aumentar la capacidad de los nodos individuales)
> para adaptarse a diferentes requisitos de carga de trabajo.

En resumen, la escalabilidad en multicomputadores se logra mediante la
optimización de la latencia de comunicación, el ancho de banda y el
balance de carga, junto con el diseño de una arquitectura modular y
ﬂexible que permita la expansión del sistema de manera eﬁciente.

> **●** **Explica** **los** **desafíos** **de** **la**
> **sincronización** **en** **sistemas** **distribuidos** **y**
> **describe** **al** **menos** **dos** **algoritmos** **de**
> **sincronización** **(como** **el** **algoritmo** **de** **Lamport**
> **y** **el** **algoritmo** **de** **Ricart-Agrawala).** **Discute**
> **cómo** **estos** **algoritmos** **aseguran** **la** **exclusión**
> **mutua** **y** **las** **posibles** **desventajas.**

En sistemas distribuidos, la sincronización es un desafío fundamental
debido a la falta de un reloj global y a la posibilidad de que múltiples
procesos compartan recursos concurrentemente. Dos desafíos principales
en la sincronización son la coordinación de eventos entre procesos y la
garantía de exclusión mutua, donde solo un proceso puede acceder a un
recurso compartido en un momento dado.

Dos algoritmos comunes de sincronización en sistemas distribuidos son el
algoritmo de Lamport y el algoritmo de Ricart-Agrawala:

> 1\. Algoritmo de Lamport:
>
> ● Este algoritmo utiliza relojes lógicos para ordenar eventos en un
> sistema distribuido, permitiendo que los procesos coordinen sus
> acciones.
>
> ● Se basa en el concepto de relojes lógicos que asignan marcas de
> tiempo a los eventos, lo que permite establecer un orden parcial entre
> los eventos.
>
> ● Para garantizar la exclusión mutua, Lamport propuso el uso de
> relojes lógicos para determinar el orden de solicitud y liberación de
> recursos compartidos.
>
> 2\. Algoritmo de Ricart-Agrawala:
>
> ● Este algoritmo se utiliza para garantizar la exclusión mutua en
> sistemas distribuidos donde varios procesos compiten por recursos
> compartidos.
>
> ● Cada proceso solicita acceso al recurso compartido enviando una
> solicitud a los demás procesos y espera recibir respuestas de todos
> los demás antes de acceder al recurso.
>
> ● El algoritmo garantiza que solo un proceso pueda acceder al recurso
> compartido a la vez, evitando así posibles conﬂictos.

Ambos algoritmos aseguran la exclusión mutua, pero tienen algunas
desventajas:

> ● Complejidad: Tanto el algoritmo de Lamport como el de
> Ricart-Agrawala pueden ser complejos de implementar y entender,
> especialmente en sistemas distribuidos de gran escala.
>
> ● Latencia: El algoritmo de Ricart-Agrawala puede introducir latencia
> adicional debido a la necesidad de esperar a que todos los demás
> procesos respondan antes de acceder al recurso compartido.
>
> ● Overhead de comunicación: Ambos algoritmos requieren comunicación
> entre los procesos para coordinar las acciones, lo que puede
> introducir un overhead signiﬁcativo en sistemas con alta carga de
> comunicación.

Es decir, los algoritmos de sincronización en sistemas distribuidos,
como el de Lamport y el de Ricart-Agrawala, son fundamentales para
garantizar la coherencia y la exclusión mutua entre los procesos, pero
pueden presentar desafíos en términos de complejidad, latencia y
overhead de comunicación.

> **●** **Describe** **los** **componentes** **clave** **en** **el**
> **diseño** **de** **un** **clúster** **de** **alto** **rendimiento,**
> **incluyendo** **nodos** **de** **computación,** **redes** **de**
> **interconexión,** **almacenamiento** **y** **software** **de**
> **gestión.** **Discute** **las** **decisiones** **de** **diseño**
> **que** **afectan** **el** **rendimiento** **y** **la**
> **escalabilidad** **del** **clúster.** **Modelos** **de**
> **Programación** **para** **Clústeres**

En el diseño de un clúster de alto rendimiento, varios componentes clave
deben considerarse:

> 1\. Nodos de computación:
>
> ● Los nodos de computación son los componentes individuales del
> clúster que realizan el procesamiento de datos.
>
> ● Seleccionar hardware con capacidad de procesamiento y memoria
> adecuada para las cargas de trabajo previstas es crucial para
> garantizar un rendimiento óptimo.
>
> 2\. Redes de interconexión:
>
> ● La red de interconexión conecta los nodos de computación y facilita
> la comunicación entre ellos.
>
> ● La elección de una red de alta velocidad y baja latencia, como
> InﬁniBand o Ethernet de alta velocidad, es esencial para garantizar
> una comunicación eﬁciente entre nodos y minimizar los cuellos de
> botella de red.
>
> 3\. Almacenamiento:
>
> ● El almacenamiento proporciona espacio para datos y programas, y
> puede ser local o compartido entre los nodos.
>
> ● Utilizar sistemas de almacenamiento de alto rendimiento, como
> almacenamiento en red (NAS) o almacenamiento conectado
>
> directamente (DAS), para garantizar un acceso rápido a los datos y una
> alta disponibilidad.
>
> 4\. Software de gestión:
>
> ● El software de gestión incluye sistemas operativos, middleware y
> herramientas de administración que facilitan la conﬁguración, el
> monitoreo y la administración del clúster.
>
> ● Utilizar software robusto y escalable que permita la gestión
> eﬁciente de recursos y la programación de tareas es crucial para
> maximizar la utilización del clúster.

Las decisiones de diseño que afectan el rendimiento y la escalabilidad
del clúster incluyen:

> ● Escalabilidad horizontal y vertical: Diseñar el clúster para que
> pueda crecer tanto en tamaño (agregando más nodos) como en capacidad
> de procesamiento (aumentando los recursos de los nodos existentes)
> según sea necesario.
>
> ● Balance de carga: Implementar mecanismos para distribuir
> uniformemente la carga de trabajo entre los nodos del clúster,
> evitando así cuellos de botella y maximizando la utilización de
> recursos.
>
> ● Tolerancia a fallos: Incorporar redundancia y mecanismos de
> recuperación ante fallos para garantizar la disponibilidad continua
> del clúster incluso en caso de errores o fallas de hardware.
>
> ● Modelos de programación para clústeres: Utilizar modelos de
> programación paralela y distribuida, como MPI (Message Passing
> Interface) o Apache Hadoop, que permiten a los desarrolladores
> escribir programas que aprovechan eﬁcazmente los recursos del clúster
> y escalan para manejar grandes volúmenes de datos.

En resumen, el diseño de un clúster de alto rendimiento implica la
cuidadosa selección y conﬁguración de nodos de computación, redes de
interconexión, almacenamiento y software de gestión, junto con
decisiones de diseño que afectan el rendimiento y la escalabilidad del
sistema. Esto incluye consideraciones como la escalabilidad, el balance
de carga, la tolerancia a fallos y la elección de modelos de
programación adecuados para el clúster.

> **●** **Compara** **y** **contrasta** **los** **modelos** **de**
> **programación** **para** **clústeres,** **como** **MPI** **(Message**
> **Passing** **Interface)** **y** **OpenMP** **(Open**
> **Multi-Processing).**
>
> **Discute** **las** **ventajas** **y** **desventajas** **de** **cada**
> **modelo** **y** **proporciona** **ejemplos** **de** **aplicaciones**
> **típicas.**

MPI (Message Passing Interface) y OpenMP (Open Multi-Processing) son
modelos de programación utilizados en clústeres para permitir la
ejecución paralela de aplicaciones. Aquí hay una comparación entre
ambos:

> 1\. MPI (Message Passing Interface):
>
> ● MPI es un modelo de programación de paso de mensajes que se utiliza
> para la comunicación entre procesos en un clúster.
>
> ● Permite que los procesos intercambien datos mediante el envío y
> recepción de mensajes explícitos entre sí.
>
> ● Ventajas: Es altamente escalable y adecuado para aplicaciones
> distribuidas y paralelas que requieren una comunicación intensiva
> entre procesos.
>
> ● Desventajas: Requiere un diseño explícito de la lógica de
> comunicación y puede ser más complejo de implementar y depurar en
> comparación con otros modelos.
>
> 2\. OpenMP (Open Multi-Processing):
>
> ● OpenMP es un modelo de programación de memoria compartida que
> permite la ejecución paralela de aplicaciones en sistemas
> multiprocesador.
>
> ● Permite que los procesos compartan datos mediante la especiﬁcación
> de regiones paralelas dentro del código, que se ejecutan
> simultáneamente en múltiples núcleos de procesamiento.
>
> ● Ventajas: Es más fácil de usar y más transparente para el
> programador, ya que requiere menos cambios en el código existente para
> paralelizarlo.
>
> ● Desventajas: Puede no ser tan escalable como MPI para aplicaciones
> que requieren comunicación intensiva entre procesos, ya que los
> recursos compartidos pueden convertirse en cuellos de botella.

Ejemplos de aplicaciones típicas para cada modelo incluyen:

> ● MPI: Simulaciones numéricas, cálculos cientíﬁcos intensivos en
> datos, procesamiento de imágenes y grandes análisis de datos
> distribuidos.
>
> ● OpenMP: Aplicaciones que pueden dividirse en tareas independientes y
> paralelizables, como bucles de cálculo intensivo, transformaciones de
> imágenes y procesamiento de texto.

En resumen, MPI es más adecuado para aplicaciones que requieren una
comunicación intensiva entre procesos en clústeres distribuidos,
mientras que OpenMP es más adecuado para aplicaciones que pueden
aprovechar la paralelización de tareas en sistemas multiprocesador con
memoria compartida. La elección entre ambos modelos depende de las
necesidades especíﬁcas de la aplicación y del equilibrio entre la
complejidad y el rendimiento.

> **●** **Explica** **la** **importancia** **de** **la** **tolerancia**
> **a** **fallos** **en** **clústeres** **y** **describe** **las**
> **técnicas** **comunes** **para** **lograrla,** **como** **la**
> **replicación** **de** **datos,** **el** **checkpointing** **y**
> **la** **migración** **de** **tareas.** **Discute** **los**
> **desafíos** **asociados** **con** **cada** **técnica.**

La tolerancia a fallos en clústeres es crucial para garantizar la
disponibilidad continua y la integridad de los datos, especialmente en
entornos de computación de alto rendimiento donde la falla de un
componente puede tener consecuencias graves. Aquí hay una explicación de
su importancia y algunas técnicas comunes para lograrla:

> 1\. Importancia de la tolerancia a fallos:
>
> ● La tolerancia a fallos en clústeres es esencial para garantizar la
> continuidad operativa y la integridad de los datos, minimizando el
> impacto de fallas de hardware, software o de red.
>
> ● Permite que los sistemas continúen operando incluso cuando ocurren
> fallas, evitando interrupciones en el servicio y pérdidas de datos
> críticos.
>
> 2\. Técnicas comunes para lograr tolerancia a fallos: a. Replicación
> de datos:
>
> ● Consiste en mantener múltiples copias de los datos en diferentes
> nodos del clúster para garantizar la disponibilidad y la recuperación
> ante fallos.
>
> ● Desafíos: Requiere un manejo cuidadoso de la consistencia de datos
> entre las réplicas y puede aumentar los requisitos de almacenamiento y
> ancho de banda de la red.
>
> 3\. b. Checkpointing:
>
> ● Implica guardar periódicamente el estado del sistema o de las
> aplicaciones en un punto conocido como "checkpoint", que puede
> utilizarse para reiniciar la ejecución en caso de falla.
>
> ● Desafíos: Requiere determinar el momento adecuado para realizar
> checkpoints sin afectar signiﬁcativamente el rendimiento de las
> aplicaciones y la sobrecarga asociada con la escritura y lectura de
> datos de checkpoint.
>
> 4\. c. Migración de tareas:
>
> ● Permite trasladar tareas o procesos de un nodo a otro en caso de que
> ocurra una falla en el nodo original, asegurando que la ejecución del
> trabajo continúe sin interrupciones.
>
> ● Desafíos: Requiere una gestión eﬁciente de recursos y una
> infraestructura de red robusta para garantizar una migración rápida y
> transparente de tareas.

En resumen, la tolerancia a fallos en clústeres es esencial para
garantizar la disponibilidad y la integridad de los datos. Las técnicas
comunes como la replicación de datos, el checkpointing y la migración de
tareas ayudan a lograrla, pero cada una presenta desafíos únicos que
deben abordarse para garantizar su efectividad y eﬁciencia.

> **●** **Describe** **los** **métodos** **utilizados** **para**
> **evaluar** **el** **rendimiento** **de** **un** **clúster,** **como**
> **benchmarks** **(por** **ejemplo,** **LINPACK,** **HPCG)** **y**
> **métricas** **(por** **ejemplo,** **FLOPS,** **latencia,** **ancho**
> **de** **banda).** **Explica** **cómo** **interpretar** **los**
> **resultados** **y** **utilizarlos** **para** **optimizar** **el**
> **rendimiento** **del** **clúster.**

Los métodos utilizados para evaluar el rendimiento de un clúster
incluyen el uso de

benchmarks y métricas especíﬁcas. Aquí se describen ambos:

> 1\. Benchmarks:
>
> ● Los benchmarks son programas diseñados para medir el rendimiento de
> un sistema en tareas especíﬁcas. Algunos ejemplos comunes de
> benchmarks para clústeres incluyen LINPACK y HPCG para el rendimiento
> de cálculos numéricos, SPEC MPI para aplicaciones MPI, y STREAM para
> medir el rendimiento de la memoria.
>
> ● Estos benchmarks ejecutan una serie de pruebas y generan métricas de
> rendimiento que pueden compararse con resultados de otros sistemas
> para evaluar el desempeño relativo.
>
> 2\. Métricas:
>
> ● Las métricas de rendimiento incluyen medidas como FLOPS (operaciones
> de punto ﬂotante por segundo), latencia de red, ancho de banda de red,
> tiempo de ejecución de aplicaciones y eﬁciencia energética.
>
> ● Estas métricas proporcionan información detallada sobre diferentes
> aspectos del rendimiento del clúster, como la capacidad de cálculo, la
> eﬁciencia de comunicación y el consumo de recursos.

Interpretar los resultados de las pruebas de rendimiento y métricas
implica

comparar los valores obtenidos con los de sistemas de referencia o con
objetivos

establecidos previamente. Algunos pasos importantes incluyen:

> ● Identiﬁcar los cuellos de botella: Analizar las métricas para
> identiﬁcar áreas donde el rendimiento del clúster es subóptimo, como
> latencia de red alta o baja eﬁciencia de cálculo.
>
> ● Optimización: Utilizar los resultados para identiﬁcar áreas de
> mejora y realizar ajustes en la conﬁguración del clúster, como
> optimizar la conﬁguración de red, ajustar la asignación de recursos o
> mejorar la eﬁciencia de los algoritmos utilizados.
>
> ● Evaluación continua: Realizar pruebas de rendimiento periódicas para
> evaluar el impacto de los cambios realizados y garantizar que el
> clúster esté funcionando de manera óptima a lo largo del tiempo.

Es decir, los benchmarks y las métricas de rendimiento son herramientas

importantes para evaluar y optimizar el rendimiento de un clúster.
Interpretar los

resultados y utilizarlos para realizar ajustes en la conﬁguración del
clúster ayuda a

maximizar su eﬁciencia y capacidad de procesamiento.

> **●** **Análisis** **de** **escalabilidad\_** **Un** **sistema**
> **multiprocesador** **tiene** **8** **núcleos** **y** **se**
> **observa** **que** **una** **aplicación** **que** **tarda** **100**
> **segundos** **en** **ejecutarse** **en** **un** **solo** **núcleo**
> **tarda** **20** **segundos** **en** **ejecutarse** **en** **8**
> **núcleos.** **Calcula** **la** **aceleración** **(speedup)** **y**
> **la** **eﬁciencia** **del** **sistema.** **¿Es** **el** **sistema**
> **escalable?** **Justiﬁca** **tu** **respuesta.**

Para calcular la aceleración (speedup) del sistema, utilizamos la
fórmula:

Speedup=Tiempo de ejecucion en multiples nucleos / Tiempo de ejecucion
en un solo nucleo

Dado que el tiempo de ejecución en un solo núcleo es de 100 segundos y
en 8 núcleos es de 20 segundos, el speedup sería:

Speedup=100 segundos/20 segundos=5

Para calcular la eﬁciencia del sistema, utilizamos la fórmula:

Eficiencia=Speedup/Numero de nucleos

Dado que el sistema tiene 8 núcleos, la eﬁciencia sería:

Eficiencia=5/8=0.625

El speedup obtenido es de 5 y la eﬁciencia es del 62.5%. El speedup
indica cuánto más rápido es el sistema en comparación con un solo
núcleo, y la eﬁciencia indica cuánto de esa velocidad adicional se
aprovecha con cada núcleo adicional.

En este caso, el speedup obtenido es signiﬁcativo, lo que indica que el
sistema multiprocesador es escalable en términos de velocidad de
ejecución. Sin embargo, la eﬁciencia del sistema es del 62.5%, lo que
signiﬁca que no se está utilizando plenamente el potencial de todos los
núcleos. Esto puede deberse a overheads de comunicación, dependencia de
datos u otros factores que limitan la eﬁciencia del paralelismo. A pesar
de esto, el sistema sigue siendo escalable en términos de velocidad de
ejecución, aunque podría mejorar su eﬁciencia con optimizaciones
adicionales.

> **●** **Describe** **el** **problema** **de** **la** **cena** **de**
> **los** **ﬁlósofos** **y** **cómo** **se** **aplica** **a** **los**
> **sistemas** **de** **multiprocesadores.** **Propón** **una**
> **solución** **utilizando** **semáforos** **o** **monitores** **y**
> **discute** **las** **posibles** **situaciones** **de** **deadlock**
> **y** **cómo** **evitarlas.**

El problema de la cena de los ﬁlósofos es un clásico problema de
concurrencia que ilustra los desafíos de sincronización y exclusión
mutua en sistemas multiprocesadores. En este problema, un grupo de
ﬁlósofos se sienta alrededor de una mesa redonda con un plato de
espaguetis frente a cada uno, y entre cada par de platos hay un tenedor.
Los ﬁlósofos pasan su tiempo pensando y comiendo espaguetis, pero solo
pueden comer cuando tienen ambos tenedores adyacentes.

Este problema se aplica a los sistemas multiprocesadores cuando
múltiples procesos compiten por recursos compartidos, como acceso a
datos críticos o hardware compartido.

Una solución común al problema de la cena de los ﬁlósofos es utilizar
semáforos o monitores para controlar el acceso a los tenedores. Aquí hay
una posible solución utilizando semáforos:

> 1\. Cada tenedor se representa como un semáforo binario inicializado
> en 1, lo que indica que está disponible.
>
> 2\. Cada ﬁlósofo intenta tomar los tenedores adyacentes utilizando
> operaciones de espera y señal en los semáforos correspondientes.
>
> 3\. Si un ﬁlósofo no puede tomar ambos tenedores, espera hasta que
> estén disponibles.
>
> 4\. Una vez que un ﬁlósofo ha terminado de comer, libera los tenedores
> adyacentes, lo que permite que otros ﬁlósofos los utilicen.

Para evitar situaciones de deadlock, donde todos los ﬁlósofos están
esperando un tenedor y ninguno puede avanzar, se pueden implementar
varias estrategias:

> 1\. Asimetría: Permitir que un ﬁlósofo tome primero el tenedor
> izquierdo y luego el derecho, mientras que los demás toman el derecho
> y luego el izquierdo. Esto rompe la circularidad y evita el deadlock.
>
> 2\. Límite de espera: Si un ﬁlósofo no puede obtener ambos tenedores
> después de esperar un tiempo determinado, puede soltar los tenedores y
> volver a intentarlo más tarde.
>
> 3\. Ordenamiento de recursos: Asignar un número único a cada tenedor y
> requerir que los ﬁlósofos los tomen en orden ascendente o descendente,
> evitando así la competencia directa por los mismos recursos.

Implementar estas estrategias garantiza que los ﬁlósofos puedan comer
sin incurrir en situaciones de deadlock, lo que mejora la eﬁciencia y la
ﬁabilidad del sistema multiprocesador.

> **●** **Investiga** **un** **caso** **de** **estudio** **real** **de**
> **un** **clúster** **de** **alto** **rendimiento** **utilizado**
> **en** **una** **aplicación** **cientíﬁca** **o** **industrial.**
> **Describe** **la** **arquitectura** **del** **clúster,** **el**
> **tipo** **de** **aplicaciones** **que** **ejecuta,** **y** **los**
> **desafíos** **y** **soluciones** **implementadas** **en**
> **términos** **de** **rendimiento** **y** **escalabilidad.**

Un caso de estudio real de un clúster de alto rendimiento es el clúster
de supercomputación Frontera ubicado en el Centro de Computación
Avanzada de la Universidad de Texas en Austin. Este clúster es uno de
los sistemas de computación más potentes del mundo y se utiliza para una
amplia gama de aplicaciones cientíﬁcas e industriales.

Arquitectura del clúster: Frontera consta de más de 8000 nodos de
computación equipados con procesadores Intel Xeon y aceleradores GPU
NVIDIA Tesla. Está conectado por una red de alta velocidad InﬁniBand
HDR, lo que proporciona una comunicación rápida y eﬁciente entre los
nodos.

Tipo de aplicaciones: Frontera se utiliza para una variedad de
aplicaciones cientíﬁcas e industriales, incluyendo simulaciones
climáticas y atmosféricas, modelado molecular y diseño de fármacos,
análisis de datos genómicos, simulaciones de ﬂuidos y aerodinámica,
entre otros. Estas aplicaciones son computacionalmente intensivas y
requieren una gran capacidad de cálculo para procesar grandes volúmenes
de datos en tiempo real.

Desafíos y soluciones implementadas:

> ● Rendimiento y escalabilidad: Frontera enfrenta el desafío de
> proporcionar un rendimiento óptimo y escalabilidad para una variedad
> de cargas de trabajo heterogéneas. Para abordar esto, se implementan
> técnicas como la optimización de código, la paralelización eﬁciente de
> algoritmos y el uso de aceleradores GPU para acelerar cálculos
> intensivos.
>
> ● Gestión de recursos: Con miles de nodos y usuarios simultáneos, la
> gestión eﬁciente de recursos es esencial. Frontera utiliza sistemas de
> gestión de colas avanzados que asignan recursos de manera dinámica
> según la carga de trabajo y las prioridades de los usuarios,
> garantizando un uso eﬁciente de los recursos y minimizando los tiempos
> de espera.
>
> ● Energía y enfriamiento: Los grandes clústeres de supercomputación
> como Frontera consumen una gran cantidad de energía y generan calor,
> lo que plantea desafíos en términos de eﬁciencia energética y
> enfriamiento. Para abordar esto, se implementan soluciones de
> enfriamiento eﬁcientes, como sistemas de refrigeración líquida y
> gestión de energía inteligente, para mantener la temperatura dentro de
> los límites operativos y reducir el consumo de energía.

En resumen, el clúster Frontera es un ejemplo de cómo se pueden abordar
los desafíos de rendimiento y escalabilidad en aplicaciones cientíﬁcas e
industriales a través de una arquitectura avanzada, técnicas de
optimización y gestión eﬁciente de recursos.

> **●** **Realiza** **una** **evaluación** **comparativa** **teórica**
> **de** **dos** **arquitecturas** **de** **clústeres** **diferentes**
> **(por** **ejemplo,** **uno** **basado** **en** **CPU** **y** **otro**
> **basado** **en** **GPU).** **Discute** **las** **ventajas** **y**
> **desventajas** **de** **cada** **arquitectura** **para**
> **diferentes** **tipos** **de** **aplicaciones.**

Una evaluación comparativa teórica entre un clúster basado en CPU y otro
basado en GPU puede proporcionar una visión sobre las ventajas y
desventajas de cada arquitectura en diferentes tipos de aplicaciones:

Clúster basado en CPU:

> ● Ventajas:
>
> 1\. Versatilidad: Las CPU son altamente versátiles y pueden manejar
> una amplia gama de tareas computacionales.
>
> 2\. Memoria compartida: Las CPU tienen acceso a grandes cantidades de
> memoria compartida, lo que facilita el intercambio de datos entre los
> procesos.
>
> 3\. Flexibilidad de programación: Las CPUs son compatibles con una
> amplia variedad de lenguajes de programación y herramientas de
> desarrollo.
>
> ● Desventajas:
>
> 1\. Rendimiento limitado en paralelismo: Las CPUs están optimizadas
> para tareas secuenciales y tienen un rendimiento limitado en
> aplicaciones altamente paralelas.
>
> 2\. Mayor consumo de energía: Las CPUs suelen consumir más energía que
> las GPUs, lo que puede aumentar los costos operativos.
>
> 3\. Menor eﬁciencia en cálculos intensivos: Para aplicaciones que
> requieren una gran cantidad de cálculos intensivos, las CPUs pueden no
> ser la mejor opción debido a su menor cantidad de núcleos y unidades
> de procesamiento.

Clúster basado en GPU:

> ● Ventajas:
>
> 1\. Alto rendimiento en paralelismo: Las GPUs están diseñadas
> especíﬁcamente para tareas altamente paralelas y pueden proporcionar
> un rendimiento signiﬁcativamente mayor en aplicaciones que pueden
> aprovechar este paralelismo.
>
> 2\. Eﬁciencia energética: Las GPUs suelen consumir menos energía por
> cálculo que las CPUs, lo que puede resultar en menores costos
> operativos.
>
> 3\. Mayor cantidad de núcleos: Las GPUs tienen una gran cantidad de
> núcleos de procesamiento, lo que las hace ideales para aplicaciones
> que requieren una gran cantidad de cálculos.
>
> ● Desventajas:
>
> 1\. Memoria limitada y compartida: Las GPUs suelen tener menos memoria
> que las CPUs y la memoria puede estar compartida entre los núcleos de
> procesamiento, lo que puede limitar el rendimiento en algunas
> aplicaciones.
>
> 2\. Programación más compleja: La programación para GPUs puede ser más
> compleja que para CPUs debido a la arquitectura altamente paralela y
> la necesidad de optimizar el código para aprovechar al máximo los
> recursos disponibles.
>
> 3\. Limitaciones en aplicaciones secuenciales: Las GPUs pueden no ser
> tan eﬁcientes como las CPUs en aplicaciones secuenciales o de un solo
> hilo de ejecución debido a su enfoque en el paralelismo masivo.

Es decir, la elección entre un clúster basado en CPU y uno basado en GPU
dependerá de las características especíﬁcas de las aplicaciones y los
requisitos de rendimiento. Las CPUs son más adecuadas para aplicaciones
versátiles y de uso general, mientras que las GPUs ofrecen un
rendimiento excepcional en aplicaciones altamente paralelas y cálculos
intensivos.

> 1 . Implementa la multiplicación de dos matrices grandes en paralelo
> utilizando la
>
> librería multiprocessing.
>
> \[ \]
>
> from multiprocessing import Pool
>
> import numpy as np
>
> def matrix_multiply_segment(args):
>
> A_segment, B = args
>
> return np.dot(A_segment, B)
>
> if \_\_name\_\_ == "\_\_main\_\_":
>
> A = np.random.rand(1000, 1000)
>
> B = np.random.rand(1000, 1000)
>
> num_processes = 4
>
> segment_size = A.shape\[0\] // num_processes
>
> segments = \[(A\[i \* segment_size:(i + 1) \* segment_size\], B) for i
> in range(num_processes)\]
>
> with Pool(num_processes) as pool:
>
> results = pool.map(matrix_multiply_segment, segments)
>
> C = np.vstack(results)
>
> print("Matrix multiplication completed.")

2 . Implementa la suma de dos vectores grandes distribuidos entre varios
nodos

utilizando mpi4py.

\[ \]

> from mpi4py import MPI
>
> import numpy as np

comm = MPI.COMM_WORLD

rank = comm.Get_rank()

size = comm.Get_size()

vector_size = 1000000

local_size = vector_size // size

if rank == 0:

> A = np.random.rand(vector_size)
>
> B = np.random.rand(vector_size)

else:

> A = None
>
> B = None

local_A = np.empty(local_size, dtype='d')

local_B = np.empty(local_size, dtype='d')

comm.Scatter(A, local_A, root=0)

comm.Scatter(B, local_B, root=0)

local_C = local_A + local_B

> if rank == 0:
>
> C = np.empty(vector_size, dtype='d')
>
> else:
>
> C = None
>
> comm.Gather(local_C, C, root=0)
>
> if rank == 0:
>
> print("Vector addition completed.")

3 . Implementa una simulación de Monte Carlo para calcular el valor de
Pi en

paralelo en un clúster utilizando mpi4py.

\[ \]

> from mpi4py import MPI
>
> import numpy as np
>
> comm = MPI.COMM_WORLD
>
> rank = comm.Get_rank()
>
> size = comm.Get_size()
>
> num_samples = 1000000
>
> local_samples = num_samples // size
>
> np.random.seed(rank)
>
> local_count = 0
>
> for \_ in range(local_samples):
>
> x, y = np.random.rand(2)
>
> if x\*\*2 + y\*\*2 \<= 1.0:
>
> local_count += 1
>
> total_count = comm.reduce(local_count, op=MPI.SUM, root=0)
>
> if rank == 0:
>
> pi_estimate = (4.0 \* total_count) / num_samples
>
> print(f"Estimated Pi: {pi_estimate}")

4 . Divide y procesa un gran archivo de texto en un clúster, donde cada
nodo procesa

una parte del archivo y luego los resultados se combinan.

\[ \]

> from mpi4py import MPI
>
> comm = MPI.COMM_WORLD
>
> rank = comm.Get_rank()
>
> size = comm.Get_size()
>
> if rank == 0:
>
> with open('large_text_ﬁle.txt', 'r') as ﬁle:
>
> lines = ﬁle.readlines()
>
> else:
>
> lines = None
>
> lines = comm.scatter(lines, root=0)
>
> local_word_count = sum(len(line.split()) for line in lines)
>
> total_word_count = comm.reduce(local_word_count, op=MPI.SUM, root=0)
>
> if rank == 0:
>
> print(f"Total word count: {total_word_count}")

5 . Usa pthread para dividir un arreglo en segmentos y sumarlos en
paralelo

\[ \]

> \#include \<pthread.h\>
>
> \#include \<stdio.h\>
>
> \#include \<stdlib.h\>

\#deﬁne NUM_THREADS 4

\#deﬁne ARRAY_SIZE 1000000

int array\[ARRAY_SIZE\];

long long sum = 0;

pthread_mutex_t mutex;

void\* sum_segment(void\* arg) {

> int start = (int)arg \* (ARRAY_SIZE / NUM_THREADS);
>
> int end = start + (ARRAY_SIZE / NUM_THREADS);
>
> long long local_sum = 0;
>
> for (int i = start; i \< end; i++) {
>
> local_sum += array\[i\];
>
> }
>
> pthread_mutex_lock(&mutex);
>
> sum += local_sum;
>
> pthread_mutex_unlock(&mutex);
>
> return NULL;

}

int main() {

> pthread_t threads\[NUM_THREADS\];
>
> pthread_mutex_init(&mutex, NULL);
>
> for (int i = 0; i \< ARRAY_SIZE; i++) {
>
> array\[i\] = rand() % 100;
>
> }
>
> for (int i = 0; i \< NUM_THREADS; i++) {
>
> pthread_create(&threads\[i\], NULL, sum_segment, (void\*)i);
>
> }
>
> for (int i = 0; i \< NUM_THREADS; i++) {
>
> pthread_join(threads\[i\], NULL);
>
> }
>
> pthread_mutex_destroy(&mutex);
>
> printf("Total sum: %lld\n", sum);
>
> return 0;

}

6 . Implementa la suma de dos vectores grandes distribuidos entre varios
nodos

utilizando MPI en C.

\[ \]

\#include \<mpi.h\>

\#include \<stdio.h\>

\#include \<stdlib.h\>

int main(int argc, char\*\* argv) {

> MPI_Init(&argc, &argv);
>
> int rank, size;
>
> MPI_Comm_rank(MPI_COMM_WORLD, &rank);
>
> MPI_Comm_size(MPI_COMM_WORLD, &size);
>
> int vector_size = 1000000;
>
> int local_size = vector_size / size;
>
> double\* local_A = (double\*)malloc(local_size \* sizeof(double));
>
> double\* local_B = (double\*)malloc(local_size \* sizeof(double));
>
> double\* local_C = (double\*)malloc(local_size \* sizeof(double));
>
> for (int i = 0; i \< local_size; i++) {
>
> local_A\[i\] = rank + 1;
>
> local_B\[i\] = rank + 2;
>
> }

MPI_Allreduce(local_A, local_C, local_size, MPI_DOUBLE, MPI_SUM,
MPI_COMM_WORLD);

> for (int i = 0; i \< local_size; i++) {
>
> local_C\[i\] = local_A\[i\] + local_B\[i\];
>
> }
>
> free(local_A);
>
> free(local_B);
>
> free(local_C);
>
> MPI_Finalize();
>
> return 0;

}

7 . Implementa una simulación de Monte Carlo para calcular el valor de
Pi en

paralelo en un clúster utilizando MPI en C.

\[ \]

\#include \<mpi.h\>

\#include \<stdio.h\>

\#include \<stdlib.h\>

int main(int argc, char\*\* argv) {

> MPI_Init(&argc, &argv);
>
> int rank, size;
>
> MPI_Comm_rank(MPI_COMM_WORLD, &rank);
>
> MPI_Comm_size(MPI_COMM_WORLD, &size);
>
> long long num_samples = 1000000;
>
> long long local_samples = num_samples / size;
>
> long long local_count = 0;
>
> unsigned int seed = rank;
>
> for (long long i = 0; i \< local_samples; i++) {
>
> double x = (double)rand_r(&seed) / RAND_MAX;
>
> double y = (double)rand_r(&seed) / RAND_MAX;
>
> if (x \* x + y \* y \<= 1.0) {
>
> local_count++;
>
> }
>
> }
>
> long long total_count;

MPI_Reduce(&local_count, &total_count, 1, MPI_LONG_LONG_INT, MPI_SUM, 0,
MPI_COMM_WORLD);

> if (rank == 0) {
>
> double pi_estimate = (4.0 \* total_count) / num_samples;
>
> printf("Estimated Pi: %f\n", pi_estimate);
>
> }
>
> MPI_Finalize();
>
> return 0;

}

\[ \]

> \## Tus respuestas
