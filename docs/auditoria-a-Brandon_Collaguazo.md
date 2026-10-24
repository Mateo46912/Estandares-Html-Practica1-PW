
# Informe de auditoría - Black Cat Café

## Expectativas de la auditoría

### Requisito Base 2 - Formulario accesible

Se espera que todos los campos del formulario tengan
bien asignadas las etiquetas y estén correctamente
asociadas mediante los atributos `for` e `id`.


### Requisito Base 5 - Contraste de colores

Se espera que los textos tengan un contraste mínimo de
4.5:1 para cumplir el nivel AA de accesibilidad, tanto
en modo claro como en modo oscuro.


### Requisito Base 6 - Navegación con teclado

Se espera que los enlaces del menú tengan un nombre
accesible lo que permitiría identificar su destino mediante
el 'tab' y permitiría que el narrador los identifique



## Revisión general

Se revisaron los requisitos base y específicos de la ficha N.º 7 de Black Cat Café. Se comprobó en el código la existencia de etiquetas semánticas, la estructura de los encabezados, la tabla con los elementos solicitados, los campos del formulario, las imágenes con texto alternativo y el uso de Grid, Flexbox y variables CSS. También se revisó la existencia del campo para subir archivos con tipos restringidos, el breakpoint de 1024 px y el modo oscuro mediante `prefers-color-scheme`. Se daba por hecho que estos elementos estaban implementados correctamente, durante la revisión del código no se identificaron otros problemas estructurales, a excepción de los problemas especificados a continuación. Los chequeos de validaciones W3C de HTML y CSS no dieron ningún error.

## Hallazgos encontrados

| N.º | Requisito | Ubicación (archivo y línea o selector) | Hallazgo | Norma que incumple | Evidencia | Severidad |
|---|---|---|---|---|---|---|
| 1 | Base 6: navegación con teclado y accesibilidad | `index.html`, líneas 17-22 | Los enlaces del menú están vacíos y no tienen texto que permita identificar a qué sección dirige cada uno | WCAG 2.2, criterios 2.4.4 y 4.1.2 | [Código HTML](evidencias/Evidencia_Menu_Html.png) / [DevTools - Accesibilidad](evidencias/Evidencia_Menu_Devtools_Accesibilidad.png) / [Navegación visual](evidencias/Evidencia_Menu_Visualmente.png) | Alta |
| 2 | Base 2: formulario accesible | `index.html`, líneas 83-87 | La etiqueta asociada al correo es `for="nombre"`, pero el id del correo es `id="correo"`. Por eso, la etiqueta está asociada al campo del nombre y el correo queda sin nombre accesible. | WCAG 2.2, criterios 1.3.1, 3.3.2 y 4.1.2 | [Código HTML](evidencias/Evidencia_Etiqueta_Correo_Html.png) / [DevTools - Accesibilidad](evidencias/Evidencia_Etiqueta_Correo_Devtools.png) / [Prueba de foco](evidencias/Evidencia_Etiqueta_Correo_Foco.png) | Alta |
| 3 | Base 5: contraste de colores | `estilos.css`, líneas 4, 14 y 183-185 | El botón "Enviar Solicitud" utiliza texto blanco sobre el color `--color-primario`. En modo claro tiene un contraste de 4.16:1 y en modo oscuro de 2.84:1. Ambos valores son inferiores al mínimo de 4.5:1 exigido en temas de accesibilidad. | WCAG 2.2, criterio 1.4.3 (Contraste mínimo, nivel AA) | [Contraste modo claro](evidencias/Evidencia_Contraste_Claro.png) / [Contraste modo oscuro](evidencias/Evidencia_Contraste_Oscuro.png) | Media |



## Validaciones W3C

HTML: Validado con W3C Nu HTML Checker, sin errores ni advertencias.

CSS: Validado con W3C CSS Validator (CSS nivel 3 + SVG), sin errores.

Evidencias:

- [Validación HTML](evidencias/Evidencia_Validacion_HTML.png)
- [Validación CSS](evidencias/Evidencia_Validacion_CSS.png)



