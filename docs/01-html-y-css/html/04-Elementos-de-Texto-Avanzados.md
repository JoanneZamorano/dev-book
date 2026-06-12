# HTML Semántico y Elementos de Texto Avanzados

Este resumen recopila la importancia del HTML semántico y describe las etiquetas clave para estructurar texto, citas, fechas y anotaciones avanzadas.

---

## 1. Importancia del HTML Semántico

El HTML semántico consiste en utilizar etiquetas que aportan significado y estructura al contenido, en lugar de definir únicamente su apariencia visual.

* **Jerarquía de Encabezados:** Es fundamental utilizar correctamente las etiquetas desde `<h1>` (nivel más alto e importante) hasta `<h6>` (nivel más bajo) para mantener una estructura lógica.
* **Elementos de Presentación (Obsoletos):** Etiquetas como `<center>`, `<big>` y `<font>` están obsoletas porque solo definían la apariencia (tarea que hoy en día corresponde al CSS).
* **Elementos Semánticos:** Etiquetas como `<header>`, `<nav>` y `<figure>` que ayudan a los navegadores y motores de búsqueda a entender qué función cumple cada sección del documento.

---

## 2. Elementos Estructurales Comunes

* **`<header>` (Encabezado):** Define la cabecera de un documento o de una sección específica.
* **`<main>` (Principal):** Contiene el contenido principal y exclusivo de la página web.
* **`<section>` (Sección):** Divide el contenido en bloques o secciones más pequeñas.
* **`<nav>` (Navegación):** Representa una sección que contiene enlaces de navegación del sitio.
* **`<figure>` (Figura):** Se utiliza como contenedor para ilustraciones, imágenes o diagramas.

```html
<main>
    <section id="inicio">
        <h2>Introducción Semántica</h2>
        <p>El contenido de <strong>gran importancia</strong> va aquí, mientras que los términos en otros idiomas como 
        <i lang="en">"webmaster"</i> o el texto <s>obsoleto</s> se marcan de forma diferente.</p>
    </section>

    <section>
        <h2>Conceptos y Referencias</h2>
        <dl>
            <dt>Acrónimo</dt>
            <dd>La <abbr title="HyperText Markup Language">HTML</abbr> es clave en la web.</dd>
        </dl>

        <p>Como se indica en <cite>Libro Dev</cite>: <q>HTML estructurará tu mundo</q>.</p>
        <blockquote cite="https://ejemplo.com">
            <p>Cita larga en bloque extraída de una fuente externa.</p>
        </blockquote>
    </section>

    <section>
        <h2>Datos y Código</h2>
        <p>Publicado el <time datetime="2026-06-12">12 de junio</time>.</p>
        <p>Usa <code>let x = 2;</code> para calcular m<sup>2</sup> o la fórmula del H<sub>2</sub>o.</p>
        
        <pre>
        Texto preformateado
        que respeta   los espacios.
        </pre>

        <figure>
            <img src="foto.jpg" alt="Vista miniatura" />
            <figcaption>Pie de foto explicativo.</figcaption>
        </figure>
    </section>
</main>
```

---

## 3. Énfasis y Distinciones de Texto

HTML ofrece diferentes etiquetas para modificar el impacto visual del texto, cada una con un propósito semántico distinto:

* **`<em>` (Énfasis):** Marca el texto con un énfasis de estrés o énfasis hablado (suele mostrarse en cursiva).
* **`<strong>` (Importancia fuerte):** Indica que el texto tiene una gran importancia o urgencia (suele mostrarse en negrita).
* **`<i>` (Texto idiomático):** Se usa para resaltar pensamientos, términos técnicos, palabras en otro idioma o voces alternas. No indica importancia, solo que el texto es diferente al que lo rodea. Se puede usar el atributo `lang` para especificar el idioma (por ejemplo, `lang="fr"` para el francés).
* **`<b>` (Atraer atención):** Se utiliza para llamar la atención sobre palabras clave o nombres de productos en resúmenes y reseñas. No añade una importancia semántica real al significado del contenido.
* **`<s>` (Tachado):** Representa contenido que ya no es preciso, correcto o relevante.

```html
    <p>
        Es fundamental aprender <strong>HTML semántico</strong> porque 
    <em>aporta estructura real</em> al contenido de tu web.
    </p>

    <p>
    Evita por completo usar etiquetas de presentación <s>obsoletas</s>, 
    ya que hoy en día es mejor captar la <b>atención</b> del usuario con estilos 
    o destacar términos extranjeros como <i lang="en">"responsive"</i>.
    </p>
```

---

## 4. Listas de Descripción

Para organizar agrupaciones de términos y definiciones, se utiliza una estructura de tres elementos:

* **`<dl>` (Lista de descripción):** Envuelve y representa la lista completa de términos y descripciones.
* **`<dt>` (Término):** Especifica el término o palabra que se va a definir.
* **`<dd>` (Detalles):** Contiene la descripción o definición correspondiente al término anterior.

```html
<dl>
    <dt>Estilos de Énfasis</dt>
    <dd>
        Se usa <strong>strong</strong> para dar mucha importancia y 
        <em>em</em> para el énfasis hablado.
    </dd>

    <dt>Estilos Especiales</dt>
    <dd>
        Marcamos texto <s>incorrecto o tachado</s>, destacamos palabras clave con 
        <b>b</b>, e identificamos términos extranjeros usando <i lang="en">inline</i>.
    </dd>
</dl>
```

---

## 5. Citas y Referencias

* **`<blockquote>` (Cita en bloque):** Se usa para secciones largas de texto citadas de otra fuente. Incluye el atributo `cite`, cuyo valor debe ser la URL de la fuente original.
* **`<q>` (Cita en línea):** Se utiliza para representar citas breves integradas dentro de un párrafo.
* **`<cite>` (Citación):** Se emplea para atribuir visualmente la fuente de un trabajo referenciado, marcando habitualmente el título de la obra o referencia.

```html
    <p>
    Como se menciona en <cite>El Quijote</cite>, una de las frases más 
    famosas es: <q>En un lugar de la Mancha...</q>.
    </p>

    <blockquote cite="https://www.ejemplo.com/libro">
    <p>Esta es una sección más larga de texto que se cita directamente de un bloque o fuente externa separada.</p>
    </blockquote>
```

---

## 6. Datos, Formatos y Elementos Técnicos

### Fechas y Horas (`<time>`)
Se utiliza para representar fechas u horas. Cuenta con el atributo `datetime` para traducir este valor a un formato legible por máquinas (estándar **ISO 8601**). El formato estándar es `YYYY-MM-DDThh:mm:ss`, donde la letra `T` actúa como separador entre la fecha y la hora.

### Texto Técnico y Matemático
* **`<abbr>` (Abreviatura):** Representa abreviaturas o acrónimos. Permite usar el atributo `title` para mostrar la descripción completa al pasar el cursor por encima.
* **`<address>` (Dirección):** Se utiliza para indicar la información de contacto del autor o entidad de la página.
* **`<code>` (Código en línea):** Se usa para insertar un fragmento corto de código de computadora.
* **`<pre>` (Texto preformateado):** Muestra el texto respetando los espacios en blanco y saltos de línea tal y como están escritos en el código fuente.
* **`<sup>` (Superíndice):** Eleva el texto. Útil para exponentes matemáticos, letras superiores o números ordinales.
* **`<sub>` (Subíndice):** Baja el texto respecto a la línea base. Común para fórmulas químicas o variables numéricas.
* **`<u>` (Anotación no articulada):** Renderiza el texto con una línea inferior para indicar una anotación no textual.

```html
<p>
  La <abbr title="Organización de las Naciones Unidas">ONU</abbr> declaró que el 
  agua (H<sub>2</sub>O) es vital. Su web usa el puerto <sup>80</sup> y requiere 
  revisar esta <u>anotación ortográfica</u>.
</p>

<p>
  Escribe a nuestra dirección si tienes dudas: 
  <address>contacto@ejemplo.com</address>
</p>

<p>Para imprimir en consola usa el fragmento <code>console.log()</code>.</p>

<pre>
Bloque de texto preformateado
  que respeta   todos los espacios
    y saltos de línea.
</pre>
```

### Tipografía de Asia Oriental (Ruby)
Se utiliza para añadir guías de pronunciación o explicaciones sobre caracteres ideográficos:
* **`<ruby>`:** Contenedor principal de la anotación.
* **`<rt>`:** Contiene el texto de la anotación o pronunciación.
* **`<rp>`:** Paréntesis de seguridad que se muestran únicamente en navegadores antiguos que no soportan la tipografía ruby.

```html
<p>
    La palabra para "gato" en japonés se escribe así: 
    <ruby>
        猫 <rp>(</rp><rt>neko</rt><rp>)</rp>
    </ruby>.
</p>
```

---

## 7. Enlaces Internos (Jump Links)

Los enlaces internos permiten a los usuarios saltar directamente a otra sección de la misma página web (muy útil para tablas de contenido o páginas muy largas). 

Para implementarlos se utiliza la etiqueta de anclaje `<a>` con el atributo `href="#id"`, asegurándose de que el elemento de destino tenga configurado exactamente ese mismo `id`.

```html
<a href="#glosario">Ir al Glosario</a>

<h2 id="glosario">Glosario Semántico</h2>
<p>Aquí empieza la sección a la que has saltado.</p>
```