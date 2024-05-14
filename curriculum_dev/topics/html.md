# HTML: HyperText Markup Language

> **Tip**: la mejor manera de aprender conceptos que son tan nuevos y abstractos es ponerlos a prueba y observar el resultado. En lugar de ponerte a leer toooooooodo, tratando de entender y memorizar (cosa que no deberías ni intentar), lee algo y ve a probar para que veas cómo funciona realmente más allá de las palabras del texto.

HTML (*HyperText Markup Language)* o Lenguaje de Marcado de Hipertexto es el lenguaje utilizado para crear la estructura de una página web. Los archivos que contienen HTML, se guardan con la extensión .HTML. Es algo el equivalente a crear documentos con formato Word, Excel , etc.

Un documento HTML simple se ve así "por dentro":

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Mi primera web</title>
  </head>
  <body>
    <h1>¡Hola Mundo!</h1>
    <p>Esta es mi primera web</p>
  </body>
</html>
```

Lo primero que puedes notar es que se utilizan "etiquetas" además del contenido propiamente dicho. El navegador "lee" el HTML y lo presenta según las reglas del lenguaje como lo que conoces coloquialmente como "página web" 

Revisando directamente la documentación del [Mozilla Developer Network](https://developer.mozilla.org/es/docs/Learn/HTML/Introduccion_a_HTML/iniciar) vemos la siguiente definición:

> HTML (HyperText Markup Language) **no** es un lenguaje de programación, es un lenguaje de marcado, usado para decirle a tu navegador cómo estructurar las páginas que visitas. Puede ser tan complejo o tan simple como desee el desarollador web.
> 
> HTML consiste en una serie de elementos, que puedes utilizar para encerrar, envolver, o marcar partes diferentes del contenido para hacer que aparezcan de una cierta manera, o actúen de determinada forma. Las etiquetas que envuelven un trozo de contenido pueden hacer que dicho contenido enlace con otra página, ponga una palabra en cursiva, etcétera.

¿Por qué dice que no es un lenguaje de programación? Puedes averiguarlo por tu cuenta.

## Anatomía de un elemento HTML

Salvo algunas excepciones (por ejemplo `<!DOCTYPE html>`), los elementos HTML comienzan con una `etiqueta de apertura (o inicio)` y terminan con una `etiqueta de cierre (o fin)`. Por ejemplo, el elemento `p`, que indica un párrafo, comienza con la etiqueta de inicio `<p>` y termina con la etiqueta de cierre `</p>`. El texto que se encuentra entre las etiquetas de apertura y de cierre es el *contenido* del elemento, en este caso un párrafo.

![Ejemplo etiqueta](https://user-images.githubusercontent.com/25906896/39716065-df4e7158-51f4-11e8-9a4c-90f1e82bcd09.png)

Como irás aprendiendo, para comunicarnos con las máquinas, es indispensable la precisión. De la misma manera que para terminar una oración, debes poner un punto, en HTML debes poner la etiqueta de "cierre" exactamente como se espera. 

Si te equivocas de símbolos u omites ponerlos como se espera, el navegador "interpretará" tus instrucciones con "errores". 

## Anidamiento HTML

Un elemento puede contener otros elementos o etiquetas `HTML`. Esto se llama *anidamiento*. Observa las etiquetas `<em>` y `<strong>` que están dentro de las etiquetas `<p>`.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>HTML anidado</title>
  </head>
  <body>
    <h1>Laboratoria</h1>
    <p>Código <em>que</em> <strong>transforma</strong></p>
  </body>
</html>
```

## Elementos HTML

Tienes a tu disposición múltiples elementos HTML para construir la estructura que necesites. Por ejemplo:

1. Encabezados para títulos y subtítulos.
2. Un enlace/liga.
3. Una tabla.
4. Una lista.
5. Una imagen.
6. Una línea divisoria.
7. Una cita.
8. Resaltar un texto.

Puedes complementar revisando [este enlace]([Referencia de Elementos HTML - HTML: Lenguaje de etiquetas de hipertexto | MDN](https://developer.mozilla.org/es/docs/Web/HTML/Element)). Te recomendamos que no intentes aprenderte todos, solamente vas a conseguir :dizzy_face: aturdirte. Hay una razón por la que estamos "dosificando" el contenido a medida que avanzas. 

## Etiquetas vacías

Por ejemplo, [el elemento `<img>` para agregar una imagen a tu página](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/img) y habrás notado que no tiene una etiqueta de cierre y, por lo tanto, no tiene "contenido":

```html
<img src="https://es.wikipedia.org/static/images/icons/wikipedia.png">
```

Algunas etiquetas no tienen directamente contenido; en su lugar reciben el contenido desde una *fuente* ("src" de *source* en inglés = fuente). Esto es lo que sucede con el elemento `img`. El atributo `src` especifica la fuente del contenido en forma de URL que debe tener la etiqueta `img`

## Comentarios en HTML

Agregar comentarios a tu código `HTML` puede ser de gran utilidad. Es como dejar migas de pan o pistas para tu yo del futuro y evitar tener que recordar tantísimos detalles. 

Para definir un comentario en `HTML`, usamos las etiquetas `<!--` para abrir el comentario y `-->` para cerrarlo.

```html
<!-- Esto es un comentario. No se verá en la web, pero sí en mi código. -->
```

## Atributos

Los atributos proveen información adicional sobre el contenido de un elemento pero que no ve el usuario. En algunos casos agregan características y/o comportamiento a tu elemento `HTML`. Los atributos aparecen en la **etiqueta de apertura** del elemento y consisten de dos partes: un nombre y un valor, separados por un signo de igual (`=`).

```html
<a href="http://laboratoria.la/" target="_blank" title="Página de inicio de Laboratoria">Ir a Laboratoria</a>
```

En el caso del ejemplo anterior, podemos visualizar tres atributos: el atributo `href`, el atributo `target` y el atributo `title`.

- El atributo `href` especifica la dirección web a la que quieres que apunte el enlace; es decir, donde el navegador navega cuando se le hace clic. En este ejemplo vemos que apunta a la página de inicio de Laboratoria: [http://laboratoria.la/](http://laboratoria.la/)

- El atributo `target` especifica el contexto de navegación que será usado para mostrar el enlace. Por ejemplo, `target="_blank"` mostrará el enlace en una nueva pestaña. Si quieres mostrar el enlace en la pestaña actual solo omite este atributo.

- El atributo `title` especifica información extra sobre el enlace, como qué página es la que estás enlazando. En nuestro ejemplo dice "Página de inicio de Laboratoria". Esto aparecerá como información cuando se pase el cursor por encima del enlace.
