# Modelo de negocio de TrIAderma

Para entender los posibles modelos de negocio de TrIAderma, es preciso recordar que el producto se comercializa bajo la licencia permisiva Apache 2.0.

## Modelo de negocio Compliance-as-a-Service

Nuestro modelo de negocio se basaría en cumplir con el **Marcado CE bajo el Reglamento de Productos Sanitarios** (MDR - EU 2017/745). Este sello regulatorio no se otorga al código fuente, sino al Fabricante Legal para una versión controlada de ese código que se clasifica como _Software as a Medical Device (SaMD)_.

A nivel de validación y transparencia, publicamos la metodología clínica, las arquitecturas, los resultados estadísticos (Sensibilidad, Especificidad, Curvas ROC) y las matrices de confusión derivadas de ensayos clínicos. Sin embargo, los datasets de entrenamiento altamente curados y el Dossier Técnico del Sistema de Calidad (ISO 13485) se mantienen estrictamente protegidos como secreto comercial (Trade Secret), compartiéndose únicamente, y bajo acuerdos de confidencialidad, con Autoridades Sanitarias y Organismos Notificados para auditoría.

En cuanto a cómo se distribuiría el modelo en el marco del Sistema de Salud Pública Española, se contemplan dos opciones:

1. Que TrIAderma ofrezca una solución de **SaaS Gestionado**. Para ello, tendría que definirse una capa de integración _software_ que serían los concectores específicos para los diversos proveedores informáticos que usa cada comunidad autónoma u hospital (Diraya en Andalucía, IANUS en Galicia, Selene o HP-HIS en otras regiones). Dichos conectores deben regirse por estándares robustos médicos como: HL7, FHIR o DICOM. Se facturaría por una integración "llave en mano" de esta capa que garantizase la interoperabilidad con los sistemas de Información Hospitalaria y de Historia Clínica.

2. Un modelo B2B2B en el que se contrata una **empresa externa como Integrador/Distribuidor** de nuestro modelo. Este caso facilitaría el proceso de desarrollo y venta pero responderíamos ante cualquier falta de la otra empresa como Fabricante Legal.

## Barreras de entrada para la competencia

- Para evitar que otras empresas se lucren con nuestro producto sin obtener nosotros retribución alguna, mantenemos privado el Dosier Técnico del Sistema de Calidad (ISO 13485) sin el cual es extremadamente difícil que otras empresas cumplan con el MDR usando nuestro mismo modelo.

- Una vez que hayamos implantado nuestra solución en el Sistema Nacional de Salud, podríamos incluir cláusulas para la recolección anónima de datos, los cuales como mencionamos en varias ocasiones no se compartirán con terceros, lo que nos permitiría actualizar nuestro sistema, que debe pasar desde cero el proceso de auditoría regulatoria MDR. Esto facilitará que la competencia se quede desfasada.

- Otra barrera de entrada para competidores sería que aunque dispongan de nuestro modelo, no contarían con los ingenieros que hay detrás ni con todo el conocimiento de cómo depurar la red. Esto también les podría dificultar cumplir con el MDR usando nuestro mismo modelo ya que para algunos casos obliga a la explicabilidad algorítmica.

## Riesgos de Lock-in

- **Lock-in Tecnológico (Bajo):** Al usar Apache 2.0, el riesgo de bloqueo tecnológico es nulo. Cualquier hospital o competidor puede descargar los pesos, el código base y ejecutar el modelo de forma independiente si deciden prescindir de los servicios de TrIAderma.

- **Lock-in de Datos e Integración (Alto):** Una vez que TrIAderma está entrelazado con el sistema HL7/FHIR del hospital, el pipeline de imágenes DICOM y los flujos de trabajo de los dermatólogos, el coste de sustitución (cambiar a otro proveedor de CDSS) es extremadamente alto en términos de tiempo, re-entrenamiento del personal y procesos de validación de IT.

## Conflictos Potenciales con la Comunidad

- **Riesgo de Bifurcación (Forking) Competitiva:** La licencia Apache 2.0 permite que gigantes tecnológicos (AWS, Google Cloud, o corporaciones de HealthTech) tomen el código de TrIAderma, lo empaqueten en su propia infraestructura de salud y lo vendan sin devolver un solo euro al proyecto original. Para mitigar esto, TrIAderma debe mantener el liderazgo en la marca, la validación clínica (estudios publicados) y la velocidad de actualización de los pesos.

## Comparativa con Modelos Descartados

| **Modelo No Elegido**                   | **Descripción**                                                                                                                                   | **Por qué se descarta para TrIAderma**                                                                                                                                                                              |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Doble Licencia (Dual Licensing)**     | Ofrecer el software bajo una licencia restrictiva (ej. AGPL) de forma gratuita, y vender una licencia comercial para eximir de las restricciones. | **Incompatible con la estrategia elegida.** Ya se ha optado por Apache 2.0, que permite el uso comercial sin fricciones. Cambiar a AGPL limitaría la adopción rápida en la comunidad científica y hospitalaria.     |
| **Monetización de Datos (Data-driven)** | Ofrecer el software o SaaS gratis a cambio de recolectar, anonimizar y vender los datos clínicos e imágenes a farmacéuticas o aseguradoras.       | **Riesgo ético y legal inasumible.** Viola los principios de confianza del paciente, choca frontalmente con la regulación estricta del EHDS/RGPD y destruiría la reputación de la herramienta en el sector público. |
| **Open Core Funcional (Crippleware)**   | Liberar un modelo básico o de baja resolución de forma gratuita y cobrar por el modelo avanzado de alta precisión.                                | **Riesgo clínico.** Capar la precisión diagnóstica del modelo gratuito contradice la ética médica de un CDSS. Si el triaje Open Source es deficiente, la comunidad lo rechazará y no habrá validación científica.   |


