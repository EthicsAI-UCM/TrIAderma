# Análisis de riesgos y límites del proyecto

## Tabla de riesgos
| Nombre del riesgo | Descripción | Gravedad (1-5) | Probabilidad (1-5) | Acciones de prevención | Acciones de contingencia |
| :--- | :--- | :---: | :---: | :--- | :--- |
| Filtración de datos | Brecha de seguridad que permita a atacantes acceder a los datos de los diversos pacientes. | 5 | 3 | Priorizar la codificación de los datos, y la seguridad de la aplicación. | Informar a las instituciones pertinentes, a los usuarios, y cerrar temporalmente la app y cualquier tipo de acceso. |
| Sesgo de color de piel | Falta de datos balanceados puede provocar peores resultados en ciertos tonos de piel. | 2 | 4 | Asegurar que los conjuntos de entrenamiento tienen una distribución de datos suficientemente equilibrada. | Seguir re-entrenando el modelo con datos más diversificados para intentar reducir el sesgo. |
| Falsos negativos | El modelo puede tener una alta tasa de falsos negativos (enfermedades reales clasificadas como que no lo son). | 4 | 2 | Entrenar y ajustar el modelo cuanto sea necesario para reducir esta tasa, y no desplegarlo hasta que tenga un valor suficientemente bajo. | Continuamente reentrenar el modelo con más datos de enfermedades para compensar el diagnóstico, y así reducir la probabilidad de fallo en el futuro. |
| Falsos positivos | Justo al revés que el riesgo anterior: enfermedades falsas clasificadas como reales. El riesgo de esto es que una alta tasa podría causar el mismo problema que intentamos evitar: la sobresaturación de centros médicos. | 3 | 4 | De nuevo, al igual que antes, ajustar el modelo para reducir esta tasa. | No es tan grave como pasar por alto enfermedades reales, por tanto una vez el paciente llegue a la cita médica, se verá que era una falsa alarma. |
| Uso indebido por menores | La app no debe ser usada por menores de edad sin supervisión de un adulto responsable a su cargo, debido a la sensibilidad de los datos que se usan. | 5 | 2 | Imponer algún tipo de control de edad. Ya que nuestro producto está enfocado a nivel nacional, podría enlazarse con la identificación fiscal del paciente. | Cortar el acceso/tumbar la cuenta, par evitar futuros usos de la misma. |
| Saturación por muchos accesos | El servidor hosteando el modelo puede no estar preparado para recibir un grand número de accesos simultáneos de golpe, colapsando el sistema. | 2 | 1 | Es una medida fácil de evitar, ya que conocemos el potencial riesgo, y por tanto podemos preparar el servidor para un alto número de peticiones a la vez, suficientemente alto como para evitar el colapso. | Desconectar temporalmente el sistema mientras nos ocupamos de aumentar la capacidad. |
| App inaccesible para colecivos | La app puede no estar preparada para ciertos colectivos, como gente con alguna discapacidad física, o personas de edad avanzada. | 3 | 2 | Seguir los patrones WCAG de diseño de interfaces. | Dar una forma accesible para poder pedir citas presenciales, o un tfno de contacto. |
| Cuentas no legítimas | Usuarios malévolos podrían dedicarse a crear cuentas falsas para saturar el sistema (DoS), o a cualquier otro tipo de actividad maliciosa. | 2 | 1 | A la hora de crear una cuenta nueva, solicitar algún tipo de identificación de manera que no pueda haber varias cuentas pertenecientes a un solo individuo. | Tumbar la cuenta de manera inmediata. |

## Plausibilidad
### Dependencia tecnológica
De cara a los requisitos y dependencias de la tecnología actual, no hay problema alguno.
Utilizamos técnicas que ya existen hoy en día, y por tanto el desarrollo del modelo y de
la app es realísticamente factible.

### Sensibilidad de los datos
Como se ha mencionado y criticado en los debates, nuestro modelo ciertamente trabaja
con datos potencialmente sensibles de los usuarios, sobre todo en la parte gráfica
(imágenes íntimas). Ante esto, debemos tener cuidado con cómo tratamos y codificamos
los datos, para evitar filtraciones indeseadas.

### Sesgos
Otro de los temas altamente tratados en nuestro proyecto son los sesgos, específicamente
de piel. Esto se debe a que los conjuntos de datos disponibles se componen mayormente de
imágenes de piel clara. Esto causa un gran desbalance en le entrenamiento que sin lugar
a dudas tendremos que tener en cuenta para ver como resolverlo.

## Líneas rojas
### Privacidad
El modelo/app nunca forzará al usuario a subir imágenes si este no lo desea. Se le
recomendará que lo haga para obtener mejores resultados, pero nunca será imprescindible
para el correcto funcionamiento.

### Diagnóstico
El modelo nunca dará un diagnóstico médico antes de que un doctor haya examinado al
paciente y haya dado el visto bueno para ello. Esto por ley está prohibido.

### Menores
El modelo nunca podrá ser usado por menores de manera independiente. Si los pacientes no
alcanzasen la mayoría de edad, serían los padres o tutores legales los que manejasen la
app, y serían estos los que tomarían las decisiones.

### Comercialización de datos *(Opcional)*
El modelo nunca usará los datos provistos por los pacientes para fines comerciales, ni
los cederá a terceros.

## Emergencias
### Quién
Los responsables de poner en pausa el modelo seríamos nosotros (como desarrolladores y
mantenedores del sistema), y tal vez algún comité médico que dé la orden por razones
justificadas.

### Cuándo
El sistema debería detenerse en casos como brechas de seguridad, donde los datos
personales de los pacientes puedan estar en riesgo de ser expuestos. También se puede
dar el caso de que el modelo falle excesivamente, causando un gran impacto en los
diagnósticos. Incluso podríamos detener el modelo si encontrásemos un fallo que
afectase a la forma de codificar las imágenes, ya que como se ha mencionado previamente,
es imprescindible para asegurar la privacidad de los pacientes.

### Cómo
Para detener el modelo, podríamos cortar las respuestas de la API de acceso al modelo, de
manera que no sea accesible para los usuarios, e indicando que el modelo se encuentra
desconectado por X razón. Una vez apagado e informado, notificaríamos a las
instituciones pertinentes sobre las causas y el estado.

## Rendición de cuentas
### Canal de reclamación
Sería fácil implementar una función en la app (botón, apartado, etc...) mediante la
cual tanto los usuarios como los especialistas pudieran mandar reclamaciones, las cuales
nosotros recibiríamos y analizaríamos para intentar solventar el problema. Podemos
aproximar que la reclamación ha sido recibida en menos de 24 horas y que daríamos una
respuesta inicial durante los primeros 7 días.

### Revisión humana
Sí, el usuario puede exigir una revisión humana ante el desacuerdo con los resultados
propuestos por el modelo. Nuestra app no es más que una herramienta con el fin de ayudar
tanto a los pacientes como a los especialistas, jamás como un reemplazo de estos
últimos. En cuanto a escala, puede derivar desde una simple cita con el especialista
hasta un comité médico si fuera necesario, en caso de que el modelo hubiera causado
graves daños en el paciente. Cabe destacar de nuevo que es solo una herramienta, en
el caso de que el especialista fuera el que tomó una decisión errónea y dañina, nosotros
no nos hacemos responsables de las consecuencias.

### Formas de reparación
Podemos asignar una cita para que se pueda hacer un diagnóstico de nuevo, desechando
el previo, y así poder corregir el estado. También, en caso de daños graves, podríamos
disponer de algún tipo de seguro que cubriese los perjuicios sobre el paciente.
