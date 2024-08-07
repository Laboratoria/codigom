# ¿Qué es una unidad relativa?

Las unidades relativas son un tipo de medida mucho más potente y habitual en el CSS que creamos generalmente. Al contrario que las unidades absolutas, las unidades relativas dependen de algún otro factor (elemento padre, tamaño de letra, interlineado, etc...). Tienen una curva de aprendizaje más compleja, pero son ideales para trabajar en dispositivos con diferentes tamaños, ya que son muy flexibles y versátiles y, bien utilizadas, pueden ahorrar trabajo de desarrollo.

## Las unidades relativas más conocidas son las siguientes:

| Unidad     | Medida aproximada                                         | Ejemplo                    |
| ---------- | --------------------------------------------------------- | -------------------------- |
| %          | Relativa a herencia (concretamente, al elemento padre)    | 50% = mitad del padre      |
| em / rem   | Relativo al font-size en ese elemento                     | 1.5em = 1.5 \* 16px = 24px |
| ex / rex   | Relativo a la altura del carácter x minúscula             | 1ex ~ 0.5em                |
| ch / rch   | Relativo al ancho del carácter 0                          | 1ch ~ 1 carácter           |
| cap / rcap | Relativo a la altura del primer carácter en mayúscula     |                            |
| ic / ric   | Relativo al ancho del glifo 水 CJK (Chino-Japonés-Koreano) |                            |
| lh / rlh   | Relativo al line-height en ese elemento                   |                            |

Probablemente, las más conocidas son %, em y rem, por lo que vamos a empezar con ellas.

### La unidad de porcentaje (%)

Los porcentajes llevan mucho tiempo en el universo de CSS, sin embargo requieren cierta destreza y deben usarse con cuidado en nuestras primeras fases de aprendizaje, ya que el valor de porcentaje establecido depende del tamaño del elemento padre inmediato.

```html
<div class="parent">
  <div class="child"></div>
</div>
```

En este caso anterior, el elemento padre `.parent` tendrá un tamaño de 200px. Su hijo, el elemento `.child` tiene un tamaño de ancho de 50%, o lo que es lo mismo, la mitad del tamaño de su padre: 100px. Por otro lado, si el elemento padre `.parent` no tuviera una propiedad `width` definida, su elemento hijo tendría valor 0. Entenderemos mejor este último caso cuando veamos la propiedad `display`.

Cuando estés empezando, cada vez que utilices porcentajes (%) como unidad en una propiedad CSS, asegúrate de que su elemento contenedor padre tiene esa propiedad definida con un valor específico.

### La unidad em

La unidad em se utiliza para definir un tamaño en base al tamaño que tiene establecido el navegador en la tipografía (tamaño de la fuente) en el elemento HTML actual donde se aplica. Por defecto, y para simplificar, se puede asumir que 1em es un valor aproximado a 16px.

#### Unidades relativas en CSS: em

Imaginemos que el tamaño de la fuente establecida en el navegador del usuario es exactamente 16px. Una cantidad 1em equivaldría a 16px, mientras que una cantidad de 2em sería justo el doble: 32px. Por otro lado, una cantidad de 0.5em sería justo la mitad: 8px.

```css
.element {
  background: blue;
  font-size: 32px;
  width: 2em;
  height: 2em;
  color: white;
}
```

En este ejemplo, el cuadrado azul sería de tamaño 32x32 píxeles. Sin embargo, en el siguiente ejemplo, observa que no tenemos `font-size` definido en el elemento, sino en el elemento padre (`.container`). Como la propiedad `font-size` es heredable, la propiedad `font-size` de `.element` también es 32px, sin embargo, el tamaño de ancho del rectángulo azul sería: 32px, mientras que el tamaño de alto sería 64px:

```css
.container {
  font-size: 32px;
  color: white;
}

.element {
  background: blue;
  width: 1em;
  height: 2em;
}
```

Este tipo de unidad es bastante interesante a la hora de establecer medidas que sean proporcionales al tamaño establecido de la fuente del elemento que estamos diseñando.

### La unidad rem (root em)

Muchas de las unidades que vamos a ver en esta sección están prefijadas por la letra `r`. Esta letra simboliza la palabra `root` (raíz), por lo que en este caso estamos hablando de unidades `em` en el elemento raíz.

Esta unidad toma la idea de la unidad `em`, pero en lugar de tomar el tamaño `font-size` del elemento actual, toma el tamaño del elemento raíz, es decir, el elemento `<html>` o la pseudoclase `:root`. Esta forma nos permite trabajar con múltiplos del tamaño base:

```css
:root {
  font-size: 22px; /* Tamaño base */
}

h1 {
  font-size: 2rem; /* El doble: 2 x 22px = 44px */
}

h2 {
  font-size: 1rem; /* El mismo: 1 x 22px = 22px */
}
```

Como podemos ver, una vez hemos definido el tamaño base del documento, luego solo tenemos que utilizar las unidades `rem` para hacer referencia a una escala del tamaño base. En el ejemplo anterior, los elementos `<h1>` tendrán 44px de tamaño, ya que hemos establecido `2rem`, que significa «el doble que el tamaño base». Por otro lado, los elementos `<h2>` tendrían el mismo tamaño: 22px.

Esto nos da una ventaja principal considerable: si queremos cambiar el tamaño del texto en general, sólo tenemos que cambiar el `font-size` de la pseudoclase `:root`, puesto que el resto de unidades son factores de escalado y se modificarán todas en consecuencia al cambio del `:root`. Algo, sin duda, muy práctico y fácil de mantener.

## Otras unidades relativas

Existen otras unidades relativas que puedes utilizar. Vamos a explicarlas a continuación.

### La unidad ex

La unidad `ex` es una unidad menos conocida, que hace referencia al tamaño de alto de la primera letra minúscula de la tipografía. Por simplificar, podemos asumir que 1ex es aproximadamente 0.5em, es decir, la mitad del tamaño del `font-size` del elemento actual.

Históricamente, la medida `ex` está basada en la altura del carácter `x` en minúscula, que es aproximadamente un poco más de la mitad de la fuente actual (depende de la tipografía utilizada).

#### Altura de la x minúscula

De la misma forma que vimos con `em` y `rem`, tenemos la unidad `rex`, que no es una unidad que cuente dinosaurios, sino la unidad `ex` que toma como referencia el elemento raíz del documento.

### La unidad ch

La unidad `ch` es una unidad también bastante desconocida que hace referencia al tamaño de ancho de un carácter alfanumérico europeo. Por simplificar, se suele asumir que tiene un tamaño de ancho de 0.5em.

```css
.element {
  font-family: 'Victor Mono', monospace;
  font-size: 2rem;
  background: #111;
  color: #eee;
  width: 8ch;
}
```

Históricamente, la unidad `ch` hacia referencia al tamaño de ancho de un carácter `0`, por aquello de que las tipografías monoespaciadas se utilizaban sobre todo para números o textos que ocupan el mismo espacio.

De la misma forma que con `em` y `rem`, tenemos la unidad `rch`, que tiene el mismo significado que `ch` pero haciendo referencia al elemento raíz del documento.

### La unidad cap

La unidad `cap` es una unidad de nueva generación que permite indicar tamaños basados en el tamaño de alto de la primera letra mayúscula de la tipografía.

De la misma forma que con `em` y `rem`, tenemos la unidad `rcap`, que tiene el mismo significado que `cap` pero haciendo referencia al elemento raíz del documento.

### La unidad ic

La unidad `ic` es una unidad de nueva generación que permite indicar tamaños basados en el tamaño típico de un carácter CJK. Las siglas CJK son las que se utilizan para hacer referencia a caracteres Chino-Japonés-Koreano.

De la misma forma que con `em` y `rem`, tenemos la unidad `ric`, que tiene el mismo significado que `ic` pero haciendo referencia al elemento raíz del documento.

### La unidad lh

La unidad `lh` es una unidad de nueva generación que permite indicar tamaños basados en el interlineado de la tipografía. Es decir, el tamaño se define en base a la propiedad `line-height`, por lo que se establecen en base a su valor.

```css
.element {
  background: indigo;
  color: #eee;
  font-family: 'Victor Mono', monospaced;
  font-size: 2rem;
  height: 2lh;
  line-height: 120%;
}
```

Por defecto, la propiedad `line-height` tiene comúnmente el valor 120% o 1.2, por lo que si establecemos un valor `2lh` a la propiedad `height`, significa que el tamaño de alto del `.element` será de dos veces el interlineado actual, o sea, un valor de 240% o 2.4.

De la misma forma que con `em` y `rem`, tenemos la unidad `rlh`,

que tiene el mismo significado que `lh` pero haciendo referencia al elemento raíz del documento.
