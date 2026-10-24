# Usuarios
"Quién usa el sistema, quién se ve afectado y qué relaciones de poder hay."

## Médico de cabecera
Es el principal usuario directo de la aplicación. Es el encargado de interpretar y validar las propuestas de la IA, siempre
basándose en su propio criterio profesional y sin caer el el sesgo de automatización. Debe mantener un correcto orden en la
cola de triaje y derivar a telecita aquellos casos más sencillos.

Tiene una desventaja clara y es que si se le impone la herramienta (y supuesto que el modelo cumple con los requisitos de 
sesgos, fiabilidad y transparencia), es el médico el que asume la responsabilidad ante un error condicionado por la salida
del modelo.

## Dermatólogo especialista
Atiende los casos graves priorizados por el modelo y tiene acceso a gráficos de evolución el paciente. Esto puede liberar 
cargas en el seguimiento presencial del paciente y potencialmente la carga total de trabajo si recibe únicamente los casos
que realmente requieren de un especialista.

También existe el escenario en el que la IA peque de conservador y se saturen las consultas derivadas a dermatólogo.

## Paciente digitalizado y autónomo
Es el usuario capaz de usar e interactuar con la aplicación con la mayor normalidad. Envían fotos, describen síntomas,
responden preguntas y reciben la atención del médico de forma digital. Es uno de los usuarios más vulnerables
en el sistema, pues son los directamente afectados por la herramienta de triaje. No pueden acceder con facilidad a 
los criterios por los que ha sido evaluados, pues es primero la sugerencia de la IA y después la validación del médico.

## Colectivos vulnerables y sesgados
Son pacientes expuestos a brechas tecnológicas, de accesibilidad y/o algorítmicas. Buscan una atención justa y no discriminatoria
tanto en el uso de la aplicación como en la evaluación por parte del modelo. Son los más vulnerables en esta cadena de poder
pues, o no pueden fácilmente aprovechar las ventajas y comodidades que ofrece la aplicación, o siempre tienen la duda de si la 
demora (o posición en la cola) ha sido producto de un sesgo en el modelo de evaluación o ha sido el médico el que ha decidido
por encima de la recomendación de la IA.

## Hospital
Es el que compra el software y lo integra dentro del ecosistema sanitario. Busca reducir las listas de espera y optimizar los 
recursos. Entre sus responsabilidades se encuentra el fomentar un uso apropiado de la herramienta. Deben proveer de guías a
los médicos y establecer condiciones de trabajo realistas que minimicen las probabilidades de un incidente. Más concretamente,
y con un ejemplo, no deben pedir a un médico que evalúe una cantidad de casos muy grande en poco tiempo (lo que inevitablemente
fomentaría el sesgo de automatización).
