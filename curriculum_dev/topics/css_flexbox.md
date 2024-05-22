# Flexbox

## ¿Qué es Flexbox?

Por mucho tiempo las únicas herramientas disponibles para la creación de _layouts_ en CSS y posicionar elementos con una buena compatibilidad entre diferentes navegadores era `float` y `position`. Sin embargo, estas herramientas tenían algunas limitaciones bastante frustrantes, especialmente cuando teníamos en cuenta lo _responsive_.
Algunas tareas que consideramos básicas en un _layout_, como centrar de manera vertical un elemento según el contenedor en el que esté, hacer que elementos en fila ocupen la misma cantidad de espacio o que las columnas sean del mismo tamaño independientemente del contenido que tengan dentro, eran imposibles o muy dificiles de lograrse con `float` o `position`, al menos de una forma práctica y _flexible_.

Flexbox (que viene de _Flexible Box_) fue creada para que estas tareas fuesen mucho más simples y funcionales: los hijos de un elemento con Flexbox pueden posicionarse en cualquier dirección y pueden tener dimensiones flexibles para adaptarse.

## Elementos

**Flex container** es el elemento que va a contener una estructura de elementos. Se puede definir utilizando la propiedad `display` con valor `flex` o `inline-flex`.

```html
<div class="flex-container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

```css
.flex-container {
  display: flex;
}
```

**Flex Item** los elementos _hijos_ de un flex container.

**Ejes** son las direcciones basicas que existen en un flex container: _main axis_ que sería el eje horizontal o el eje principal y _cross axis_ que es el eje vertical.

## Propiedades para elementos madre

Cuando utilizamos _Flexbox_, es muy importante saber qué propiedades son declaradas en los elementos madre (por ejemplo, un `section` que alineará a los elementos hijos o _flex items_) y cuáles serán declarados en los elementos hijos. Abajo estan algunas de las propiedades que deben ser declaradas utilizando un elemento madre como selector (para alinear a sus hijos):

**flex-direction** determina el origen y el fin del flujo de dos items. Siguen el patrón establecido en la escritura occidental: de izquierda hacia derecha en `row`, de arriba hacia abajo en `column`, y para indicar que sea el sentido inverso, podemos utilizar `-reverse`.

```css
.flex-container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```

![flex-direction](https://css-tricks.com/wp-content/uploads/2018/10/flex-direction.svg)

Podrás definir si los elementos tienen que caber en una misma línea o se iran rompiendo en varias líneas con la propiedad **flex-wrap**.

```css
.flex-container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

![flex-wrap](https://css-tricks.com/wp-content/uploads/2018/10/flex-wrap.svg)

La propiedad **flex-flow** es un tipo de propiedad _shorthand_ (una sola declaración que incluye varios valores relacionados a una misma propiedad) que incluye `flex-direction` y `flex-wrap`. Determina el orden en el cual aparecerán los elementos.

**justify-content** define la alineación de los hijos en el largo del eje principal.

```css
.flex-container {
  justify-content: flex-start | flex-end | center | space-between | space-around
    | space-evenly;
}
```

![justify-content](https://css-tricks.com/wp-content/uploads/2018/10/justify-content.svg)

**align-items** define el comportamiento predeterminado de como los _flex items_ son alineados de acuerdo al eje vertical (_cross axis_). De esta forma, funciona de una manera similar a `justify-content`, pero en el eje perpendicular.

```css
.flex-container {
  align-items: stretch | flex-start | flex-end | center | baseline;
}
```

![align-items](https://css-tricks.com/wp-content/uploads/2018/10/align-items.svg)

**align-content** alinea el contenido dentro del contenedor cuando haya espacio extra en el eje vertical, similar a como `justify-content` alinea los items individuales en el eje principal.

```css
.flex-container {
  align-content: flex-start | flex-end | center | space-between | space-around |
    stretch;
}
```

## ![align-content](https://css-tricks.com/wp-content/uploads/2018/10/align-content.svg)Propriedades para elementos hijos

A continuación, veremos las propiedades que pueden ser declaradas teniendo como selector a los elementos hijos.

```html
<div class="flex-container">
  <div class="flex-item">1</div>
  <div class="flex-item">2</div>
  <div class="flex-item">3</div>
</div>
```

Esto significa que donde existe un elemento madre con propiedad _flex_, es posible atribuir propiedades flex específicas a sus hijos.

_¡Importante!_

- CSS no se encarga de la jerarquía entre madre e hijos; no va a aplicar las propiedades flex a elementos HTML que no estén directamente relacionados.
- Para que las propiedades funcionen en los elementos hijos, los contenedores madre deberán tener la propiedad _flex_.
- Las propiedades `float`, `clear` y `vertical-align` no tienen ningún efecto en los _flex items_.

La propiedad **order** determina el orden en el cual apareceran los elementos.

```css
.flex-item {
  order: <número>; /* el valor por default es 0*/
}
```

**flex-grow** define la habilidad de un elemento hijo de 'crecer' y ocupar un área más grande si es necesario. Por ejemplo, si en una lista de 3 hijos, 2 de ellos tienen la propiedad `flex-grow: 1` y uno de ellos tiene `flex-grow: 2`, este último crecerá para ocupar el doble de tamaño de sus hermanos.

```css
.flex-item {
  flex-grow: <número>; /* el valor por default es 0 */
}
```

![grow](https://css-tricks.com/wp-content/uploads/2018/10/flex-grow.svg)

**align-self** permite un alineamiento predeterminado (definido por `align-items`) que sobrescribirá para items individuales.

```css
.flex-item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```

![align-self](https://css-tricks.com/wp-content/uploads/2018/10/align-self.svg)

Existen otras propiedades para los hijos como `flex-shrink`, `flex-basis` y el shorthand `flex`, puedes investigar más sobre ellos para conocer aún más propiedades.

## Flexbox vs. Media Queries

### Media Queries

**Qué son:**

- Son reglas condicionales de CSS que permiten aplicar estilos específicos en función de características del dispositivo, como el ancho de la pantalla.

**Para qué sirven:**

- Son ideales para definir "puntos de quiebre" (`breakpoints`) en tu diseño. Por ejemplo, puedes cambiar el diseño cuando la pantalla es menor a 600px (para móviles) y mayor a 1200px (para escritorio).

**Ejemplo de uso:**

```css
/* Estilos generales para todos los dispositivos */
body {
  font-size: 16px;
}

/* Estilos específicos para dispositivos con pantallas de hasta 600px */
@media (max-width: 600px) {
  body {
    font-size: 14px;
  }
}

/* Estilos específicos para dispositivos con pantallas de más de 1200px */
@media (min-width: 1200px) {
  body {
    font-size: 18px;
  }
}
```

### Flexbox

**Qué es:**

- Es un sistema de diseño CSS que organiza los elementos dentro de un contenedor flexible (`flex container`).

**Para qué sirve:**

- Proporciona un control detallado sobre la alineación, dirección y distribución de los elementos dentro del contenedor, sin importar el tamaño exacto del dispositivo.
- Es útil para diseños que necesitan ser fluidos y adaptarse a cambios de tamaño de manera flexible.

**Ejemplo de uso:**

```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.item {
  flex: 1;
}
```

### Diferencias Clave

1. **Función Principal:**
   
   - **Media Queries:** Ajusta estilos en función de características específicas del dispositivo, como el ancho de la pantalla.
   - **Flexbox:** Organiza y distribuye elementos dentro de un contenedor de manera flexible, sin depender de características específicas del dispositivo.

2. **Puntos de Quiebre:**
   
   - **Media Queries:** Necesitas definir puntos de quiebre específicos para aplicar diferentes estilos.
   - **Flexbox:** Ajusta automáticamente los elementos dentro de un contenedor según el espacio disponible.

3. **Control y Flexibilidad:**
   
   - **Media Queries:** Ofrecen control sobre cuándo se aplican ciertos estilos, pero no sobre cómo se distribuyen los elementos dentro de un contenedor.
   - **Flexbox:** Ofrece control detallado sobre la distribución de los elementos dentro de un contenedor, independientemente de los puntos de quiebre.

### Ejemplo Combinado

**Uso de Media Queries y Flexbox juntos:**

- Puedes usar Media Queries para definir cuándo cambiar el diseño y Flexbox para ajustar la disposición de los elementos dentro de ese diseño.

```css
/* Estilos generales para todos los dispositivos */
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.item {
  flex: 1;
}

/* Estilos específicos para dispositivos con pantallas de hasta 600px */
@media (max-width: 600px) {
  .container {
    flex-direction: column;
  }
}
```

En este ejemplo, usamos Media Queries para cambiar la dirección del contenedor Flexbox de una fila a una columna cuando la pantalla es menor a 600px de ancho. Flexbox se encarga de la disposición flexible de los elementos dentro del contenedor, sin importar el tamaño exacto del dispositivo.
