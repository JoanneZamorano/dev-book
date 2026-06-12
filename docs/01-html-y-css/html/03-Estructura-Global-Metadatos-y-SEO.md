# Estructura Global, Metadatos y SEO
Podemos entender la etiqueta `<head>` como el cerebro de nuestro documento. Contiene metadatos e información "detrás de escena" necesaria para los navegadores, motores de búsqueda y plataformas sociales. Los metadatos son, esencialmente, los datos de los datos (como la geolocalización o la fecha incrustada en una fotografía de un teléfono móvil).

__¿Por qué usar las etiquetas dentro de `<head>`?__

- Organización: Permiten separar de forma limpia la información de la estructura del contenido visible.
- Mantenimiento: Simplifican la gestión, indexación y escalabilidad de la página web.
- Rendimiento: Optimizan la velocidad de carga mediante preconexiones y cargas asíncronas de recursos.

## Etiquetas Esenciales del `<head>`
- `<title>`: Define el título de la página que se muestra en la pestaña del navegador y es el enlace principal en los resultados de búsqueda de Google.
- `<base>`: Define la URL base y el objetivo (target) por defecto para todos los enlaces relativos contenidos dentro del documento.
- `<link>`: Establece una relación entre el documento actual y un recurso externo (hojas de estilo CSS, favicons, fuentes tipográficas, etc.). También se usa para optimizar el rendimiento mediante la preconexión a servidores externos.
- `<script>`: Permite cargar o ejecutar código JavaScript para añadir funcionalidades interactivas a la página. Al usarse en esta sección, se suele incluir el atributo defer para evitar que bloquee la carga visual del HTML.

```html
<title>Apuntes de Joa</title>
<base href="https://www.amazon.com/" target="_blank" />
<link rel="stylesheet" href="style.css" />
<link rel="icon" href="favicon.png" type="image/png" />
<link rel="preconnect" href="https://fonts.googleapis.com" />
<script src="script.js" defer></script>

```

## `<meta>` Etiquetas: SEO y Redes Sociales
Las etiquetas <meta> definen metadatos específicos del documento que analizan los motores de búsqueda y los navegadores.

__Configuración General y SEO Técnico__

- `charset`: Establece la codificación de caracteres estándar (normalmente UTF-8) para mostrar correctamente cualquier idioma, tildes y símbolos especiales.
- `viewport`: Configura las dimensiones y la escala de la ventana gráfica para que la página sea responsive (correctamente adaptable a pantallas de teléfonos móviles y tablets).
- `description`: Proporciona una breve descripción del contenido de la página que los buscadores muestran justo debajo del título en los resultados de búsqueda.
- `keywords`: Lista de palabras clave relacionadas con el contenido (actualmente ignorada por los buscadores principales para el posicionamiento, pero útil como metadato de control interno).
- `author`: Especifica el nombre de la persona o entidad creadora del documento.

```html
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<meta name="description" content="Mi página web de apuntes sobre DAM" />
<meta name="keywords" content="DAM, Java, JavaScript" />
<meta name="author" content="Joa Zamorano" />
```

## Meta-etiquetas enfocadas a Redes Sociales 
Estas propiedades controlan de forma estricta cómo aparece el contenido del sitio web (generando tarjetas de previsualización automáticas con título, imagen y descripción) cuando se comparte el enlace en plataformas como Facebook, LinkedIn o X (Twitter).

__Protocolo Open Graph (`og:`)__

- `og:title`: El título llamativo y optimizado que se mostrará en la publicación de la red social.
- `og:description`: El resumen breve que acompaña al título dentro de la tarjeta compartida.
- `og:image`: La URL de la imagen en miniatura (preview) que capturará la atención visual del usuario en su feed.
- `og:url`: La dirección web exacta y canónica a la que serán redirigidos los usuarios al hacer clic sobre la publicación.
- `og:type`: Representa el tipo de contenido del objeto que se comparte (por ejemplo: un sitio web general, un artículo de blog, un vídeo o una pista de música).

```html
<meta property="og:title" content="Guía Definitiva de Flexbox y Grid en CSS" />
<meta property="og:description" content="Domina el diseño responsive y aprende a maquetar tus páginas web como un profesional con este análisis profundo." />
<meta property="og:image" content="https://tusitio.com/img/css-guide-preview.png" />
<meta property="og:url" content="https://tusitio.com/blog/guia-flexbox-grid" />
<meta property="og:type" content="article" />
```

## Tarjetas de Twitter / X (twitter:)

- `twitter:card`: Define el formato visual de la tarjeta que se generará en la cronología (como un resumen simple o un resumen con imagen grande).
- `twitter:title`: El título optimizado específicamente para el feed de esta plataforma.
- `twitter:description`: El texto de resumen adaptado a las dinámicas de lectura de esta red social.
- `twitter:image`: La imagen de previsualización configurada con las dimensiones y proporciones óptimas que exige la interfaz.

```html
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="Guía Definitiva de Flexbox y Grid en CSS" />
<meta name="twitter:description" content="Domina el diseño responsive y aprende a maquetar tus páginas web como un profesional con este análisis profundo." />
<meta name="twitter:image" content="https://tusitio.com/img/css-guide-twitter.png" />
```