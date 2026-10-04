## Cálculo de afectados
Partimos de la base de que los sistemas de clasificación de gravedad como el Deterioration Index han demostrado resultados
que se alejan de la perfecta clasificación. A nivel de episodio global del paciente, se obtuvo un AUROC de 0,685[1] lo que
asumimos que es una buena estimación de lo que podría ser el rendimiento de nuestro modelo.

### Resumen del impacto en 1 millón de pacientes (escenario conservador)

| Categoría | Proporción | N.º de pacientes afectados al año |
| :--- | :--- | :--- |
| **Casos graves no detectados** (Falsos Negativos) | ~50% - 60% de los enfermos | **20.000 – 30.000 pacientes** en riesgo sin alerta. |
| **Alertas innecesarias / Errores** (Falsos Positivos) | ~90% - 96% de las alertas | **200.000 – 500.000 pacientes** sobre-diagnosticados / estresados. |
| **Atención anticipada correcta** (Verdaderos Positivos) | ~4% - 10% de las alertas | **20.000 – 30.000 pacientes** beneficiados realmente. |

Con estos datos vemos de primeras que las alertas innecesarias serían demasiadas, lo que en esencia sería un fracaso para
la liberación en la gestión que promete nuestro sistema (aún así obviamente es mejor que clasificar a mano 1M de pacientes).

## Actores y colectivos beneficiados
- Médicos de cabecera y el sistema de salud pública: El sistema alivia la saturación de las consultas al evitar que los médicos 
deban atender todas las citas presenciales y permitir la derivación de casos básicos a telecita.   

- Pacientes con patologías graves o evidentes: Al ordenar los huecos libres del dermatólogo según la importancia del caso,
los pacientes en riesgo crítico (por ejemplo, con melanomas fácilmente detectables por la IA) podrían recibir atención
mucho más rápido.

## Actores y colectivos perjudicados
- Pacientes con baja alfabetización digital y/o rechazo tecnológico: Es el caso de ancianos o personas que se han quedado
atrás con la tecnología. En estos casos, se verían obligadas a depender del personal sanitario para gestionar sus consultas
y su caso de forma manual (seguramente con mucha espera).
- Pacientes discriminados por el modelo: dado que seguramente no podamos asegurar la imparcialidad del modelo (los tonos de
piel oscuros tienen tendencia a una peor detección por parte de los modelos).

## Citas
1. https://pmc.ncbi.nlm.nih.gov/articles/PMC10366696/#H1-3-ZOI230708
