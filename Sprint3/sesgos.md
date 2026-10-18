# Sesgos que puede sufrir TrIAderma

En dermatología existen una gran cantidad de sesgos que afectan negativamente en el entrenamiento del modelo. Estos sesgos existen desde cualquier fuente, inclusive la futura [ehds[1]](https://health.ec.europa.eu/ehealth-digital-health-and-care/european-health-data-space-regulation-ehds_es).

## Sesgos a la hora de entrenar el modelo [2] [3]

### Etnias minoritarias y pieles oscuras

La mayoría de datasets disponibles hoy en día poseen una clara mayoría de pieles claras y rasgos europeos o norteamericanos. Esto afecta negativamente ya que un desbalance de este calibre con modelos que usan redes convolucionales fuerza a que solo se aprendan los patrones sobre pixeles claros, y por tanto, aumenta gravemente la tasa de error en etnias minoritarias.

### Desbalance de género.

Estudios aseguran que datasets como el datasets como el LFW poseen un 77.5% de caras masculinas. Al igual que en el anterior punto, esto es un problema que afecta a la mujer negativamente, ya que la muestra no representar el balance real que es cercano a un 50%, siendo realmente menos hombres uqe mujeres globalmente. Además, a nivel de ML este desbalance tiene el mismo efecto que el sesgo anterior.

### datos sintéticos y duplicados.

Como intento de solución a los sesgos anteriores, algunos desarrolladores duplicaron entraras o intentaron crear nuevos datos con el fin de equilibrar muestras. El problema esque los datos sintéticos vienen de los reales , por tanto, muchos de ellos al usar técnicas de balanceo clásicas heredan algun sesgo en el intento de eliminar otros. Esto también ocurre ya que muchos datasets no etiquetan la etnia o el género del paciente, lo que imposibilita el balanceo de datos.

### diferencias de edad.

Hay varios reportes que afirman que la mayoría de datos que poseen las bases de datos son provenientes de personas adultas, que tiene sentido debido a que los menores no pueden dar consentimiento sin los adultos. Esto genera también un desbalance que afecta negativamente al diagnóstico de menores, sobre todo los bebés cuyas características en la piel difieren más con un adulto.


### Patologías raras.

Obviamente hay patologías, como algunas de las uñas o casos como la piel de mariposa que no estan reportadas en el sistema, esto pese a ser negativo también representa menos de un 1% de la población, por tanto tampoco nos podemos arriesgar a que el sistema puede ponderar de forma frecuente estas patologías

## Desprivilegio en el colectivo anciano

No son necesarios estudios para saber que una app móvil le dificulta las cosas al colectivo anciano al no estar acostumbrados a las nuevas tecnologías. Esto se puede arreglar con las soluciones que dimos el anterior sprint de adaptabilidad al usuario, pero muchos ancianos pueden llegar a sentirse desprivilegiados usando la app. Dado este sesgo, mantenemos la decisión con más razon de permitir que la app la usen también en citas presenciales para que los ancianos puedan usar las vías tradicionales.

## Colectivos afectados y efectos de usos problemáticos

Con esto podemos diferenciar claramente a 3 colectivos afectados, las étnias minoritarias, las mujeres y las personas que no estan en edad adulta.

## ¿Cómo solucionamos esto?

afortunadamente, gracias al ehds, teniendo distintos datasets y datos sueltos reales podriamos crear un dataset fiel sin datos sintéticos, lo que permitiria mitigar muchos sesgos hablados. Además en caso de que no tuvieramos el servicio en 2030, intentado hacer una colaboración con algún hospital (Instituto de Investigación Sanitaria (IIS)) podriamos poner nosotros mismos las condiciones para crear el mejor modelo. Ademas, como nombramos en otros sprints, se puede crear varias versiones del producto, usando los mismos fallos que tengamos para mejorar el modelo. Al actuar sobre el sistema sanitario y seguir permitiendo la vía clásica los pacientes incluso estando graves pueden ser tratados a tiempo si se requiriese hasta tener un producto cerca de la perfección.

## Referencias usadas

(https://health.ec.europa.eu/ehealth-digital-health-and-care/european-health-data-space-regulation-ehds_es) [1]

[Kleinberg G, Diaz MJ, Batchu S, Lucke-Wold B. Racial underrepresentation in dermatological datasets leads to biased machine learning models and inequitable healthcare.J Biomed Res. 2022;3(1):42-47.](https://www.probiologists.com/abstract/racial-underrepresentation-in-dermatological-datasets-leads-to-biased-machine-learning-models-and-inequitable-healthcare) [2]

[Fabian Gröger, Simone Lionetti, Philippe Gottfrois, Alvaro Gonzalez-Jimenez, Lea Habermacher, Labelling Consortium, Ludovic Amruthalingam, Matthew Groh, Marc Pouly, Alexander A. Navarini](https://doi.org/10.64898/2025.12.27.25342585)[3]