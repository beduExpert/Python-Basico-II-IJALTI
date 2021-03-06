[`Backend Fundamentals`](../../README.md) > [`Sesi贸n 01`](../README.md) > `Ejemplo 3`

# Ejemplo 3: Arquitectura Cliente- Servidor

**Objetivo:**

- Comprender las diferencias entre un cliente y un servidor web, 
- La manera en la que se comunican.
- Los diferentes tipos de servidores y protocolos m谩s comunes de la web
**Requerimientos:**

- Navegador web y cuaderno o aplicaci贸n para tomar notas.


## 馃懢 Servidor web


Un servidor web es un conjunto de software y hardware que responden las peticiones que los clientes hacen sobre *World Wide Web*.

Para responder a las peticiones, los servidores utilizan distintos protocolos de transferencia de datos por una red, siendo los principales:

- HTTP/HTTPS
- SMTP 
- FTP

Su prop贸sito principal es permitir el acceso al contenido de los sitios web que requieren lxs usuarixs, para esto, el servidor almacena, procesa y env铆a las paginas web.

## 驴C贸mo funciona un servidor web? 馃

El hardware del servidor est谩 conectado a la internet y permite el intercambio de informaci贸n con otros clientes tambi茅n conectados a la red. Este es una computadora que almacena el contenido del sitio web tales como los archivos HTML, JavaScript, CSS, imagenes, etc, es decir, es un **host**.

Mientras que el software controla el acceso que tienen lxs usuarixs a los archivos del servidor. Todo esto utilizando un modelo cliente servidor. Se accede a este mediante la url (Uniform Resource Locator) del sitio, que sirve como el localizador del sitio y asegura que el contenido ser谩 entregado a quienes que lo solicitaron.

Todo este proceso se hace utilizando el modelo **cliente/servidor**.

## Proceso

Cuando entramos al navegador y colocamos la direcci贸n de nuestro sitio web favorito, el navegador hace el siguiente proceso para encontrar la p谩gina que le pedimos:

1. Con la url, identifica la direcci贸n IP del servidor en el que se *hostea* el sitio que le pedimos
1. Hace una solicitud de los archivos necesarios con el protocolo HTTP 
1. El servidor acepta la petici贸n, busca los archivos y los env铆a como respuesta

![](img/proceso.jpg)

### 馃攼 Arquitectura Cliente-servidor

La arquitectura que gobierna la web actualmente es la arquitectura cliente-servidor.

### 馃懃 **Cliente**

El cliente se ocupa de hacer peticiones, recibir respuestas y presentarlas al usuario.  En los primeros d铆as eran ordenadores de uso com煤n, ahora un cliente es cualquier tipo de dispositivo capaz de enviar una petici贸n, esto engloba smartphones y dispositivos inteligentes como bocinas, luces, refrigeradores, relojes, termostatos, etc.

### 馃捊 **Servidor**

Es un sistema dise帽ado espec铆ficamente para satisfacer las demandas de informaci贸n de los clientes. El servidor recibe las peticiones del cliente, las procesa y responde la informaci贸n solicitada.

Los servidores suelen realizar tareas complejas y especializadas, com煤nmente tambi茅n hacen peticiones a otros sistemas como a servidores de bases de datos o servicios externos e internos *(micro-servicios)*.

## 鉁夛笍 Protocolo HTTP

En computaci贸n, un protocolo es 煤nicamente una manera en la que acordamos que se comunicar谩 un sistema.  

Haciendo una analog铆a podemos decir que un protocolo en la vida real ser铆a la serie de reglas del sistema postal de correo. Si hoy quisi茅ramos enviar una carta por correo necesitar铆amos escribir en un sobre el nombre y la direcci贸n del destinatario, esta direcci贸n a su vez contendr铆a su c贸digo postal, tambi茅n necesitar铆amos un timbre y los datos del remitente. 

De manera similar, el protocolo base para el funcionamiento de la web es el protocolo HTTP, que significa *"Hypertext Transfer Protocol"*. Este protocolo de petici贸n-respuesta est谩 basado en otros protocolos que funcionan en un nivel m谩s bajo de la red. 

<img src="img/HTTP__layers.png" width="700">


### 馃摢 Peticiones

HTTP define un conjunto de m茅todos de petici贸n *(request method)* para indicar que acci贸n se desea realizar. Los m茅todos m谩s importantes son:

### `GET`

Solicita una representaci贸n de un recurso espec铆fico. Las peticiones que usan el m茅todo GET 煤nicamente obtienen datos.

### `POST`

El m茅todo聽**POST**聽se utiliza para enviar una entidad a un recurso en espec铆fico, causando a menudo un cambio en el estado o efectos secundarios en el servidor. Tambi茅n es com煤n que se utilice para crear nuevos registros de recursos en una API.

### `PUT`

El modo聽**PUT**聽reemplaza todas las representaciones actuales del recurso de destino con la carga 煤til de la petici贸n.

### `DELETE`

El m茅todo聽**DELETE**聽borra un recurso聽en espec铆fico.

Estos m茅todos proporcionan las llamadas operaciones **CRUD** o simplemente el **CRUD** y son:

- `Create`
- `Read`
- `Update`
- `Delete`

Puedes encontrar todos los m茅todos existentes en el [siguiente enlace:](https://developer.mozilla.org/es/docs/Web/HTTP/Methods)

### 馃摣 Respuestas

Las respuestas adem谩s de que pueden estar conformadas opcionalmente por un cuerpo o contenido, son definidas por un c贸digo de respuesta. Los c贸digos de respuesta indican si una petici贸n se ha completado exitosamente o no, y nos brindan informaci贸n sobre el estado de la respuesta. Las respuestas se dividen en 5 categor铆as:

1. **Informativas (`100`-`199`)** Usualmente se utilizan para informar que se recibi贸 la petici贸n o informaci贸n .
2. **脡xito (`200`鈥揱299`)** Indica que la petici贸n fue recibida correctamente, entendida y aceptada.
3. **Redirecciones (`300`鈥揱399`)** Le indican al cliente que es necesaria una acci贸n de su parte para completar la petici贸n.
4. **Error del lado del cliente (`400`鈥揱499`)** La solicitud no puede procesarse por un error por parte del cliente, como puede ser un error en sintaxis o falta de alg煤n header.
5. **Error del lado del servidor (`500`鈥揱599`)** La solicitud era aparentemente v谩lida, pero el servidor fall贸 al completarla (errores de conexi贸n, no se encontr贸 la informaci贸n, etc.).

Algunos de los c贸digos de respuesta m谩s comunes son:

### `200 OK` 

Todo salio bien, es la respuesta est谩ndar para peticiones correctas.
![](https://http.cat/200)

### `301 MOVED PERMANENTLY`

El servidor se movi贸 y 茅sta y todas las peticiones futuras deben ser dirigidas a la nueva URL.

![](https://http.cat/301)

### `302 FOUND`

Se requiere que el cliente realice una redirecci贸n temporal. 
![](https://http.cat/302)

### `404 NOT FOUND`

El servidor web no puedo encontrar el recurso solicitado.

![](https://http.cat/404)

### `500 Internal Server Error`

Ocurri贸 un error dentro del servidor al intentar resolver la petici贸n. Es el c贸digo de error m谩s com煤n

![](https://http.cat/500)

Puedes encontrar m谩s c贸digos de respuesta en los 

- [HTTP response status codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
- [HTTP Cats](https://http.cat/)


[`Atr谩s: Sesi贸n 03`](../README.md) | [`Siguiente: Reto-04`](../Reto-04)

