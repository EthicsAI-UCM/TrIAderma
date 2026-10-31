# Licencias de los componentes

En cualquier proyecto de IA hay dos componentes que necesitan distintas licencias, los modelos usados, que la mayoría tienen licencias y los datos. A esto se le suma las propias licencias que deberia tener el proyecto como tal.

En este apartado abordaremos para cada herramienta que deberiamos usar, las licencias que tienen de por si y cómo nos restringen.

## Modelos que usamos

Como mencionamos en el primer sprint, TrIAderma funciona a partir de modelos de segmentación, los dos más famosos de código abierto son SAM 2 y YOLO.

| Característica | SAM 2 (Meta) | YOLO (Ultralytics v8, v11, v26) |
| --- | --- | --- |
| **Licencia base** | Apache License 2.0 | AGPL-3.0 (Enterprise de pago opcional) |
| **Naturaleza de la licencia (¿Vírica / Copyleft?)** | **No es vírica (Permisiva).** No requiere copyleft. Puedes incluirlo en proyectos de código propietario o cerrado sin restricciones. | **Sí, altamente vírica (Copyleft fuerte).** Obliga a publicar el código fuente de tu aplicación bajo la misma licencia si interactúas con ella incluso a través de una red. |
| **Uso comercial gratuito (Código cerrado)** | Sí. Puedes monetizar sin abrir tu código. | No. Debes liberar todo tu código o comprar una licencia comercial a Ultralytics. |
| **Enfoque técnico principal** | Segmentación (Máscaras exactas a nivel de píxel). | Detección (Bounding boxes / cajas delimitadoras). |
| **Precisión en bordes (Dermatología)** | Muy alta. Traza la forma exacta, vital para evaluar asimetrías y bordes irregulares. | Baja. Las cajas delimitan la zona, pero no la morfología exacta de la lesión. |
| **Adaptabilidad médica** | Excelente. Se puede afinar (*fine-tuning*) para segmentar lesiones cutáneas complejas. | Buena para clasificar o localizar, pero inferior para delimitar morfología. |

Como vemos para proyectos médicos, lo mejor es usar SAM ya que no es vírico y es bastate permisivo, en cambio YOLO requiere comprar la licencia al mínimo que queramos que el código sea privado. Esto también nos ayuda a decantarnos finalmente por usar SAM 2 a la hora de desarrollar el modelo de IA

## Licencias de los datos

### Anonimato de los datos

Para que no haya conflictos entre licencias de software y de datos, un punto clave es no filtrar los datos con el código, esto significa que el código solo debe llevar los pesos entrenados o la arquitectura sin entrenar. Si no hay licencias de datos que colisionan por ejemplo con Apache 2, pese a ser esta una licencia muy permisiva.

Además cabe destacar que cualquier foto tomada es considerada propiedad intelectual con todos los derechos reservados, ya que es la restricción por defecto, esto implica que su uso está prohibido aparentemente. Afortunadamente cuando se colabora con un hospital o se usan herramientas como el ehds, los derechos de explotación son cedidos.
El EHDS (Reglamento UE 2025/327, en vigor desde marzo de 2025) habilita el uso secundario de datos sanitarios electrónicos con fines de investigación, innovación y políticas sanitarias, pero si son pseudoanonimizados, lo que implica que esto, pese a que ya lo teníamos en cuenta, ahora es un mínimo necesario.

### Comparación distintas fuentes de datos

Como mencionamos en lso sprints 2 y 3, hay dos fuentes principales, la ehds y los datos de un hospital propios. En verdad hay un tercer caso, que es buscar um socio como shaip que nos proporcione los datos, estos últimos tienen muchas condiciones como se verá después, pero es conveniente tenerlos en cuenta en una comparación.

| Fuente de Datos | Instrumento Legal / Licencia | Condiciones de Uso | Restricciones Principales |
| --- | --- | --- | --- |
| **Espacio Europeo de Datos Sanitarios (EHDS)** | Permiso de Datos (emitido por un Organismo de Acceso - HDAB) | El proyecto debe calificar como "uso secundario" (investigación, innovación, entrenamiento de IA médica). | **Cero descargas:** Los datos solo pueden procesarse dentro de un Entorno de Procesamiento Seguro (SPE).<br>

<br>

<br>**Prohibición penal:** Ilegal intentar reidentificar pacientes o usar datos para seguros/marketing. |
| **Colaboraciones Directas (Hospitales)** | Acuerdos de Transferencia (DTA) y Procesamiento (DPA) | Requiere aprobación previa del protocolo por el **Comité de Ética (CEIm)** del hospital y un contrato bilateral a medida. | **Uso finalista:** Limitado exclusivamente al proyecto exacto definido en el contrato.<br>

<br>

<br>**Ciclo de vida:** Obligación estricta de destruir o devolver las imágenes al finalizar el estudio. La propiedad intelectual del algoritmo suele compartirse. |
| **Socios Terceros / Proveedores (ej. Shaip)** | Licencia de Datos Comerciales (Contrato B2B) | Transacción comercial con pago de tarifas. Requiere garantías de indemnidad sobre el consentimiento informado y anonimización previa. | **Uso interno:** Licencia no exclusiva para entrenar modelos.<br>

<br>

<br>**Prohibición de reventa:** Estrictamente prohibido distribuir, sublicenciar, publicar de código abierto o revender el conjunto de datos crudos (las imágenes en sí). |

### Conclusiones

Vemos que lo ideal sigue siendo usar datos de hospitales o del ehds, pero no podemos intentar descubrir o filtrar identidades y borrar los datos una vez los usemos para entrenar, como dicen sus licencias.

## Bibliografía

repositorio SAM 2
https://github.com/facebookresearch/sam2

repositorio YOLO
https://github.com/ultralytics/ultralytics

Conversación con gemini para comparar licencias y crear la tabla en el apartado de modelos
https://gemini.google.com/share/d/1Nqi2Lgq-KjofaJ6QgKeuFb5WiNht3Zmv?usp=sharing

Pagina del ministerio de cultura en relación con la proteción de datos en fotografías humanas
https://www.cultura.gob.es/planes-nacionales/dam/jcr:f5e2a630-b206-45fe-99ae-7b5bfd6da892/los-derechos-sobre-las-fotografias-y-sus-limitaciones.pdf

Pagina de shaip
https://es.shaip.com/solutions/healthcare-ai/

Pagina ehds
https://health.ec.europa.eu/ehealth-digital-health-and-care/european-health-data-space-regulation-ehds_es

Conversación con gemini relativa a comprar las licencias de datos
https://gemini.google.com/share/d/1kxGLKG8nV73Mj9LpUCaYT7f7JAVtGsFr?usp=sharing
