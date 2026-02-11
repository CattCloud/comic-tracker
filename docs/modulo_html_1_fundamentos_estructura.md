# MÓDULO HTML-1: Fundamentos y Estructura Semántica

## 📚 Introducción

HTML (HyperText Markup Language) es el **lenguaje de marcado** que estructura el contenido de la web. No es un lenguaje de programación, sino un sistema de etiquetas que le dice al navegador: "esto es un título", "esto es un párrafo", "esto es un enlace".

**Analogía:** Si una página web fuera una casa, HTML sería la estructura (paredes, techo, habitaciones), CSS sería la decoración (pintura, muebles), y JavaScript sería la funcionalidad (electricidad, plomería).

---

## 1️⃣ Estructura Semántica Básica

La **semántica** en HTML significa usar etiquetas que describen el **significado** del contenido, no solo su apariencia. Esto beneficia a:
- **Navegadores:** Entienden mejor la estructura
- **Lectores de pantalla:** Ayudan a personas con discapacidad visual
- **Motores de búsqueda:** Indexan mejor tu contenido
- **Desarrolladores:** El código es más legible y mantenible

### 1.1 `<header>` - Encabezado

**¿Qué es?** Contenedor para contenido introductorio o de navegación.

**¿Dónde se usa?**
- Al inicio de la página (encabezado principal)
- Al inicio de un `<article>` o `<section>` (encabezado de sección)

**Sintaxis:**
```html
<header>
  <h1>ComicTracker</h1>
  <p>Tu biblioteca digital de cómics</p>
</header>
```

**Contenido típico:**
- Logo o nombre del sitio
- Navegación principal
- Eslogan o descripción breve
- Herramientas de búsqueda

**Ejemplo completo:**
```html
<header>
  <img src="logo.png" alt="Logo ComicTracker">
  <h1>ComicTracker</h1>
  <nav>
    <ul>
      <li><a href="#inicio">Inicio</a></li>
      <li><a href="#coleccion">Mi Colección</a></li>
    </ul>
  </nav>
</header>
```

---

### 1.2 `<main>` - Contenido Principal

**¿Qué es?** Contenedor para el contenido **principal y único** de la página.

**Reglas importantes:**
- ✅ Solo **uno** por página
- ✅ No debe estar dentro de `<header>`, `<footer>`, `<nav>`, `<article>`, o `<aside>`
- ✅ Debe contener el contenido central que cambia entre páginas

**Sintaxis:**
```html
<main>
  <h2>Mis Cómics Favoritos</h2>
  <!-- Contenido principal aquí -->
</main>
```

**¿Qué va dentro?**
- El contenido único de esta página
- Artículos, secciones, formularios principales
- Todo lo que NO sea navegación, pie de página o barras laterales

**Ejemplo:**
```html
<main>
  <h2>Últimos Cómics Añadidos</h2>
  <section>
    <article>
      <h3>Spider-Man #1</h3>
      <p>Añadido el 10 de febrero de 2026</p>
    </article>
  </section>
</main>
```

---

### 1.3 `<footer>` - Pie de Página

**¿Qué es?** Contenedor para información de cierre o metadatos.

**¿Dónde se usa?**
- Al final de la página (pie de página principal)
- Al final de un `<article>` o `<section>` (pie de sección)

**Sintaxis:**
```html
<footer>
  <p>&copy; 2026 ComicTracker. Todos los derechos reservados.</p>
</footer>
```

**Contenido típico:**
- Información de copyright
- Enlaces a redes sociales
- Información de contacto
- Enlaces legales (Privacidad, Términos)
- Autor y fecha de publicación (en artículos)

**Ejemplo completo:**
```html
<footer>
  <nav>
    <a href="#privacidad">Privacidad</a>
    <a href="#terminos">Términos</a>
    <a href="#contacto">Contacto</a>
  </nav>
  <p>&copy; 2026 ComicTracker</p>
  <p>Síguenos en <a href="#">Twitter</a> y <a href="#">Instagram</a></p>
</footer>
```

---

### 1.4 `<nav>` - Navegación

**¿Qué es?** Contenedor para bloques de navegación principales.

**¿Cuándo usarlo?**
- ✅ Menú principal del sitio
- ✅ Tabla de contenidos
- ✅ Paginación importante
- ❌ NO para cualquier grupo de enlaces (solo navegación importante)

**Sintaxis:**
```html
<nav>
  <ul>
    <li><a href="#inicio">Inicio</a></li>
    <li><a href="#coleccion">Colección</a></li>
    <li><a href="#estadisticas">Estadísticas</a></li>
  </ul>
</nav>
```

**Buena práctica:** Usa listas (`<ul>`) dentro de `<nav>` para estructurar los enlaces.

**Ejemplo con múltiples navegaciones:**
```html
<!-- Navegación principal -->
<nav aria-label="Navegación principal">
  <ul>
    <li><a href="#inicio">Inicio</a></li>
    <li><a href="#coleccion">Colección</a></li>
  </ul>
</nav>

<!-- Navegación del pie de página -->
<footer>
  <nav aria-label="Navegación legal">
    <a href="#privacidad">Privacidad</a>
    <a href="#terminos">Términos</a>
  </nav>
</footer>
```

**Nota:** `aria-label` ayuda a diferenciar múltiples navegaciones en la misma página.

---

### 1.5 `<section>` - Sección Temática

**¿Qué es?** Agrupación temática de contenido relacionado.

**Regla de oro:** Si tiene un encabezado natural (`<h2>`, `<h3>`, etc.), probablemente debería ser un `<section>`.

**Sintaxis:**
```html
<section>
  <h2>Cómics de Marvel</h2>
  <!-- Contenido relacionado con Marvel -->
</section>
```

**¿Cuándo usarlo?**
- Agrupar contenido por tema
- Dividir una página larga en partes lógicas
- Cada sección debería poder tener su propio encabezado

**Ejemplo:**
```html
<main>
  <section>
    <h2>Cómics de Marvel</h2>
    <p>Explora nuestra colección de superhéroes Marvel</p>
    <!-- Lista de cómics Marvel -->
  </section>
  
  <section>
    <h2>Cómics de DC</h2>
    <p>Descubre los héroes del universo DC</p>
    <!-- Lista de cómics DC -->
  </section>
</main>
```

---

### 1.6 `<article>` - Contenido Independiente

**¿Qué es?** Contenido que tiene sentido por sí solo y podría distribuirse independientemente.

**Pregunta clave:** ¿Este contenido tendría sentido en un feed RSS o si lo compartieras aisladamente?

**Sintaxis:**
```html
<article>
  <h3>The Amazing Spider-Man #1</h3>
  <p>Publicado en marzo de 1963</p>
  <p>Primera aparición de Spider-Man en su propia serie.</p>
</article>
```

**Casos de uso:**
- Publicaciones de blog
- Noticias
- Comentarios de usuarios
- Tarjetas de productos
- Entradas de foro

**Ejemplo completo:**
```html
<article>
  <header>
    <h3>The Amazing Spider-Man #1</h3>
    <p>Publicado el <time datetime="1963-03">Marzo 1963</time></p>
  </header>
  
  <img src="spiderman1.jpg" alt="Portada de Spider-Man #1">
  
  <p>Primera aparición de Spider-Man en su propia serie.</p>
  
  <footer>
    <p>Guionista: Stan Lee | Dibujante: Steve Ditko</p>
  </footer>
</article>
```

---

### 1.7 `<section>` vs `<article>` - ¿Cuál usar?

| Criterio | `<section>` | `<article>` |
|----------|-------------|-------------|
| **Independencia** | Parte de un todo mayor | Contenido autónomo |
| **Reutilización** | Depende del contexto | Puede distribuirse solo |
| **Ejemplo** | Capítulo de un libro | Artículo de revista |
| **En ComicTracker** | "Sección de Marvel" | "Tarjeta de un cómic" |

**Pueden anidarse:**
```html
<section>
  <h2>Últimos Cómics</h2>
  
  <article>
    <h3>Spider-Man #1</h3>
    <p>Descripción...</p>
  </article>
  
  <article>
    <h3>Batman #1</h3>
    <p>Descripción...</p>
  </article>
</section>
```

---

### 1.8 Estructura Completa de Página

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>ComicTracker - Mi Colección</title>
</head>
<body>
  
  <header>
    <h1>ComicTracker</h1>
    <nav>
      <ul>
        <li><a href="#inicio">Inicio</a></li>
        <li><a href="#coleccion">Colección</a></li>
      </ul>
    </nav>
  </header>
  
  <main>
    <section>
      <h2>Mis Cómics Favoritos</h2>
      
      <article>
        <h3>Spider-Man #1</h3>
        <p>Mi cómic favorito de la infancia</p>
      </article>
      
      <article>
        <h3>Batman: Year One</h3>
        <p>Una obra maestra de Frank Miller</p>
      </article>
    </section>
  </main>
  
  <footer>
    <p>&copy; 2026 ComicTracker</p>
  </footer>
  
</body>
</html>
```

---

## 2️⃣ Headings Jerárquicos (`<h1>` a `<h6>`)

Los **headings** (encabezados) crean una jerarquía de contenido, como el índice de un libro.

### 2.1 La Jerarquía

```html
<h1>Título Principal</h1>        <!-- Nivel 1: Solo uno por página -->
  <h2>Subtítulo</h2>              <!-- Nivel 2 -->
    <h3>Sub-subtítulo</h3>        <!-- Nivel 3 -->
      <h4>Sección menor</h4>      <!-- Nivel 4 -->
        <h5>Subsección</h5>       <!-- Nivel 5 -->
          <h6>Detalle mínimo</h6> <!-- Nivel 6 -->
```

### 2.2 Reglas de Oro

**1. Un solo `<h1>` por página**
```html
<!-- ✅ BIEN -->
<h1>ComicTracker - Mi Colección</h1>

<!-- ❌ MAL: Múltiples h1 -->
<h1>ComicTracker</h1>
<h1>Mi Colección</h1>
```

**2. No saltes niveles**
```html
<!-- ✅ BIEN: Secuencia lógica -->
<h1>Título Principal</h1>
<h2>Sección</h2>
<h3>Subsección</h3>

<!-- ❌ MAL: Salto de h2 a h4 -->
<h1>Título Principal</h1>
<h4>Subsección</h4>
```

**3. No uses headings solo por tamaño**
```html
<!-- ❌ MAL: Usar h3 porque "se ve bien" -->
<h3>Este texto debería ser un párrafo</h3>

<!-- ✅ BIEN: Usa CSS para el tamaño -->
<p class="texto-grande">Este es un párrafo con estilo</p>
```

### 2.3 Ejemplo Práctico

```html
<h1>ComicTracker - Guía Completa</h1>

  <h2>Introducción</h2>
  <p>Bienvenido a ComicTracker...</p>
  
  <h2>Cómics por Editorial</h2>
  
    <h3>Marvel Comics</h3>
    <p>Explora el universo Marvel...</p>
    
      <h4>Spider-Man</h4>
      <p>Títulos principales de Spider-Man...</p>
      
      <h4>X-Men</h4>
      <p>Títulos principales de X-Men...</p>
    
    <h3>DC Comics</h3>
    <p>Descubre el universo DC...</p>
    
      <h4>Batman</h4>
      <p>Títulos principales de Batman...</p>
```

### 2.4 Beneficios de la Jerarquía Correcta

- **Accesibilidad:** Lectores de pantalla navegan por headings
- **SEO:** Motores de búsqueda entienden la estructura
- **Navegación:** Los usuarios escanean headings para encontrar información
- **Mantenibilidad:** Código más organizado y fácil de entender

---

## 3️⃣ Listas (`<ul>`, `<ol>`, `<li>`)

Las listas organizan información relacionada. HTML ofrece dos tipos principales.

### 3.1 `<ul>` - Lista No Ordenada (Unordered List)

**¿Cuándo usarla?** Cuando el **orden no importa**.

**Sintaxis:**
```html
<ul>
  <li>Spider-Man</li>
  <li>Batman</li>
  <li>Wonder Woman</li>
</ul>
```

**Renderizado visual:**
- Spider-Man
- Batman
- Wonder Woman

**Casos de uso:**
- Características de un producto
- Menús de navegación
- Listas de ingredientes
- Etiquetas o categorías

**Ejemplo práctico:**
```html
<h3>Géneros de cómics</h3>
<ul>
  <li>Superhéroes</li>
  <li>Ciencia ficción</li>
  <li>Fantasía</li>
  <li>Horror</li>
</ul>
```

---

### 3.2 `<ol>` - Lista Ordenada (Ordered List)

**¿Cuándo usarla?** Cuando el **orden SÍ importa**.

**Sintaxis:**
```html
<ol>
  <li>Comprar el cómic</li>
  <li>Leer el cómic</li>
  <li>Guardarlo en la colección</li>
</ol>
```

**Renderizado visual:**
1. Comprar el cómic
2. Leer el cómic
3. Guardarlo en la colección

**Casos de uso:**
- Instrucciones paso a paso
- Rankings o clasificaciones
- Cronologías
- Recetas

**Ejemplo práctico:**
```html
<h3>Top 5 Cómics de Spider-Man</h3>
<ol>
  <li>The Amazing Spider-Man #33</li>
  <li>Spider-Man: Blue</li>
  <li>Ultimate Spider-Man #1</li>
  <li>The Night Gwen Stacy Died</li>
  <li>Kraven's Last Hunt</li>
</ol>
```

---

### 3.3 Atributos de `<ol>`

**`start` - Comenzar desde un número específico:**
```html
<ol start="5">
  <li>Quinto elemento</li>
  <li>Sexto elemento</li>
</ol>
```

**`type` - Cambiar el estilo de numeración:**
```html
<!-- Números: 1, 2, 3 (por defecto) -->
<ol type="1">
  <li>Primero</li>
</ol>

<!-- Letras mayúsculas: A, B, C -->
<ol type="A">
  <li>Primero</li>
</ol>

<!-- Letras minúsculas: a, b, c -->
<ol type="a">
  <li>Primero</li>
</ol>

<!-- Números romanos mayúsculas: I, II, III -->
<ol type="I">
  <li>Primero</li>
</ol>

<!-- Números romanos minúsculas: i, ii, iii -->
<ol type="i">
  <li>Primero</li>
</ol>
```

**`reversed` - Orden descendente:**
```html
<ol reversed>
  <li>Tercer lugar</li>
  <li>Segundo lugar</li>
  <li>Primer lugar</li>
</ol>
```
Renderiza: 3, 2, 1

---

### 3.4 Listas Anidadas

Puedes anidar listas dentro de elementos `<li>`:

```html
<h3>Universos de Cómics</h3>
<ul>
  <li>Marvel
    <ul>
      <li>Spider-Man</li>
      <li>X-Men</li>
      <li>Avengers</li>
    </ul>
  </li>
  <li>DC
    <ul>
      <li>Batman</li>
      <li>Superman</li>
      <li>Justice League</li>
    </ul>
  </li>
</ul>
```

**Regla importante:** La lista anidada va **dentro** del `<li>`, no directamente dentro del `<ul>`.

```html
<!-- ❌ MAL -->
<ul>
  <li>Marvel</li>
  <ul>
    <li>Spider-Man</li>
  </ul>
</ul>

<!-- ✅ BIEN -->
<ul>
  <li>Marvel
    <ul>
      <li>Spider-Man</li>
    </ul>
  </li>
</ul>
```

---

## 4️⃣ Enlaces y Navegación (`<a>`)

El elemento `<a>` (anchor/ancla) crea **hipervínculos** que conectan páginas y recursos.

### 4.1 Sintaxis Básica

```html
<a href="destino">Texto del enlace</a>
```

**Componentes:**
- `href` (hypertext reference): URL de destino
- Contenido: Texto visible del enlace

### 4.2 Tipos de Enlaces

#### **1. Enlaces Externos (a otros sitios)**
```html
<a href="https://www.marvel.com">Sitio oficial de Marvel</a>
```

#### **2. Enlaces Internos (a otras páginas del mismo sitio)**
```html
<a href="coleccion.html">Mi Colección</a>
<a href="/comics/marvel.html">Cómics Marvel</a>
```

#### **3. Enlaces a Secciones (anclas)**
```html
<!-- Enlace que apunta a un ID -->
<a href="#seccion-marvel">Ir a Marvel</a>

<!-- Elemento con ID -->
<section id="seccion-marvel">
  <h2>Cómics de Marvel</h2>
</section>
```

#### **4. Enlaces de Email**
```html
<a href="mailto:contacto@comictracker.com">Contáctanos</a>
```

#### **5. Enlaces de Teléfono**
```html
<a href="tel:+525512345678">Llámanos</a>
```

---

### 4.3 Atributos Importantes

#### **`target` - Dónde abrir el enlace**

```html
<!-- Abrir en la misma pestaña (por defecto) -->
<a href="coleccion.html">Mi Colección</a>

<!-- Abrir en nueva pestaña -->
<a href="https://www.marvel.com" target="_blank">Marvel</a>
```

**⚠️ Seguridad:** Cuando uses `target="_blank"`, añade `rel="noopener noreferrer"`:

```html
<a href="https://sitio-externo.com" target="_blank" rel="noopener noreferrer">
  Sitio Externo
</a>
```

**¿Por qué?** Previene vulnerabilidades de seguridad y mejora el rendimiento.

#### **`rel` - Relación con el destino**

```html
<!-- Enlace patrocinado -->
<a href="tienda.com" rel="sponsored">Comprar aquí</a>

<!-- Enlace no seguido por motores de búsqueda -->
<a href="registro.html" rel="nofollow">Registrarse</a>

<!-- Enlace a recurso descargable -->
<a href="comic.pdf" download rel="noopener">Descargar PDF</a>
```

#### **`download` - Descargar en lugar de navegar**

```html
<a href="spiderman-wallpaper.jpg" download>Descargar Wallpaper</a>

<!-- Con nombre personalizado -->
<a href="img123.jpg" download="spiderman-wallpaper.jpg">Descargar</a>
```

---

### 4.4 Buenas Prácticas

**1. Texto descriptivo (no "click aquí")**
```html
<!-- ❌ MAL -->
<a href="marvel.html">Click aquí</a> para ver cómics de Marvel

<!-- ✅ BIEN -->
<a href="marvel.html">Ver cómics de Marvel</a>
```

**2. Indicar enlaces externos**
```html
<a href="https://marvel.com" target="_blank" rel="noopener noreferrer">
  Sitio oficial de Marvel (abre en nueva pestaña)
</a>
```

**3. Enlaces accesibles**
```html
<!-- Si el enlace es solo un icono, usa aria-label -->
<a href="perfil.html" aria-label="Ver mi perfil">
  <img src="icono-perfil.png" alt="">
</a>
```

---

## 5️⃣ Imágenes (`<img>`)

El elemento `<img>` inserta imágenes en la página.

### 5.1 Sintaxis Básica

```html
<img src="ruta/imagen.jpg" alt="Descripción de la imagen">
```

**Atributos obligatorios:**
- `src` (source): Ruta de la imagen
- `alt` (alternative text): Descripción textual

### 5.2 El Atributo `alt` - Texto Alternativo

**¿Para qué sirve?**
- Lectores de pantalla lo leen en voz alta
- Se muestra si la imagen no carga
- Ayuda al SEO

**Reglas para escribir `alt`:**

```html
<!-- ✅ BIEN: Descripción concisa y útil -->
<img src="spiderman.jpg" alt="Spider-Man balanceándose entre edificios">

<!-- ❌ MAL: Demasiado genérico -->
<img src="spiderman.jpg" alt="imagen">

<!-- ❌ MAL: Redundante -->
<img src="spiderman.jpg" alt="Imagen de Spider-Man balanceándose">

<!-- ✅ BIEN: Imagen decorativa (alt vacío) -->
<img src="decoracion.png" alt="">
```

**Casos especiales:**

```html
<!-- Imagen decorativa: alt vacío (no omitir el atributo) -->
<img src="linea-decorativa.png" alt="">

<!-- Imagen con texto importante: incluir el texto en alt -->
<img src="logo-comictracker.png" alt="ComicTracker">

<!-- Imagen compleja: descripción breve en alt, detalle en texto cercano -->
<figure>
  <img src="grafico-ventas.png" alt="Gráfico de ventas de cómics 2020-2026">
  <figcaption>
    El gráfico muestra un incremento del 45% en ventas digitales...
  </figcaption>
</figure>
```

---

### 5.3 Atributos de Dimensiones

```html
<!-- Especificar ancho y alto (en píxeles) -->
<img src="portada.jpg" alt="Portada de Spider-Man #1" width="300" height="450">
```

**Beneficios:**
- El navegador reserva espacio antes de cargar la imagen
- Evita saltos de contenido (mejor experiencia de usuario)
- Mejora el rendimiento percibido

**Nota:** Los valores son en píxeles, pero CSS puede redimensionar la imagen después.

---

### 5.4 Imágenes Responsivas

#### **`srcset` - Múltiples resoluciones**

```html
<img 
  src="spiderman-small.jpg" 
  srcset="
    spiderman-small.jpg 400w,
    spiderman-medium.jpg 800w,
    spiderman-large.jpg 1200w
  "
  sizes="(max-width: 600px) 400px, (max-width: 1000px) 800px, 1200px"
  alt="Spider-Man"
>
```

**Explicación:**
- `srcset`: Lista de imágenes con sus anchos (`w` = width)
- `sizes`: Indica qué tamaño usar según el ancho de pantalla
- El navegador elige la imagen más apropiada

#### **`<picture>` - Diferentes formatos o recortes**

```html
<picture>
  <!-- Imagen para móviles -->
  <source media="(max-width: 600px)" srcset="portada-mobile.jpg">
  
  <!-- Imagen para tablets -->
  <source media="(max-width: 1000px)" srcset="portada-tablet.jpg">
  
  <!-- Imagen por defecto (desktop) -->
  <img src="portada-desktop.jpg" alt="Portada de Spider-Man #1">
</picture>
```

---

### 5.5 Formatos de Imagen Recomendados

| Formato | Uso | Ventajas |
|---------|-----|----------|
| **JPEG** | Fotografías, imágenes complejas | Buen balance calidad/tamaño |
| **PNG** | Logos, iconos, transparencias | Soporta transparencia |
| **SVG** | Iconos, logos, gráficos vectoriales | Escalable sin pérdida de calidad |
| **WebP** | Uso general (moderno) | Mejor compresión que JPEG/PNG |
| **AVIF** | Uso general (muy moderno) | Mejor compresión que WebP |

**Ejemplo con formatos modernos:**
```html
<picture>
  <source srcset="portada.avif" type="image/avif">
  <source srcset="portada.webp" type="image/webp">
  <img src="portada.jpg" alt="Portada de Spider-Man #1">
</picture>
```

---

### 5.6 Lazy Loading (Carga Diferida)

```html
<img src="imagen.jpg" alt="Descripción" loading="lazy">
```

**¿Qué hace?** La imagen solo se carga cuando está cerca de entrar en el viewport.

**Beneficios:**
- Carga inicial más rápida
- Ahorro de ancho de banda
- Mejor rendimiento

**Cuándo NO usarlo:**
- Imágenes "above the fold" (visibles sin scroll)
- Imágenes críticas para la experiencia inicial

---

## 6️⃣ Botones vs Enlaces (`<button>` vs `<a>`)

Esta es una de las confusiones más comunes en HTML. **No son intercambiables.**

### 6.1 Regla de Oro

| Elemento | Uso | Pregunta clave |
|----------|-----|----------------|
| **`<a>`** | **Navegación** | ¿Lleva a otra página/sección? |
| **`<button>`** | **Acción** | ¿Ejecuta una acción en la página actual? |

### 6.2 `<a>` - Enlaces (Navegación)

**Úsalo cuando:**
- Navegas a otra página
- Saltas a una sección de la página
- Descargas un archivo
- Abres un email/teléfono

```html
<!-- ✅ BIEN: Navegación -->
<a href="coleccion.html">Ver mi colección</a>
<a href="#top">Volver arriba</a>
<a href="comic.pdf" download>Descargar PDF</a>
```

**Características:**
- Siempre tiene `href`
- Se puede abrir en nueva pestaña (clic derecho)
- Los motores de búsqueda lo siguen
- Funciona sin JavaScript

---

### 6.3 `<button>` - Botones (Acciones)

**Úsalo cuando:**
- Envías un formulario
- Abres/cierras un modal
- Ejecutas JavaScript
- Cambias el estado de la aplicación

```html
<!-- ✅ BIEN: Acciones -->
<button type="submit">Guardar cómic</button>
<button type="button" onclick="abrirModal()">Añadir a favoritos</button>
<button type="button">Mostrar más</button>
```

**Tipos de botones:**

```html
<!-- Envía un formulario (por defecto) -->
<button type="submit">Enviar</button>

<!-- Botón genérico (no envía formulario) -->
<button type="button">Click aquí</button>

<!-- Resetea un formulario -->
<button type="reset">Limpiar</button>
```

**Características:**
- NO navega a otra página
- Puede contener HTML complejo (iconos, texto)
- Requiere JavaScript para la mayoría de acciones
- No tiene `href`

---

### 6.4 Comparación Directa

#### **Escenario 1: Añadir a favoritos**

```html
<!-- ❌ MAL: Enlace para una acción -->
<a href="#" onclick="añadirFavorito()">Añadir a favoritos</a>

<!-- ✅ BIEN: Botón para una acción -->
<button type="button" onclick="añadirFavorito()">Añadir a favoritos</button>
```

#### **Escenario 2: Ver detalles de un cómic**

```html
<!-- ✅ BIEN: Enlace para navegación -->
<a href="comic-detalle.html?id=123">Ver detalles</a>

<!-- ❌ MAL: Botón para navegación -->
<button onclick="location.href='comic-detalle.html?id=123'">Ver detalles</button>
```

#### **Escenario 3: Abrir un modal**

```html
<!-- ❌ MAL: Enlace para abrir modal -->
<a href="#" onclick="abrirModal()">Abrir modal</a>

<!-- ✅ BIEN: Botón para abrir modal -->
<button type="button" onclick="abrirModal()">Abrir modal</button>
```

---

### 6.5 Estilizando Botones como Enlaces (y viceversa)

**Puedes hacer que un botón se vea como un enlace con CSS:**

```html
<button type="button" class="link-style">Parece un enlace</button>
```

```css
.link-style {
  background: none;
  border: none;
  color: blue;
  text-decoration: underline;
  cursor: pointer;
}
```

**Pero la semántica sigue siendo importante:**
- Usa `<button>` para acciones
- Usa `<a>` para navegación
- Estiliza según necesites con CSS

---

### 6.6 Accesibilidad

**Botones:**
- Se activan con `Enter` y `Espacio`
- Lectores de pantalla anuncian: "Botón"
- No se pueden abrir en nueva pestaña

**Enlaces:**
- Se activan solo con `Enter`
- Lectores de pantalla anuncian: "Enlace"
- Se pueden abrir en nueva pestaña (Ctrl+Click)

**Ejemplo accesible:**
```html
<!-- Botón con icono -->
<button type="button" aria-label="Eliminar cómic">
  <svg aria-hidden="true"><!-- Icono de basura --></svg>
</button>

<!-- Enlace con icono -->
<a href="perfil.html" aria-label="Ver perfil">
  <svg aria-hidden="true"><!-- Icono de usuario --></svg>
</a>
```

---

## 📋 Resumen de Decisiones

### ¿Qué elemento usar?

```
¿Lleva a otra página o sección?
├─ SÍ → <a href="...">
└─ NO → ¿Ejecuta una acción?
    ├─ SÍ → <button type="button">
    └─ NO → ¿Es parte de un formulario?
        ├─ SÍ → <button type="submit">
        └─ NO → Probablemente sea <button> o <div>
```

---

## ✅ Checklist de Buenas Prácticas

**Estructura Semántica:**
- [ ] Un solo `<h1>` por página
- [ ] Un solo `<main>` por página
- [ ] Jerarquía de headings sin saltos
- [ ] `<nav>` solo para navegación principal
- [ ] `<article>` para contenido independiente
- [ ] `<section>` para agrupaciones temáticas

**Listas:**
- [ ] `<ul>` cuando el orden no importa
- [ ] `<ol>` cuando el orden importa
- [ ] Listas anidadas dentro de `<li>`

**Enlaces:**
- [ ] Texto descriptivo (no "click aquí")
- [ ] `target="_blank"` con `rel="noopener noreferrer"`
- [ ] `href` siempre presente en `<a>`

**Imágenes:**
- [ ] Atributo `alt` siempre presente
- [ ] `alt` vacío para imágenes decorativas
- [ ] `width` y `height` para reservar espacio
- [ ] `loading="lazy"` para imágenes fuera del viewport inicial

**Botones vs Enlaces:**
- [ ] `<a>` para navegación
- [ ] `<button>` para acciones
- [ ] `type="button"` en botones que no envían formularios

---

## 🎯 Ejercicio Práctico Integrador

Crea una página de "Detalle de Cómic" que incluya:

1. **Estructura semántica completa** (`<header>`, `<main>`, `<footer>`)
2. **Navegación** con `<nav>` y lista de enlaces
3. **Jerarquía de headings** correcta (h1, h2, h3)
4. **Imagen de portada** con `alt` descriptivo y dimensiones
5. **Lista ordenada** de capítulos
6. **Lista no ordenada** de personajes
7. **Enlace** para comprar el cómic
8. **Botón** para añadir a favoritos
9. **Sección de metadatos** usando elementos semánticos

**Requisitos:**
- HTML válido y semántico
- Accesibilidad correcta
- Uso apropiado de cada elemento

---

## 📚 Recursos Adicionales

- **MDN Web Docs:** Documentación oficial de HTML
- **HTML5 Doctor:** Guías sobre elementos semánticos
- **W3C Validator:** Valida tu HTML
- **WebAIM:** Recursos de accesibilidad web

---

**¡Recuerda!** HTML semántico no solo hace que tu código sea más limpio, sino que hace la web más accesible para todos. Cada etiqueta correcta es un paso hacia una web mejor. 🌐✨
