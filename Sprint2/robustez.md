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
