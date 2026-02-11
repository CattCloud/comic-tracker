# 🏗️ FASE 1: HTML PURO - Construcción del Esqueleto
## ComicTracker - Solo HTML Semántico

---

## 🎯 Objetivo de la Fase

Construir la **estructura HTML completa** de ComicTracker cubriendo **todos los temas de HTML** de tu lista de competencias, sin ningún estilo CSS (solo HTML puro y semántico).

**Duración estimada:** 1 semana (8-10 horas a 2h/día)

---

## 📚 Temas HTML a Cubrir

### ✅ Básicos
- Estructura semántica básica (`<header>`, `<main>`, `<footer>`, `<nav>`, `<section>`, `<article>`)
- Headings jerárquicos (`<h1>` a `<h6>`)
- Listas (`<ul>`, `<ol>`, `<li>`)
- Enlaces y navegación (`<a>`)
- Imágenes (`<img>`)
- Botones vs Enlaces (`<button>` vs `<a>`)

### ✅ Intermedios
- Formularios semánticos (`<form>`, `<label>`, `<input>`, `<textarea>`, `<select>`)
- Atributos de formulario (`required`, `pattern`, `minlength`, `maxlength`, `autocomplete`)
- Tipos de input modernos (`type="email"`, `type="tel"`, `type="date"`, `type="number"`, `type="search"`)
- Atributos ARIA básicos (`aria-label`, `aria-labelledby`, `aria-describedby`, `aria-hidden`)
- Meta tags esenciales (`<title>`, `<meta name="description">`, `<meta name="viewport">`)

---

## 📦 Estructura de Módulos HTML

La Fase 1 se divide en **4 módulos progresivos**:

1. **Módulo HTML-1:** Estructura Base y Navegación
2. **Módulo HTML-2:** Contenido Principal y Cards
3. **Módulo HTML-3:** Formularios y Búsqueda
4. **Módulo HTML-4:** Componentes Avanzados y Accesibilidad

---

## 📦 MÓDULO HTML-1: Estructura Base y Navegación
**Duración:** 2-3 horas

### 🎓 Temas a Practicar
- ✅ Estructura semántica básica (`<header>`, `<main>`, `<footer>`, `<nav>`, `<section>`)
- ✅ Headings jerárquicos (`<h1>` a `<h6>`)
- ✅ Listas (`<ul>`, `<ol>`, `<li>`)
- ✅ Enlaces (`<a>`)
- ✅ Meta tags esenciales

---

### 📝 TAREA 1.1: Estructura HTML5 Base

**Archivo a crear:** `index.html`

#### 🎯 Objetivo
Crear el documento HTML5 base con todos los meta tags esenciales y la estructura correcta.

#### 📋 Requisitos Específicos

Tu documento HTML debe incluir:

1. **Declaración DOCTYPE**
   - Debe ser la primera línea del documento
   - Debe indicar que es HTML5

2. **Elemento `<html>`**
   - Debe tener el atributo de idioma configurado a español
   - Debe contener `<head>` y `<body>`

3. **Sección `<head>` con meta tags:**
   - **Codificación de caracteres:** UTF-8
   - **Viewport:** Configurado para dispositivos móviles (width=device-width, initial-scale=1.0)
   - **Description:** Una descripción de 120-160 caracteres sobre qué es ComicTracker
   - **Author:** Tu nombre
   - **Title:** Un título descriptivo para la página (aparecerá en la pestaña del navegador)

4. **Sección `<body>`**
   - Debe estar vacía por ahora (la llenarás en las siguientes tareas)

#### ✅ Criterios de Aceptación

- [ ] El documento comienza con `<!DOCTYPE html>`
- [ ] El elemento `<html>` tiene el atributo `lang` con valor apropiado
- [ ] Hay exactamente 4 meta tags en el `<head>`: charset, viewport, description, author
- [ ] El meta description tiene entre 120-160 caracteres
- [ ] El `<title>` es descriptivo y menciona "ComicTracker"
- [ ] El documento tiene estructura válida: html > head + body

#### 💡 Pistas

- Investiga la sintaxis correcta de HTML5 DOCTYPE (es muy simple, solo 3 palabras)
- El atributo `lang` usa códigos ISO (español = "es")
- Los meta tags usan el formato: `<meta name="..." content="...">`
- El meta viewport es crítico para responsive design

#### 🔍 Validación

Una vez terminado, valida tu HTML en: https://validator.w3.org/

---

### 📝 TAREA 1.2: Header con Logo y Navegación

**Ubicación:** Dentro del `<body>`, como primer elemento

#### 🎯 Objetivo
Crear un header semántico con el logo/título de la aplicación y un menú de navegación principal.

#### 📋 Requisitos Específicos

Tu header debe incluir:

1. **Contenedor semántico de header**
   - Usa el elemento HTML5 apropiado para encabezados de página

2. **Sección de Logo/Branding:**
   - Un heading de nivel 1 (el más importante) con el texto "📚 ComicTracker"
   - Un párrafo descriptivo: "Tu biblioteca personal de cómics"

3. **Navegación principal:**
   - Contenedor semántico para navegación
   - Atributo ARIA que describa que es "Navegación principal"
   - Lista no ordenada con 4 elementos:
     - Inicio (enlace a #inicio)
     - Mi Colección (enlace a #coleccion)
     - Estadísticas (enlace a #estadisticas)
     - Agregar Cómic (enlace a #agregar)

#### ✅ Criterios de Aceptación

- [ ] Se usa el elemento semántico `<header>` (no un `<div>`)
- [ ] Hay exactamente UN `<h1>` en todo el documento (este)
- [ ] El `<h1>` contiene el emoji 📚 y el texto "ComicTracker"
- [ ] Se usa el elemento semántico `<nav>` para la navegación
- [ ] El `<nav>` tiene el atributo `aria-label` con un valor descriptivo
- [ ] La navegación usa una lista `<ul>` (no `<div>` ni `<span>`)
- [ ] Hay exactamente 4 items `<li>` en la lista
- [ ] Cada item contiene un enlace `<a>` con atributo `href` que apunta a un ancla (#id)
- [ ] Los enlaces tienen texto descriptivo visible

#### 💡 Pistas

- `<header>` es diferente de `<head>` - uno es semántico, otro es metadata
- Solo puede haber UN `<h1>` por página (es el título principal)
- `<nav>` indica que el contenido es para navegación
- `aria-label` se escribe como: `aria-label="texto descriptivo"`
- Los enlaces internos usan el formato: `href="#nombre-seccion"`
- Las listas de navegación siempre deben usar `<ul>` por semántica

#### 🔍 Preguntas de Reflexión

- ¿Por qué usar `<nav>` en lugar de un `<div class="navigation">`?
- ¿Por qué la navegación debe ser una lista `<ul>` y no solo enlaces sueltos?
- ¿Qué beneficio tiene `aria-label` para usuarios con lectores de pantalla?

---

### 📝 TAREA 1.3: Sección Hero (Bienvenida)

**Ubicación:** Dentro de un `<main>`, como primera sección

#### 🎯 Objetivo
Crear la sección principal de bienvenida que explica qué es ComicTracker.

#### 📋 Requisitos Específicos

Tu sección hero debe incluir:

1. **Contenedor principal:**
   - Elemento semántico para el contenido principal de la página (solo uno por documento)

2. **Sección de bienvenida:**
   - Elemento semántico para agrupar contenido relacionado
   - Atributo `id` con valor "inicio" (para que funcione el enlace del nav)

3. **Contenido de la sección:**
   - Heading de nivel 2: "Descubre y Organiza tus Cómics Favoritos"
   - Primer párrafo: Descripción de las funcionalidades (gestionar colección, calificar, escribir reseñas, descubrir títulos)
   - Segundo párrafo: Dos enlaces de llamada a la acción:
     - "Explorar Colección" → #coleccion
     - "Agregar Cómic" → #agregar

#### ✅ Criterios de Aceptación

- [ ] Se usa el elemento `<main>` como contenedor principal
- [ ] Solo hay UN `<main>` en todo el documento
- [ ] Dentro del `<main>` hay una `<section>` con `id="inicio"`
- [ ] La sección tiene un `<h2>` como título (jerarquía correcta: h1 > h2)
- [ ] Hay dos párrafos `<p>` con contenido descriptivo
- [ ] El segundo párrafo contiene dos enlaces `<a>`
- [ ] Los enlaces tienen `href` que apuntan a #coleccion y #agregar
- [ ] Los enlaces tienen texto descriptivo (no "click aquí")

#### 💡 Pistas

- `<main>` debe contener el contenido principal único de la página
- `<section>` agrupa contenido relacionado temáticamente
- El atributo `id` debe ser único en todo el documento
- La jerarquía de headings debe ser lógica: h1 (título principal) > h2 (secciones) > h3 (subsecciones)
- Los enlaces dentro de párrafos se escriben inline: `<p>Texto <a href="#">enlace</a> más texto</p>`

#### 🔍 Preguntas de Reflexión

- ¿Por qué usar `<h2>` y no `<h1>` o `<h3>`?
- ¿Qué diferencia hay entre `<section>` y `<div>`?
- ¿Por qué el `id` debe coincidir con el `href` del nav?

---

### 📝 TAREA 1.4: Footer

**Ubicación:** Después del `<main>`, como último elemento del `<body>`

#### 🎯 Objetivo
Crear un footer completo con información de la aplicación, enlaces rápidos y copyright.

#### 📋 Requisitos Específicos

Tu footer debe incluir:

1. **Contenedor semántico de footer**
   - Elemento HTML5 apropiado para pie de página

2. **Cuatro secciones dentro del footer:**

   **Sección 1 - Branding:**
   - Heading de nivel 3: "ComicTracker"
   - Párrafo: "Tu compañero para gestionar tu colección de cómics"

   **Sección 2 - Enlaces Rápidos:**
   - Heading de nivel 4: "Enlaces Rápidos"
   - Lista no ordenada con 3 enlaces:
     - Inicio → #inicio
     - Mi Colección → #coleccion
     - Estadísticas → #estadisticas

   **Sección 3 - Información:**
   - Heading de nivel 4: "Información"
   - Lista no ordenada con 3 enlaces:
     - Sobre el Proyecto → #sobre
     - Contacto → #contacto
     - Privacidad → #privacidad

   **Sección 4 - Copyright:**
   - Párrafo con símbolo de copyright (©), año 2026 y texto: "ComicTracker - Proyecto de aprendizaje HTML, CSS, JavaScript"
   - Párrafo: "Desarrollado por" seguido de tu nombre en énfasis fuerte

#### ✅ Criterios de Aceptación

- [ ] Se usa el elemento `<footer>` (no `<div>`)
- [ ] El `<footer>` está FUERA del `<main>` (hermano, no hijo)
- [ ] Hay un `<h3>` para el branding
- [ ] Hay dos `<h4>` para las subsecciones (jerarquía: h1 > h2 > h3 > h4)
- [ ] Hay dos listas `<ul>` con 3 items cada una
- [ ] Todos los enlaces tienen `href` válidos
- [ ] El símbolo © se usa mediante la entidad HTML correcta (no copiar/pegar el símbolo)
- [ ] Se usa el elemento semántico apropiado para dar énfasis fuerte al nombre

#### 💡 Pistas

- `<footer>` debe estar al mismo nivel que `<main>`, no dentro
- La jerarquía de headings continúa: h1 (header) > h2 (secciones) > h3 (footer) > h4 (subsecciones del footer)
- El símbolo © se escribe con una entidad HTML: `&copy;`
- Para énfasis fuerte (importante) se usa `<strong>`, no `<b>`
- Puedes agrupar cada sección del footer en `<div>` para organización

#### 🔍 Preguntas de Reflexión

- ¿Por qué `<footer>` debe estar fuera de `<main>`?
- ¿Cuál es la diferencia entre `<strong>` y `<b>`?
- ¿Por qué usar entidades HTML como `&copy;` en lugar de copiar el símbolo?

---

### ✅ Checklist de Validación del Módulo HTML-1

Antes de continuar al Módulo 2, verifica:

#### Estructura General
- [ ] El documento tiene DOCTYPE HTML5
- [ ] Hay un solo `<html>` con atributo `lang`
- [ ] El `<head>` contiene los 4 meta tags requeridos
- [ ] El `<title>` es descriptivo

#### Jerarquía de Headings
- [ ] Hay exactamente UN `<h1>` en todo el documento
- [ ] Los headings siguen jerarquía lógica (h1 > h2 > h3 > h4)
- [ ] No hay saltos en la jerarquía (ej: h1 > h3 sin h2)

#### Semántica
- [ ] Se usa `<header>` para el encabezado
- [ ] Se usa `<nav>` para la navegación
- [ ] Se usa `<main>` para el contenido principal
- [ ] Se usa `<footer>` para el pie de página
- [ ] Se usa `<section>` para agrupaciones temáticas

#### Enlaces
- [ ] Todos los `<a>` tienen atributo `href`
- [ ] Los enlaces internos usan formato #id
- [ ] Los textos de enlaces son descriptivos

#### Accesibilidad
- [ ] El `<nav>` tiene `aria-label`
- [ ] Se usa `&copy;` para el símbolo de copyright

#### Validación W3C
- [ ] El HTML pasa la validación en https://validator.w3.org/ sin errores

---

## 📦 MÓDULO HTML-2: Contenido Principal y Cards
**Duración:** 2-3 horas

### 🎓 Temas a Practicar
- ✅ `<article>` - Contenido independiente
- ✅ `<section>` - Agrupación temática
- ✅ Imágenes (`<img>`) con atributos correctos
- ✅ Headings jerárquicos en contexto
- ✅ Botones vs Enlaces

---

### 📝 TAREA 2.1: Sección de Galería de Cómics

**Ubicación:** Dentro del `<main>`, después de la sección hero

#### 🎯 Objetivo
Crear la estructura de la sección que contendrá todas las cards de cómics.

#### 📋 Requisitos Específicos

Tu sección de galería debe incluir:

1. **Contenedor de sección:**
   - Elemento semántico para agrupar contenido relacionado
   - Atributo `id` con valor "coleccion"

2. **Header de la sección:**
   - Elemento semántico para encabezado de sección
   - Heading de nivel 2: "Todos los Cómics"
   - Párrafo: "20 cómics en tu colección"

3. **Contenedor para las cards:**
   - Un `<div>` que contendrá las cards de cómics
   - (Las cards las crearás en la siguiente tarea)

#### ✅ Criterios de Aceptación

- [ ] Se usa `<section>` con `id="coleccion"`
- [ ] Dentro de la section hay un `<header>` (header de sección, no de página)
- [ ] El header contiene un `<h2>` con el título
- [ ] Hay un párrafo `<p>` con el contador
- [ ] Hay un `<div>` vacío que contendrá las cards

#### 💡 Pistas

- Puede haber múltiples `<header>` en un documento (uno por página, otros por sección)
- El `id="coleccion"` debe coincidir con el enlace del nav (#coleccion)
- El `<div>` contenedor puede estar vacío por ahora

---

### 📝 TAREA 2.2: Card de Cómic Individual

**Ubicación:** Dentro del `<div>` contenedor de la sección de galería

#### 🎯 Objetivo
Crear la estructura HTML de UNA card de cómic. Luego duplicarás esta estructura 20 veces con datos diferentes.

#### 📋 Requisitos Específicos para CADA card

Cada card debe incluir:

1. **Contenedor semántico:**
   - Elemento apropiado para contenido independiente y auto-contenido

2. **Imagen de portada:**
   - Elemento de imagen
   - URL de placeholder: `https://via.placeholder.com/200x300/6366f1/ffffff?text=NombreComic`
   - Texto alternativo descriptivo (no solo "portada")
   - Ancho especificado: 200px
   - Alto especificado: 300px

3. **Información del cómic:**
   - Heading de nivel 3 con el título del cómic
   - Párrafo con **Autor:** seguido del nombre (usar énfasis fuerte para "Autor:")
   - Párrafo con **Artista:** seguido del nombre
   - Párrafo con **Editorial:** seguida del nombre
   - Párrafo con **Año:** seguido del año
   - Párrafo con **Géneros:** seguidos de los géneros separados por comas (usar `<span>` para cada género)
   - Párrafo con **Páginas:** seguido del número
   - Párrafo con la sinopsis del cómic

4. **Acciones:**
   - Párrafo contenedor de acciones con:
     - Enlace "Ver Detalles" → #detalle-nombrecomic
     - Botón "Marcar como Leído" (tipo button, no submit)
     - Botón "Agregar a Favoritos" (tipo button)

#### ✅ Criterios de Aceptación (por cada card)

- [ ] Se usa `<article>` como contenedor (contenido independiente)
- [ ] La imagen tiene los 4 atributos requeridos: src, alt, width, height
- [ ] El atributo `alt` es descriptivo (ej: "Portada del cómic Watchmen de Alan Moore")
- [ ] Hay un `<h3>` con el título del cómic
- [ ] Se usa `<strong>` para las etiquetas (Autor:, Artista:, etc.)
- [ ] Los géneros están dentro de `<span>` individuales
- [ ] Hay un enlace `<a>` para "Ver Detalles"
- [ ] Hay dos `<button>` con `type="button"` (no type="submit")
- [ ] Se usa `<a>` para navegación y `<button>` para acciones

#### 📊 Datos para las 20 Cards

Crea 20 cards con estos cómics (varía los colores en las URLs de placeholder):

1. **Watchmen** - Alan Moore, Dave Gibbons, DC Comics, 1986, Superhero/Mystery/Drama, 416 páginas
2. **The Sandman Vol. 1** - Neil Gaiman, Sam Kieth, DC Comics, 1989, Fantasy/Horror/Drama, 232 páginas
3. **Maus** - Art Spiegelman, Art Spiegelman, Pantheon Books, 1991, Biography/History/Drama, 296 páginas
4. **Batman: The Dark Knight Returns** - Frank Miller, Frank Miller, DC Comics, 1986, Superhero/Action/Drama, 224 páginas
5. **Saga Vol. 1** - Brian K. Vaughan, Fiona Staples, Image Comics, 2012, Sci-Fi/Fantasy/Romance, 160 páginas
6. **V for Vendetta** - Alan Moore, David Lloyd, DC Comics, 1988, Dystopian/Thriller/Political, 296 páginas
7. **Y: The Last Man Vol. 1** - Brian K. Vaughan, Pia Guerra, DC Comics, 2002, Sci-Fi/Adventure/Drama, 128 páginas
8. **Persepolis** - Marjane Satrapi, Marjane Satrapi, Pantheon Books, 2000, Biography/History/Drama, 160 páginas
9. **Fables Vol. 1** - Bill Willingham, Lan Medina, DC Comics, 2002, Fantasy/Mystery/Drama, 128 páginas
10. **The Walking Dead Vol. 1** - Robert Kirkman, Tony Moore, Image Comics, 2004, Horror/Drama/Survival, 136 páginas
11. **Scott Pilgrim Vol. 1** - Bryan Lee O'Malley, Bryan Lee O'Malley, Oni Press, 2004, Comedy/Romance/Action, 168 páginas
12. **Bone: The Complete Edition** - Jeff Smith, Jeff Smith, Cartoon Books, 1991, Fantasy/Adventure/Comedy, 1344 páginas
13. **Locke & Key Vol. 1** - Joe Hill, Gabriel Rodríguez, IDW Publishing, 2008, Horror/Fantasy/Mystery, 152 páginas
14. **Invincible Vol. 1** - Robert Kirkman, Cory Walker, Image Comics, 2003, Superhero/Action/Drama, 120 páginas
15. **Preacher Vol. 1** - Garth Ennis, Steve Dillon, DC Comics, 1995, Horror/Western/Drama, 352 páginas
16. **Hellboy Vol. 1** - Mike Mignola, Mike Mignola, Dark Horse Comics, 1994, Horror/Fantasy/Action, 128 páginas
17. **Transmetropolitan Vol. 1** - Warren Ellis, Darick Robertson, DC Comics, 1997, Sci-Fi/Cyberpunk/Political, 144 páginas
18. **Black Hole** - Charles Burns, Charles Burns, Pantheon Books, 2005, Horror/Drama/Coming-of-age, 368 páginas
19. **The Boys Vol. 1** - Garth Ennis, Darick Robertson, Dynamite Entertainment, 2006, Superhero/Action/Dark Comedy, 152 páginas
20. **Daytripper** - Fábio Moon & Gabriel Bá, Fábio Moon & Gabriel Bá, DC Comics, 2010, Drama/Literary/Slice of Life, 256 páginas

#### 💡 Pistas

- `<article>` se usa para contenido que podría existir independientemente
- El atributo `alt` debe describir la imagen para alguien que no puede verla
- `width` y `height` en imágenes previenen layout shift (mejora performance)
- `<span>` es un contenedor inline sin significado semántico
- `type="button"` evita que el botón envíe un formulario
- Usa diferentes colores hex en las URLs de placeholder para variedad visual

#### 🔍 Preguntas de Reflexión

- ¿Por qué usar `<article>` en lugar de `<div>`?
- ¿Cuál es la diferencia entre `<a>` y `<button>`? ¿Cuándo usar cada uno?
- ¿Por qué es importante el atributo `alt` en las imágenes?
- ¿Qué pasa si no especificas `width` y `height` en las imágenes?

---

### ✅ Checklist de Validación del Módulo HTML-2

Antes de continuar al Módulo 3, verifica:

#### Estructura
- [ ] Hay una `<section id="coleccion">` en el `<main>`
- [ ] La sección tiene un `<header>` con `<h2>` y párrafo

#### Cards de Cómics
- [ ] Hay exactamente 20 `<article>` (uno por cómic)
- [ ] Cada `<article>` contiene toda la información requerida
- [ ] Los 20 cómics tienen datos diferentes

#### Imágenes
- [ ] Todas las imágenes tienen los 4 atributos: src, alt, width, height
- [ ] Los atributos `alt` son descriptivos (no genéricos)
- [ ] Las URLs de placeholder tienen colores variados

#### Botones vs Enlaces
- [ ] Se usa `<a>` para "Ver Detalles" (navegación)
- [ ] Se usa `<button type="button">` para las acciones
- [ ] Ningún botón tiene `type="submit"` (aún no hay formularios)

#### Jerarquía
- [ ] Los títulos de las cards son `<h3>` (h1 > h2 > h3)
- [ ] Se usa `<strong>` para énfasis, no `<b>`

---

## 📦 MÓDULO HTML-3: Formularios y Búsqueda
**Duración:** 2-3 horas

### 🎓 Temas a Practicar
- ✅ Formularios semánticos (`<form>`, `<label>`, `<input>`, `<textarea>`, `<select>`)
- ✅ Atributos de formulario (`required`, `pattern`, `minlength`, `maxlength`, `autocomplete`)
- ✅ Tipos de input modernos (`search`, `number`, `url`, `date`)

---

### 📝 TAREA 3.1: Formulario de Búsqueda

**Ubicación:** Dentro del `<main>`, antes de la sección de colección

#### 🎯 Objetivo
Crear un formulario de búsqueda semántico y accesible.

#### 📋 Requisitos Específicos

Tu formulario de búsqueda debe incluir:

1. **Contenedor de sección:**
   - Elemento `<section>` sin id (no necesita navegación directa)
   - Heading de nivel 2: "Buscar Cómics"

2. **Formulario:**
   - Elemento de formulario con role ARIA apropiado para búsqueda
   
3. **Campo de búsqueda:**
   - Label asociado al input: "Buscar por título, autor o género:"
   - Input de tipo especializado para búsqueda (no text)
   - ID único para conectar con el label
   - Atributo `name` con valor "search"
   - Placeholder: "Ej: Watchmen, Alan Moore, Superhero..."
   - Autocompletado desactivado

4. **Botón de envío:**
   - Botón de tipo submit con texto "Buscar"

#### ✅ Criterios de Aceptación

- [ ] Hay una `<section>` con `<h2>` "Buscar Cómics"
- [ ] Se usa `<form>` con `role="search"`
- [ ] Hay un `<label>` con atributo `for` que coincide con el `id` del input
- [ ] El input tiene `type="search"` (no type="text")
- [ ] El input tiene `id`, `name`, `placeholder` y `autocomplete="off"`
- [ ] El label y el input están correctamente asociados
- [ ] Hay un `<button type="submit">`

#### 💡 Pistas

- `role="search"` indica a tecnologías asistivas que es un formulario de búsqueda
- `<label for="id-del-input">` conecta el label con el input
- `type="search"` muestra una X para limpiar en navegadores modernos
- `autocomplete="off"` evita sugerencias del navegador
- El `placeholder` NO reemplaza al `<label>` (el label es obligatorio)

#### 🔍 Preguntas de Reflexión

- ¿Por qué el `<label>` es obligatorio incluso si hay placeholder?
- ¿Qué ventaja tiene `type="search"` sobre `type="text"`?
- ¿Cómo se conecta un label con su input?

---

### 📝 TAREA 3.2: Formulario de Filtros Avanzados

**Ubicación:** Dentro del `<main>`, después del formulario de búsqueda

#### 🎯 Objetivo
Crear un formulario complejo con diferentes tipos de inputs: radio buttons, checkboxes, inputs numéricos y select.

#### 📋 Requisitos Específicos

Tu formulario de filtros debe incluir:

1. **Contenedor de sección:**
   - `<section>` con heading de nivel 2: "Filtrar Colección"

2. **Formulario con 4 grupos de campos:**

   **Grupo 1 - Filtrar por Estado:**
   - Usar elemento para agrupar campos relacionados
   - Título del grupo: "Filtrar por Estado"
   - 5 opciones de radio (solo una seleccionable):
     - Todos (seleccionado por defecto)
     - Leídos
     - Por Leer
     - Favoritos
     - Abandonados
   - Todos los radios deben tener el mismo `name` para agruparse
   - Cada radio debe tener su propio `value`

   **Grupo 2 - Filtrar por Género:**
   - Agrupar campos relacionados
   - Título: "Filtrar por Género"
   - 5 checkboxes (selección múltiple):
     - Superhero
     - Fantasy
     - Horror
     - Sci-Fi
     - Drama
   - Todos los checkboxes deben tener `name="genre"`
   - Cada checkbox debe tener su propio `value`

   **Grupo 3 - Filtrar por Año:**
   - Agrupar campos
   - Título: "Filtrar por Año"
   - Dos inputs numéricos:
     - "Desde:" (mínimo 1900, máximo 2026, placeholder "1980")
     - "Hasta:" (mínimo 1900, máximo 2026, placeholder "2026")
   - Cada input debe tener label asociado

   **Grupo 4 - Ordenar por:**
   - Agrupar campos
   - Título: "Ordenar por"
   - Label: "Criterio:"
   - Lista desplegable con 6 opciones:
     - Título (A-Z)
     - Título (Z-A)
     - Año (Antiguo primero)
     - Año (Nuevo primero)
     - Calificación (Mayor primero)
     - Calificación (Menor primero)

3. **Botones de acción:**
   - Botón de submit: "Aplicar Filtros"
   - Botón de reset: "Limpiar Filtros"

#### ✅ Criterios de Aceptación

- [ ] Se usa `<fieldset>` para agrupar campos relacionados (4 grupos)
- [ ] Cada `<fieldset>` tiene un `<legend>` con el título
- [ ] Los 5 radio buttons tienen el mismo `name` (para agruparse)
- [ ] Un radio tiene el atributo `checked` (seleccionado por defecto)
- [ ] Los 5 checkboxes tienen `name="genre"` y diferentes `value`
- [ ] Los inputs numéricos tienen `type="number"`, `min`, `max` y `placeholder`
- [ ] Cada input tiene un `<label>` asociado correctamente
- [ ] Se usa `<select>` con múltiples `<option>` para la lista desplegable
- [ ] Hay un `<button type="submit">` y un `<button type="reset">`

#### 💡 Pistas

- `<fieldset>` agrupa campos relacionados visualmente y semánticamente
- `<legend>` es el título del fieldset (primer hijo)
- Radio buttons con el mismo `name` se excluyen mutuamente
- `checked` en un radio lo marca por defecto
- Checkboxes permiten selección múltiple
- `type="number"` muestra teclado numérico en móviles
- `min` y `max` validan el rango de números
- `<select>` crea una lista desplegable
- `<option value="...">Texto visible</option>` son las opciones
- `type="reset"` limpia el formulario a sus valores iniciales

#### 🔍 Preguntas de Reflexión

- ¿Cuál es la diferencia entre radio buttons y checkboxes?
- ¿Por qué los radios necesitan el mismo `name`?
- ¿Qué ventaja tiene `type="number"` sobre `type="text"` para números?
- ¿Para qué sirve el atributo `value` en inputs?

---

### 📝 TAREA 3.3: Formulario de Agregar Cómic

**Ubicación:** Dentro del `<main>`, crear nueva `<section id="agregar">`

#### 🎯 Objetivo
Crear un formulario completo para agregar un nuevo cómic con validación HTML5.

#### 📋 Requisitos Específicos

Tu formulario debe incluir:

1. **Contenedor de sección:**
   - `<section id="agregar">` (para el enlace del nav)
   - Heading de nivel 2: "Agregar Nuevo Cómic"

2. **Formulario con 3 grupos de campos:**

   **Grupo 1 - Información Básica:**
   - Título del grupo: "Información Básica"
   - 7 campos:
     1. **Título:** Input text, obligatorio, mínimo 1 carácter, máximo 200, sin autocompletar
     2. **Autor:** Input text, obligatorio, sin autocompletar
     3. **Artista:** Input text, opcional, sin autocompletar
     4. **Editorial:** Input text, opcional, sin autocompletar
     5. **Año de Publicación:** Input numérico, opcional, rango 1900-2026
     6. **Número de Páginas:** Input numérico, opcional, mínimo 1
     7. **URL de la Portada:** Input especializado para URLs, opcional, placeholder con ejemplo

   **Grupo 2 - Sinopsis:**
   - Título: "Sinopsis"
   - Label: "Descripción del cómic:"
   - Área de texto multilínea con:
     - 5 filas de altura
     - Máximo 500 caracteres
     - Placeholder descriptivo
   - Texto de ayuda debajo: "Máximo 500 caracteres" (usar elemento para texto pequeño)

   **Grupo 3 - Mi Reseña Personal:**
   - Título: "Mi Reseña Personal"
   - 4 campos:
     1. **Calificación:** Lista desplegable con opciones:
        - Sin calificar (value vacío)
        - ⭐ 1 - Muy malo
        - ⭐⭐ 2 - Malo
        - ⭐⭐⭐ 3 - Regular
        - ⭐⭐⭐⭐ 4 - Bueno
        - ⭐⭐⭐⭐⭐ 5 - Excelente
     2. **Mi Reseña:** Área de texto, 8 filas, sin límite de caracteres
     3. **Estado de Lectura:** Lista desplegable con:
        - Por Leer
        - Leyendo
        - Leído
        - Abandonado
     4. **Fecha de Lectura:** Input especializado para fechas

3. **Botones:**
   - Submit: "Guardar Cómic"
   - Reset: "Limpiar Formulario"

#### ✅ Criterios de Aceptación

- [ ] Hay 3 `<fieldset>` con sus respectivos `<legend>`
- [ ] Todos los inputs tienen `<label>` asociados correctamente
- [ ] Los campos obligatorios tienen el atributo `required`
- [ ] Los inputs de texto tienen `minlength` y/o `maxlength` donde se especifica
- [ ] Se usa `type="url"` para la URL de portada
- [ ] Se usa `type="number"` para año y páginas, con `min` y `max` apropiados
- [ ] Se usa `<textarea>` para textos largos (sinopsis y reseña)
- [ ] Los textareas tienen el atributo `rows` especificado
- [ ] Se usa `type="date"` para la fecha de lectura
- [ ] Se usa `<small>` para el texto de ayuda
- [ ] Hay dos `<select>` con sus respectivas `<option>`
- [ ] Hay botones de submit y reset

#### 💡 Pistas

- `required` hace que el campo sea obligatorio (validación HTML5)
- `minlength` y `maxlength` validan la longitud del texto
- `type="url"` valida que sea una URL válida
- `<textarea>` es para texto multilínea (no `<input type="text">`)
- `rows` define la altura del textarea
- `type="date"` muestra un selector de fecha en navegadores modernos
- `<small>` es semántico para texto de ayuda o aclaraciones
- Una `<option>` puede tener `value=""` (vacío) para "sin selección"

#### 🔍 Preguntas de Reflexión

- ¿Cuándo usar `<input>` y cuándo `<textarea>`?
- ¿Qué diferencia hay entre validación HTML5 y validación con JavaScript?
- ¿Por qué usar tipos especializados (url, date, number) en lugar de text?

---

### ✅ Checklist de Validación del Módulo HTML-3

Antes de continuar al Módulo 4, verifica:

#### Formulario de Búsqueda
- [ ] Tiene `role="search"`
- [ ] El label está asociado al input
- [ ] Se usa `type="search"`

#### Formulario de Filtros
- [ ] Hay 4 `<fieldset>` con `<legend>`
- [ ] Los radios tienen el mismo `name` y uno tiene `checked`
- [ ] Los checkboxes permiten selección múltiple
- [ ] Los inputs numéricos tienen `min` y `max`
- [ ] Hay un `<select>` con 6 opciones

#### Formulario de Agregar
- [ ] Hay 3 `<fieldset>` organizados lógicamente
- [ ] Los campos obligatorios tienen `required`
- [ ] Se usan tipos especializados: url, number, date
- [ ] Los textareas tienen `rows` y `maxlength`
- [ ] Todos los inputs tienen labels asociados

#### General
- [ ] Todos los formularios tienen botones de submit
- [ ] Los labels usan `for` e `id` para asociarse
- [ ] No hay inputs sin label

---

## 📦 MÓDULO HTML-4: Componentes Avanzados y Accesibilidad
**Duración:** 2-3 horas

### 🎓 Temas a Practicar
- ✅ Atributos ARIA (`aria-label`, `aria-labelledby`, `aria-describedby`, `aria-hidden`)
- ✅ Roles ARIA (`role="dialog"`, `role="tablist"`, `role="tab"`, `role="tabpanel"`)
- ✅ Listas de definición (`<dl>`, `<dt>`, `<dd>`)

---

### 📝 TAREA 4.1: Modal de Detalles

**Ubicación:** Al final del `<body>`, después del `<footer>`

#### 🎯 Objetivo
Crear un modal accesible con ARIA para mostrar detalles completos de un cómic.

#### 📋 Requisitos Específicos

Tu modal debe incluir:

1. **Contenedor principal del modal:**
   - `<div>` con id único: "modal-detalle"
   - Role ARIA para diálogos
   - Atributo ARIA que lo conecte con su título (usando id del h2)
   - Atributo ARIA que lo conecte con su descripción (usando id del contenido)
   - Atributo ARIA para ocultarlo de screen readers: "true"

2. **Documento interno:**
   - `<div>` con role="document" (contenido del modal)

3. **Header del modal:**
   - Elemento `<header>`
   - Heading de nivel 2 con id "modal-title": "Watchmen"
   - Botón de cerrar:
     - Tipo button
     - Símbolo: ✕
     - Atributo ARIA label: "Cerrar modal"

4. **Contenido del modal:**
   - `<div>` con id "modal-description"
   - Imagen de portada (300x450px)
   - Sección de información con:
     - Heading de nivel 3: "Información del Cómic"
     - Lista de definiciones con pares clave-valor:
       - Autor: Alan Moore
       - Artista: Dave Gibbons
       - Editorial: DC Comics
       - Año: 1986
       - Páginas: 416
       - Géneros: Superhero, Mystery, Drama
   - Sección de sinopsis:
     - Heading de nivel 3: "Sinopsis"
     - Párrafo con la sinopsis
   - Sección de reseña:
     - Heading de nivel 3: "Mi Reseña"
     - Párrafo con calificación: "⭐⭐⭐⭐⭐ 5/5"
     - Párrafo con texto de reseña
   - Sección de estado:
     - Heading de nivel 3: "Estado de Lectura"
     - Párrafo con estado: "Leído"
     - Párrafo con fecha: "15 de enero de 2026"

5. **Footer del modal:**
   - Elemento `<footer>`
   - 3 botones (tipo button):
     - Editar
     - Eliminar
     - Cerrar

#### ✅ Criterios de Aceptación

- [ ] El contenedor principal tiene `role="dialog"`
- [ ] Tiene `aria-labelledby` apuntando al id del `<h2>`
- [ ] Tiene `aria-describedby` apuntando al id del contenido
- [ ] Tiene `aria-hidden="true"` (se mostrará con JS después)
- [ ] Hay un `<div role="document">` dentro
- [ ] El botón de cerrar tiene `aria-label="Cerrar modal"`
- [ ] Se usa `<dl>`, `<dt>`, `<dd>` para la información estructurada
- [ ] Hay 4 secciones con `<h3>` cada una
- [ ] Todos los botones son `type="button"`

#### 💡 Pistas

- `role="dialog"` indica que es un modal/diálogo
- `aria-labelledby` conecta el modal con su título
- `aria-describedby` conecta el modal con su contenido
- `aria-hidden="true"` oculta el elemento de screen readers
- `aria-label` proporciona etiqueta a elementos sin texto visible
- `<dl>` (definition list), `<dt>` (term), `<dd>` (definition) son perfectos para pares clave-valor
- El modal estará oculto por defecto (se mostrará con CSS/JS después)

#### 🔍 Preguntas de Reflexión

- ¿Por qué usar `aria-labelledby` en lugar de `aria-label`?
- ¿Cuándo usar `<dl>/<dt>/<dd>` en lugar de párrafos o tablas?
- ¿Por qué el botón de cerrar necesita `aria-label`?

---

### 📝 TAREA 4.2: Sistema de Pestañas (Tabs)

**Ubicación:** Reemplazar la sección de colección existente

#### 🎯 Objetivo
Convertir la sección de galería en un sistema de pestañas accesible con ARIA.

#### 📋 Requisitos Específicos

Tu sistema de tabs debe incluir:

1. **Contenedor de sección:**
   - `<section>` (puede mantener o no el id="coleccion")
   - Heading de nivel 2: "Mi Colección"

2. **Lista de pestañas:**
   - `<div>` con role para lista de pestañas
   - Atributo ARIA label: "Filtros de colección"
   - 5 botones, cada uno con:
     - Role para pestaña
     - Atributo ARIA para indicar si está seleccionada (true/false)
     - Atributo ARIA que conecte con su panel (aria-controls)
     - ID único
     - Texto:
       - "Todos (20)" - seleccionada por defecto
       - "Leídos (8)"
       - "Por Leer (10)"
       - "Favoritos (5)"
       - "Abandonados (2)"

3. **Paneles de contenido:**
   - 5 `<div>`, cada uno con:
     - ID único (debe coincidir con aria-controls del botón)
     - Role para panel de pestaña
     - Atributo ARIA que lo conecte con su pestaña (aria-labelledby)
     - Atributo `hidden` en los paneles inactivos (todos excepto "Todos")
     - Contenido: Párrafo descriptivo de qué muestra ese panel

#### ✅ Criterios de Aceptación

- [ ] El contenedor de pestañas tiene `role="tablist"`
- [ ] El contenedor tiene `aria-label` descriptivo
- [ ] Hay 5 botones con `role="tab"`
- [ ] Solo un botón tiene `aria-selected="true"` (los demás "false")
- [ ] Cada botón tiene `aria-controls` apuntando al id de su panel
- [ ] Cada botón tiene un `id` único
- [ ] Hay 5 paneles con `role="tabpanel"`
- [ ] Cada panel tiene `aria-labelledby` apuntando al id de su pestaña
- [ ] Los paneles inactivos tienen el atributo `hidden`
- [ ] Los IDs de `aria-controls` coinciden con los IDs de los paneles

#### 💡 Pistas

- `role="tablist"` indica que es un contenedor de pestañas
- `role="tab"` indica que es una pestaña
- `role="tabpanel"` indica que es el contenido de una pestaña
- `aria-selected` indica qué pestaña está activa
- `aria-controls` conecta la pestaña con su panel
- `aria-labelledby` conecta el panel con su pestaña
- `hidden` es un atributo HTML5 que oculta elementos
- Los valores de `aria-controls` y `aria-labelledby` deben ser IDs válidos

#### 🔍 Preguntas de Reflexión

- ¿Por qué usar roles ARIA en lugar de solo CSS para ocultar/mostrar?
- ¿Cómo saben los screen readers qué panel corresponde a qué pestaña?
- ¿Qué diferencia hay entre `hidden` y `display: none` en CSS?

---

### 📝 TAREA 4.3: Sección de Estadísticas

**Ubicación:** Dentro del `<main>`, crear nueva `<section id="estadisticas">`

#### 🎯 Objetivo
Crear una sección de estadísticas accesible con información numérica.

#### 📋 Requisitos Específicos

Tu sección de estadísticas debe incluir:

1. **Contenedor de sección:**
   - `<section id="estadisticas">`
   - Heading de nivel 2: "Mis Estadísticas de Lectura"

2. **Grid de estadísticas principales:**
   - Contenedor `<div>`
   - 4 artículos, cada uno con:
     - Elemento `<article>`
     - Heading de nivel 3 con el nombre de la estadística
     - Párrafo con el número
     - Atributo ARIA label en el párrafo con contexto completo
   - Estadísticas:
     - Total de Cómics: 20
     - Cómics Leídos: 8
     - Por Leer: 10
     - Favoritos: 5

3. **Sección de géneros más leídos:**
   - Contenedor `<div>`
   - Heading de nivel 3: "Géneros Más Leídos"
   - Lista ordenada (ranking) con 5 géneros:
     1. Superhero (6 cómics)
     2. Drama (5 cómics)
     3. Fantasy (4 cómics)
     4. Horror (3 cómics)
     5. Sci-Fi (2 cómics)

4. **Promedio de calificación:**
   - Contenedor `<div>`
   - Heading de nivel 3: "Promedio de Calificación"
   - Párrafo con:
     - `<span>` con aria-label descriptivo
     - Contenido: "⭐⭐⭐⭐ 4.2/5"

5. **Cómics leídos este año:**
   - Contenedor `<div>`
   - Heading de nivel 3: "Cómics Leídos Este Año"
   - Párrafo con número: 5
   - Atributo ARIA label: "5 cómics leídos en 2026"

#### ✅ Criterios de Aceptación

- [ ] Hay una `<section id="estadisticas">`
- [ ] Hay 4 `<article>` para las estadísticas principales
- [ ] Cada estadística tiene un `<h3>` y un `<p>`
- [ ] Los párrafos con números tienen `aria-label` con contexto
- [ ] Se usa `<ol>` para el ranking de géneros (lista ordenada)
- [ ] La lista tiene exactamente 5 items
- [ ] El promedio usa `<span>` con `aria-label` descriptivo
- [ ] Todos los headings son `<h3>` (jerarquía: h1 > h2 > h3)

#### 💡 Pistas

- `<ol>` es una lista ordenada (con números)
- `aria-label` en números proporciona contexto para screen readers
- Un número solo ("20") no tiene contexto, pero "20 cómics en total" sí
- `<article>` es apropiado para cada estadística (contenido independiente)

#### 🔍 Preguntas de Reflexión

- ¿Por qué usar `<ol>` en lugar de `<ul>` para el ranking?
- ¿Por qué agregar `aria-label` a números que ya son visibles?
- ¿Cuándo usar `<article>` vs `<div>`?

---

### ✅ Checklist Final de la Fase 1 (HTML Completo)

#### Estructura General
- [ ] Documento HTML5 válido con DOCTYPE
- [ ] Meta tags esenciales (charset, viewport, description, author, title)
- [ ] Solo un `<h1>` en todo el documento
- [ ] Jerarquía de headings correcta sin saltos (h1 > h2 > h3 > h4)
- [ ] Solo un `<main>` por página

#### Semántica
- [ ] `<header>` para encabezado de página
- [ ] `<nav>` para navegación con `aria-label`
- [ ] `<main>` para contenido principal
- [ ] `<footer>` para pie de página
- [ ] `<section>` para agrupaciones temáticas
- [ ] `<article>` para contenido independiente (cards, estadísticas)

#### Contenido
- [ ] 20 cards de cómics con datos completos y diferentes
- [ ] Formulario de búsqueda con `role="search"`
- [ ] Formulario de filtros con fieldsets, radios, checkboxes, select
- [ ] Formulario de agregar cómic con validación HTML5
- [ ] Modal con ARIA completo
- [ ] Sistema de tabs con roles ARIA
- [ ] Sección de estadísticas

#### Imágenes
- [ ] Todas tienen `src`, `alt`, `width`, `height`
- [ ] Los `alt` son descriptivos (no genéricos)

#### Formularios
- [ ] Todos los inputs tienen `<label>` asociados
- [ ] Se usan tipos especializados (search, number, url, date)
- [ ] Los campos obligatorios tienen `required`
- [ ] Hay validación con minlength, maxlength, min, max
- [ ] Los botones tienen `type` correcto (submit, reset, button)

#### Accesibilidad ARIA
- [ ] Modal tiene role="dialog", aria-labelledby, aria-describedby, aria-hidden
- [ ] Tabs tienen role="tablist", role="tab", role="tabpanel"
- [ ] Se usa aria-selected en tabs
- [ ] Se usa aria-controls y aria-labelledby para conectar tabs y panels
- [ ] Botones sin texto tienen aria-label
- [ ] Números tienen aria-label con contexto

#### Validación Final
- [ ] El HTML pasa validación W3C sin errores: https://validator.w3.org/
- [ ] No hay errores de consola al abrir en navegador
- [ ] La página es navegable con teclado (Tab, Enter)
- [ ] Los enlaces internos (#id) funcionan correctamente

---

## 🎯 Resultado Esperado

Al finalizar la Fase 1 tendrás:

1. **Un documento HTML completo y funcional** con:
   - Estructura semántica correcta
   - 20 cómics con información completa
   - 3 formularios funcionales
   - Modal y sistema de tabs con ARIA
   - Sección de estadísticas

2. **Todos los 11 temas HTML cubiertos:**
   - ✅ Estructura semántica básica
   - ✅ Headings jerárquicos
   - ✅ Listas (ul, ol, dl)
   - ✅ Enlaces
   - ✅ Imágenes
   - ✅ Botones vs Enlaces
   - ✅ Formularios semánticos
   - ✅ Atributos de formulario
   - ✅ Tipos de input modernos
   - ✅ Atributos ARIA
   - ✅ Meta tags

3. **HTML válido, semántico y accesible:**
   - Pasa validación W3C
   - Usa elementos semánticos apropiados
   - Implementa ARIA correctamente
   - Es navegable por teclado

---

## 📝 Notas Importantes

- **NO agregues CSS todavía** - La página se verá sin estilos, eso es normal
- **NO agregues JavaScript todavía** - Los formularios no funcionarán, está bien
- **Enfócate en la semántica** - Usa los elementos correctos para cada propósito
- **Valida frecuentemente** - Usa W3C validator después de cada módulo
- **Comparte tu código para revisión** - Una vez terminado cada módulo, compártelo para feedback

---

## 🚀 Próximos Pasos

1. ✅ Completa los 4 módulos de HTML
2. ✅ Valida tu HTML en https://validator.w3.org/
3. ✅ Comparte tu código para revisión
4. ⏭️ **Continúa con la Fase 2: CSS Puro** (estilizar todo el HTML que creaste)
