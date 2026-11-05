# Licencia de TrIAderma

Como hemos podido ver en `licencias.md`, TrIAderma está sujeta a la licencia de SAM y a la licencia de datos que usemos, dependiendo de si usamos ehds o el hospital varía. Por tanto tenemos que buscar una licencia software que sea compatible con las dos posibles licencias de datos, con los datos privados de los pacientes y con la licencia de SAM 2, la Apache 2.0.

## Intereses de TrIAderma

Afortunadamente, a nivel de código tenemos mucha libertad, ya que Apache 2 no es vírica ni restringe a no usar licencias privadas.

Para una herramienta que afecta a tantas vidas, un interés claro es que el código sea revisado y pueda ser mejorado por otros expertos del área, con el fin de mejorar la eficiencia médica. Esto implica de primeras que nuestra licencia *no deberia involucrar un producto privado*.

Una vez sabemos esto, hay un segundo interés muy importante, la protección legal nuestra, estamos hablando de que nuestra aplicación está pensada como una herramienta de soporte, pero como hemos visto en otros sprints, un caso límite que se ha visto juzgado era el hecho de que un médico se confiara. Para ello en software médico existen licencias que exigen que el médico responsable verifique los resultados y nos libera de cualquier responsabilidad médica.

## Compatibilidad con los datos

La separación entre **código/modelo** y **datos de entrenamiento** es el pilar que permite la sostenibilidad legal de TrIAderma:

* **Datos de EHDS:** Exigen el procesamiento estricto dentro de un Entorno de Procesamiento Seguro (SPE) y la prohibición absoluta de reidentificación o descarga masiva del conjunto de datos crudos.


* **Datos Hospitalarios (DTA / CEIm):** Limitan el uso de las imágenes exclusivamente a la investigación acordada y obligan a su posterior destrucción o custodia.



Al publicar únicamente la arquitectura de software y los *pesos* del modelo derivado (*checkpoints*), cumplimos con el principio de anonimización y uso secundario. Ninguna de estas dos fuentes de datos impone que el código fuente derivado deba ser cerrado o comercial, por lo que **cualquiera de las opciones open-source o éticas es 100% compatible con los datos sanitarios empleados**.


## Tipos de licencias de software

Aquí mecionaremos muchas licencias, algunas de ellas ya mecionadas en el otro documento, como las de YOLO y sus variantes.

### Licencias Permisivas (Sin Copyleft)
Permiten utilizar, modificar, integrar y comercializar el software sin obligación de publicar ni liberar el código derivado.

* **MIT:** La más concisa y popular. Otorga libertad total a cambio de mantener la nota de copyright. No contempla licencias ni protecciones explícitas de patentes.
* **Apache 2.0 (Licencia de SAM 2):** Es el estándar de IA (Meta, Google). Permisiva como MIT, pero añade **concesiones explícitas de patentes** y rescisión automática en caso de litigios por infracción de patentes.
* **BSD (3-Clause):** Similar a MIT, pero añade una cláusula formal que prohíbe usar el nombre del proyecto o de sus creadores para fines de patrocinio o promoción sin permiso explícito por escrito.

### Licencias Copyleft Débil o Por Módulo
Exigen publicar las modificaciones de los archivos bajo la misma licencia, pero permiten su vinculación (*linking*) con código cerrado o comercial en el resto del proyecto.

* **MPL 2.0 (Mozilla Public License):** Copyleft aplicado a nivel de archivo individual. Si se modifica un archivo MPL, ese archivo debe liberarse; el resto de archivos del proyecto pueden ser propietarios.

### Licencias Copyleft Fuerte / Víricas
Obligan a que todo el ecosistema de código que interactúe o incorpore el componente adopte idéntica licencia abierta.

* **GPLv3:** Exige publicar todo el código derivado si el software se distribuye ejecutablemente a un cliente.
* **AGPLv3 (Licencia por defecto de YOLO):** Copyleft diseñado para arquitecturas en la nube (SaaS). Si los usuarios interactúan con la app a través de una red (redes IP, API REST), la entidad está legalmente obligada a liberar **todo** el código fuente de la plataforma.
* **EUPL v1.2 (European Union Public Licence):** Licencia copyleft oficial de la Comisión Europea aprobada en 23 idiomas. Es equivalente a AGPLv3 en cobertura de red/SaaS y protección de patentes, pero jurídicamente adaptada a la legislación europea y altamente compatible con otras licencias open-source mediante su matriz de compatibilidad.

### Licencias Específicas de IA, Éticas y "Source-Available"
Nuevos esquemas creados para controlar la responsabilidad de la IA, evitar el uso no supervisado o impedir que gigantes tecnológicos monopolicen infraestructura sin contrapartida.

* **OpenRAIL / OpenRAIL-M (Open Responsible AI License):** Diseñadas por BigScience y RAIL Initiative para modelos de ML. Es una licencia abierta pero añade un apéndice vinculante de **restricciones de uso conductual**. Permite auditar y redistribuir los *weights* y código, pero prohíbe expresamente usos como el diagnóstico médico autónomo sin supervisión facultativa.
* **BSL 1.1 (Business Source License):** Licencia de código visible (Source-Available). Gratuita para desarrollo, pruebas y pequeños volúmenes, pero exige pago para producción comercial o SaaS. Incluye conversión automática a Apache 2.0 tras un periodo fijado (máximo 4 años).
* **SSPL (Server Side Public License):** Diseñada por MongoDB. Versión ultra-restrictiva de AGPLv3 que exige liberar el código fuente de toda la infraestructura y herramientas de gestión SaaS del servidor si se ofrece el software como servicio.


| Licencia | Tipo de Licencia | ¿Es Vírica / Copyleft? | Cobertura en la Nube (SaaS) | Cláusula de Patentes | Enfoque Legal Destacado |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **MIT** | Permisiva | No | No restringe | No | Máxima sencillez, sin garantía legal |
| **Apache 2.0** | Permisiva | No | No restringe | **Sí (Protección activa)** | Estándar en IA (Licencia de SAM 2) |
| **BSD (3-Clause)** | Permisiva | No | No restringe | No | Cláusula explícita de no-promoción |
| **MPL 2.0** | Copyleft Débil | Solo a nivel de archivo | No restringe | Sí | Permite módulos cerrados adyacentes |
| **LGPLv3** | Copyleft Débil | No (si se usa dynamic link) | No restringe | Sí | Pensada para librerías vinculadas |
| **GPLv3** | Copyleft Fuerte | **Sí (A nivel de distribución)** | No cubre ejecución por red | Sí | Copyleft clásico de software libre |
| **AGPL-3.0** | Copyleft Fuerte | **Sí (Vírica en SaaS / Red)** | **Sí (Obliga a abrir código)** | Sí | Fuerza transparencia total en la nube |
| **EUPL v1.2** | Copyleft Europeo | **Sí (Compatible con GPL/AGPL)**| **Sí (Cubre provisión web)** | Sí | Adaptada al derecho de la Unión Europea |
| **OpenRAIL-M** | IA / Ética | No | No restringe | Según variante | **Prohíbe diagnósticos sin médico** |
| **BSL 1.1** | Source-Available | Restricción comercial | Prohíbe SaaS competidor | No | Conversión temporal a Apache 2.0 |
| **SSPL** | Source-Available | **Sí (Extremo)** | **Sí (Obliga a abrir infraestructura)**| Sí | Creada para evitar explotación cloud |
---
## Licencias a ponderar en TrIAderma

Considerando que buscamos un marco abierto, colaborativo y con una exención de responsabilidad médica absoluta, se evalúan las siguientes opciones:

1. **Apache 2.0 (Licencia Permisiva Estándar):**
* **Ventajas:** Total compatibilidad nativa con SAM 2 (misma licencia). Es el estándar de la industria, incluye cláusula explícita de concesión y protección contra patentes. Además, cuenta con una de las cláusulas de limitación de responsabilidad ("AS IS" / Sin garantías) más robustas y probadas judicialmente del mercado.
* **Inconvenientes:** Como cualquier licencia de software estándar, su exención de responsabilidad es genérica y no menciona específicamente el ámbito clínico (lo cual debe solucionarse con un aviso legal externo a la licencia).


2. **OpenRAIL-M (Responsible AI License - Medical Focus):**
* **Ventajas:** Diseñada específicamente para IA, prohíbe explícitamente usos poco éticos o el diagnóstico autónomo sin supervisión médica.
* **Inconvenientes:** **Es un riesgo legal encubierto.** Al intentar regular el comportamiento del usuario final, los desarrolladores asumen una carga de vigilancia implícita. Además, no es reconocida como una licencia "Open Source" por la OSI, lo que bloquea su adopción en ecosistemas de investigación puros.


3. **EUPL v1.2 (European Union Public Licence):**
* **Ventajas:** Traducida y adaptada al marco jurídico europeo. Ideal si el proyecto recibe fondos de la UE o se enmarca fuertemente en el EHDS.
* **Inconvenientes:** Es Copyleft (vírica en SaaS). Esto obligaría a cualquier hospital que despliegue TrIAderma en sus servidores web a publicar sus posibles modificaciones, lo que puede causar rechazo en instituciones sanitarias privadas con estrictas políticas de TI.



## Decisión final

Para **TrIAderma**, la opción elegida es la licencia **Apache 2.0 tanto para el código base como para los pesos (checkpoints) del modelo**, complementada con un **Aviso Médico de Exención de Responsabilidad (Medical Disclaimer)**.

Esta estrategia híbrida separa la propiedad intelectual de la responsabilidad civil:

1. **Compatibilidad y Estandarización (Apache 2.0):** Garantiza compatibilidad absoluta con SAM 2 y respeta los principios de anonimización y uso secundario del **EHDS** y los **datos hospitalarios**. Permite a la comunidad médica y científica auditar, mejorar e integrar el modelo sin fricciones legales. Su robusta cláusula "AS IS" nos protege a nivel de desarrollo de software.
2. **Protección Clínica Específica (Medical Disclaimer + Términos de Uso):** En lugar de usar una licencia "ética" dudosa, la responsabilidad médica se delega legalmente forzando la aceptación de un Aviso Médico antes de usar la herramienta. Este descargo (que debe constar en el `README` y en la interfaz de usuario) estipulará explícitamente que:
* *TrIAderma es exclusivamente un Sistema de Soporte a la Decisión Clínica (CDSS) para fines de investigación y triaje.*
* *Bajo ninguna circunstancia sustituye el juicio clínico de un profesional sanitario colegiado.*
* *Los desarrolladores del software y proveedores del modelo quedan eximidos de cualquier responsabilidad por negligencia, diagnósticos erróneos o mala praxis médica derivada de la sobreconfianza (*automation bias*) en la herramienta.*



De este modo, obtenemos lo mejor de ambos mundos: un producto 100% Open Source y una barrera legal sólida frente a un posible uso clínico irresponsable.


## Bibliografía

* Web con todas las licencias OpenSource: [https://opensource.org/licenses](https://opensource.org/licenses)


* Apache Software Foundation - Texto Apache License 2.0: [https://www.apache.org/licenses/LICENSE-2.0](https://www.apache.org/licenses/LICENSE-2.0)


* RAIL Initiative - Licencias Éticas para IA (OpenRAIL): [https://www.licenses.ai/](https://www.licenses.ai/)

* Comisión Europea - European Union Public Licence (EUPL v1.2): https://interoperable-europe.ec.europa.eu/licence/european-union-public-licence-version-12-eupl

* GNU Project - Texto GNU Affero General Public License (AGPL-3.0): https://www.gnu.org/licenses/agpl-3.0.html

* Conversación con Gemini para conocer licencias enrevesadas: [https://gemini.google.com/share/d/1b4n7jlG8F6mR5v_t8AbPlopLoTPE25OH?usp=sharing](https://gemini.google.com/share/d/1b4n7jlG8F6mR5v_t8AbPlopLoTPE25OH?usp=sharing)


* Reglamento Europeo del Espacio de Datos Sanitarios (EHDS): [https://health.ec.europa.eu/ehealth-digital-health-and-care/european-health-data-space-regulation-ehds_es](https://health.ec.europa.eu/ehealth-digital-health-and-care/european-health-data-space-regulation-ehds_es)
