# Guía de contribución

¡Gracias por tu interés en **TrIAderma**! Antes de empezar, ten en cuenta cómo es este repositorio:

> TrIAderma es un **proyecto universitario teórico**. No contiene ninguna implementación funcional (solo documentación y un prototipo estético) y no sirve para ejercer el triaje clínico. Consulta el [README](README.md) y su aviso médico.

Por eso, las contribuciones son sobre todo **documentación, análisis legal y ético y mejoras del prototipo**, no código de producción.

Al participar aceptas cumplir nuestro [Código de conducta](CODE_OF_CONDUCT.md).

## Estructura del repositorio

| Carpeta | Contenido |
|---|---|
| `Sprint1/` | Idea, estado del arte, actores, paradigma y riesgos éticos |
| `Sprint2/` | Especificaciones, robustez, personalización, riesgos y `mockup/` |
| `Sprint3/` | Usuarios, sesgos, equidad, compromisos de diseño y límites |
| `Sprint4/` | Licencias, uso de marca y respuesta a reclamaciones |

Las carpetas `Entrega*` y `entrega1` contienen los PDF y repartos de tareas de cada entrega. Se consideran versiones cerradas: si ves algo que corregir en ellas, abre un issue en lugar de editarlas directamente.

## Formas de contribuir

- Señalar errores, erratas o inconsistencias en la documentación.
- Aportar fuentes, normativa o casos que mejoren el análisis legal y ético (por ejemplo, EU AI Act, MDR, EHDS, RGPD).
- Revisar los análisis de sesgos, equidad y riesgos y proponer mejoras.
- Mejorar la accesibilidad y la usabilidad del prototipo (`Sprint2/mockup/`).
- Corregir enlaces rotos o la redacción.

## Cómo proponer un cambio

1. Busca si ya existe un [issue](../../issues) sobre el tema.
2. Si es un cambio pequeño (errata, enlace), haz un fork y abre directamente un pull request.
3. Si es un cambio de fondo (una conclusión, una decisión de diseño o una licencia), abre antes un issue para discutirlo.
4. Crea una rama descriptiva desde `main`:
   ```bash
   git checkout -b docs/corrige-licencias
   ```
5. Haz commits pequeños y claros, y abre el pull request usando la plantilla.

## Convenciones

- **Idioma:** el proyecto está en español. Mantén ese idioma salvo en términos técnicos o legales habituales.
- **Formato:** Markdown. Un documento por tema, dentro de la carpeta del sprint correspondiente.
- **Fuentes:** cita la normativa y las fuentes que uses y añádelas a la sección de bibliografía del documento.
- **Commits:** mensajes en imperativo y concisos (por ejemplo, `Corrige la tabla de licencias de datos`).

## Uso de herramientas de IA

Este proyecto documenta el uso de IA en cada entrega. Si usas una herramienta de IA (por ejemplo, para redactar o generar código del prototipo), indícalo en el pull request y enlaza la conversación si es posible.

## Qué no se debe subir

- **Datos de salud ni imágenes clínicas de personas reales.** Tampoco como ejemplo ni en capturas.
- Datos o imágenes con licencia incompatible con Apache 2.0 o que no puedas redistribuir.
- Credenciales, claves o datos personales.

## Licencia y marca

- Al contribuir aceptas que tu aportación se distribuya bajo la licencia [Apache 2.0](LICENSE) del proyecto.
- El nombre y el logo de TrIAderma tienen reglas de uso propias. Consúltalas en [`Sprint4/usoMarca.md`](Sprint4/usoMarca.md) y no modifiques el logo.

## Revisión

Un mantenedor revisará tu pull request y puede pedir cambios. Es parte normal del proceso.

## Dudas

Abre un issue con la etiqueta `question` o escribe a support@triaderma.com.
