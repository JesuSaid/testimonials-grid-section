# Buenas prácticas · Testimonials grid section

El reto consiste en presentar cinco testimonios con HTML y CSS. La guía original fija la paleta, la familia Barlow Semi Condensed, los pesos 500 y 600 y el cuerpo de 13 px. [Guía de estilos](./style-guide.md)

## Estructura y lectura

- En el HTML inicial, los cinco testimonios son texto corrido. El primer hito consiste en poder leer la página sin CSS e identificar quién habla y qué dijo. Mantener el orden móvil del documento, de Daniel a Kira.
- Como en *Social proof section*, agrupar cada cita con su autor. Un encabezado principal accesible da nombre al conjunto. Usar `blockquote` para las palabras de la persona y colocar la atribución fuera de la cita. Si el nombre ya acompaña al retrato y este no aporta más información, usar `alt=""`.
- Como en *Four card feature section*, compartir los estilos de tarjeta. Usar modificadores para las variantes y reservar CSS Grid para la posición de cada tarjeta en el conjunto. El adorno de comillas de Daniel aparece en escritorio y se puede aplicar como imagen de fondo.

## Referencias para el CSS

Las páginas «01 / References» y «02 / Style Guide» de Penpot reúnen las referencias y sus medidas. Los tamaños siguientes son estimaciones de los JPG, salvo el cuerpo de 13 px indicado en la guía original.

| Texto | Tamaño | Interlineado | Peso |
| --- | ---: | ---: | ---: |
| Frase destacada | 20 px | 24 px | 600 |
| Nombre | 13 px | 16 px | 500 |
| Verified Graduate | 11 px | 13 px | 500 |
| Cuerpo de la cita | 13 px | 18 px | 500 |

- A **375 px**, la referencia muestra una columna de 305 px, márgenes laterales de 35 px y 32 px entre tarjetas. Dejar que la columna se estreche a 320 px y que cada tarjeta crezca con el texto.
- A **1440 px**, hay cuatro columnas con 32 px entre columnas y 24 px entre filas. Daniel y Patrick ocupan dos columnas cada uno. Kira ocupa las dos filas de la última columna.
- El relleno de referencia es de 32 px, el radio de 8 px y los retratos miden aproximadamente 28 px. Hay 16 px entre la frase destacada y el cuerpo de la cita.
- Definir en `:root` las decisiones reutilizadas de color, tipografía y espacio. Las variantes pueden cambiar el fondo y el color del texto mediante propiedades personalizadas de la tarjeta. Comprobar el contraste del estado «Verified Graduate» sobre cada fondo.
- Empezar por una columna. Elegir las media queries con `min-width` cuando el texto y los espacios admitan más columnas. Usar propiedades lógicas para márgenes y rellenos. Una función como `clamp()` resulta útil si permite ajustar los márgenes sin comprimir las citas.
- Comprobar en DevTools la fuente y el peso realmente renderizados antes de ajustar anchos para forzar un salto de línea.

## Hitos de Git

El repositorio ya tiene un commit de preparación. Para los siguientes avances, escribir el título en inglés y agrupar los cambios que se puedan revisar juntos.

| Hito | Ejemplo de commit |
| --- | --- |
| Los cinco testimonios se entienden sin CSS | `feat: add semantic testimonial markup` |
| La fuente y los estilos compartidos cargan | `feat(ui): add typography and base styles` |
| Las cinco tarjetas se leen en una columna | `feat(ui): style mobile testimonial cards` |
| La cuadrícula reproduce la composición de escritorio | `feat(ui): add responsive testimonial grid` |
| Los README muestran el resultado y los aprendizajes | `docs: document the testimonials grid solution` |

Antes de cada commit, revisar `git status` y el diff preparado con `git diff --cached`. Comprobar los espacios sobrantes con `git diff --cached --check`. Añadir un cuerpo al commit si ayuda a explicar una decisión, por ejemplo qué limitaba el ancho mínimo de una columna.

## Revisión del resultado

- Probar a 320, 375, 768 y 1440 px y a ambos lados de cada breakpoint. Revisar desbordamiento horizontal, líneas cortadas y orden de lectura. Comparar móvil y escritorio con los JPG del reto.
- Aumentar el zoom al 200 % y al 400 % y comprobar que se puede leer hasta el final del testimonio de Kira. Validar el HTML y el CSS y revisar la carga de retratos, fuentes y fondo decorativo.
- Al cerrar el reto, actualizar los README en español e inglés con capturas de la implementación, decisiones de Grid, aprendizajes y enlaces reales. [Repositorio](https://github.com/JesuSaid/testimonials-grid-section) · [Sitio publicado](https://jesusaid.github.io/testimonials-grid-section/)
