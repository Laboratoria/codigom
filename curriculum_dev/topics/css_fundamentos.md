## CSS: Fundamentos y Ejemplos

Ahora profundizaremos en algunos de los conceptos esenciales de CSS que son fundamentales. Abordaremos el modelo de caja, explicando cómo se estructura y se distribuye el espacio alrededor de los elementos. Luego, examinaremos las propiedades `margin` y `padding` para gestionar los espacios internos y externos de los elementos. También exploraremos cómo aplicar estilos al texto y las fuentes tipográficas para mejorar la legibilidad y estética. A continuación, veremos cómo usar colores e imágenes de fondo para darle vida a tus páginas. Finalmente, aprenderemos a estilizar enlaces y a añadir transiciones para una mejor experiencia de usuario.

### Pixeles

En CSS, los píxeles (`px`) son una unidad de medida comúnmente utilizada para definir el tamaño y las dimensiones de elementos, como anchos, altos, márgenes, rellenos y fuentes. Un píxel representa un punto en la pantalla y proporciona precisión en el diseño, asegurando que los elementos se vean de la misma forma en diferentes dispositivos y resoluciones. Sin embargo, para diseños más flexibles y adaptables, también se utilizan otras unidades como porcentajes, `em`, `rem`, y unidades relativas a la ventana gráfica (`vw`, `vh`).

### Modelo de Caja

![](../../assets/CSS/BOXmODEL.png)

El modelo de caja en CSS es crucial para entender cómo se distribuye el espacio alrededor de los elementos en una página web. Cada elemento se considera una caja que consiste en cuatro áreas:

1. **Contenido**: El área donde reside el contenido del elemento.
2. **Relleno (Padding)**: El espacio entre el contenido y el borde.
3. **Borde (Border)**: El borde que rodea el relleno y el contenido.
4. **Margen (Margin)**: El espacio fuera del borde, separando el elemento de otros elementos.

```css
div {
  width: 200px;
  padding: 20px;
  border: 5px solid black;
  margin: 10px;
}
```

En este ejemplo, la caja del `div` tiene un ancho de 200px, un relleno de 20px, un borde de 5px y un margen de 10px.

### Margin y Padding

`margin` y `padding` son propiedades que controlan el espacio fuera y dentro de los elementos, respectivamente.

- **Margin**: Espacio exterior que separa un elemento de otros.
- **Padding**: Espacio interior entre el contenido y el borde del elemento.

```css
p {
  margin: 20px;
  padding: 10px;
}
```

En este ejemplo, los párrafos (`<p>`) tendrán un margen de 20px alrededor y un relleno de 10px dentro de sus bordes.

### Estilos de Texto y Fuentes Tipográficas

CSS proporciona una variedad de propiedades para estilizar el texto y las fuentes. Algunas de las más comunes incluyen:

- `font-family`: Define la fuente del texto.
- `font-size`: Establece el tamaño de la fuente.
- `color`: Cambia el color del texto.
- `text-align`: Alinea el texto.

```css
h1 {
  font-family: 'Arial', sans-serif;
  font-size: 24px;
  color: #333;
  text-align: center;
}
```

Este ejemplo estiliza los encabezados `<h1>` con la fuente Arial, un tamaño de 24px, color gris oscuro (#333), y alineación centrada.

### Colores e Imágenes de Background

Puedes usar colores sólidos o imágenes como fondo de los elementos. Las propiedades principales para esto son `background-color` y `background-image`.

```css
body {
  background-color: #f0f0f0;
}

div {
  background-image: url('background.jpg');
  background-size: cover;
}
```

En este ejemplo, el fondo del `body` es un color gris claro, y el `div` tiene una imagen de fondo que cubre todo el elemento.

### Estilos y Transiciones de Enlaces

Los enlaces (`<a>`) pueden ser estilizados para mejorar la experiencia del usuario. Las propiedades comunes incluyen `color`, `text-decoration`, y `hover`.

```css
a {
  color: #0066cc;
  text-decoration: none;
}

a:hover {
  color: #ff6600;
  text-decoration: underline;
  transition: color 0.3s;
}
```

En este ejemplo, los enlaces son de color azul (#0066cc) y sin subrayado. Al pasar el cursor sobre ellos, cambian a color naranja (#ff6600), se subrayan, y la transición de color dura 0.3 segundos.

Experimenta con estos ejemplos y propiedades para ver cómo afectan el diseño y el comportamiento de tus elementos HTML.

---

Extra. Solamente si quieres profundizar. Cuidado con meterte en un agujero del que te costará salir :seedling: :

- [El modelo de caja - Aprende desarrollo web | MDN](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/The_box_model)

- [margin - CSS | MDN](https://developer.mozilla.org/es/docs/Web/CSS/margin)

- [padding - CSS | MDN](https://developer.mozilla.org/es/docs/Web/CSS/padding)

- [Fundamentos de texto y fuentes tipográficas - Aprende desarrollo web | MDN](https://developer.mozilla.org/es/docs/Learn/CSS/Styling_text/Fundamentals)

- [Dar estilo a los enlaces - Aprende desarrollo web | MDN](https://developer.mozilla.org/es/docs/Learn/CSS/Styling_text/Styling_links)

- 
