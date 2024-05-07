# Formularios

Los formularios son una forma sencilla de solicitar información al usuario en una página web, permitiendo que ingrese información. Los formularios son uno de los puntos principales de interacción entre un usuario y un sitio web o aplicación.

Revisa brevemente la documentación del MDN sobre formularios. 

> **Tip**: recuerda no intentar memorizar ni comprender cada recurso que te recomendamos, nadie puede. Todo es un proceso en el que, poco a poco, pasarás de hacerte una idea general hasta ser capaz de utilizar algunos aspectos de lo recién aprendido. Una buena idea puede ser copiar y pegar estos ejemplos, uno a uno, en tu editor para que observes lo que sucede exactamente.

- [Formularios](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/form)

- [Formularios en HTML5](https://developer.mozilla.org/es/docs/Learn/Forms).

Agrega la etiqueta `form` para crear tu formulario.

Para agregar un elemento  `input` donde el usuario ingresará su correo electrónico y que este sea obligatorio.

Fíjate que el atributo `required` se usa para indicar que es un campo obligatorio.

```html
<form>
 <input
   type="email"
   id="email-example"
   placeholder="Email"
   name="email-example"
   required
 />
</form>
```

Para agregar una etiqueta al elemento, usa `label`.

```html
<form>
 <label for="email-example">Correo electrónico</label>
 <input
   type="email"
   id="email-example"
   placeholder="Email"
   name="email-example"
   required
 />
</form>
```

Para crear un`input` de tipo contraseña.

```html
<form>
 <label for="password-example">Password</label>
 <input
   type="password"
   id="password-example"
   placeholder="Password"
   name="password-example"
   required
 />
</form>
```

Para crear un elemento desplegable, crearás un `select` con una lista de valores predefinidos.

```html
<select name="select-example">
 <option value="value1">Primera opción</option>
 <option value="value2" selected>Segunda opción</option>
 <option value="value3">Tercera opción</option>
</select>
```

Para permitir que el usuario  sólo pueda elegir una de entre varias opciones, usa `radiobutton`.

```html
<label>
 <input type="radio" name="gender" value="female"> Mujer
</label>
<label>
 <input type="radio" name="gender" value="male"> Hombre
</label>
<label>
 <input type="radio" name="gender" value="no-gender"> Prefiero no decirlo
</label>
```

Para crear un elemento que solamente permite estar seleccionado o no, usa `checkbox`.

```html
<label>
 <input type="checkbox" name="conditions" value="accept-conditions" checked />
 Acepto los términos y condiciones
</label>
```

Para agregar un botón de enviar el formulario.

```html
<button type="submit">Enviar</button>
```

Puedes agregar los estilos que quieras usando CSS.

---
