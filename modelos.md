# Datos modelos y software

_En este documento solo voy a justificar el uso de modelos. Más aún añado alguna referencia de estudios clínicos que hablan de los retos aplicados a melanosmas, pero varios de estos se extrapolan a la generalidad del paradigma dermatológico._

## Modelos

Desde 2024 (referencia 1) ya se estaban estudiando la posibilidad de usar CNN. En tan solo dos años los estudios de imágen han mejorado drásticamente, mejorando consigo los modelos de segmentación. Considero que ya hay casos de uso de estos modelos en otras disciplinas médicas (referncia 2). Mismamente desde la experiencia de algunos de los miembros del equipo, modelos como YOLO o SAM funcionan extremedamente bien con un entrenamiento de bajos recursos. Lo bueno que tienen estos modelos también es que permiten la detección y localización del problema y también una piel sana.

Esto actualmente como está planeado es algo que existe, al final es un diagnóstico en el momento por imágen y básicamente estariamos haciendo un copycat parcial. Para ello debemos añadir a nuestro modelo otros 3 parámetros, el historial médico del caso, la gravedad actual y el hecho de cuánto tiempo lleva sin ir a una cita para no saturar con un solo paciente.

El tercer caso puede ir externo al mismo modelo, ya que simplemente se puede evaluar un mínimo de tiempo entre citas en función de la gravedad que devuelva el modelo, de esta manera el software no permite al usuario pedir una cita cada dia si no es necesario.

Respecto a los otros dos casos:

1. Por un lado tenemos el caso de añadir gravedad o algun output numérico que nos permita clasificar internamente por gravedad del caso. Con dos preguntas de gemini y la documentación de ultralytics (referncia 3), vemos que también podemos darle parametros de output extra a un segmento de salida.

2. Para el caso del historial, el output de yolo en verdad puedes devolverlo con formatos de tabla tratables, por tanto en vez de solo usar este modelo de reconocimiento podemos hacer un pipeline de modelos e el cual YOLO hacia el diagnóstico actual y otro modelo evalua la "pendiente de evolución" del caso en función del tipo de enfermedad y los parametros de gravedad dados (No es lo mismo que una irritación crezca 2 cm a que un tumor crezca 2 mm [ste último obvio es peor pese a que el evaluador de gravedad es inferior])

**referencias usadas en este apartado:**

1. https://www.sciencedirect.com/science/article/pii/S0022202X23029640
2. https://www.nature.com/articles/s41467-024-44824-z4
3. https://gemini.google.com/share/d/1I72j_UTsT73V8bw-xw02vjZHy8vkWTEh?usp=sharing

## Datos

Para los datos hay varios datasets académicos que nos pueden ser útiles para el entrenamiento del YOLO, hay estudios que resumen los mejores (referencia 1). Mismamente PubMed tiene una infinidad de datos para estudios (referencia 2, aunque esta no me la he leido por encima, es el manual y condiciones de uso de datos).

Pese a esto, cuando se hacen esta clase de aplicaciones, el protocolo a seguir más común es pedir colaboración a hospitales directamente, lo que nos permite obtener un conjunto de datos anónimos privados que se ajusten a nuestro problema exactamente, ya que los datasets académicos suelen aboradr problemas generales o más simples.

Habría que mirarlo varias personas detenidamente, pero existen protocolos ya hecho para hacer una beca de colaboración con hospitales, hay un monton de leyes por detras que también estan en la referencia 3, pero daré por hecho que es problema futuro.

**referencias usadas en este apartado:**
1. https://ieeexplore.ieee.org/abstract/document/10342692
2. https://pubmed.ncbi.nlm.nih.gov/download/
3. https://gemini.google.com/share/d/1Oyh48NlF09YbnCxqLmRJw6arDWZ0Ghcs?usp=sharing


## Software

Si alguien quiere aportar algun software ya creado animo a ampliar este apartado, pero opino que entrenando nuestro modelo de forma local tenemos los conocimientos de front-end necesarios para crear una app que sea útil a nivel de usuario y médico (habria que ver a quien orientamos más esta app).