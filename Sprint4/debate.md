# Sobre las cuestiones tratadas en el debate

TrIAderma clasifica y prioriza casos, no diagnostica. Este documento recoge siete problemas que el diseño debe resolver y la respuesta del proyecto a cada uno.

---

## 1. Pacientes que no aportan fotografía

**Problema.** Sin imagen, el sistema no puede estimar la gravedad visual, y eso no debería dejar al paciente en una posición peor de la cola.

**Cómo lo afrontamos.**

- Un caso sin foto no se clasifica como verde ni como baja prioridad. Entra como *pendiente de valoración* y lo prioriza el médico de cabecera con el cuestionario de síntomas, el historial y la exploración.
- La foto puede tomarse en el propio centro de salud y el caso sigue el mismo flujo que uno enviado desde casa.
- El aviso de la app deja claro que no hay penalización: la cita se prioriza igualmente y la valora un médico.

## 2. Acceso equitativo entre canales

**Problema.** Si la app es más rápida que la vía presencial, se crean dos sistemas sanitarios con velocidades distintas.

**Cómo lo afrontamos.**

- No existe un carril presencial aparte: el médico de cabecera usa la herramienta en consulta con todos los pacientes. Un caso rojo que entra por cita presencial tiene el mismo plazo máximo de 14 días que uno que entra por la app.
- Se fija un margen máximo de diferencia entre canales, con un 20 % como punto de partida a ajustar con el hospital. Si se supera, se revisa el funcionamiento antes de ampliar el uso de la app.
- Que más pacientes usen la app puede liberar huecos presenciales, esto es hipótesis que se deberá de comprobar con métricas apropiadas.

## 3. Calidad de imagen según tono de piel, edad y zona corporal

**Problema.** El módulo de calidad no solo valora nitidez, también exposición, contraste y color. Si rechaza más fotos de pieles oscuras, esas personas repiten capturas y se retrasan, un sesgo que una métrica global no refleja.

**Cómo lo afrontamos.**

- Los mínimos de robustez se exigen por fototipo, rango de edad y zona anatómica, además de en global.
- Un rechazo nunca deja al paciente sin salida: tras ciertos intentos fallidos, el caso puede pasar a cita presencial.

## 4. Reclamaciones y revisión de casos urgentes

**Problema.** Un plazo de respuesta de 7 días es incompatible con un caso rojo mal clasificado, que tiene un máximo de 14 días. Además, quien no usa la app debe poder reclamar igualmente.

**Cómo lo afrontamos.** Se separan dos procesos:

- **Revisión clínica del caso.** Si el paciente o el médico detectan una posible clasificación errónea, el médico revisa el caso y decide su prioridad. No depende del equipo de TrIAderma. Para posibles errores en casos rojos o amarillos, el objetivo es resolverlo en un máximo de 48 horas. Mientras tanto, el caso pasa a prioridad manual.
- **Reclamación al sistema.** Sirve para corregir el modelo o la aplicación. Acuse de recibo en 24 horas y respuesta inicial en 7 días.

Canales disponibles sin necesidad de usar la app: mostrador del centro de salud, el médico en nombre del paciente, teléfono de contacto y el correo de TrIAderma.

Si los médicos señalan errores frecuentes en casos rojos, se activa el protocolo de pausa del sistema.

## 5. Enfermedades que se presentan de forma distinta según tono de piel y sexo

**Problema.** Equilibrar el número de imágenes por grupo no basta si la enfermedad cambia de aspecto o de localización. Por ejemplo, en pieles oscuras el melanoma es proporcionalmente más frecuente en palmas, plantas y uñas, y signos como el eritema se aprecian peor. La localización también varía entre mujeres y hombres. Estos ejemplos deben confirmarse con los dermatólogos del proyecto.

**Cómo lo afrontamos.**

- Cada patología crítica se evalúa por fototipo, por zona anatómica, por sexo y por edad. La lista de patologías críticas la fija un comité dermatológico.
- Donde no hay datos suficientes para medirla, el sistema no clasifica por su cuenta: devuelve baja confianza y el caso pasa a revisión médica.
- Se avisa al médico de la tasa de acierto esperada según tono de piel, zona y edad.

## 6. Etiquetado de los datos para auditar la equidad

**Problema.** Auditar el rendimiento por subgrupos exige etiquetas de fototipo, sexo, edad y zona que muchos conjuntos de datos no incluyen.

**Cómo lo afrontamos.**

- **Fototipo.** Lo asignan dermatólogos del hospital colaborador o del entorno de datos del EHDS: dos por imagen y un tercero si discrepan. Se mide y se publica el grado de acuerdo entre ellos. La escala principal es Fitzpatrick (I a VI).
- **Sexo y edad.** Se toman de la historia clínica, no se deducen de la foto.
- **Origen étnico.** No se etiqueta, no consideramos que se sea clínicamente relevante, conociendo ya el fototipo de piel.
- Con datos del EHDS, todo el etiquetado se hace dentro del entorno de procesamiento seguro.
- En uso real, el médico confirma el fototipo en el expediente del paciente, y ese dato alimenta la auditoría.
- Si no hay etiquetas fiables no se puede auditar la equidad y, por tanto, no se despliega el sistema.

## 7. Falsos negativos: casos rojos clasificados como verdes

**Problema.** La sensibilidad exigida antes de producción no garantiza que no ocurran fallos en el uso diario, y un caso rojo en la cola verde puede esperar demasiado.

**Cómo lo afrontamos.**

- **Verde exige confianza alta.** Ante la duda, el caso sube como mínimo a amarillo. El coste son más falsos positivos, que se absorben con telecita antes que con cita presencial.
- **Los verdes también tienen plazo.** Máximo de XX días desde la apertura del caso para entrar en el proceso de teledermatología y primera petición de foto de seguimiento como tarde a los XX días. El seguimiento continuo puede informar de un rojo mal clasificado.
- **Revisión humana de verdes.** El médico de cabecera valida cada clasificación, y un dermatólogo revisa una muestra aleatoria de verdes (un 5 %) y todos los de baja confianza.
- **Aviso de empeoramiento.** El paciente puede indicar que la lesión ha cambiado (sangra, crece, cambia de color). Esto sube la prioridad y solicita una foto nueva de inmediato. La app muestra estas señales de alarma.
- **Medición en producción.** Se registra qué porcentaje de verdes se reclasifican a amarillo o rojo y cuánto tardan. Si se supera lo observado en validación, se activa el protocolo de pausa.

---

## Limitaciones conocidas

- Sin fotografía, el sistema no puede evaluar la gravedad visual de un caso.
- Las cifras de este documento son objetivos pendientes de validación.
- El despliegue depende de la colaboración con un hospital y con dermatólogos.
- La brecha digital se reduce con la captura asistida en el hospital y el modo guiado, pero no desaparece.
