# Compromisos de diseño

Como se ha podido observar en `sesgos.md` hay 3 sesgos principales en dermatología, etnias género y edad. Además de la imposibilidad de un discapacitado o anciano de usar la app que se observó en el sprint 2.

Por tanto podemos decir que debemos tener varios compromisos que cuimplir:

### 1. Compromiso con la Equidad Étnica y la Inclusión de Pieles Oscuras

* **Mitigación del sesgo:** Superar el desbalance de datos que sobre-representa a las pieles claras y causa altas tasas de error o falsos diagnósticos en etnias minoritarias.
* **Compromiso técnico:** Nos comprometemos a no emplear únicamente datos sintéticos o duplicaciones simplistas para balancear el modelo. Aprovecharemos el marco del **EHDS (European Health Data Space)** o alianzas estratégicas con Institutos de Investigación Sanitaria (IIS) para curar e integrar datasets reales, diversos e imparciales en fototipos de piel.
* **Garantía clínica:** Auditaremos el modelo para asegurar que aprenda estructuras dermatológicas complejas y no meros patrones de contraste o color de piel, evitando clasificar tonalidades oscuras como patologías.

### 2. Compromiso con la Representación de Género y Anatomía Diferenciada

* **Mitigación del sesgo:** Corregir el sesgo de datos de género y la disparidad en la presentación clínica de patologías (como la alta prevalencia de melanomas en extremidades inferiores en mujeres frente al torso en hombres).
* **Compromiso técnico:** Reequilibrar las muestras de entrenamiento hacia la paridad ($50/50$) y etiquetar explícitamente variables anatómicas y de sexo biológico.
* **Garantía clínica:** Auditaremos que las tasas de sensibilidad y error del algoritmo sean equivalentes entre hombres y mujeres, asegurando que no se subestimen o sobreestimen lesiones según la zona corporal analizada.

### 3. Compromiso de Accesibilidad e Inclusión Tecnológica para el Colectivo Anciano

* **Mitigación de la brecha digital:** Evitar que las personas mayores se sientan excluidas o frustradas al intentar usar la tecnología médica.


* **Compromiso de diseño (UX/UI):** Implementar un **Modo Guiado** con explicaciones sencillas paso a paso y asistencia asistida por voz para capturar fotografías de manera correcta.


* **Integración con vías tradicionales:** Mantenemos la vía de citación y atención presencial tradicional para garantizar que la app sea un complemento accesible y no una barrera infranqueable de atención.

### 4. Compromiso de Protección Integral y Gestión Tutelada en el Caso Infantil

* **Mitigación de barreras de acceso y desbalance de edad:** Responder a la falta de representación de datos en edad pediátrica/infantil y a la imposibilidad legal del menor para solicitar citas de forma autónoma.
* **Compromiso funcional:** Permitir la vinculación directa de la cuenta del adulto/tutor legal autenticado para gestionar la salud del menor de forma segura y supervisada.
* **Garantía clínica:** Ponderar con cautela los diagnósticos en pieles infantiles o de bebés, reconociendo sus diferencias morfológicas frente a la piel adulta.

### 5. Compromiso con la Objetividad Clínica y el Diseño Accesible Universal

* **Objetividad:** Mantener la medicina como una ciencia objetiva, rechazando la personalización de criterios clínicos en función de creencias o valores.


* **Cumplimiento de estándares:** Seguir pautas de diseño accesible (WCAG) que incluyan alternativas de texto para contenido visual, tamaño de texto personalizable e interfaces intuitivas para personas con discapacidades.



---

### Resumen del Flujo de Garantía de Equidad

$$\text{Curación de Datos Diversos (EHDS/IIS)} \longrightarrow \text{Auditoría de Sesgo por Subgrupo} \longrightarrow \text{Interfaz Accesible y Modo Guiado} \longrightarrow \text{Respaldo Sanitario Presencial}$$