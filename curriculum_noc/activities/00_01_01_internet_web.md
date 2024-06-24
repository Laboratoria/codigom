# &#11045; Entendiendo Internet y la Web

**Dificultad:** 🌻

**Aprendizaje:** 🍯

**Tiempo:** ⏱ 30min

## Introducción

Antes de comenzar, es crucial que tengas una claridad básica de qué es y cómo funciona la Internet y la World Wide Web (WWW), que a menudo, se usan indistintamente, pero son cosas distintas y funciones diferenciadas. También cómo y para qué se comunican las máquinas (servidores / bots) para conseguir diferentes propósitos.

## ¿Qué es Internet?

Internet, por otro lado, es la infraestructura global de redes que conecta millones de computadoras y dispositivos en todo el mundo. Es la red física que permite la comunicación y el intercambio de datos entre estos dispositivos. Desde su origen como un proyecto militar, Internet ha evolucionado hasta convertirse en una red global que facilita la comunicación, el acceso a la información y una amplia gama de servicios, desde el correo electrónico hasta el comercio electrónico y las redes sociales.

## ¿Qué es la World Wide Web?

La World Wide Web (WWW) es una parte de Internet que conocemos y usamos a diario. En castellano significa "Red de alcance mundial". Es un sistema de distribución de documentos de hipertexto o hipermedios interconectados y accesibles a través de Internet mediante un navegador web. Cuando visitas un sitio web, estás utilizando la WWW. Puedes ver páginas web que contienen una variedad de contenido, como texto, imágenes, videos y más, y puedes navegar entre ellas a través de enlaces.

## Tráfico de Internet: Humanos vs. Máquinas

Aunque solemos pensar en el tráfico de Internet como generado principalmente por personas utilizando sitios web o aplicaciones  para comunicarse, consumir o compartir contenido, etc. No obstante, la realidad es que la mayor parte del tráfico se genera **entre servidores y robots**, aunque esté gatillado por la actividad humana.

Los servidores se conectan entre sí para intercambiar información. Este intercambio ocurre incluso entre servidores de distintos productos/servicios. Por ejemplo:

### Ejemplo 1: Integración de Servicios de Pago

Un sitio de comercio electrónico necesita procesar pagos de manera segura.

**Comunicación entre Servidores:**

1. **Cliente hace un pago:** Compra y proporciona los detalles de pago.
2. **Servidor del comercio electrónico:** Envía una solicitud al servidor del proveedor de servicios de pago (por ejemplo, Stripe o PayPal) con la información del pago.
3. **Servidor del Proveedor de Pago:** Recibe la solicitud, procesa el pago y devuelve una respuesta al servidor del sitio de comercio electrónico, indicando si el pago fue exitoso o no.
4. **Confirmación de Pago:** El servidor del sitio de comercio electrónico recibe la respuesta y actualiza el estado del pedido del cliente en su base de datos.

### Ejemplo 2: Autenticación de Usuarios

Cada vez que usas "Iniciar sesión con mi cuenta de Google" en algún sitio web que usa la autenticación de G.

**Comunicación entre Servidores:**

1. **Usuario inicia sesión con Google:** El usuario selecciona la opción de "Iniciar sesión con Google" en la aplicación web.
2. **Autenticación con Google:** La aplicación web redirige a la usuaria a la página de autenticación de Google, ahí ingresa sus credenciales (correo electrónico y contraseña). se solicita a la usuaria que autorice a la aplicación web para acceder a la información de su cuenta de Google.
3. **Google envía un código de autorización:** Una vez que la usuaria autoriza la aplicación, Google la redirige de vuelta a la aplicación web con un código de autorización.
4. **Servidor de la Aplicación Web:** El servidor de la aplicación web recibe el código de autorización y envía una solicitud al servidor de Google para intercambiar ese código por un *token* de acceso.
5. **Servidor de Google:** El servidor de Google verifica el código de autorización y, si es válido, devuelve un *token* de acceso y un *token* de actualización al servidor de la aplicación web.
6. **Acceso a Recursos Protegidos:** El servidor de la aplicación web utiliza el *token* de acceso para autenticar a la usuaria y permitirle acceder a los recursos protegidos en la aplicación. Además, puede usar el *token* de actualización para obtener un nuevo *token* de acceso cuando el actual expire.
7. **Confirmación de Autenticación:** El servidor de la aplicación web puede almacenar el *token* de acceso y el *token* de actualización en su base de datos para gestionar futuras solicitudes de acceso del usuario.

Como ves en estos dos simples ejemplos, hay todo un "mundo paralelo" de comunicaciones e intercambio de datos entre servidores, es ese el tipo de tráfico que es mayoritario en Internet.

El concepto de ***backend*** se refiere, precisamente, a la parte de una aplicación web o sitio web que no es visible para la usuaria final, pero que es esencial para su funcionamiento.

## La Importancia de las API

Las API (Interfaz de Programación de Aplicaciones) son esenciales en el mundo de no-code e IA. Una API es un conjunto de reglas que permiten que una aplicación se comunique con otra de manera predefinida, limitada y segura. 

Una posible metáfora para explicar una API sería un restaurante. El mesero (API) toma los pedidos de los clientes (solicitudes), los lleva a la cocina (backend) y trae la comida (respuesta) de vuelta a los clientes. Eso es muy diferente a lo caótico e inseguro que sería que cada cliente entre a la cocina a decir lo que quiere, etc. etc. Cada aplicación o sitio decide qué datos quiere intercambiar, en qué lenguajes de programación, bajo qué reglas, etc.

Muchas plataformas de no-code, las API permiten integrar diferentes servicios y automatizar tareas complejas sin necesidad de programación. Por ejemplo, herramientas como Zapier utilizan APIs para conectar aplicaciones y automatizar flujos de trabajo, lo que permite a los usuarios crear automatizaciones entre servicios como Google Sheets, Slack, y muchos otros sin escribir código.

### Ejemplo de Uso de APIs en No-Code

Imagina que quieres automatizar el proceso de enviar un mensaje de agradecimiento a nuevos suscriptores de tu newsletter. Con una herramienta no-code como Zapier, puedes crear una "zap" que utilice la API de tu servicio de correo electrónico para detectar nuevos suscriptores y automáticamente enviarles un mensaje de agradecimiento a través de la API de tu plataforma de email marketing.

---

## Actividad

Aprender a hacer preguntas, intentar formular nuestro propio entendimiento, así como incorporar otros puntos de vista, enriquece nuestro entendimiento de cualquier conocimiento recién adquirido.

Investiga brevemente sobre las siguientes preguntas. **Elije 1 o 2 respuestas que más te sorprendieron y comenta al respecto.**

1. ¿Se puede acceder a todos los sitios web Internet, o existen excepciones?
2. ¿Es posible tener acceso a Internet sin poder acceder a la Web? ¿Cómo?
3. ¿Cómo funcionan los navegadores web para mostrarnos los sitios web?
4. Los motores de búsqueda en la Web, ¿son parte de la Web o de Internet?
5. ¿Cuál es la diferencia entre una página web y un sitio web?
6. ¿Es lo mismo un dominio que una URL? ¿Cómo se estructuran?
7. ¿Qué significa que una página web sea dinámica? ¿Cómo se compara con una estática?
8. ¿Podemos considerar las redes sociales como parte de la Web o son algo aparte de Internet?
9. ¿Cuál es la diferencia entre el front-end y el back-end en desarrollo web?
10. ¿Qué es el Internet de las Cosas (IoT) y cómo cambia nuestra interacción con el mundo físico?

## Insumos adicionales para tu aprendizaje:

- Dr. Google (siempre)

- AI: ChatGPT, Gemini, Perplexity, Bing, etc.. Recuerda que pueden alucinar y mentirte descaradamente, verifica siempre.

- [¿Cómo funciona Internet?](https://www.youtube.com/watch?v=-InB0vz_Mec)

## Guía de Autoevaluación

No habrás cumplido con la actividad si:

- [x] No investigaste sobre cada una de las preguntas.
- [x] No comentas en el hilo de Discord sobre 1 o 2 rptas que te parecieron interesantes.

---

> :mega: 💬 [**Comenta en el hilo de Discord:**](https://discord.com/channels/1209273049304666113/1215445879411052554) sobre 1 o 2 respuestas a las preguntas de investigación que te parecieron particularmente interesantes o novedosas. No tengas miedo de parecer “que no sabes nada”, por algo estás acá ¿verdad?. Además, es hermoso aprender y compartir algo al respecto.

--- 
