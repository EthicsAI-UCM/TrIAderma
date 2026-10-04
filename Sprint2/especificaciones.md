# Ficha técnica detallada de TrIAderma

## ¿Qué es TrIAderma?

- Herramienta de soporte en el triaje de dermatología en hospitales públicos.
- Permite, de forma online con fotos o de forma presencial ayudando al médico de cabecera, a hacer una evaluación previa de la patología y su gravedad, permitiendo asi ordenar los huecos libres con el dermatólogo según la importancia del caso.
- Esto libera saturación para los médicos de cabecera ya que no tienen que pasar todas las citas presenciales y permite derivar casos muy básicos a telecita.
- En TODO momento, el personal cualificado puede cambiar las listas de espera y validar los análisis de la herramienta, ya que una IA no puede controlar diagnósticos ni listas directamente debido al reglamento que lo califica como herramienta de alto riesgo.
- Una vez el diagnóstico y la receta estánm hechas, la herramienta con redes neuronales permite evaluar con fotos cómo evoluciona el tratamiento y pedir otra cita si fuese necesario. Esto Sí es legal.

## ¿Cómo entrenamos y qué datos usamos?

Se puede hacer una colaboración con un hospital, o en caso de desarrollo independiente existen distintos organismos que sirven de asistencia para que la herramienta se pueda usar sin problemas legales.

Estos mismos organismos poseen el Espacio Europeo de Datos de Salud (EEDS):
1. capacitará a las personas para que accedan, controlen y compartan sus datos de salud electrónicos a través de las fronteras para la prestación de asistencia sanitaria (uso primario de datos);
2. permitirá la reutilización segura y fiable de los datos sanitarios en actividades de investigación, innovación, formulación de políticas y reglamentación (uso secundario de datos);
3. fomentará un mercado único para los sistemas de historia clínica electrónica (HCE), apoyando tanto el uso primario como el secundario.


## ¿Sesgos de piel?
- Hay sesgos en la piel cuando se detectan enfermedades, sobre todo cuando hay que diferenciar un melanoma.
- Lo único que podemos hacer es buscar unos datos lo más ricos posibles para entrenar bien el modelo
- pese a esto estudios ya dicen que aunque sobreentrenes el sesgo existe y la gente de tonos oscuros tienden más a errores.
- Para ello, si los resultados en entrenamiento diesen a que haya sesgo, simplemente detectando el color de piel sin IA pues de puede avisar al médico de que la tasa de acierto en este primer modelo sea x%, aunque en un marco 2030 con las nuevas leyes es muy probable que se creen bases de datos mucho más ricas

## ¿Problemas legales?

Obviamente hay problemas de privacidad y de que los resultados sean fiables. Afortunadamente hay una oficina de IA europea que da asistencia para que cumpla estos reglamentos y fomenta el desarrollo de las mismas. 
Respecto a la seguridad de los datos del paciente, hay que asegurar que su imagen y sus datos esten protegidos, si derivamos el diagnostico a un deterioration index y el historial del paciente lo preprocesamos para que la ia solo reciba lo necesario se pueden ocultar todos los datos (básicamente edge computing).

También habría que pensar en cómo se siente un paciente a nivel ético usando la app, pero eso va muy relacionado al mock up
## Bibliografía usada

- https://health.ec.europa.eu/ehealth-digital-health-and-care/artificial-intelligence-healthcare_es  Muy buena web europea que cuenta todo lo legal arededor de esto
- https://health.ec.europa.eu/ehealth-digital-health-and-care/european-health-data-space-regulation-ehds_es
- https://www.sciencedirect.com/science/article/pii/S0022202X23029640