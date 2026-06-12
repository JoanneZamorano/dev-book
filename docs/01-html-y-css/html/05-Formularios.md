# Formularios en HTML

Los formularios son el mecanismo principal para recolectar datos introducidos por los usuarios y enviarlos a un servidor o procesarlos en la aplicación web.

## 1. El Contenedor Principal (`<form>`)

Es la etiqueta que envuelve y agrupa todos los elementos interactivos del formulario. Cuenta con dos atributos fundamentales para gestionar el envío de datos:

* **`action`**: Especifica la URL del servidor o destino a donde se deben enviar los datos recolectados cuando el usuario procesa el formulario.
* **`method`**: Define el método HTTP que se utilizará para transferir la información. Los dos valores principales son:
    * `GET`: Envía los datos de forma pública adjuntándolos de forma visible directamente en la barra de direcciones (URL). Se usa principalmente para búsquedas o filtrados.
    * `POST`: Envía los datos de forma oculta y segura dentro del cuerpo de la petición HTTP. Se utiliza para enviar información sensible (contraseñas) o datos de creación y modificación (registro de usuarios).

```html

```

## 2. Etiquetas de Estructura y Accesibilidad

Para mantener un formulario accesible, legible y bien estructurado para todos los usuarios y lectores de pantalla, se utilizan componentes específicos de organización:

* **`<label>`**: Define la etiqueta de texto asociada directamente a un elemento de entrada de datos. Facilita la accesibilidad permitiendo que, al hacer clic en el texto, el cursor salte automáticamente al campo interactivo correspondiente.
* **`<fieldset>`**: Contenedor semántico que agrupa de forma visual y lógica varios campos o controles que tienen una temática común dentro del mismo formulario.
* **`<legend>`**: Define el título o descripción corta para el grupo de campos creado por un elemento fieldset.

```html

```

## 3. Elementos de Entrada y Selección de Datos

### El Elemento Versátil (`<input>`)
Es el elemento interactivo más común y cambia por completo su comportamiento, apariencia y restricciones visuales según el valor asignado a su atributo `type`.

#### Tipos de Entrada de Texto y Datos Comunes:
* `text`: Campo estándar para cadenas de texto cortas (nombres, apellidos).
* `password`: Campo de texto que oculta los caracteres introducidos sustituyéndolos por puntos o asteriscos para proteger la privacidad.
* `email`: Campo optimizado para direcciones de correo electrónico, que valida de forma automática si el texto contiene la estructura adecuada (un símbolo arroba y un dominio).
* `number`: Restringe el campo para que solo acepte valores numéricos, permitiendo configurar límites máximos y mínimos.
* `url`: Campo diseñado exclusivamente para introducir direcciones web válidas.
* `tel`: Campo específico para números de teléfono (útil para desplegar el teclado numérico en dispositivos móviles).

```html

```

#### Tipos de Control y Selección:
* `checkbox`: Casilla de verificación de tipo booleano. Permite al usuario marcar o desmarcar una o varias opciones independientes dentro de un grupo.
* `radio`: Botón de opción circular. A diferencia de las casillas, solo permite seleccionar una única opción exclusiva dentro de un grupo que comparta el mismo identificador de nombre.
* `file`: Botón interactivo que permite al usuario seleccionar e incorporar uno o varios archivos desde el almacenamiento de su propio dispositivo para subirlos a la web.

```html

```

### Bloques de Texto Largo (`<textarea>`)
Se utiliza para campos que requieren múltiples líneas de texto (comentarios, opiniones, descripciones largas). Dispone de los atributos `rows` y `cols` para predefinir el tamaño inicial de la caja de texto.

```html

```

### Listas Desplegables (`<select>`)
Crea un menú desplegable para ahorrar espacio en la interfaz. El contenedor principal es la etiqueta `select` y cada una de las opciones disponibles dentro de la lista se define mediante etiquetas de contenido llamadas `<option>`.

```html

```

## 4. Botones de Acción (`<button>`)

Permiten al usuario interactuar y desencadenar eventos sobre el formulario. Al igual que el input, su comportamiento depende estrictamente de su atributo `type`:

* `submit`: El tipo por defecto. Envía de forma automática todos los datos recolectados en el formulario hacia la dirección especificada en el atributo action.
* `reset`: Borra y limpia de forma inmediata todos los campos del formulario, devolviéndolos a sus valores iniciales predeterminados.
* `button`: Un botón genérico que no realiza ninguna acción por sí mismo, diseñado para ser programado con funciones interactivas personalizadas mediante JavaScript.

```html

```

## 5. Atributos Esenciales de los Controles

Los elementos de un formulario admiten una serie de atributos clave que controlan su comportamiento, su validación nativa y la forma en que los datos viajan al servidor:

* **`name`**: Es el atributo más importante para el servidor. Actúa como el identificador o clave de la información introducida; sin este atributo, los datos de ese campo específico no se enviarán al procesar el formulario.
* **`id`**: Identificador único del elemento dentro de la página, utilizado principalmente para enlazar el control de entrada con su etiqueta label correspondiente.
* **`value`**: Define el valor inicial predeterminado del campo o el valor que se enviará de forma interna al servidor (crucial en los botones de tipo radio y checkbox).
* **`placeholder`**: Texto de ayuda en color gris translúcido que aparece dentro del campo antes de que el usuario escriba algo, sirviendo como sugerencia o ejemplo de formato.
* **`required`**: Atributo booleano que impide el envío del formulario si el campo se encuentra vacío, forzando al usuario a rellenarlo.
* **`disabled`**: Desactiva el control por completo, impidiendo que el usuario interactúe con él y evitando que su valor se envíe al servidor.
* **`readonly`**: Permite al usuario ver y enfocar el contenido del campo, pero le impide modificar su valor. A diferencia de disabled, este valor sí se envía al servidor.

```html
<form action="procesar_registro.php" method="post" enctype="multipart/form-data">
    
    <fieldset>
        <legend>Datos de Usuario</legend>
        
        <label for="username">Nombre:</label>
        <input type="text" id="username" name="usuario" placeholder="Ej. JoaDev" required />

        <label for="avatar">Foto de perfil:</label>
        <input type="file" id="avatar" name="foto" accept="image/*" />
    </fieldset>

    <fieldset>
        <legend>Preferencias</legend>

        <label for="rol">Rol principal:</label>
        <select id="rol" name="rol_usuario" required>
            <option value="">Selecciona una opción</option>
            <option value="frontend">Frontend</option>
            <option value="backend">Backend</option>
        </select>

        <label for="juego">Videojuego favorito:</label>
        <input type="text" id="juego" name="videojuego" list="juegos-disponibles" />
        <datalist id="juegos-disponibles">
            <option value="The Legend of Zelda" />
            <option value="Super Mario Odyssey" />
            <option value="Elden Ring" />
        </datalist>
    </fieldset>

    <div style="margin: 15px 0;">
        <label>Progreso del perfil:</label>
        <progress value="75" max="100"></progress>
    </div>

    <input type="submit" value="Registrarse" />
</form>
```