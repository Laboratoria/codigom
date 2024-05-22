# Formularios

**Tiempo:** ⏱ 15min

## Estructura básica de un formulario

> **Tip**: recuerda no intentar memorizar ni comprender cada recurso que te recomendamos, nadie puede. Todo es un proceso en el que, poco a poco, pasarás de hacerte una idea general hasta ser capaz de utilizar algunos aspectos de lo recién aprendido. Una buena idea puede ser copiar y pegar estos ejemplos, uno a uno, en tu editor para que observes lo que sucede exactamente.

Un formulario en HTML se define utilizando la etiqueta `<form>`. Dentro de esta etiqueta, se pueden incluir varios tipos de campos de entrada. Veamos algunos de los campos más comunes y cómo se utilizan:

## Campos de entrada básicos

1. **Campo de texto**:
   Los campos de texto permiten ingresar información como nombres o direcciones.
   
   ```html
   <label for="nombre">Nombre:</label>
   <input type="text" id="nombre" name="nombre" placeholder="Ingresa tu nombre">
   ```

2. **Campo de número (`type=number`)**:
   Este tipo de campo se usa para ingresar valores numéricos. Puedes especificar valores mínimos y máximos utilizando los atributos `min` y `max`.
   
   ```html
   <label for="edad">Edad:</label>
   <input type="number" id="edad" name="edad" min="1" max="100" required>
   ```

3. **Campo de fecha (`type=date`)**:
   Permite a los usuarios seleccionar una fecha de un calendario.
   
   ```html
   <label for="fecha-nacimiento">Fecha de nacimiento:</label>
   <input type="date" id="fecha-nacimiento" name="fecha-nacimiento" required>
   ```

4. **Área de texto**:
   Utilizada para que los usuarios ingresen textos largos, como comentarios o mensajes.
   
   ```html
   <label for="mensaje">Mensaje:</label>
   <textarea id="mensaje" name="mensaje" placeholder="Escribe tu mensaje aquí"></textarea>
   ```

## Listas desplegables

Las listas desplegables permiten a los usuarios seleccionar una opción de una lista predefinida. Se crean usando las etiquetas `<select>` y `<option>`.

```html
<label for="pais">País:</label>
<select id="pais" name="pais">
  <option value="argentina">Argentina</option>
  <option value="mexico">México</option>
  <option value="españa">Brasil</option>
</select>
```

## Etiquetas y Marcadores de Posición

Las etiquetas (`label`) y los marcadores de posición (`placeholder`) son elementos importantes en la creación de formularios web accesibles y fáciles de usar.

- **Etiqueta (`label`)**:
  Las etiquetas son cruciales para la accesibilidad y la usabilidad de los formularios. Asociar una etiqueta con un campo de formulario mediante el atributo `for` mejora la experiencia del usuario, ya que hace clic en la etiqueta para enfocar el campo correspondiente. Esto es especialmente útil para usuarios que dependen de tecnologías asistivas, como lectores de pantalla.
  
  ```html
  <label for="email">Correo Electrónico:</label>
  <input type="email" id="email" name="email" required>
  ```
  
  En el ejemplo anterior, la etiqueta `label` está asociada con el campo de entrada `input` mediante el atributo `for`, que coincide con el `id` del campo. Esto asegura que cuando se haga clic en el texto "Correo Electrónico", el cursor se ubicará en el campo de entrada correspondiente.

- **Marcador de posición (`placeholder`)**:
  Los marcadores de posición proporcionan pistas visuales dentro del campo de entrada sobre qué tipo de información se debe ingresar. Esto ayuda a los usuarios a comprender rápidamente qué se espera de ellos sin necesidad de leer instrucciones adicionales.
  
  ```html
  <input type="text" id="username" name="username" placeholder="Usuario">
  ```
  
  En este caso, el `placeholder` "Usuario" aparece dentro del campo de entrada hasta que el usuario comienza a escribir. Esto puede mejorar la usabilidad del formulario al dar indicaciones claras y directas sobre el tipo de datos esperados.

**Importancia**:

1. **Accesibilidad**: Las etiquetas son esenciales para hacer que los formularios sean accesibles a usuarios con discapacidades, garantizando que puedan navegar y completar formularios utilizando tecnologías asistivas.
2. **Usabilidad**: Los marcadores de posición mejoran la experiencia del usuario al proporcionar instrucciones contextuales dentro del campo de entrada, lo que puede reducir errores y aumentar la eficiencia al completar formularios.

El uso adecuado de etiquetas y marcadores de posición no solo mejora la accesibilidad y usabilidad, sino que también contribuye a la apariencia profesional y la funcionalidad de tus formularios.

### Validación de formularios

La validación de formularios es un paso crucial para asegurar que los datos ingresados por los usuarios sean correctos y útiles. Validar los datos en navegador de la usuaria y antes de ser enviados a cualquier lugar, mejora la experiencia de uso al proporcionar retroalimentación inmediata mediante mensajes de error y evita que se envíen datos erróneos al servidor, reduciendo la carga de procesamiento y evitando posibles errores en el manejo de la información.

Atributos para validar los datos de los formularios antes de enviarlos:

- **`required`** (requerido):
  Este atributo asegura que un campo debe ser llenado antes de enviar el formulario. Es especialmente útil para campos que son obligatorios, como el nombre o el correo electrónico.
  
  ```html
  <input type="text" id="nombre" name="nombre" required>
  ```
  
  En el ejemplo anterior, el campo de texto para el nombre debe ser llenado, de lo contrario, el formulario no se enviará.

- **`pattern`** (patrón):
  Define un patrón de expresiones regulares que la entrada debe coincidir. Es útil para validar formatos específicos, como números de teléfono o códigos postales.
  
  ```html
  <label for="telefono">Teléfono:</label>
  <input type="tel" id="telefono" name="telefono" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}" placeholder="123-456-7890" required>
  ```
  
  Aquí, el `pattern` asegura que el número de teléfono ingresado siga el formato `123-456-7890`.

- **`min` y `max`** (valores mínimo y máximo):
  Establecen los valores mínimo y máximo para campos numéricos, asegurando que las usuarias ingresen datos dentro de un rango específico.
  
  ```html
  <label for="cantidad">Cantidad:</label>
  <input type="number" id="cantidad" name="cantidad" min="1" max="10" required>
  ```
  
  En este caso, la usuaria debe ingresar un número entre 1 y 10.

**Importancia de la Validación**:

1. **Prevención de errores**: La validación ayuda a evitar errores comunes en la entrada de datos, como omitir campos obligatorios o ingresar datos en un formato incorrecto.
2. **Mejora de la experiencia de la usuaria**: Al proporcionar retroalimentación inmediata, los usuarios pueden corregir errores antes de enviar el formulario, lo que hace el proceso más eficiente y menos frustrante.
3. **Seguridad**: Validar datos en el lado del cliente puede ayudar a prevenir algunos tipos de ataques, como la inyección de código, aunque siempre debe complementarse con validación del lado del servidor para una seguridad completa.
4. **Integridad de los datos**: Asegura que los datos recibidos sean consistentes y en el formato esperado, lo que facilita su procesamiento y análisis posteriores.

## Estilos básicos con CSS

Utilizar estilos CSS  en tus formularios es esencial para mejorar la apariencia y la usabilidad de los mismos. Un formulario bien diseñado no solo es visualmente atractivo sino también accesible y fácil de usar. 

Comencemos con un ejemplo simple de CSS:

```html
<style>
  form {
    max-width: 400px;
    margin: auto;
    padding: 1em;
    border: 1px solid #ccc;
    border-radius: 1em;
  }
  label {
    margin-top: 1em;
    display: block;
  }
  input, textarea, select {
    width: 100%;
    padding: 0.5em;
    margin-top: 0.5em;
    border: 1px solid #ccc;
    border-radius: 0.25em;
  }
  input[type="submit"] {
    background: blue;
    color: white;
    border: none;
    padding: 1em;
    margin-top: 1em;
    cursor: pointer;
  }
  input[type="submit"]:hover {
    background: darkblue;
  }
</style>
```

1. **Formulario (`form`)**:
   El estilo del formulario se centra en su ancho máximo, margen, padding, borde y bordes redondeados para darle una apariencia particular.

2. **Etiquetas (`label`)**:
   Las etiquetas se muestran como bloques con margen superior para separarlas de los campos de entrada.

3. **Campos de entrada (`input`, `textarea`, `select`)**:
   Se aplica un estilo a los campos de entrada para tener un ancho del 100%, padding interno para mayor comodidad al escribir, margen superior para separarlos de los elementos anteriores, y bordes y bordes redondeados para una apariencia consistente.

4. **Botón de envío (`input[type="submit"]`)**:
   Al botón de envío se le aplica un estilo con un fondo de color azul, texto blanco, sin borde, y padding para hacerlo más grande y fácil de hacer clic. Además, se añade un efecto hover para cambiar el color cuando el usuario pasa el cursor sobre él.

#### Importancia de los estilos

- **Mejora de la usabilidad**: Los formularios son más fáciles de usar. Los campos más grandes y espaciados adecuadamente facilitan la interacción, especialmente en dispositivos táctiles.
- **Accesibilidad**: Ayudan a que los formularios sean más accesibles para todas las usuarias, incluidas aquellas con dificultades o discapacidades sensoriales. Asegurarse de que los campos de entrada y las etiquetas sean claramente visibles y legibles es crucial.
- **Consistencia visual**: Un estilo consistente ayuda a que tu formulario se integre mejor con el diseño general de tu sitio web, proporcionando una experiencia de uso más coherente.

### CSS Responsivo

Si bien esta sección se centra en la estilización básica, es importante mencionar que la creación de formularios responsivos es fundamental para asegurar que funcionen bien en todos los dispositivos y tamaños de pantalla. Asegurarte de que tu formulario sea responsivo significa que se verá bien y funcionará correctamente tanto en pantallas de escritorio grandes como en dispositivos móviles más pequeños.

**Ejemplo de media query para formularios responsivos:**

```html
<style>
  @media (max-width: 600px) {
    form {
      padding: 0.5em;
    }
    input, textarea, select {
      padding: 0.25em;
    }
    input[type="submit"] {
      padding: 0.75em;
    }
  }
</style>
```

En este ejemplo, los estilos del formulario se ajustan cuando el ancho de la pantalla es de 600px o menos, haciendo que los elementos del formulario sean más compactos y adecuados para pantallas pequeñas.
