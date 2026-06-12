# Estructura, Multimedia y Rutas

## 1. Fundamentos de los Elementos HTML
Los elementos son los bloques de construcción de cualquier documento HTML. Representan la estructura del contenido (encabezados, párrafos, enlaces, imágenes, etc.).

### Sintaxis Básica
La mayoría de los elementos constan de una etiqueta de apertura, el contenido y una etiqueta de cierre:
```html
<elementName>Content goes here</elementName>
```

### Elementos Vacíos (Void Elements)
Son aquellos que no pueden tener contenido ni necesitan una etiqueta de cierre; solo disponen de una etiqueta de inicio. Es común y aceptable verlos con o sin una barra inclinada `/` al final:

`<img>` o `<img/>`

`<meta>` o `<meta/>`

### Atributos
Son valores que se ubican dentro de la etiqueta de apertura para proporcionar información adicional o especificar el comportamiento del elemento. Su sintaxis básica es element `attribute="value"`.

Atributos Booleanos: Son atributos que pueden estar presentes o ausentes. Si están presentes, su valor es verdadero; de lo contrario, es falso (ej. `disabled`, `readonly`, `required`, `controls`, `loop`, `muted`, `allowfullscreen`).

## 2. Elementos Comunes del Cuerpo (`<body>`)
Encabezados (`<h1>` a `<h6>`): Se utilizan para indicar la importancia del contenido. Entre menor sea el número, más importante es el contenido (por ejemplo, `<h1>` es más importante que `<h2>`).

Párrafos (`<p>`): Se utilizan para estructurar los bloques de texto en una página web.

Contenedores y Organización:

- `<section>`: Se utiliza para dividir el contenido en secciones más pequeñas.
- `<div>`: Es un elemento genérico que no tiene significado semántico. Se usa como contenedor para agrupar otros elementos.
- `<main>`: Representa el contenido principal de una página web.
- `<footer>`: Se coloca en la parte inferior del documento y suele contener información de derechos de autor (copyright) u otros enlaces importantes.

Énfasis de Texto:

- `<em>`: Se utiliza para poner énfasis básico en un fragmento de texto.
- `<strong>`: Se utiliza para poner un énfasis fuerte, indicando un sentido de urgencia o seriedad.

Listas:

- Desordenadas (`<ul>`): Crean listas con viñetas; contienen elementos `<li>` anidados en su interior.
- Ordenadas (`<ol>`): Crean listas numeradas o secuenciales utilizando también elementos `<li>`.
Ejemplos de listas:

=== "Listas Desordenadas"
    ```html
    <ul>
      <li>hierba gatera</li>
      <li>punteros láser</li>
      <li>lasaña</li>
    </ul>
    ```

=== "Listas Ordenadas"
    ```html
    <ol>
      <li>tratamiento contra pulgas</li>
      <li>truenos</li>
      <li>otros gatos</li>
    </ol>
    ```


Figuras:

- El elemento `<figure>` se utiliza para agrupar contenido multimedia como imágenes y diagramas. 
- El elemento <`figcaption`> se emplea para representar una leyenda o título para dicho contenido dentro de la figura.

## 3. Identificadores, Clases y Enlaces
### IDs vs. Clases
- IDs `id`: Son identificadores únicos para elementos HTML. Solo deben usarse una vez por documento y no pueden contener espacios (se recomienda usar guiones para separar palabras).
- Clases `class`: Se utilizan para agrupar elementos con el fin de aplicarles estilos y comportamientos. A diferencia de los IDs, se puede reutilizar el mismo nombre de clase en todo el documento y su valor puede incluir espacios para asignar múltiples clases.

__Enlaces `<a>` y el Atributo target__
El elemento de anclaje `<a>` aplica enlaces a una página web mediante el atributo href (que especifica la URL de destino). El atributo target le dice al navegador dónde debe abrir dicha URL:

| Atributo de Video | Descripción |
| :--- | :--- |
| `controls` | Muestra los controles predeterminados del navegador para video (play, pausa, volumen, etc.). |
| `autoplay` | Comienza a reproducir el video automáticamente tan pronto como esté listo. |
| `loop` | Hace que el video vuelva a empezar automáticamente cada vez que termine. |
| `muted` | Silencia el audio del video por defecto. |
| `poster` | Especifica una imagen que se mostrará mientras el video se descarga o hasta que el usuario presione play. |
| `preload` | Sugiere al navegador cómo debe cargarse el video al cargar la página (`none`, `metadata`, `auto`). |
| `src` | La URL del archivo de video que se va a reproducir. |
| `width` y `height` | Establecen las dimensiones del reproductor de video en píxeles. |

#### Estados de los Enlaces (Pseudoclases)
- `:link:` Estado por defecto de un enlace que el usuario aún no ha visitado ni con el que ha interactuado.
- `:visited:` Se aplica cuando el usuario ya ha visitado la página a la que apunta el enlace.
- `:hover:` Se activa cuando el usuario mantiene el cursor sobre el enlace.
- `:focus:` Se aplica cuando el enlace recibe el foco (por ejemplo, al navegar con el teclado).
- `:active:` Se aplica a los enlaces que están siendo activados (por ejemplo, durante el clic izquierdo del mouse).

## 4. Rutas Absolutas vs. Relativas
Una ruta es una cadena de texto que especifica la ubicación de un archivo o directorio en un sistema de archivos para enlazar recursos (imágenes, hojas de estilo, scripts).

__Sintaxis de Ruta:__
- `/` o `\`: Separador de rutas (depende del sistema operativo).
- `.`: Señala el directorio actual.
- `..`: Señala el directorio padre.

### Ruta Absoluta
Es un enlace completo a un recurso. Comienza desde el directorio raíz, incluye toda la jerarquía de carpetas, el nombre del archivo con su extensión y, si está en la web, incluye también el protocolo (`http`, `https`, `file`) junto al nombre del dominio.

### Ruta Relativa
Especifica la ubicación de un archivo en relación con el directorio del archivo actual. No incluye el protocolo ni el nombre de dominio, lo que la hace más corta y flexible para enlaces internos del mismo sitio.

## 5. Elementos Multimedia y Contenido Reemplazado
Un elemento reemplazado es aquel cuyo contenido está determinado por un recurso externo en lugar de estar definido por el propio CSS del documento.

### Imágenes (`<img>`)
Se utiliza para agregar imágenes. Requiere el atributo `src` para especificar la ubicación del archivo y es una buena práctica incluir el atributo `alt` (texto alternativo descriptivo).

- Formatos de imagen: Aunque PNG y JPG son comunes, se recomienda usar formatos más optimizados como WEBP o AVIF, a menos que se requiera soporte para navegadores antiguos.
- SVGs: Gráficos vectoriales escalables que rastrean datos basados en rutas y ecuaciones. Se pueden escalar a cualquier tamaño sin perder calidad.

### Elemento `<iframe>`
Significa inline frame. Es un elemento en línea utilizado para incorporar otro contenido HTML directamente dentro de la página actual. Admite atributos como `src`, `width`, `height` y `allowfullscreen` (que permite el modo de pantalla completa).

### Audio (`<audio>`) y Video (`<video>`)
Permiten añadir contenido de sonido y video de forma nativa. El elemento audio soporta formatos como mp3, wav y ogg, mientras que el video soporta mp4, ogg y webm.

- Atributos clave:
    - `controls`: Atributo booleano que habilita los controles integrados del reproductor (pausa, volumen, etc.). Si se omite, no se mostrarán.
    - `loop`: Hace que el archivo se reproduzca de manera continua.
    - `muted`: Inicia el contenido en estado silenciado.
    - `poster` (Exclusivo de `<video>`): Permite mostrar una imagen fija mientras el video se está descargando.
- Elemento `<source>`: Dado que el soporte de formatos varía entre navegadores, se pueden incluir múltiples etiquetas `<source>` dentro de `<audio>` o `<video>` para que el navegador seleccione de forma automática la primera fuente compatible que entienda.

## 6. Estructura Global, Metadatos y SEO
Todo documento HTML estándar requiere una plantilla base con los siguientes elementos esenciales:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title>freeCodeCamp</title>
  <link rel="stylesheet" href="./styles.css" />
</head>
<body>
  </body>
</html>
```

- `<!DOCTYPE html>`: Informa al navegador qué versión de HTML se está utilizando.
- `<html lang="...">`: Es el elemento de nivel superior o raíz del documento. El atributo lang especifica el idioma.
- `<head>`: Contiene metadatos e información detrás de escena necesaria para los navegadores y motores de búsqueda.
- `<meta charset="utf-8" />`: Establece la codificación de caracteres estándar UTF-8 que el sistema utiliza para almacenar y mostrar los datos de los caracteres.
- `<title>`: Establece el texto que aparece en la pestaña o ventana del navegador.
- `<link>`: Se usa para enlazar recursos externos como hojas de estilo CSS (rel="stylesheet") o iconos del sitio mediante el atributo href.
- `<body>`: Representa y contiene todo el contenido visible del documento HTML.
- `<script>`: Se utiliza para incrustar o enlazar código ejecutable. Aunque se puede escribir JavaScript directamente dentro de las etiquetas, la mejor práctica es enlazar a un archivo externo usando el atributo src (`<script src="archivo.js"></script>`).

### SEO y Etiquetas Open Graph (OG)
- __SEO__ (Optimización para Motores de Búsqueda): Práctica que optimiza las páginas web para que sean más visibles y ocupen mejores lugares en los buscadores. El elemento `<meta name="description" content="...">` ayuda proporcionando una breve descripción de la página.

- __Etiquetas Open Graph__: Este protocolo permite controlar cómo aparece el contenido del sitio web cuando se comparte en plataformas de redes sociales (Facebook, LinkedIn, etc.) mediante elementos `<meta>` dentro del `<head>`:

   - `property="og:title"`: Establece el título que se muestra en las publicaciones de redes sociales.
   - `property="og:type"`: Representa el tipo de contenido que se comparte (ej. website, article, video, music).
   - `property="og:image"`: Establece la imagen miniatura que se mostrará en la publicación.
   - `property="og:url"`: Configura la URL exacta a la que los usuarios serán redirigidos al hacer clic.

## 7. Entidades HTML
Una entidad HTML (o referencia de carácter) es un conjunto de caracteres especiales que sirve para representar un carácter reservado en el lenguaje. Esto evita que el navegador los confunda con código HTML real. Ejemplos comunes:

- El símbolo ampersand: `&amp;` (representa a &)
- El símbolo menor que: `&lt;` (representa a <)