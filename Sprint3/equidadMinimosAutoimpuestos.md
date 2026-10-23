# Definición general

Por el artículo 10 del AI Act, los modelos deben someterse a pruebas específicas para detectar brechas de rendimiento entre subgrupos antes de salir al mercado (cláusula 7). En este marco, se crea un informe armonizado con la Comisión Europea, ISO/IEC TR 24027:2021[1], que define métricas específicas y requisitos técnicos que se deben cumplir.

## Métricas de equidad [2]

Estas son algunas métricas de equidad que se definen en el informe ISO, pero no son las únicas que debería cumplir el modelo:

- Demographic Parity: Mide que la probabilidad de que el modelo prediga cierta patología no cambia si está condicionada a que se predice para pacientes de una u otra condición (en nuestro caso pieles oscuras/claras o de personas jóvenes/ancianas). No tiene en cuenta la etiqueta real. $P(\hat{Y}=1∣A=a)=P(\hat{Y}=1∣A=b)∀a,b$

- Equalized Odds: En este caso, se mide que la tase de verdaderos positivos y la de falsos positivos sea igual para todos los grupos.
  
  - True Positive Rate (TPR) Equality: $P(\hat{Y}=1∣Y=1,A=a)=P(\hat{Y}=1∣Y=1,A=b)∀a,b$
  - False Positive Rate (FPR) Equality:
    $P(\hat{Y}=1∣Y=0,A=a)=P(\hat{Y}=1∣Y=0,A=b)∀a,b$



## Mínimos autoimpuestos

Aparte de cumplir con las métricas descritas arriba, hemos descrito unos mínimos que debe cumplir nuestro modelo antes de llevarlo a producción:

1. Mínimo de sensibilidad en patologías críticas: Exigiríamos una sensibilidad superior al 99% para casos críticos (melanoma, melanome in situ, carcinomas). Para lesiones benignas bastaría con una especifidad > 85%. Estos números son completamente orientativos.

2. El modelo mantendrá una degradación máxima del $5\%$ en la sensibilidad global frente a artefactos comunes de la práctica clínica (vello corporal moderado, variaciones de iluminación de $\pm30\%$ o leve desenfoque de movimiento), garantizando mediante aumentación de datos que las máscaras de segmentación mantengan un índice Dice $\ge 0,85$ sobre lesiones parcialmente ocluidas (hasta un máximo del $25\%$ de oclusión perimetral). Como guardarraíl adicional, se implementará un módulo que evaluará si la imagen cumple unos mínimos de calidad. También, se trabajará con los datos crudos del sensor para reconstruir la mejor imagen posible.

3. Tiempos máximos en la cola de triaje (estándar de la **Vía Rápida Oncológica del Servicio Nacional de Salud (SNS)**). Debemos garantizar que bajo un escenario de alta afluencia (en las pruebas será simulado), el sistema de cola garantiza en todo momento que los pacientes con riesgo crítico reciban atención especializada dentro de unos plazos:
   
   1. **Alerta Roja / Alta Sospecha (Melanoma o Carcinoma Invasivo):** Tiempo máximo de espera en cola $\le 14$ días (2 semanas) desde que Atención Primaria sube la imagen hasta la citación/confirmación en Dermatología.
   
   2. **Alerta Amarilla / Lesión Dudosa:** Tiempo máximo en cola $\le 30$ días.
   
   3. **Alerta Verde / Patología Benigna o No Crítica:** Integrada en el flujo ordinario de teledermatología según disponibilidad del hospital.





https://cdn.standards.iteh.ai/samples/77607/c0664994eace4bd597db80bb10c18dec/ISO-IEC-TR-24027-2021.pdf [1]

https://www.geeksforgeeks.org/artificial-intelligence/fairness-metrics-demographic-parity-equalized-odds/ [2]


