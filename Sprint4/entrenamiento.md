# Plan de entrenamiento sin violación de derechos de autor

Una fotografía clínica tiene dos capas de protección: los derechos de autor sobre la imagen y la protección de los datos de salud de la persona fotografiada. Por defecto, cualquier foto es propiedad de quien la tomó y no se puede reutilizar sin permiso. Por eso TrIAderma no entrena con material recopilado de internet: solo usa datos cuyo permiso de uso queda documentado antes de empezar.

## Qué no hacemos

- No extraemos imágenes de buscadores, redes sociales, ni páginas web, aunque sean públicas. Que algo sea accesible no significa que sea reutilizable.
- No usamos conjuntos de datos con licencia no comercial para entrenar el modelo final. Muchos datasets académicos usan licencias de ese tipo, y sirven para investigar pero no para un producto.
- No publicamos datos, solo código y pesos.

## De dónde salen los datos

| Fuente | Cómo se obtiene el permiso |
| --- | --- |
| Espacio Europeo de Datos de la Salud (EHDS) | Permiso de datos emitido por el organismo. El entrenamiento se hace dentro del entorno de procesamiento seguro, sin descargar nada. (ver web EHDS) |
| Hospital colaborador | Contrato de transferencia y de procesamiento de datos. El contrato recoge expresamente la cesión de los derechos de explotación sobre las imágenes para entrenar. |
| Datasets públicos | Solo se usan los que permiten uso comercial, tras revisar su licencia uno por uno. El resto se limita a pruebas internas de investigación. |

Los datos de EHDS y de hospital son los que aportan el volumen y la diversidad que necesita el modelo. Si no se consigue acceso a ninguna de las dos vías, el modelo no se puede entrenar

## Cómo se entrena

1. **Modelo base con licencia abierta.** Partimos de SAM 2, publicado bajo Apache 2.0, que permite uso comercial y modificación. Conservamos los avisos de licencia y atribución que exige.
2. **Ajuste fino con datos autorizados.** Solo con las fuentes de la tabla anterior, dentro del entorno donde se alojan.
3. **Registro de procedencia.** Cada fuente tiene una ficha con su origen, licencia, fecha de acceso, uso permitido y responsable. Ningún dato entra en el entrenamiento sin ficha.
4. **Separación entre datos y producto.** El repositorio contiene código y pesos bajo Apache 2.0. Las imágenes nunca salen del entorno autorizado, así que las licencias de los datos no se mezclan con la del software.

## Qué comprobamos antes de publicar los pesos

- Que el contrato con cada fuente permite distribuir un modelo derivado de sus datos. Si no lo permite, los pesos no se publican.
- Que el modelo no reproduce imágenes de entrenamiento. Se prueba antes de la publicación.

## Si alguien reclama

Si un titular de derechos reclama sobre un dato, se retira de inmediato de la ficha y del conjunto de entrenamiento, y se reentrena el modelo sin él. Como todo está registrado, se puede saber qué versiones del modelo se vieron afectadas. Este proceso es lento, y es otra razón para no admitir datos sin permiso claro desde el principio.
