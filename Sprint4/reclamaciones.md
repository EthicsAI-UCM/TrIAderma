# Respuesta a reclamaciones

## Introducción
Para poder aproximar el curso de acción ante reclamaciones de propiedad intelectual, es preciso
definir primero las posibles fuentes de conflicto, es decir, partes de nuestro proyecto
potencialmente vulnerables a reclamación. Estas son:
- Marca:
    - Nombre
    - Logo

- Modelo: Los diferentes tipos de modelos pre-entrenados que usemos
- Datos: La fuente y los derechos de uso de dichos datos.

Cabe destacar que tendríamos asignada una dirección de correo destinada simple y únicamente a
reclamaciones, para recibirlas y posteriormente contactar al individuo/entidad sobre el
método de acción consecuente. Revisaríamos dicho correo a diario, atentos a cualquier novedad,
para poder resolver los conflictos de la manera más rápida posible.

## Casos

### Marca

#### Nombre
Hemos investigado en la [OEPM](https://consultas2.oepm.es/LocalizadorWeb/busquedaDenominacion),
y no han saltado colisiones por nuestro nombre, por lo que la marca no está registrada. Aun así,
en caso de recibir una reclamación, nos pondríamos en contacto para poder solventar el problema.
En caso de ser una reclamación correcta, tendríamos que pensar un nuevo nombre para el producto,
asegurándonos de que el nuevo no fuese propenso a nuevas reclamaciones.

#### Logo
Nuestro ha sido creado desde 0 por nosotros. Todo lo que se ve en la imagen ha sido creado a mano,
por lo que no nos podrían meter una reclamación derechos. El único caso extremo sería alegar que
el logo es muy similar al de una entidad concreta. Ante esto, en nuestra defensa diremos que usamos
figuras sencillas (triángulo, círculos, EKG, lineas, degradado de colores normales). Al ser figuras
tan extendidas en los ámbitos de medicina y/o tecnología, las oficinas de patentes y marcas rara
vez conceden exclusividad sobre ellas. Investigando en internet, no hemos encontrado iconos lo
suficientemente parecidos como para que nos pudieran poner una reclamación.

### Modelo
Los algoritmos matemáticos no pueden estar sujetos a patentes, pero los modelos pre-entrenados sí
pueden estar regsitrados por una entidad. Estos modelos están mencionados [aquí](./Licencias.md).
Por permisividad, hemos seleccionado SAM (versión 2) para nuestro proyecto. Por tanto, si incluimos
los avisos obligatorios de la licencia Apache 2.0, Meta no podría reclamarnos nada. Si aún así
recibiésemos una reclamación por el uso de algún método, tendríamos que plantear un cambio
estructural en el modelo, y volover a entrenarlo, lo que tardaría un tiempo considerable. Mientras,
habría que cerrar la app.

### Datos
En caso de reclamación sobre los datos, sería también complejo, ya que serían una parte clave de
nuestra app. Por tanto, habría que re-entrenar de 0 con datos nuevos que no estuviesen sujetos a
esta reclamación, y eso podría llevar también mucho tiempo.

# Bibliografía
https://share.gemini.google/OXF482hCVuY5
