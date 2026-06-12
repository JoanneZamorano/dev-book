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

`<img>` o `<img/>` y `<meta>` o `<meta/>`

### Atributos
Son valores que se ubican dentro de la etiqueta de apertura para proporcionar información adicional o especificar el comportamiento del elemento. Su sintaxis básica es element `attribute="value"`.

Atributos Booleanos: Son atributos que pueden estar presentes o ausentes. Si están presentes, su valor es verdadero; de lo contrario, es falso (ej. `disabled`, `readonly`, `required`, `controls`, `loop`, `muted`, `allowfullscreen`).

## 2. Elementos Comunes del Cuerpo (`<body>`)
__Encabezados (`<h1>` a `<h6>`)__ 

Se utilizan para indicar la importancia del contenido. Entre menor sea el número, más importante es el contenido (por ejemplo, `<h1>` es más importante que `<h2>`).

__Párrafos (`<p>`)__

Se utilizan para estructurar los bloques de texto en una página web.

__Estructura y Bloques Semánticos (Layout)__

Estas etiquetas dividen el cuerpo de la web en regiones clave, facilitando la accesibilidad, el SEO y la lectura por parte de los navegadores:

- `<main>`: Representa el contenido principal, único y central de la página web. No debe duplicarse en otros documentos.
- `<header>`: Define la cabecera visual de la página o de una sección. Suele contener el logotipo, títulos, nombres de autores o barras de introducción.
- `<nav>`: Define un bloque o zona dedicada exclusivamente a la navegación, agrupando enlaces internos o externos (menús, índices o tablas de contenidos).
- `<section>`: Se utiliza para dividir el contenido en secciones o bloques temáticos más pequeños dentro del documento.
- `<article>`: Define una entidad de contenido independiente y autoexplicativa por sí misma que podría ser distribuida o reutilizada de forma autónoma (ej. un artículo de blog, una reseña, un post de foro o un comentario).
- `<aside>`: Representa una sección de contenido relacionado tangencialmente con el tema principal (ej. barras laterales, publicidad, cajas de datos o enlaces recomendados).
- `<footer>`: Se coloca en la parte inferior del documento o de una sección. Suele contener información de derechos de autor (copyright), datos de contacto o enlaces legales.
Formularios y Búsqueda
- `<search>`: Introduce un área semántica dedicada específicamente a la búsqueda dentro de la página, envolviendo normalmente a un formulario de filtrado o consulta.
Datos e Información de Contacto
- `<address>`: Define la información de contacto del autor o propietario del documento o artículo (puede incluir correos electrónicos, URLs, direcciones físicas o números de teléfono).
Contenedores Genéricos (Sin valor semántico)
- `<div>`: Es un elemento puramente genérico que no aporta ningún significado conceptual. Se utiliza únicamente como "caja" o divisor para agrupar otros elementos con el fin de aplicarles estilos CSS o manipularlos con JavaScript. ¡Cuidado! Hay que evitar el "abuso del div" para no empobrecer la accesibilidad de la web.

__Énfasis de Texto:__

- `<em>`: Se utiliza para poner énfasis básico en un fragmento de texto.
- `<strong>`: Se utiliza para poner un énfasis fuerte, indicando un sentido de urgencia o seriedad.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="utf-8" />
    <title>Ejemplo Semántico Completo</title>
    <link rel="stylesheet" href="estilos.css" />
</head>
<body>
    <header>
        <h1>Dev-Book de Joa</h1>
        <nav>
            <ul>
                <li><a href="#principal">Inicio</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>
    <search>
        <form>
            <input type="search" placeholder="Buscar apuntes..." />
        </form>
    </search>
    <main id="principal">
        <section>
            <h2>Apuntes de HTML5</h2>
            <p>Aprender semántica es <strong>muy importante</strong> para el SEO.</p>
            <div class="caja-alerta">
                <p><em>Nota rápida:</em> No abuses de esta etiqueta.</p>
            </div>
            <article>
                <h3>Reseña de Etiquetas</h3>
                <p>Las listas pueden ser de dos tipos:</p>
            </article>
        </section>
        <aside>
            <h3>Enlaces recomendados</h3>
            <p>Visita la documentación oficial de MDN.</p>
        </aside>
    </main>
    <footer>
        <address>
            Escrito por <a href="mailto:joa@devbook.com">Joa</a>
        </address>
        <p>Copyright &copy; 2026 - Mi Cuaderno de Bitácora</p>
    </footer>
    <script src="archivo.js"></script>
</body>
</html>
```

__Listas:__

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

### Otros elementos

- `style`: Aplica estilos CSS directamente a un elemento.
- `lang`: Define el idioma del contenido del elemento.
- `dir`: Indica la dirección del texto (`ltr` para izquierda a derecha o `rtl` para derecha a izquierda).
- `title`: Muestra un texto informativo al pasar el cursor sobre el elemento.
- `data-`: Permite almacenar datos personalizados en un elemento.
- `accesskey`: Permite asignar una tecla de acceso rápido a un elemento HTML, facilitando la navegación para usuarios con necesidad de accesibilidad o que prefieren el teclado al ratón.

## 3. Identificadores, Clases y Enlaces
### IDs vs. Clases
- __IDs `id`__: Son identificadores únicos para elementos HTML. Solo deben usarse una vez por documento y no pueden contener espacios (se recomienda usar guiones para separar palabras).
- __Clases `class`__: Se utilizan para agrupar elementos con el fin de aplicarles estilos y comportamientos. A diferencia de los IDs, se puede reutilizar el mismo nombre de clase en todo el documento y su valor puede incluir espacios para asignar múltiples clases.

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

```html
<style>
        a:link {
            color: #00bcd4; 
            text-decoration: none;
        }
        a:visited {
            color: #9c27b0; 
        }
        a:hover {
            color: #ff5722;
            text-decoration: underline;
        }
        a:focus {
            outline: 2px solid #ff5722;
            background-color: #fff3e0;
        }
        a:active {
            color: #e91e63; 
        }
    </style>
```

## 4. Rutas Absolutas vs. Relativas
Una ruta es una cadena de texto que especifica la ubicación de un archivo o directorio en un sistema de archivos para enlazar recursos (imágenes, hojas de estilo, scripts).

__Sintaxis de Ruta:__

- `/` o `\`: Separador de rutas (depende del sistema operativo).
- `.`: Señala el directorio actual.
- `..`: Señala el directorio padre.

### Ruta Absoluta
Es un enlace completo a un recurso. Comienza desde el directorio raíz, incluye toda la jerarquía de carpetas, el nombre del archivo con su extensión y, si está en la web, incluye también el protocolo (`http`, `https`, `file`) junto al nombre del dominio.

```html
<a href="https://developer.mozilla.org">Visitar MDN</a>
```

### Ruta Relativa
Especifica la ubicación de un archivo en relación con el directorio del archivo actual. No incluye el protocolo ni el nombre de dominio, lo que la hace más corta y flexible para enlaces internos del mismo sitio.

```html
<img src="./imagenes/logo.png" alt="Logo de mi web" />
```

## 5. Elementos Multimedia y Contenido Reemplazado
Un elemento reemplazado es aquel cuyo contenido está determinado por un recurso externo en lugar de estar definido por el propio CSS del documento.

### Imágenes (`<img>`)
La etiqueta `img` se utiliza para mostrar una imagen en la aplicación web. Es una de las etiquetas más utilizadas en HTML y es compatible con todos los navegadores web.

#### Atributos:

* `src`: Ruta de la imagen. Especifica la ruta del archivo de imagen que se desea mostrar. La ruta puede ser relativa o absoluta.
* `alt`: Texto alternativo. Proporciona un texto alternativo que describe la imagen. Este texto se muestra si la imagen no se puede cargar o si el usuario tiene un lector de pantalla. Es importante para la accesibilidad web.
* `title`: Información sobre la imagen. Muestra un texto informativo al pasar el cursor sobre la imagen.
* `loading`: Carga de la imagen. Indica cómo se debe cargar la imagen. Puede ser:
    * `"eager"`: Carga la imagen inmediatamente.
    * `"lazy"`: Carga la imagen solo cuando es visible en la pantalla (mejora el rendimiento de la web).
    * `"auto"`: El navegador decide cómo cargar la imagen.

```html
<img 
<img 
  src="[https://images.unsplash.com/photo-1506744038136-46273834b3fb](https://images.unsplash.com/photo-1506744038136-46273834b3fb)" 
  alt="Valle de Yosemite con un río reflejando las montañas al atardecer" 
  title="Parque Nacional de Yosemite, California - Vista panorámica desde el valle" 
  loading="lazy"
/>
/>
```

__Formatos de imagen:__ 
Aunque PNG y JPG son comunes, se recomienda usar formatos más optimizados como WEBP o AVIF, a menos que se requiera soporte para navegadores antiguos.

SVGs: Gráficos vectoriales escalables que rastrean datos basados en rutas y ecuaciones. Se pueden escalar a cualquier tamaño sin perder calidad.

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

```html
<audio controls loop muted>
    <source src="audio/podcast.mp3" type="audio/mpeg" />
    <source src="audio/podcast.ogg" type="audio/ogg" />
</audio>

<video controls loop muted poster="imagenes/portada-video.jpg" width="480">
    <source src="videos/tutorial.webm" type="video/webm" />
    <source src="videos/tutorial.mp4" type="video/mp4" />
</video>
```

## 6. Entidades HTML
Una entidad HTML (o referencia de carácter) es un conjunto de caracteres especiales que sirve para representar un carácter reservado en el lenguaje. Esto evita que el navegador los confunda con código HTML real. Ejemplos comunes:

- El símbolo ampersand: `&amp;` (representa a &)
- El símbolo menor que: `&lt;` (representa a <)

```html
<p>
    Para abrir una etiqueta de párrafo en HTML, debes escribir el símbolo 
    <strong>&lt;</strong> seguido de la letra p y el símbolo 
    <strong>&gt;</strong> (es decir: &lt;p&gt;).
</p>

<p>
    Si tienes dudas sobre desarrollo, escríbenos a soporte 
    <strong>&amp;</strong> ayuda, o revisa los términos de uso 
    <strong>&copy;</strong> 2026.
</p>
```