# 10 casos extremos que pueden romper nuestro modelo


## 1. Calidad de las fotos
### Problema
Nuestro modelo proporciona los mejores resultados posibles suponinendo que las imágenes tiene una calidad
decente. Sin embargo, si la calidad no es la mejor, o la iluminación es contraproducente (flash, falta de
luz, etc...) la coloración de la piel cambia en dicha imagen, pudiendo afectar a las decisiones del modelo.

### Solución
Nuestra interfaz vendría con unas pautas para guiar al usuario e intentar asegurar que tomase la mejor
fotografía posible. Podría incluir ayudas para centrar la imagen, asegurar que la enfermedad quede bien
reconocible, etc...


## 2. Tonalidad de la piel
### Problema
Como se ha mencionado previamente en varios apartados, este tipo de modelos tienen a fallar más en personas
con tonos de piel más oscuros. Esto se debe a que, en general, en personas con la piel más oscura se tarda
más en detectar las enfermedades dermatológicas, en etapas más avanzadas. Esto provoca una diferencia en la
cantidad de datos en etapas tempranas.

### Solución
Intentar obtener datos de entrenamiento lo menos sesgados posibles, equilibrando el número de muestras.
Esto, aún así, puede no ser suficiente, así que podría tener un sistema de detección del color de piel
para poder informar al especialista sobre el porcentaje de error.


## 3. Historial corrupto o falsificado
### Problema
También se puede dar el caso en el que el usuario proporciona un historial médico con errores (por las
razones que fueran), o directamente falsificado. Ante esto, el modelo (por razones obvias) no sería
capaz de deducir correctamente la situación del paciente.

### Solución


## 4. Analíticas corruptas o falsificadas
### Problema
Al igual que con el historial médico, un paciente puede enviar datos erróneos o falsificados de unas
analíticas, por ejemplo para hacer creer al especialista que no hay ningún problema (o viceversa,
como hace la gente para obtener medicamentos innecesarios). Ante esto, nuestro modelo tampoco sería
de ayuda.

### Solución
Aqui, nuestro modelo podría tener un paso de verificación. A diferencia del historial, las analíticas
son un poco más fáciles de verificar, ya que los resultados están relacionados entre sí. En el caso de
que la falsificación fuera extremadamente profesional y realista, ahí nuestro modelo ya no podría hacer
nada.


## 5. Imagen falsificada
### Problema
El paciente podría enviar imágenes que no fueran de su piel, como kiwis. Ante imágenes que no
correspondieran al tema tratado, el modelo podría devolver salidas inesperadas y desorbitadas.

### Solución
Enviar fotos desde distintos ángulos que permitan verificar el elemento que se está fotografiando.

## 6. Ignorar el seguimiento
### Problema
Además, el paciente podría decidir ignorar los consejos del especialista al cargo y del modelo,
abandonando el seguimiento de su enfermedad. El modelo por tanto perdería información clave del
desarrollo, ya que si el paciente decidiese reanudar el seguimiento, no contaría con el contexto
intermedio del periodo de tiempo que perdió.

### Solución
El modelo podría detectar la falta de actividad, y en caso de superar un umbral específico, podría
alertar al especialista al cargo y dejarle saber que su paciente no está cooperando. De esta manera,
el especialista tomaría las medidas que considerase necesarias. También podríamos mandar al búho de
Duolingo a casa del paciente para que le diese una lección...

## 7. Enviar fotos de otras patologías en el seguimiento
### Problema
Si en el seguimiento el paciente envía foto de otra patologías, se pueden alterar los resultados gravemente.

### Solución:
El modelo es capaz de diferenciar entre patologías, si añadimos que en el seguimiento también se evalua si ha habido un cambio,en caso positivo avisar al paciente que no es la misma enfermedad, y si no lo ha hecho a posta ofrecer pedir otra cita.

## 8. Falsificar síntomas
### Problema
El usuario el redactar los síntomas puede falsificarlos para agravar el problema.

### Solución
Si la gravedad de la imagen no cuadra con los síntomas derivar a un análisis médico directamente para evitar problemas con la IA.

## 9. Caída de servidores
### Problema
Si los servidores se caen los usuarios no podrán ver sus recetas ni pedir citas.

### Solución
Permitir un backup de las recetas en el móvil para que el usuario las pueda seguir viendo, además el recordatorio puede ser simplemente local. Respecto a las citas se avisará al usuario de que la IA no va y que vaya presencialmente al médico más cercano si es muy urgente.

## 10. No hay permisos de camara
### Problema
Nuestro modelo no sirve si los usuarios no dan permisos de cámara, lo cual es normal que no se fíen y no lo den

### Solución
Se podría ofrecer que redacten solo los síntomas pero obligarle a ir al médico de cabecera, básicamente pedir cita de forma corriente, ya que no podemos asegurar nada.
