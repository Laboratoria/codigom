# HTML semántico

Los `div` son un excelente recurso para agrupar contenido de forma lógica y con ello poder darle estilos particulares a ciertas secciones. Por muchos años se usaron los `div` como único recurso para agrupar contenido. Sin embargo, muchas web tienden a tener una estructura similar y a contener elementos comunes. Por ejemplo, casi todos los productos en la web tienen una cabecera, un menú de navegación, un contenido principal, contenido secundario, un footer, etc.

Revisando la documentación del MDN sobre [estructura web y documentación](https://developer.mozilla.org/es/docs/Learn/HTML/Introduccion_a_HTML/estructura) podemos extraer:

> En nuestro código HTML, podemos crear secciones de contenido basadas en su funcionalidad — usando elementos que representen las diferentes secciones del contenido descritas anteriormente sin ambigüedad, de forma que las tecnologías de ayuda y los lectores de pantalla puedan reconocer esos elementos y asistir en tareas como "encontrar el menú de navegación", o "encontrar el contenido principal".

En la siguiente imagen vemos como era el uso de HTML antes, como se puede observar hay muchos `<div>`. Ahora gracias a la semántica de HTML 5 podemos usar nuevas etiquetas para estructurar correctamente una página web.

![](../assets/2024-03-13-09-24-23-image.png)

Para implementar estas secciones semánticas, HTML dispone de etiquetas adecuadas que podemos usar para representar estas secciones. Revisa el link anterior e investiga el uso de los siguientes elementos semánticos:

- `<header>`
- `<nav>`
- `<main>`
- `<aside>`
- `<article>`
- `<section>`
- `<figure>`
- `<footer>`

---