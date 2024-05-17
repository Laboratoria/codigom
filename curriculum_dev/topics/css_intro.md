# Introducción a CSS

## ¿Qué es CSS?

CSS (Cascading Style Sheets) es un lenguaje de estilos utilizado para describir la presentación de documentos escritos en HTML o XML. CSS se encarga de cómo se ven los elementos en una página web, permitiendo separar el código referente al contenido del de la presentación. Con CSS, se pueden aplicar estilos como colores, fuentes, espaciados, tamaños, y disposición de los elementos en la página, creando así diseños atractivos y profesionales.

### ¿Cómo es la Sintaxis Básica de CSS?

La sintaxis básica de CSS consiste en reglas formadas por **selectores** y **declaraciones**. Una regla CSS tiene el siguiente formato:

```css
selector {
  propiedad: valor;
}
```

- **Selector**: Indica qué elementos HTML se verán afectados por las reglas de estilo. Los selectores pueden ser de tipo, clase, ID, entre otros.
- **Declaraciones**: Dentro de las llaves `{}`, se colocan las propiedades y valores que se aplicarán a los elementos seleccionados. Cada declaración tiene una propiedad (qué aspecto se quiere modificar) seguida de dos puntos `:`, y un valor (cómo se quiere modificar ese aspecto) seguido de un punto y coma `;`.

#### Ejemplo de una Regla CSS Básica:

```css
p {
  color: blue;
  font-size: 16px;
}
```

En este ejemplo:

- El **selector** `p` selecciona todos los elementos `<p>` (párrafos) en el documento HTML.
- La **declaración** `color: blue;` establece que el color del texto de los párrafos será azul.
- La **declaración** `font-size: 16px;` establece que el tamaño de la fuente será de 16 píxeles.

## Selectores básicos

Los selectores básicos en CSS se utilizan para seleccionar y aplicar estilos a elementos HTML. Aquí hay una breve explicación de cada uno:

1. **Selector de Tipo**: Selecciona todos los elementos de un tipo específico. Ejemplo: `p` selecciona todos los párrafos `<p>`.

2. **Selector de Clase**: Selecciona todos los elementos con una clase específica. Ejemplo: `.miClase` selecciona todos los elementos con `class="miClase"`.

3. **Selector de ID**: Selecciona el elemento con un ID específico. Ejemplo: `#miID` selecciona el elemento con `id="miID"`.

4. **Selector Universal**: Selecciona todos los elementos. Ejemplo: `*` selecciona todos los elementos en la página.

5. **Selector de Atributo**: Selecciona elementos que tienen un atributo específico. Ejemplo: `[type="text"]` selecciona todos los elementos con `type="text"`.

### Ejemplos

```css
/* Selector de tipo */
p {
  color: blue;
}

/* Selector de clase */
.miClase {
  font-size: 16px;
}

/* Selector de ID */
#miID {
  background-color: yellow;
}

/* Selector universal */
* {
  margin: 0;
  padding: 0;
}

/* Selector de atributo */
[input[type="text"]] {
  border: 1px solid black;
}
```

## Reglas de Cascada y Herencia en CSS

CSS, o Cascading Style Sheets, utiliza un conjunto de reglas conocidas como "cascada" y "herencia" para determinar cómo se aplican los estilos a los elementos HTML. Estos conceptos son fundamentales para entender cómo funcionan y se priorizan las reglas de estilo en una página web.

Es posible que en algún momento descubras que el CSS que esperabas que se aplique a un elemento "no funciona". Esto puede ocurrir cuando has creado dos reglas que podrían aplicarse al mismo elemento. La cascada y la especificidad controlan qué regla se aplica cuando hay conflictos o superposición. Es posible que la regla que finalmente se aplica a tu elemento no sea la que esperas, por lo que es crucial entender cómo funcionan estos mecanismos.

### Cascada

En CSS, la cascada significa que el orden de las reglas es importante: cuando dos reglas tienen la misma especificidad, se aplica la que aparece última en el CSS.

En el siguiente ejemplo, hay dos reglas que pueden aplicarse a un h1. El h1 termina siendo azul porque estas reglas tienen la misma especificidad y, por lo tanto, se aplica la última.

En este ejemplo, el `h1` será azul porque la última regla en el CSS tiene prioridad.

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      h1 {
        color: red;
      }
      h1 {
        color: blue;
      }
    </style>
  </head>
  <body>
    <h1>Texto en h1</h1>
  </body>
</html>
```

### Especificidad

La especificidad determina cuál regla se aplica cuando diferentes selectores pueden afectar el mismo elemento. Básicamente, mide lo específico que es un selector:

- Un selector de elemento es menos específico y tiene una puntuación de especificidad más baja.
- Un selector de clase es más específico y tiene una puntuación de especificidad más alta.

Por ejemplo, si hay dos reglas que pueden aplicarse a un h1, este será rojo si una de las reglas usa un selector de clase, ya que esta tiene mayor especificidad, incluso si la regla con el selector de elemento está más abajo en el código.

Aquí, el `h1` será verde porque el selector de clase `.highlight` tiene mayor especificidad que el selector de elemento `h1`.

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      h1 {
        color: red;
      }
      .highlight {
        color: green;
      }
    </style>
  </head>
  <body>
    <h1 class="highlight">Texto en h1</h1>
  </body>
</html>
```

### Herencia

En CSS, la herencia significa que ciertos valores de propiedades establecidas para elementos padre son heredados por sus elementos hijo, mientras que otros no.

Por ejemplo, si un elemento tiene establecido el color y la fuente, todos sus hijos también tendrán esos valores, a menos que se les haya aplicado un color y una fuente diferentes.

Algunas propiedades, como el ancho, no se heredan. Si un elemento tiene un ancho del 50%, sus descendientes no tendrán automáticamente un 50% del ancho del padre, lo que evitaría complicaciones en el uso de CSS.

En este caso, el texto del párrafo `<p>` será de color púrpura y usará la fuente Arial porque hereda estos estilos del elemento padre `<div class="parent">`.

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      .parent {
        color: purple;
        font-family: Arial, sans-serif;
      }
    </style>
  </head>
  <body>
    <div class="parent">
      <p>Texto heredado</p>
    </div>
  </body>
</html>
```

## Valores y unidades

En CSS, el uso de valores y unidades depende del contexto y los objetivos del diseño.

> Por ahora no te compliques innecesariamente la vida intentado memorizar todo, simplemente ocúpate de comprender que hay diferentes maneras de abordar las necesidades. Poco a poco las irás incorporando a tu trabajo.

Aquí tienes un breve resumen:

### Unidades Relativas

1. **`em` y `rem`**:

   - **`em`**: Relativa al tamaño de la fuente del elemento contenedor.
   - **`rem`**: Relativa al tamaño de la fuente de la raíz (html).
   - **Recomendación**: Usar `rem` para tamaños globales y `em` para tamaños específicos que necesitan ser relativos al contexto local.

2. **Porcentajes (`%`)**:

   - Relativos al tamaño del elemento contenedor.
   - **Recomendación**: Útil para layouts flexibles y responsivos, especialmente en anchuras y alturas.

3. **Viewport Units (`vw`, `vh`, `vmin`, `vmax`)**:

   - **`vw`**: 1% del ancho del viewport.
   - **`vh`**: 1% de la altura del viewport.
   - **`vmin`**: 1% del menor entre el ancho y la altura del viewport.
   - **`vmax`**: 1% del mayor entre el ancho y la altura del viewport.
   - **Recomendación**: Ideales para diseños que se adapten al tamaño de la ventana del navegador, como en elementos de fondo o layouts fluidos.

### Unidades Absolutas

1. **Píxeles (`px`)**:

   - Valor absoluto que no cambia con el contexto.
   - **Recomendación**: Útil para bordes finos, sombras, y cuando se necesita precisión fija.

2. **Otros (pt, pc, in, cm, mm)**:

   - Usados principalmente en impresiones o cuando se necesita un tamaño exacto físico.
   - **Recomendación**: En diseño web, es raro su uso; `px`, `em`, `rem` y las viewport units son más comunes y flexibles.

### Unidades Funcionales

1. **`calc()`**:

   - Permite hacer cálculos con diferentes unidades.
   - **Recomendación**: Muy útil para combinaciones dinámicas y precisas, por ejemplo, `width: calc(100% - 50px);`.

2. **CSS Custom Properties (Variables)**:

   - Definidas con `--variable-name` y utilizadas con `var(--variable-name)`.
   - **Recomendación**: Facilitan la gestión de temas y valores repetitivos, facilitando el mantenimiento del código.

### General

- **Diseño Responsivo**: Combina unidades relativas y absolutas para crear _layouts_ que se adapten a diferentes tamaños de pantalla.
- **Accesibilidad**: Considera el tamaño de fuente adecuado para la legibilidad, utilizando `rem` para escalar fuentes según la configuración del usuario.

### Ejemplo Práctico

```css
html {
  font-size: 16px; /* Base size */
}

body {
  font-size: 1rem; /* 16px */
  margin: 0;
  padding: 0;
}

.container {
  width: 80%;
  max-width: 1200px;
  padding: 2rem; /* 32px */
}

.header {
  height: 10vh; /* 10% of viewport height */
  background-color: #333;
}

.button {
  padding: 1em 2em;
  font-size: 1em; /* Relative to container's font size */
}
```

Estas recomendaciones te ayudarán a mantener un diseño flexible, responsivo y accesible.

## Comentarios en CSS

Así como es buena práctica comentar tu código HTML y JavaScript, es buena práctica comentar tu CSS. Los comentarios en CSS se hacen de la siguiente manera:

- El comienzo se indica mediante los caracteres `/*`.
- El final del comentario se indica mediante `*/`.

Veamos un ejemplo:

```css
/* Comentario en CSS */
```

---

## ¿Cómo se agrega CSS en un documento HTML?

Existen tres opciones:

### 1. CSS _Inline_

> **Nota si estás trabajando en CodePen:** Esto lo puedes hacer y funcionará según lo esperado.

Con el atributo style, agregamos estilos directamente a los elementos HTML. Por ejemplo, así le damos un estilo específicamente al elemento `h1`

```html
<h1 style="color:blue; background-color:yellow; border: 1px solid black;">
  ¡Hola Mundo!
</h1>
```

En el navegador, el se vería así:

![Inline Style](https://github.com/Laboratoria/curricula-js/blob/632783f957accef3442934c87cecd254a202f2db/03-interactive-site/00-html-and-css/02-css/img-inline-style.png?raw=true)

Esta forma de agregar CSS puede estar muy bien si estás comenzando a aprender porque te facilita ver los resultados y entender lo que estás haciendo. No obstante, no es la manera de trabajar recomendada. Su mantenimiento puede ser muy ineficiente. ¿Te imaginas tener que actualizar cada una de las líneas de código para cada uno de los 10 encabezados `h2` que haya en una sola página, o en todo un sitio con decenas de páginas?

Además, estamos mezclando la información de estilo con la información estructural del HTML, haciendo el CSS difícil de leer y de entender. Manteniendo los distintos tipos de código separados y puros, se facilitará la tarea a aquellos que vayan a trabajar posteriormente en el código. Recuerda que siempre debes pensar en organizar tu código de una manera que facilita a otros entender lo que estás haciendo.

### 2. CSS en la sección _head_ del documento HTML

**Nota si estás trabajando en CodePen:** Esto no lo puedes hacer. Recuerda que CodePen ya incluye (oculta) la única etiqueta `<head>` que se admite para cada documento `HTML` y tú no la puedes modificar (ni siquiera la puedes ver). No obstante, es importante que sepas cómo funciona realmente todo.

Otra opción es colocar los estilos dentro de un elemento HTML `<style>` que colocamos en la sección `<head>`. Por ejemplo, para representar los mismos estilos del `h1` anterior tendríamos lo siguiente:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Entendiendo CSS</title>
    <style>
      h1 {
        color: blue;
        background-color: yellow;
        border: 1px solid black;
      }
    </style>
  </head>
  <body>
    <h1>¡Hola Mundo!</h1>
  </body>
</html>
```

Este método continúa siendo ineficiente. ¿Qué pasa si necesitas estilos similares en otras páginas del mismo sitio web? Tendrías que repetir los estilos en cada una de las páginas.

### 3. Hoja de estilos CSS externa

> **Nota si estás trabajando en CodePen:** No es necesario que agregues
> `<link rel="stylesheet" etc...` a tu código HTML, de eso se encarga CodePen "detrás de las cortinas". No obstante, es importante que sepas cómo funciona realmente todo.

La manera ideal de agregar estilos es tener un archivo CSS separado de tu archivo HTML. Todos los estilos se incluirán en este archivo externo de tipo CSS , que se enlazarán desde cada una de las páginas HTML mediante la etiqueta html `<link>` (enlace).

Cabe mencionar que este enlace externo puede ser un archivo que esta en tu PC o un enlace a un archivo externo de Internet. (una dirección HTTP)

En el caso de nuestro ejemplo anterior con los estilos para el `h1`, tendríamos dos archivos:

#### Archivo `index.html`

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Entendiendo CSS</title>
    <!--Enlace a archivo que esta en la misma computadora-->
    <link rel="stylesheet" href="style.css" />
    <!-- o enlace a archivo que esta en internet, uno u otro.-->
    <link
      rel="stylesheet"
      href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"
    />
  </head>
  <body>
    <h1>¡Hola Mundo!</h1>
  </body>
</html>
```

#### Archivo `style.css`

```css
h1 {
  color: blue;
  background-color: yellow;
  border: 1px solid black;
}
```

> **Nota**: si estás trabajando en CodePen, el enlace se hace "automágicamente". Sin embargo, es importante que sepas cómo funciona realmente "por detrás" para que lo puedas hacer cuando uses otros [editores de código](editors_codepen.md).

La etiqueta `<link>` cuenta con el atributo `rel` para indicar la relación del documento enlazado con el actual. El uso más común para este atributo es especificar el enlace a una hoja de estilos externa: el atributo `rel` se establece con valor `stylesheet`. El atributo `href` se establece con la ruta a la hoja de estilos externa para dar formato a la página. En el ejemplo anterior, dado que el archivo a linkear se encuentra en nuestro propio ambiente, simplemente le ponemos el nombre del archivo: `style.css`.
