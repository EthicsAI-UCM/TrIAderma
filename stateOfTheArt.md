# Paradigma actual

En la lista OASI donde se recopilan numerosos algoritmos, existe el _Epic Deterioration Index_, que es un índice automatizado que se uso para ponderar gravedaden la época del covid y no saturar así los servicios de emergencias. Al final este algoritmo, como se menciona en otros documentos, no valora la evolución del paciente ni su historial médico, solo la situiación actual.

Sus características son las siguientes:
- Pondera con Ml la demografia, las constantes vitales y resultados del laboratorio
- El modelo devuelve un real entre 0 y 100
- Algunos laboratorios y hospitales tras distintos experimentos han creado reglas lógicas alrededor de este resultado:
_**DI score between 0 and 30 as “low risk,” between 31 and 60 as “medium risk,” and between 61 and 100 as “high risk” for deterioration.6**_

Al final esta formula como se menciona en el apartado de modelos es muy útil para ponderar gravedad, ya que podemos añadir constantes vitales con la imagen para dar una gravedad. Lo que es espacialmente util para el segundo modelo que valora el historial médico ya que le simplificamos enormemente la entrada.

**referencias usadas**
1. https://docs.google.com/spreadsheets/d/1T4VYr46wNiD_Y5cT6nt8xsXfcCTWJ94K8oWHcGHfRjk/edit?gid=123983785#gid=123983785 (Fila 71)
2. https://undark.org/2021/05/27/health-care-algorithm-promise-peril/
3. https://www.sciencedirect.com/science/article/pii/S0022480425000423