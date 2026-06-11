## 📅 ¿Qué es HTML y para qué sirve?

**HTML** significa *HyperText Markup Language* (Lenguaje de Marcas de Hipertexto). Lo primero y más importante que debes grabar a fuego: **no es un lenguaje de programación**. No tiene lógica, ni condicionales, ni bucles. 

Su única función es **definir la estructura y el contenido de una página web**. Piensa en HTML como el esqueleto de un edificio: define dónde van las paredes (párrafos), las puertas (enlaces) y las ventanas (imágenes). Luego vendrá CSS a pintarlo y JavaScript a darle vida.

---

## 🛠️ Sintaxis básica de una etiqueta HTML

HTML funciona mediante **etiquetas** (tags), que son palabras clave encerradas entre símbolos de menor que `<` y mayor que `>`.

### 1. Etiqueta de apertura y cierre
La inmensa mayoría de los elementos en HTML envuelven al contenido utilizando un juego doble:

* **Etiqueta de apertura:** Le dice al navegador dónde empieza el elemento (ejemplo: `<p>`).
* **Etiqueta de cierre:** Le dice dónde termina. Es idéntica a la de apertura pero lleva una barra inclinada `/` antes del nombre (ejemplo: `</p>`).

```html
<p>Esto es el contenido de un párrafo.</p>
```

---

## 🏗️ 2. Estructura completa de un documento HTML5

Para que un navegador entienda que está leyendo una página web moderna, el archivo necesita una estructura mínima obligatoria. Aquí tienes la plantilla base:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Primera Página</title>
</head>
<body>
    <h1>¡Hola Mundo desde mi dev-book!</h1>
</body>
</html>
```

### 2.1 Declaración del tipo de documento (`<!DOCTYPE html>`)
Es la primera línea de cualquier archivo web. No es una etiqueta HTML en sí, sino una instrucción para el navegador que dice: *"Oye, prepárate porque lo que viene a continuación es un documento HTML5 moderno"*.

### 2.2 Elemento `<html>`
Es la raíz de todo el documento. Envuelve absolutamente todo el código de la página. Siempre debe llevar el atributo `lang="es"` para decirle a los motores de búsqueda y a los lectores de pantalla que el contenido está en español.

### 2.3 Elemento `<head>`
Es la "cabeza" del documento. Todo lo que metes aquí dentro es invisible para el usuario, pero vital para el navegador. Contiene los metadatos de la página:

* **`charset="UTF-8"`**: Configuración de caracteres para que funcionen las tildes y la "ñ".
* **`viewport`**: Configuración de la pantalla para que la web sea responsiva y se adapte perfectamente a teléfonos móviles y tablets.
* **`<title>`**: Define el texto exacto que aparece en la pestaña de tu navegador.

### 2.4 Elemento `<body>`
Es el "cuerpo" de la página. Aquí va absolutamente todo lo que el usuario sí puede ver en su pantalla: los títulos (`<h1>`), los párrafos (`<p>`), los enlaces (`<a>`), las imágenes y los formularios.

---

## 🌐 3. DOCTYPE y compatibilidad con navegadores

En los años 90 y principios de los 2000, la web era un caos: cada navegador interpretaba el código como quería. Si no especificabas el tipo de documento al principio, los navegadores modernos activaban de forma automática un modo de renderizado antiguo llamado **"Quirks Mode"** (modo de compatibilidad). En este modo, el navegador intentará emular los fallos de Internet Explorer 5 para que las páginas viejas no se rompieran, lo que hacía que los diseños modernos se descuadraran por completo.

Al escribir **`<!DOCTYPE html>`** al inicio del archivo, fuerzas al navegador a activar el **"Standards Mode"** (modo estándar). Esto obliga a Google Chrome, Safari, Firefox y Edge a seguir las reglas oficiales y modernas de HTML5 por igual, garantizando que tu web se comporte y se vea de la misma forma en cualquier rincón.

---

## 🏅 4. Validación de HTML

Escribir código que "funcione" a simple vista no significa que cumpla con los estándares. Los navegadores son extremadamente permisivos; si se te olvida cerrar un tag como `</p>`, el navegador intentará "adivinar" dónde terminaba y lo arreglará en segundo plano. Sin embargo, esto consume recursos del dispositivo y puede provocar que tu interfaz se rompa misteriosamente en otros navegadores.

Para comprobar que tu estructura es perfecta y sigue las reglas oficiales del consorcio **W3C** (el organismo internacional que regula los estándares de la web), se utilizan herramientas automáticas llamadas **Validadores**.

El más famoso y utilizado a nivel profesional es el **W3C Markup Validation Service**. Solo tienes que subir tu archivo `.html` o copiar tu código directamente allí; la herramienta escaneará tu estructura y te dará un reporte limpio indicándote si tienes errores de sintaxis. ¡Es ideal para limpiar vicios de maquetación!

---

## 💬 5. Los comentarios en HTML

Los comentarios son líneas de texto que el navegador ignora por completo a la hora de dibujar la web. Sirven exclusivamente para que dejes anotaciones, expiraciones o recordatorios dentro de tu código para ti mismo o para otros desarrolladores que lean tu proyecto en el futuro.

En HTML se escriben así: `<!-- Esto es un comentario -->`


> 💡 **Truco de productividad en VS Code:** No hace falta que escribas los símbolos a mano. Colócate en cualquier línea de tu archivo y pulsa **`Ctrl + /`** (en Windows) para comentar o descomentar esa línea al instante.
`