# 10 casos extremos que pueden romper nuestro modelo


## 1. Calidad de las fotos
### Problema
Nuestro modelo proporciona los mejores resultados posibles suponinendo que las imágenes tiene una calidad
decente. Sin embargo, si la calidad no es la mejor, o la iluminación es contraproducente (flash, falta de
luz, etc...) la coloración de la piel cambia en dicha imagen, pudiendo afectar a las decisiones del modelo.

### Solución


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


## 3. ...
