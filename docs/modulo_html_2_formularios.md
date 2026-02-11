# MÓDULO HTML-2: Formularios y Entrada de Datos

## 📚 Introducción

Los **formularios** son la forma principal de recopilar información del usuario en la web. Desde un simple campo de búsqueda hasta un complejo registro de usuario, los formularios son fundamentales para la interactividad.

**Analogía:** Un formulario HTML es como una hoja de papel con campos que el usuario completa. Cuando presiona "Enviar", esa información se envía a un servidor (o se procesa con JavaScript).

---

## 1️⃣ Elemento `<form>` - Contenedor Principal

El elemento `<form>` agrupa todos los campos de entrada y define cómo se enviarán los datos.

### 1.1 Sintaxis Básica

```html
<form action="/procesar" method="POST">
  <!-- Campos del formulario aquí -->
  <button type="submit">Enviar</button>
</form>
```

### 1.2 Atributos Principales

#### **`action` - ¿Dónde se envían los datos?**

```html
<!-- Enviar a un archivo PHP -->
<form action="procesar.php">

<!-- Enviar a una API -->
<form action="https://api.comictracker.com/comics">

<!-- Procesar en la misma página (omitir action) -->
<form>
```

**Nota:** Si omites `action`, los datos se envían a la URL actual.

#### **`method` - ¿Cómo se envían los datos?**

```html
<!-- GET: Datos visibles en la URL (búsquedas, filtros) -->
<form action="/buscar" method="GET">
  <input type="search" name="q">
  <button type="submit">Buscar</button>
</form>
<!-- Resultado: /buscar?q=spider-man -->

<!-- POST: Datos ocultos en el cuerpo (formularios sensibles) -->
<form action="/registro" method="POST">
  <input type="email" name="email">
  <input type="password" name="password">
  <button type="submit">Registrarse</button>
</form>
```

**¿Cuándo usar cada uno?**

| Method | Uso | Características |
|--------|-----|-----------------|
| **GET** | Búsquedas, filtros, navegación | Datos en URL, se puede marcar como favorito |
| **POST** | Registro, login, envío de datos | Datos ocultos, más seguro para información sensible |

#### **`novalidate` - Desactivar validación HTML**

```html
<!-- Útil para testing o validación personalizada con JavaScript -->
<form novalidate>
  <input type="email" required>
  <button type="submit">Enviar</button>
</form>
```

#### **`autocomplete` - Control de autocompletado**

```html
<!-- Activar autocompletado (por defecto) -->
<form autocomplete="on">

<!-- Desactivar autocompletado -->
<form autocomplete="off">
```

---

## 2️⃣ `<label>` - Etiquetas de Campos

El elemento `<label>` asocia texto descriptivo con un campo de entrada. **Es crucial para la accesibilidad.**

### 2.1 Dos Formas de Asociar

#### **Forma 1: Usando `for` e `id`**

```html
<label for="nombre-comic">Nombre del cómic:</label>
<input type="text" id="nombre-comic" name="nombre">
```

**Ventajas:**
- Más flexible (label e input pueden estar separados)
- Más común en formularios complejos

#### **Forma 2: Anidando el input**

```html
<label>
  Nombre del cómic:
  <input type="text" name="nombre">
</label>
```

**Ventajas:**
- Más conciso
- No requiere `id`

### 2.2 Beneficios de `<label>`

**1. Accesibilidad:**
```html
<!-- ✅ BIEN: Lectores de pantalla anuncian "Nombre del cómic, campo de texto" -->
<label for="nombre">Nombre del cómic:</label>
<input type="text" id="nombre">

<!-- ❌ MAL: Solo "campo de texto" (confuso) -->
<span>Nombre del cómic:</span>
<input type="text">
```

**2. Área de clic ampliada:**
```html
<!-- Al hacer clic en el texto, el input recibe el foco -->
<label for="acepto">
  <input type="checkbox" id="acepto">
  Acepto los términos y condiciones
</label>
```

### 2.3 Ejemplo Completo

```html
<form>
  <div>
    <label for="titulo">Título del cómic:</label>
    <input type="text" id="titulo" name="titulo" required>
  </div>
  
  <div>
    <label for="editorial">Editorial:</label>
    <select id="editorial" name="editorial">
      <option value="marvel">Marvel</option>
      <option value="dc">DC</option>
    </select>
  </div>
</form>
```

---

## 3️⃣ `<input>` - Campos de Entrada

El elemento `<input>` es el más versátil. Su comportamiento cambia según el atributo `type`.

### 3.1 Tipos de Input Básicos

#### **`type="text"` - Texto simple (por defecto)**

```html
<label for="titulo">Título:</label>
<input type="text" id="titulo" name="titulo">
```

#### **`type="email"` - Correo electrónico**

```html
<label for="email">Email:</label>
<input type="email" id="email" name="email">
```

**Validación automática:**
- Requiere formato válido (usuario@dominio.com)
- Teclado optimizado en móviles (muestra @)

#### **`type="password"` - Contraseña**

```html
<label for="password">Contraseña:</label>
<input type="password" id="password" name="password">
```

**Características:**
- Oculta el texto ingresado
- No se autocompleta por defecto (seguridad)

#### **`type="checkbox"` - Casilla de verificación**

```html
<label>
  <input type="checkbox" name="leido" value="si">
  Ya leí este cómic
</label>
```

**Múltiples checkboxes:**
```html
<fieldset>
  <legend>Géneros favoritos:</legend>
  
  <label>
    <input type="checkbox" name="generos" value="superheroes">
    Superhéroes
  </label>
  
  <label>
    <input type="checkbox" name="generos" value="scifi">
    Ciencia Ficción
  </label>
  
  <label>
    <input type="checkbox" name="generos" value="horror">
    Horror
  </label>
</fieldset>
```

#### **`type="radio"` - Opción única**

```html
<fieldset>
  <legend>Estado de lectura:</legend>
  
  <label>
    <input type="radio" name="estado" value="leyendo">
    Leyendo
  </label>
  
  <label>
    <input type="radio" name="estado" value="completado">
    Completado
  </label>
  
  <label>
    <input type="radio" name="estado" value="pendiente" checked>
    Pendiente
  </label>
</fieldset>
```

**Regla importante:** Todos los radio buttons del mismo grupo deben tener el **mismo `name`**.

#### **`type="file"` - Subir archivos**

```html
<label for="portada">Subir portada:</label>
<input type="file" id="portada" name="portada" accept="image/*">
```

**Atributos útiles:**
- `accept`: Tipos de archivo permitidos
- `multiple`: Permitir múltiples archivos

```html
<!-- Solo imágenes -->
<input type="file" accept="image/png, image/jpeg">

<!-- Múltiples archivos -->
<input type="file" multiple>

<!-- PDFs -->
<input type="file" accept=".pdf">
```

---

### 3.2 Tipos de Input Modernos

#### **`type="search"` - Búsqueda**

```html
<label for="buscar">Buscar cómics:</label>
<input type="search" id="buscar" name="q" placeholder="Spider-Man, Batman...">
```

**Diferencias con `type="text"`:**
- Icono de búsqueda en algunos navegadores
- Botón "X" para limpiar el campo
- Semánticamente indica búsqueda

**Ejemplo completo:**
```html
<form action="/buscar" method="GET">
  <label for="busqueda">Buscar:</label>
  <input 
    type="search" 
    id="busqueda" 
    name="q" 
    placeholder="Título, autor, editorial..."
    autocomplete="off"
  >
  <button type="submit">Buscar</button>
</form>
```

#### **`type="number"` - Números**

```html
<label for="numero">Número de edición:</label>
<input type="number" id="numero" name="numero" min="1" max="999">
```

**Atributos específicos:**

```html
<input 
  type="number" 
  name="precio"
  min="0"           <!-- Valor mínimo -->
  max="1000"        <!-- Valor máximo -->
  step="0.01"       <!-- Incremento (permite decimales) -->
  value="9.99"      <!-- Valor inicial -->
>
```

**Casos de uso:**
```html
<!-- Edad (enteros) -->
<input type="number" name="edad" min="1" max="120" step="1">

<!-- Precio (decimales) -->
<input type="number" name="precio" min="0" step="0.01">

<!-- Calificación (0-10) -->
<input type="number" name="rating" min="0" max="10" step="0.5">
```

**⚠️ Advertencia:** `type="number"` no es ideal para códigos (ISBN, teléfonos) porque:
- Elimina ceros a la izquierda
- No permite caracteres como guiones
- Para códigos, usa `type="text"` con `pattern`

```html
<!-- ❌ MAL: ISBN como number -->
<input type="number" name="isbn">

<!-- ✅ BIEN: ISBN como text con patrón -->
<input type="text" name="isbn" pattern="[0-9]{13}" placeholder="9781234567890">
```

#### **`type="url"` - URL**

```html
<label for="sitio">Sitio web oficial:</label>
<input type="url" id="sitio" name="url" placeholder="https://ejemplo.com">
```

**Validación automática:**
- Requiere formato de URL válido
- Teclado optimizado en móviles (muestra .com, /)

**Ejemplo:**
```html
<label for="wiki">Enlace a Wikipedia:</label>
<input 
  type="url" 
  id="wiki" 
  name="wiki_url"
  placeholder="https://es.wikipedia.org/wiki/..."
  pattern="https://.*"
>
```

#### **`type="date"` - Fecha**

```html
<label for="fecha-publicacion">Fecha de publicación:</label>
<input type="date" id="fecha-publicacion" name="fecha">
```

**Atributos específicos:**

```html
<input 
  type="date" 
  name="fecha_lectura"
  min="2020-01-01"     <!-- Fecha mínima -->
  max="2026-12-31"     <!-- Fecha máxima -->
  value="2026-02-11"   <!-- Fecha inicial (formato YYYY-MM-DD) -->
>
```

**Casos de uso:**
```html
<!-- Fecha de nacimiento (máximo hoy) -->
<input type="date" name="nacimiento" max="2026-02-11">

<!-- Fecha de publicación (entre 1930 y hoy) -->
<input type="date" name="publicacion" min="1930-01-01" max="2026-02-11">
```

**Otros tipos de fecha:**

```html
<!-- Mes y año -->
<input type="month" name="mes" value="2026-02">

<!-- Semana -->
<input type="week" name="semana" value="2026-W06">

<!-- Hora -->
<input type="time" name="hora" value="14:30">

<!-- Fecha y hora -->
<input type="datetime-local" name="fecha_hora" value="2026-02-11T14:30">
```

#### **`type="tel"` - Teléfono**

```html
<label for="telefono">Teléfono:</label>
<input type="tel" id="telefono" name="telefono" placeholder="+52 55 1234 5678">
```

**Características:**
- Teclado numérico en móviles
- No valida formato (varía por país)
- Usa `pattern` para validación específica

```html
<!-- Teléfono mexicano -->
<input 
  type="tel" 
  name="telefono"
  pattern="[0-9]{10}"
  placeholder="5512345678"
>
```

#### **`type="color"` - Selector de color**

```html
<label for="color-favorito">Color favorito:</label>
<input type="color" id="color-favorito" name="color" value="#ff0000">
```

**Nota:** El valor debe ser en formato hexadecimal (#RRGGBB).

#### **`type="range"` - Deslizador**

```html
<label for="calificacion">Calificación (1-10):</label>
<input type="range" id="calificacion" name="rating" min="1" max="10" value="5">
<output>5</output>
```

**Atributos:**
- `min`, `max`, `step`, `value` (igual que `number`)

**Ejemplo con JavaScript para mostrar valor:**
```html
<label for="rating">Calificación:</label>
<input 
  type="range" 
  id="rating" 
  name="rating" 
  min="0" 
  max="10" 
  step="0.5" 
  value="5"
  oninput="document.getElementById('rating-value').textContent = this.value"
>
<output id="rating-value">5</output>
```

---

### 3.3 Tabla Resumen de Tipos de Input

| Tipo | Uso | Validación | Teclado móvil |
|------|-----|------------|---------------|
| `text` | Texto general | Ninguna | Estándar |
| `email` | Correos | Formato email | Con @ |
| `password` | Contraseñas | Ninguna | Estándar |
| `search` | Búsquedas | Ninguna | Con búsqueda |
| `number` | Números | Min/max/step | Numérico |
| `url` | URLs | Formato URL | Con .com / |
| `tel` | Teléfonos | Ninguna | Numérico |
| `date` | Fechas | Formato fecha | Calendario |
| `time` | Horas | Formato hora | Reloj |
| `color` | Colores | Formato hex | Selector |
| `range` | Deslizador | Min/max | N/A |
| `file` | Archivos | Ninguna | N/A |
| `checkbox` | Sí/No múltiple | Ninguna | N/A |
| `radio` | Opción única | Ninguna | N/A |

---

## 4️⃣ `<textarea>` - Texto Multilínea

Para textos largos (comentarios, descripciones, reseñas).

### 4.1 Sintaxis Básica

```html
<label for="resena">Reseña del cómic:</label>
<textarea id="resena" name="resena" rows="5" cols="40"></textarea>
```

**Atributos específicos:**
- `rows`: Número de líneas visibles
- `cols`: Ancho en caracteres
- `maxlength`: Límite de caracteres
- `placeholder`: Texto de ayuda

### 4.2 Ejemplo Completo

```html
<label for="sinopsis">Sinopsis:</label>
<textarea 
  id="sinopsis" 
  name="sinopsis"
  rows="8"
  cols="50"
  maxlength="500"
  placeholder="Describe la historia del cómic..."
  required
></textarea>
<p>Máximo 500 caracteres</p>
```

### 4.3 Diferencias con `<input type="text">`

| Característica | `<input type="text">` | `<textarea>` |
|----------------|----------------------|--------------|
| **Líneas** | Una sola | Múltiples |
| **Tamaño** | Atributo `size` | `rows` y `cols` |
| **Valor inicial** | `value="..."` | Entre etiquetas |
| **Uso** | Nombres, emails | Comentarios, descripciones |

```html
<!-- Input: valor en atributo -->
<input type="text" value="Spider-Man">

<!-- Textarea: valor entre etiquetas -->
<textarea>Spider-Man es un superhéroe...</textarea>
```

---

## 5️⃣ `<select>` - Listas Desplegables

Para elegir una o más opciones de una lista predefinida.

### 5.1 Sintaxis Básica

```html
<label for="editorial">Editorial:</label>
<select id="editorial" name="editorial">
  <option value="marvel">Marvel Comics</option>
  <option value="dc">DC Comics</option>
  <option value="image">Image Comics</option>
  <option value="dark-horse">Dark Horse</option>
</select>
```

### 5.2 Atributos de `<option>`

#### **`value` - Valor enviado al servidor**

```html
<select name="estado">
  <!-- Lo que ve el usuario vs lo que se envía -->
  <option value="reading">Leyendo</option>
  <option value="completed">Completado</option>
  <option value="pending">Pendiente</option>
</select>
```

#### **`selected` - Opción preseleccionada**

```html
<select name="idioma">
  <option value="es" selected>Español</option>
  <option value="en">Inglés</option>
  <option value="fr">Francés</option>
</select>
```

#### **`disabled` - Opción deshabilitada**

```html
<select name="formato">
  <option value="">-- Selecciona un formato --</option>
  <option value="fisico">Físico</option>
  <option value="digital">Digital</option>
  <option value="ambos" disabled>Ambos (próximamente)</option>
</select>
```

### 5.3 Agrupación con `<optgroup>`

```html
<label for="personaje">Personaje favorito:</label>
<select id="personaje" name="personaje">
  <optgroup label="Marvel">
    <option value="spiderman">Spider-Man</option>
    <option value="ironman">Iron Man</option>
    <option value="wolverine">Wolverine</option>
  </optgroup>
  
  <optgroup label="DC">
    <option value="batman">Batman</option>
    <option value="superman">Superman</option>
    <option value="wonderwoman">Wonder Woman</option>
  </optgroup>
</select>
```

### 5.4 Selección Múltiple

```html
<label for="generos">Géneros de interés:</label>
<select id="generos" name="generos" multiple size="5">
  <option value="superheroes">Superhéroes</option>
  <option value="scifi">Ciencia Ficción</option>
  <option value="fantasy">Fantasía</option>
  <option value="horror">Horror</option>
  <option value="crime">Crimen</option>
</select>
<p>Mantén Ctrl (Cmd en Mac) para seleccionar múltiples</p>
```

**Atributos:**
- `multiple`: Permite selección múltiple
- `size`: Número de opciones visibles

---

## 6️⃣ Atributos de Formulario (Aplicables a Inputs)

### 6.1 Validación

#### **`required` - Campo obligatorio**

```html
<input type="text" name="titulo" required>
<textarea name="descripcion" required></textarea>
<select name="editorial" required>
  <option value="">-- Selecciona --</option>
  <option value="marvel">Marvel</option>
</select>
```

**Nota:** El navegador impide el envío si el campo está vacío.

#### **`minlength` y `maxlength` - Longitud de texto**

```html
<!-- Contraseña de 8-20 caracteres -->
<input type="password" name="password" minlength="8" maxlength="20" required>

<!-- Comentario de máximo 500 caracteres -->
<textarea name="comentario" maxlength="500"></textarea>
```

#### **`min` y `max` - Rango de valores**

```html
<!-- Año de publicación (1930-2026) -->
<input type="number" name="año" min="1930" max="2026">

<!-- Calificación (0-10) -->
<input type="number" name="rating" min="0" max="10" step="0.5">

<!-- Fecha de lectura (no en el futuro) -->
<input type="date" name="fecha" max="2026-02-11">
```

#### **`pattern` - Expresión regular**

```html
<!-- Código postal de 5 dígitos -->
<input type="text" name="cp" pattern="[0-9]{5}" placeholder="12345">

<!-- ISBN de 13 dígitos -->
<input type="text" name="isbn" pattern="[0-9]{13}" placeholder="9781234567890">

<!-- Solo letras y espacios -->
<input type="text" name="autor" pattern="[A-Za-z\s]+" placeholder="Stan Lee">
```

**Con mensaje personalizado:**
```html
<input 
  type="text" 
  name="codigo" 
  pattern="[A-Z]{3}-[0-9]{4}"
  title="Formato: ABC-1234"
  placeholder="ABC-1234"
>
```

---

### 6.2 Autocompletado y Sugerencias

#### **`autocomplete` - Control de autocompletado**

```html
<!-- Activar autocompletado de nombre -->
<input type="text" name="nombre" autocomplete="name">

<!-- Activar autocompletado de email -->
<input type="email" name="email" autocomplete="email">

<!-- Desactivar autocompletado -->
<input type="text" name="codigo" autocomplete="off">
```

**Valores comunes:**
- `name`: Nombre completo
- `email`: Correo electrónico
- `username`: Nombre de usuario
- `current-password`: Contraseña actual
- `new-password`: Nueva contraseña
- `tel`: Teléfono
- `street-address`: Dirección
- `postal-code`: Código postal

#### **`list` y `<datalist>` - Sugerencias**

```html
<label for="autor">Autor:</label>
<input type="text" id="autor" name="autor" list="autores-sugeridos">

<datalist id="autores-sugeridos">
  <option value="Stan Lee">
  <option value="Jack Kirby">
  <option value="Steve Ditko">
  <option value="Frank Miller">
  <option value="Alan Moore">
</datalist>
```

**Características:**
- El usuario puede escribir libremente
- Se muestran sugerencias mientras escribe
- Puede seleccionar una sugerencia o ignorarlas

**Ejemplo con URLs:**
```html
<label for="sitio">Sitio web:</label>
<input type="url" id="sitio" name="sitio" list="sitios-comics">

<datalist id="sitios-comics">
  <option value="https://www.marvel.com">
  <option value="https://www.dccomics.com">
  <option value="https://imagecomics.com">
</datalist>
```

---

### 6.3 Presentación y Usabilidad

#### **`placeholder` - Texto de ayuda**

```html
<input type="text" name="titulo" placeholder="Ej: The Amazing Spider-Man #1">
<input type="email" name="email" placeholder="tu@email.com">
<input type="search" name="q" placeholder="Buscar por título, autor...">
```

**⚠️ Advertencia:** `placeholder` NO reemplaza a `<label>`.

```html
<!-- ❌ MAL: Solo placeholder -->
<input type="text" name="nombre" placeholder="Nombre">

<!-- ✅ BIEN: Label + placeholder -->
<label for="nombre">Nombre:</label>
<input type="text" id="nombre" name="nombre" placeholder="Ej: Peter Parker">
```

#### **`readonly` - Solo lectura**

```html
<!-- El usuario puede ver pero no editar -->
<input type="text" name="isbn" value="978-1234567890" readonly>
```

**Diferencia con `disabled`:**
- `readonly`: El valor SÍ se envía al servidor
- `disabled`: El valor NO se envía al servidor

#### **`disabled` - Deshabilitado**

```html
<!-- El campo está inactivo y no se envía -->
<input type="text" name="premium" value="Función premium" disabled>
<button type="submit" disabled>Enviar</button>
```

#### **`autofocus` - Foco automático**

```html
<!-- El cursor se posiciona aquí al cargar la página -->
<input type="search" name="q" autofocus>
```

**⚠️ Usar con moderación:** Solo un campo por página.

---

### 6.4 Otros Atributos Útiles

#### **`name` - Identificador para envío**

```html
<!-- SIEMPRE necesario para enviar datos -->
<input type="text" name="titulo">
<!-- Se envía como: titulo=valor -->
```

#### **`value` - Valor inicial**

```html
<input type="text" name="autor" value="Stan Lee">
<input type="number" name="rating" value="8">
<input type="date" name="fecha" value="2026-02-11">
```

#### **`step` - Incremento**

```html
<!-- Incrementos de 0.5 -->
<input type="number" name="rating" min="0" max="10" step="0.5">

<!-- Incrementos de 5 -->
<input type="number" name="precio" min="0" max="100" step="5">

<!-- Cualquier valor (decimales) -->
<input type="number" name="precio" step="any">
```

#### **`multiple` - Múltiples valores**

```html
<!-- Múltiples archivos -->
<input type="file" name="portadas" multiple>

<!-- Múltiples emails -->
<input type="email" name="destinatarios" multiple>
```

---

## 7️⃣ Elementos Complementarios

### 7.1 `<fieldset>` y `<legend>` - Agrupación

```html
<form>
  <fieldset>
    <legend>Información del Cómic</legend>
    
    <label for="titulo">Título:</label>
    <input type="text" id="titulo" name="titulo">
    
    <label for="autor">Autor:</label>
    <input type="text" id="autor" name="autor">
  </fieldset>
  
  <fieldset>
    <legend>Estado de Lectura</legend>
    
    <label>
      <input type="radio" name="estado" value="leyendo">
      Leyendo
    </label>
    
    <label>
      <input type="radio" name="estado" value="completado">
      Completado
    </label>
  </fieldset>
</form>
```

**Beneficios:**
- Agrupa campos relacionados visualmente
- Mejora la accesibilidad
- Permite deshabilitar grupos completos

```html
<fieldset disabled>
  <legend>Funciones Premium (Deshabilitadas)</legend>
  <input type="text" name="feature1">
  <input type="text" name="feature2">
</fieldset>
```

### 7.2 `<output>` - Resultado de Cálculo

```html
<form oninput="total.value = parseInt(precio.value) * parseInt(cantidad.value)">
  <label for="precio">Precio:</label>
  <input type="number" id="precio" name="precio" value="10">
  
  <label for="cantidad">Cantidad:</label>
  <input type="number" id="cantidad" name="cantidad" value="1">
  
  <p>Total: $<output name="total" for="precio cantidad">10</output></p>
</form>
```

---

## 8️⃣ Ejemplo Completo: Formulario de Registro de Cómic

```html
<form action="/comics" method="POST" enctype="multipart/form-data">
  <fieldset>
    <legend>Información Básica</legend>
    
    <div>
      <label for="titulo">Título del cómic: *</label>
      <input 
        type="text" 
        id="titulo" 
        name="titulo" 
        required
        maxlength="100"
        placeholder="Ej: The Amazing Spider-Man #1"
      >
    </div>
    
    <div>
      <label for="autor">Autor:</label>
      <input 
        type="text" 
        id="autor" 
        name="autor"
        list="autores-populares"
        placeholder="Stan Lee"
      >
      <datalist id="autores-populares">
        <option value="Stan Lee">
        <option value="Jack Kirby">
        <option value="Frank Miller">
      </datalist>
    </div>
    
    <div>
      <label for="editorial">Editorial: *</label>
      <select id="editorial" name="editorial" required>
        <option value="">-- Selecciona una editorial --</option>
        <option value="marvel">Marvel Comics</option>
        <option value="dc">DC Comics</option>
        <option value="image">Image Comics</option>
        <option value="otros">Otros</option>
      </select>
    </div>
    
    <div>
      <label for="fecha-publicacion">Fecha de publicación:</label>
      <input 
        type="date" 
        id="fecha-publicacion" 
        name="fecha_publicacion"
        min="1930-01-01"
        max="2026-12-31"
      >
    </div>
    
    <div>
      <label for="numero">Número de edición:</label>
      <input 
        type="number" 
        id="numero" 
        name="numero"
        min="1"
        placeholder="1"
      >
    </div>
  </fieldset>
  
  <fieldset>
    <legend>Detalles</legend>
    
    <div>
      <label for="sinopsis">Sinopsis:</label>
      <textarea 
        id="sinopsis" 
        name="sinopsis"
        rows="5"
        maxlength="500"
        placeholder="Describe brevemente la historia..."
      ></textarea>
    </div>
    
    <div>
      <label for="rating">Calificación (0-10):</label>
      <input 
        type="range" 
        id="rating" 
        name="rating"
        min="0"
        max="10"
        step="0.5"
        value="5"
        oninput="document.getElementById('rating-value').textContent = this.value"
      >
      <output id="rating-value">5</output>
    </div>
    
    <div>
      <label for="portada">Portada:</label>
      <input 
        type="file" 
        id="portada" 
        name="portada"
        accept="image/*"
      >
    </div>
  </fieldset>
  
  <fieldset>
    <legend>Estado de Lectura</legend>
    
    <label>
      <input type="radio" name="estado" value="leyendo">
      Leyendo
    </label>
    
    <label>
      <input type="radio" name="estado" value="completado" checked>
      Completado
    </label>
    
    <label>
      <input type="radio" name="estado" value="pendiente">
      Pendiente
    </label>
  </fieldset>
  
  <fieldset>
    <legend>Preferencias</legend>
    
    <label>
      <input type="checkbox" name="favorito" value="si">
      Marcar como favorito
    </label>
    
    <label>
      <input type="checkbox" name="notificaciones" value="si">
      Recibir notificaciones de nuevos números
    </label>
  </fieldset>
  
  <div>
    <button type="submit">Guardar Cómic</button>
    <button type="reset">Limpiar Formulario</button>
  </div>
</form>
```

---

## 📋 Tabla Resumen de Atributos

| Atributo | Elementos | Propósito |
|----------|-----------|-----------|
| `required` | input, select, textarea | Campo obligatorio |
| `placeholder` | input, textarea | Texto de ayuda |
| `minlength` / `maxlength` | input, textarea | Longitud de texto |
| `min` / `max` | input (number, date) | Rango de valores |
| `step` | input (number, range) | Incremento |
| `pattern` | input | Validación con regex |
| `autocomplete` | input | Control de autocompletado |
| `readonly` | input, textarea | Solo lectura (se envía) |
| `disabled` | input, select, textarea, button | Deshabilitado (no se envía) |
| `autofocus` | input, select, textarea | Foco automático |
| `multiple` | input (file, email), select | Múltiples valores |
| `accept` | input (file) | Tipos de archivo |
| `list` | input | Conecta con datalist |

---

## ✅ Checklist de Buenas Prácticas

**Estructura:**
- [ ] Cada `<input>` tiene un `<label>` asociado
- [ ] Campos relacionados agrupados con `<fieldset>` y `<legend>`
- [ ] Atributo `name` en todos los campos que se envían
- [ ] Formulario tiene `action` y `method` apropiados

**Validación:**
- [ ] Campos obligatorios marcados con `required`
- [ ] Validación de formato con `type` apropiado (email, url, number)
- [ ] Límites de longitud con `minlength`/`maxlength`
- [ ] Rangos de valores con `min`/`max`
- [ ] Patrones personalizados con `pattern` y `title`

**Usabilidad:**
- [ ] `placeholder` para ejemplos (no reemplaza `label`)
- [ ] `autocomplete` apropiado para datos comunes
- [ ] `autofocus` solo en un campo (si es necesario)
- [ ] Tipos de input modernos para mejor UX móvil

**Accesibilidad:**
- [ ] Todos los `<input>` tienen `<label>` con `for`/`id`
- [ ] Radio buttons y checkboxes agrupados en `<fieldset>`
- [ ] Mensajes de error claros
- [ ] Orden lógico de tabulación

---

## 🎯 Ejercicio Práctico

Crea un formulario de "Búsqueda Avanzada de Cómics" que incluya:

1. Campo de búsqueda por texto (título/autor)
2. Filtro por editorial (select con opciones)
3. Rango de fechas (desde - hasta)
4. Rango de calificación (slider)
5. Filtros por género (checkboxes múltiples)
6. Estado de lectura (radio buttons)
7. Ordenar por (select)

**Requisitos:**
- Formulario semántico con `<fieldset>` y `<legend>`
- Todos los campos con `<label>` apropiados
- Validación HTML donde sea apropiado
- Uso de tipos de input modernos
- Método GET (para que la búsqueda sea compartible por URL)

---

## 📚 Recursos Adicionales

- **MDN Web Docs - Forms:** Guía completa de formularios HTML
- **HTML5 Input Types:** Referencia de todos los tipos de input
- **Can I Use:** Compatibilidad de navegadores para inputs modernos
- **WebAIM - Forms:** Guía de accesibilidad en formularios

---

**¡Recuerda!** Los formularios son la principal forma de interacción usuario-aplicación. Un formulario bien diseñado es accesible, intuitivo y valida datos antes de enviarlos al servidor. 📝✨
