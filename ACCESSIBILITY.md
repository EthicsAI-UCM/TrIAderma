# Declaración de accesibilidad

## Compromiso

TrIAderma plantea una herramienta de triaje para pacientes de dermatología, un público muy diverso en edad, capacidades y familiaridad con la tecnología. Por eso la accesibilidad es un requisito de diseño: cualquier implementación futura deberá cumplir como mínimo las Pautas de Accesibilidad para el Contenido Web (WCAG) 2.2, nivel AA.

## Qué cubre esta declaración

Este es un proyecto teórico y **no existe todavía ninguna aplicación**. La declaración cubre lo que hay hoy en el repositorio:

- **Documentación en Markdown**, que se visualiza con GitHub.
- **Prototipo estético** en HTML (`Sprint2/mockup/mockupTrIAderma.html`), que se ejecuta de forma local.
- **PDF de las entregas** (`Sprint1/entrega1`, `Sprint2/Entrega2`, `Sprint3/Entrega3`).
- **Logo** (`logo.svg`).

## Entornos compatibles

- Documentación: la visualización estándar de GitHub, compatible con lectores de pantalla y navegación con teclado.
- Prototipo: navegadores web actuales. No se ha probado con una lista concreta de navegadores ni de tecnologías de asistencia.

## Estado actual

El prototipo es una maqueta visual y **no se ha sometido a una auditoría de accesibilidad**. No podemos afirmar que cumpla WCAG 2.2 AA.

## Limitaciones conocidas

- El prototipo no se ha probado con lectores de pantalla ni solo con teclado.
- Muchos botones del prototipo usan iconos, y no se ha comprobado que todos tengan un nombre accesible.
- Los iconos del prototipo son gráficos vectoriales (SVG) y no se ha verificado que los decorativos estén ocultos a las tecnologías de asistencia ni que los informativos tengan alternativa textual.
- No se ha comprobado el contraste de color ni el comportamiento al ampliar el texto.
- Los PDF de las entregas no se han revisado para comprobar si están etiquetados.
- El prototipo se generó en gran parte con una herramienta de IA y se ajustó a mano, sin una revisión de accesibilidad específica.

## Mejoras previstas

- Revisar el prototipo con una herramienta automática (por ejemplo, axe o Lighthouse) y con un lector de pantalla.
- Añadir nombres accesibles a los botones de iconos y comprobar el contraste.
- Incluir los criterios de accesibilidad en las especificaciones de la futura aplicación.

## Comentarios y reporte de barreras

Si encuentras una barrera de accesibilidad, avísanos:

- Abre un [issue](../../issues/new/choose) con la etiqueta `accessibility`.
- O escribe a **support@triaderma.com**.

Indica el archivo o la pantalla afectada, la tecnología de asistencia que usas (si procede) y qué te ha impedido hacer.

## Última revisión

Esta declaración se redactó el 6 de noviembre de 2026.
