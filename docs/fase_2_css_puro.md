# 🎨 FASE 2: CSS PURO - Estilizando la Aplicación
## ComicTracker - Solo CSS (Sin Frameworks)

---

## 🎯 Objetivo de la Fase

Aplicar **estilos CSS completos** a tu HTML de ComicTracker, cubriendo **todos los temas CSS** de tu lista de competencias, sin usar frameworks (solo CSS vanilla).

**Duración estimada:** 1.5-2 semanas (12-16 horas a 2h/día)

---

## 📚 Temas CSS a Cubrir

### ✅ Básicos
- Box Model (margin, padding, border, width, height)
- Selectores (clase, ID, descendiente, hijo directo, pseudo-clases)
- Colores y tipografía (color, font-family, font-size, font-weight, line-height)
- Display (block, inline, inline-block, none)
- Position (static, relative, absolute, fixed, sticky)

### ✅ Intermedios
- Flexbox (justify-content, align-items, flex-direction, gap)
- Grid (grid-template-columns, grid-gap, grid-areas)
- Responsive Design (media queries, mobile-first)
- Transiciones y animaciones (transition, animation, @keyframes)
- Variables CSS (custom properties)
- Pseudo-elementos (::before, ::after)
- Transform (translate, scale, rotate)

### ✅ Avanzados
- Dark mode (prefers-color-scheme)
- Accesibilidad CSS (focus-visible, reduced-motion)
- Performance (will-change, contain)

---

## 📦 Estructura de Módulos CSS

La Fase 2 se divide en **5 módulos progresivos**:

1. **Módulo CSS-1:** Sistema de Diseño y Variables
2. **Módulo CSS-2:** Layout y Estructura Base
3. **Módulo CSS-3:** Componentes y Cards
4. **Módulo CSS-4:** Responsive Design y Mobile
5. **Módulo CSS-5:** Interactividad y Dark Mode

---

## 📦 MÓDULO CSS-1: Sistema de Diseño y Variables
**Duración:** 2-3 horas

### 🎓 Temas a Practicar
- ✅ Variables CSS (custom properties)
- ✅ Colores y tipografía
- ✅ Reset/Normalize CSS

---

### 📝 TAREA 1.1: Reset CSS y Box-Sizing

**Archivo a crear:** `styles.css`

#### 🎯 Objetivo
Crear un reset CSS básico para normalizar estilos entre navegadores.

#### 📋 Requisitos Específicos

Tu reset debe incluir:

1. **Reset universal:**
   - Aplicar `box-sizing: border-box` a TODOS los elementos
   - Usar el selector universal y pseudo-elementos

2. **Reset de márgenes y padding:**
   - Eliminar márgenes y padding por defecto del body
   - Configurar altura mínima del body al 100% del viewport

3. **Reset de listas:**
   - Eliminar estilos de lista por defecto (bullets, números)
   - Eliminar padding de listas

4. **Reset de imágenes:**
   - Hacer que las imágenes sean responsive por defecto
   - Mantener aspect ratio

5. **Reset de botones y formularios:**
   - Heredar tipografía del padre
   - Eliminar estilos por defecto del navegador

#### ✅ Criterios de Aceptación

- [ ] Se usa el selector `*, *::before, *::after` para box-sizing
- [ ] El body tiene margin: 0 y min-height: 100vh
- [ ] Las listas (ul, ol) no tienen list-style ni padding
- [ ] Las imágenes tienen max-width: 100% y height: auto
- [ ] Los botones e inputs heredan font

#### 💡 Pistas

- `box-sizing: border-box` hace que padding y border se incluyan en el width/height
- `min-height: 100vh` asegura que el body ocupe al menos toda la altura de la pantalla
- `max-width: 100%` previene que las imágenes se desborden de su contenedor
- `inherit` hace que un elemento herede el valor de su padre

---

### 📝 TAREA 1.2: Variables CSS (Design Tokens)

**Ubicación:** En `:root` al inicio de `styles.css`

#### 🎯 Objetivo
Definir un sistema de diseño completo usando variables CSS para colores, tipografía, espaciado y otros valores reutilizables.

#### 📋 Requisitos Específicos

Define variables CSS para:

1. **Paleta de Colores (mínimo 8 variables):**
   - Color primario (para acciones principales)
   - Color secundario
   - Color de fondo principal
   - Color de fondo secundario (cards, secciones)
   - Color de texto principal
   - Color de texto secundario (menos énfasis)
   - Color de éxito (verde)
   - Color de error/peligro (rojo)

2. **Tipografía (mínimo 5 variables):**
   - Familia de fuente principal
   - Familia de fuente para headings (puede ser la misma)
   - Tamaño base (16px o 1rem)
   - Tamaños para h1, h2, h3
   - Line-height base

3. **Espaciado (mínimo 6 variables):**
   - Espaciado extra pequeño (4px)
   - Pequeño (8px)
   - Mediano (16px)
   - Grande (24px)
   - Extra grande (32px)
   - Sección (48px o más)

4. **Otros valores:**
   - Border radius (para esquinas redondeadas)
   - Sombras (box-shadow)
   - Ancho máximo del contenedor
   - Duración de transiciones

#### ✅ Criterios de Aceptación

- [ ] Las variables se definen en el selector `:root`
- [ ] Los nombres de variables usan formato kebab-case con `--` al inicio
- [ ] Hay al menos 8 variables de color
- [ ] Hay al menos 5 variables de tipografía
- [ ] Hay al menos 6 variables de espaciado
- [ ] Los valores son coherentes y forman un sistema

#### 💡 Pistas

- `:root` es equivalente a [html](file:///d:/CURSOS%20EN%20PROGRESO/PROMPT_CURSO/index.html) pero con mayor especificidad
- Las variables CSS se definen como: `--nombre-variable: valor;`
- Se usan como: `color: var(--nombre-variable);`
- Usa HSL para colores (más fácil de ajustar): `hsl(220, 90%, 56%)`
- Crea una escala de espaciado consistente (múltiplos de 4 u 8)

#### 🔍 Preguntas de Reflexión

- ¿Por qué usar variables CSS en lugar de valores directos?
- ¿Qué ventaja tiene HSL sobre RGB o HEX?
- ¿Cómo facilitan las variables el cambio de tema (dark mode)?

---

### 📝 TAREA 1.3: Tipografía Base

**Ubicación:** Después de las variables en `styles.css`

#### 🎯 Objetivo
Configurar la tipografía base del documento usando las variables definidas.

#### 📋 Requisitos Específicos

Configura estilos para:

1. **Body:**
   - Familia de fuente usando variable
   - Tamaño de fuente base usando variable
   - Line-height para legibilidad (1.5-1.7)
   - Color de texto usando variable
   - Color de fondo usando variable

2. **Headings (h1-h6):**
   - Familia de fuente (puede ser diferente al body)
   - Font-weight más grueso (600-700)
   - Line-height más ajustado (1.2-1.3)
   - Margin-bottom consistente
   - Tamaños específicos usando variables

3. **Enlaces:**
   - Color usando variable primaria
   - Sin subrayado por defecto
   - Subrayado al hover
   - Transición suave
   - Cursor pointer

4. **Párrafos:**
   - Margin-bottom para separación

#### ✅ Criterios de Aceptación

- [ ] El body usa variables para font-family, font-size, color, background
- [ ] Los headings tienen font-weight y line-height apropiados
- [ ] Los tamaños de h1-h3 usan variables definidas
- [ ] Los enlaces tienen estado hover con transición
- [ ] Se usa `text-decoration` para el subrayado
- [ ] Los párrafos tienen margin-bottom

#### 💡 Pistas

- `line-height` sin unidad es relativo al font-size (1.5 = 150%)
- Los headings suelen tener `line-height` menor que el body
- `text-decoration: none` quita el subrayado
- `transition: all 0.3s ease` hace transiciones suaves
- Usa variables con `var(--nombre-variable)`

#### 🔍 Preguntas de Reflexión

- ¿Por qué los headings tienen line-height menor que el body?
- ¿Cuál es la diferencia entre `text-decoration: none` y `text-decoration: underline`?
- ¿Por qué agregar transición a los enlaces mejora la UX?

---

### ✅ Checklist de Validación del Módulo CSS-1

Antes de continuar al Módulo 2, verifica:

#### Reset CSS
- [ ] Hay un reset universal con `*, *::before, *::after`
- [ ] El body tiene margin: 0 y min-height: 100vh
- [ ] Las listas no tienen list-style
- [ ] Las imágenes tienen max-width: 100%
- [ ] Los botones heredan font

#### Variables CSS
- [ ] Se definieron al menos 20 variables CSS en `:root`
- [ ] Hay 8+ variables de color
- [ ] Hay 5+ variables de tipografía
- [ ] Hay 6+ variables de espaciado
- [ ] Los nombres usan kebab-case con `--`

#### Tipografía
- [ ] El body tiene tipografía base configurada
- [ ] Los headings tienen estilos consistentes
- [ ] Los enlaces tienen hover con transición
- [ ] Se usan variables en todos los estilos

---

## 📦 MÓDULO CSS-2: Layout y Estructura Base
**Duración:** 3-4 horas

### 🎓 Temas a Practicar
- ✅ Flexbox (justify-content, align-items, flex-direction, gap)
- ✅ Box Model (margin, padding, border)
- ✅ Position (sticky, relative, absolute)
- ✅ Display (flex, grid, block)
- ✅ Grid (grid-template-columns, gap)

---

### 📝 TAREA 2.1: Header y Navegación con Flexbox

**Ubicación:** En `styles.css`, crear estilos para `<header>` y `<nav>`

#### 🎯 Objetivo
Estilizar el header con logo y navegación usando Flexbox, haciéndolo sticky.

#### 📋 Requisitos Específicos

El header debe tener:

1. **Contenedor header:**
   - Fondo con color de variable
   - Padding vertical y horizontal usando variables
   - Sombra sutil (box-shadow) usando variable
   - Position sticky (se queda fijo al hacer scroll)
   - Top: 0
   - Z-index alto (ej: 1000) para estar sobre otros elementos

2. **Layout interno (Flexbox):**
   - Display flex
   - Distribuir logo y nav horizontalmente (justify-content)
   - Alinear verticalmente al centro (align-items)
   - Espacio entre logo y nav (space-between)
   - Padding horizontal usando variable

3. **Logo/Branding (h1 y párrafo):**
   - Margin: 0 (quitar márgenes por defecto)
   - Tamaño de fuente apropiado
   - Font-weight bold para el h1

4. **Navegación (nav):**
   - Lista (ul) horizontal usando Flexbox
   - Gap entre items usando variable
   - Margin: 0, padding: 0

5. **Enlaces de navegación:**
   - Padding usando variables
   - Color usando variable
   - Border-radius usando variable
   - Hover con cambio de color de fondo
   - Transición suave
   - Display block para que el padding funcione bien

#### ✅ Criterios de Aceptación

- [ ] El header usa `position: sticky` y `top: 0`
- [ ] El header tiene `z-index` alto
- [ ] El contenido interno del header usa `display: flex`
- [ ] Se usa `justify-content: space-between`
- [ ] Se usa `align-items: center`
- [ ] La navegación (ul) también usa `display: flex`
- [ ] Se usa `gap` para espaciar items de navegación
- [ ] Los enlaces tienen estados :hover con transición
- [ ] Se usan variables para todos los valores

#### 💡 Pistas

- `position: sticky` + `top: 0` hace que el header se quede arriba al scroll
- `z-index: 1000` asegura que esté sobre otros elementos
- `display: flex` en el header y en el `<ul>` de navegación
- `gap` es mejor que margin para espaciar items flex
- `justify-content: space-between` pone espacio entre logo y nav
- `align-items: center` centra verticalmente

#### 🔍 Preguntas de Reflexión

- ¿Cuál es la diferencia entre `position: sticky` y `position: fixed`?
- ¿Por qué usar `gap` en lugar de `margin` para espaciar items flex?
- ¿Qué hace `justify-content: space-between`?

---

### 📝 TAREA 2.2: Footer con CSS Grid

**Ubicación:** En `styles.css`, crear estilos para `<footer>`

#### 🎯 Objetivo
Estilizar el footer usando CSS Grid para organizar las columnas.

#### 📋 Requisitos Específicos

El footer debe tener:

1. **Contenedor footer:**
   - Fondo oscuro (diferente al header) usando variable
   - Color de texto claro usando variable
   - Padding generoso usando variables
   - Margin-top automático (para empujar al fondo si hay poco contenido)

2. **Layout con Grid:**
   - Display grid
   - 4 columnas de igual tamaño
   - Gap entre columnas usando variable
   - Padding horizontal usando variable

3. **Secciones del footer:**
   - Headings (h3, h4) con color de acento usando variable
   - Margin-bottom en headings
   - Font-size menor para h4

4. **Enlaces del footer:**
   - Color claro usando variable
   - Sin subrayado por defecto
   - Hover con color diferente
   - Transición suave
   - Display block para mejor área de click
   - Padding pequeño

5. **Copyright (última sección):**
   - Text-align center
   - Font-size menor
   - Padding superior
   - Grid-column que abarque las 4 columnas

#### ✅ Criterios de Aceptación

- [ ] El footer usa `display: grid`
- [ ] Se define `grid-template-columns` para 4 columnas
- [ ] Se usa `gap` para espaciar columnas
- [ ] El footer tiene fondo oscuro y texto claro
- [ ] Los enlaces tienen color claro y hover
- [ ] La sección de copyright abarca las 4 columnas
- [ ] Se usa `margin-top: auto` en el footer
- [ ] Se usan variables para todos los valores

#### 💡 Pistas

- `grid-template-columns: repeat(4, 1fr)` crea 4 columnas iguales
- `1fr` significa "1 fracción del espacio disponible"
- `margin-top: auto` empuja el footer al fondo si hay poco contenido
- `grid-column: 1 / -1` hace que un elemento abarque todas las columnas
- Usa variables para colores oscuros/claros

#### 🔍 Preguntas de Reflexión

- ¿Qué significa `1fr` en CSS Grid?
- ¿Cómo funciona `margin-top: auto` para empujar el footer al fondo?
- ¿Qué hace `grid-column: 1 / -1`?

---

### 📝 TAREA 2.3: Contenedor Centrado Reutilizable

**Ubicación:** En `styles.css`, crear clase `.container`

#### 🎯 Objetivo
Crear una clase reutilizable para centrar y limitar el ancho de las secciones.

#### 📋 Requisitos Específicos

Crea una clase `.container` que:

1. **Ancho:**
   - Ancho máximo usando variable (ej: 1200px)
   - Ancho del 100% hasta alcanzar el máximo
   - Padding horizontal para que no toque los bordes en móviles

2. **Centrado:**
   - Margin horizontal automático (centra el contenedor)

3. **Aplicación en HTML:**
   - Agregar la clase a las secciones principales
   - Aplicar al contenido del header (dentro del header)
   - Aplicar al contenido del footer (dentro del footer)

#### ✅ Criterios de Aceptación

- [ ] Existe una clase `.container` en CSS
- [ ] Usa `max-width` con variable
- [ ] Usa `width: 100%`
- [ ] Usa `margin: 0 auto` para centrar
- [ ] Tiene padding horizontal usando variable
- [ ] Se aplica en el HTML a las secciones principales

#### 💡 Pistas

- `max-width` limita el ancho máximo
- `width: 100%` hace que ocupe todo el ancho hasta el máximo
- `margin: 0 auto` centra horizontalmente (0 arriba/abajo, auto izquierda/derecha)
- Padding horizontal previene que el contenido toque los bordes en móviles

#### 🔍 Preguntas de Reflexión

- ¿Por qué usar `max-width` en lugar de solo `width`?
- ¿Cómo funciona `margin: 0 auto` para centrar?
- ¿Por qué agregar padding horizontal?

---

### 📝 TAREA 2.4: Secciones Principales

**Ubicación:** En `styles.css`, crear estilos para `<section>`

#### 🎯 Objetivo
Estilizar las secciones principales con espaciado consistente.

#### 📋 Requisitos Específicos

Las secciones deben tener:

1. **Espaciado:**
   - Padding vertical generoso usando variable
   - Padding horizontal usando variable (o usar .container)

2. **Secciones alternas:**
   - Crear clase `.section-alt` para secciones con fondo diferente
   - Fondo secundario usando variable

3. **Headings de sección:**
   - Text-align center
   - Margin-bottom generoso
   - Color usando variable

#### ✅ Criterios de Aceptación

- [ ] Las secciones tienen padding vertical y horizontal
- [ ] Existe una clase `.section-alt` para fondos alternos
- [ ] Los h2 de sección están centrados
- [ ] Se usan variables para espaciado y colores

#### 💡 Pistas

- Padding vertical grande mejora la legibilidad
- Alternar fondos ayuda a diferenciar secciones
- Text-align center en headings da un look más profesional

---

### ✅ Checklist de Validación del Módulo CSS-2

Antes de continuar al Módulo 3, verifica:

#### Header
- [ ] El header usa Flexbox
- [ ] Es sticky y se queda arriba al scroll
- [ ] La navegación es horizontal con gap
- [ ] Los enlaces tienen hover

#### Footer
- [ ] El footer usa CSS Grid con 4 columnas
- [ ] Tiene fondo oscuro y texto claro
- [ ] El copyright abarca las 4 columnas
- [ ] Los enlaces tienen hover

#### Contenedor
- [ ] Existe una clase `.container` reutilizable
- [ ] Está aplicada en el HTML
- [ ] Centra y limita el ancho del contenido

#### Secciones
- [ ] Las secciones tienen padding consistente
- [ ] Hay una clase para fondos alternos
- [ ] Los layouts son consistentes

---

## 📦 MÓDULO CSS-3: Componentes y Cards
**Duración:** 3-4 horas

### 🎓 Temas a Practicar
- ✅ Flexbox/Grid para componentes
- ✅ Box Model (padding, margin, border)
- ✅ Pseudo-clases (:hover, :focus, :active)
- ✅ Transform (scale, translateY)
- ✅ Transition

---

### 📝 TAREA 3.1: Cards de Cómics

**Ubicación:** En `styles.css`, crear estilos para `<article>` (cards)

#### 🎯 Objetivo
Estilizar las cards de cómics con efectos hover atractivos.

#### 📋 Requisitos Específicos

Cada card debe tener:

1. **Contenedor article:**
   - Fondo con variable
   - Border-radius usando variable
   - Padding usando variable
   - Box-shadow sutil usando variable
   - Transición para hover (0.3s)
   - Display flex con flex-direction column

2. **Imagen:**
   - Ancho completo (100%)
   - Height auto
   - Border-radius en esquinas superiores
   - Object-fit cover (mantener proporción)
   - Margin-bottom

3. **Contenido de la card:**
   - Padding interno
   - Flex-grow para ocupar espacio disponible

4. **Títulos (h3):**
   - Margin-top: 0
   - Margin-bottom
   - Color usando variable

5. **Párrafos:**
   - Margin-bottom pequeño
   - Line-height para legibilidad

6. **Hover de la card:**
   - Transform scale ligeramente (1.02-1.05) o translateY hacia arriba
   - Box-shadow más pronunciada
   - Transición suave

7. **Botones dentro de la card:**
   - Margin-top auto (empujar al fondo)
   - Display flex con gap
   - Flex-wrap para que se envuelvan en móviles

#### ✅ Criterios de Aceptación

- [ ] Las cards tienen box-shadow y border-radius
- [ ] Hay efecto hover con transform
- [ ] Las transiciones son suaves (0.3s)
- [ ] Las imágenes tienen border-radius y object-fit
- [ ] El contenido está bien espaciado
- [ ] Los botones están al fondo de la card
- [ ] Se usan variables para todos los valores

#### 💡 Pistas

- `display: flex` + `flex-direction: column` organiza el contenido verticalmente
- `flex-grow: 1` hace que el contenido ocupe el espacio disponible
- `margin-top: auto` empuja los botones al fondo
- `transform: scale(1.05)` agranda ligeramente
- `transform: translateY(-5px)` mueve hacia arriba
- `object-fit: cover` mantiene el aspect ratio de la imagen

#### 🔍 Preguntas de Reflexión

- ¿Qué hace `flex-direction: column`?
- ¿Cómo funciona `margin-top: auto` para empujar elementos al fondo?
- ¿Cuál es la diferencia entre `scale` y `translateY` para hover?

---

### 📝 TAREA 3.2: Galería con CSS Grid

**Ubicación:** En `styles.css`, crear estilos para la sección de galería

#### 🎯 Objetivo
Organizar las cards en una grilla responsive usando CSS Grid.

#### 📋 Requisitos Específicos

La galería debe:

1. **Contenedor de la galería:**
   - Display grid
   - Grid-template-columns con auto-fit o auto-fill
   - Minmax para responsive (mínimo 280px, máximo 1fr)
   - Gap usando variable
   - Padding usando variable

2. **Responsive automático:**
   - Las columnas se ajustan automáticamente según el espacio
   - Mínimo 1 columna en móvil
   - Hasta 3 columnas en desktop

#### ✅ Criterios de Aceptación

- [ ] Usa `display: grid`
- [ ] Usa `grid-template-columns` con `repeat(auto-fit, minmax(...))`
- [ ] Tiene `gap` para espaciar cards
- [ ] Es responsive sin media queries
- [ ] Se usan variables para gap

#### 💡 Pistas

- `repeat(auto-fit, minmax(280px, 1fr))` crea columnas responsive
- `auto-fit` colapsa columnas vacías
- `minmax(280px, 1fr)` define ancho mínimo y máximo
- `gap` espacía las cards automáticamente

#### 🔍 Preguntas de Reflexión

- ¿Qué hace `auto-fit` en CSS Grid?
- ¿Cómo funciona `minmax()` para hacer grids responsive?
- ¿Por qué este enfoque es mejor que usar media queries?

---

### 📝 TAREA 3.3: Botones

**Ubicación:** En `styles.css`, crear estilos para `<button>` y botones tipo enlace

#### 🎯 Objetivo
Crear estilos consistentes para todos los botones con estados interactivos.

#### 📋 Requisitos Específicos

Los botones deben tener:

1. **Estilos base:**
   - Padding usando variables (vertical y horizontal)
   - Border: none (quitar borde por defecto)
   - Border-radius usando variable
   - Font-size heredado o específico
   - Font-weight medium (500-600)
   - Cursor pointer
   - Transición suave

2. **Variantes de color:**
   - Botón primario: fondo primario, texto claro
   - Botón secundario: fondo secundario, texto oscuro
   - Botón outline: fondo transparente, border con color primario

3. **Estados interactivos:**
   - Hover: fondo más oscuro o transform scale
   - Active: transform scale más pequeño (0.95)
   - Focus: outline personalizado con color primario
   - Disabled: opacidad reducida (0.5-0.6), cursor not-allowed

4. **Clases de variantes:**
   - `.btn-primary` para botones principales
   - `.btn-secondary` para botones secundarios
   - `.btn-outline` para botones con borde

#### ✅ Criterios de Aceptación

- [ ] Los botones tienen padding, border-radius, cursor pointer
- [ ] Hay al menos 3 variantes de botones
- [ ] Los estados :hover, :active, :focus están estilizados
- [ ] El estado :disabled tiene opacidad reducida
- [ ] Las transiciones son suaves
- [ ] Se usan variables para colores

#### 💡 Pistas

- `cursor: pointer` muestra la manita al pasar el mouse
- `cursor: not-allowed` para botones disabled
- `transform: scale(0.95)` en :active da feedback táctil
- `outline` personalizado mejora accesibilidad
- Usa `filter: brightness(0.9)` para oscurecer en hover

#### 🔍 Preguntas de Reflexión

- ¿Por qué es importante el estado :focus en botones?
- ¿Qué diferencia hay entre :hover y :active?
- ¿Por qué usar `cursor: not-allowed` en disabled?

---

### 📝 TAREA 3.4: Formularios (Inputs, Selects, Textareas)

**Ubicación:** En `styles.css`, crear estilos para elementos de formulario

#### 🎯 Objetivo
Estilizar todos los elementos de formulario de manera consistente y accesible.

#### 📋 Requisitos Específicos

Los formularios deben tener:

1. **Inputs y selects:**
   - Padding usando variables
   - Border con color de variable (sutil)
   - Border-radius usando variable
   - Font-size heredado
   - Width 100% (ocupar todo el ancho disponible)
   - Transición en border-color

2. **Estado focus:**
   - Border-color más intenso (color primario)
   - Outline personalizado o box-shadow
   - Transición suave

3. **Labels:**
   - Display block
   - Margin-bottom pequeño
   - Font-weight medium
   - Color usando variable

4. **Fieldsets:**
   - Border sutil usando variable
   - Border-radius usando variable
   - Padding usando variable
   - Margin-bottom usando variable

5. **Legends:**
   - Font-weight bold
   - Padding horizontal
   - Color usando variable

6. **Textareas:**
   - Resize vertical (permitir cambiar altura, no ancho)
   - Padding, border, border-radius igual que inputs
   - Font-family heredada

7. **Inputs de radio y checkbox:**
   - Cursor pointer
   - Margin-right pequeño
   - Escala mayor (transform: scale(1.2))

#### ✅ Criterios de Aceptación

- [ ] Todos los inputs tienen estilos consistentes
- [ ] El estado :focus tiene border-color y outline personalizados
- [ ] Los labels tienen display block y margin-bottom
- [ ] Los fieldsets tienen border, padding, border-radius
- [ ] Los textareas tienen resize: vertical
- [ ] Los radios y checkboxes tienen cursor pointer
- [ ] Se usan variables para todos los valores

#### 💡 Pistas

- `width: 100%` hace que los inputs ocupen todo el ancho
- `resize: vertical` permite cambiar altura pero no ancho
- `outline: 2px solid var(--color-primario)` para focus
- `box-shadow: 0 0 0 3px rgba(...)` también funciona para focus
- `transform: scale(1.2)` agranda radios y checkboxes

#### 🔍 Preguntas de Reflexión

- ¿Por qué es importante estilizar el estado :focus?
- ¿Qué hace `resize: vertical` en textareas?
- ¿Por qué usar `width: 100%` en inputs?

---

### 📝 TAREA 3.5: Sistema de Tabs

**Ubicación:** En `styles.css`, crear estilos para el sistema de pestañas

#### 🎯 Objetivo
Estilizar el sistema de tabs con estados activos e inactivos.

#### 📋 Requisitos Específicos

El sistema de tabs debe tener:

1. **Contenedor de tabs (tablist):**
   - Display flex
   - Gap entre tabs
   - Border-bottom para separar de los paneles
   - Margin-bottom

2. **Botones de tabs:**
   - Padding usando variables
   - Border: none por defecto
   - Border-bottom grueso (3px) transparente
   - Background transparente
   - Cursor pointer
   - Transición

3. **Tab activo (aria-selected="true"):**
   - Border-bottom con color primario
   - Color de texto primario
   - Font-weight bold

4. **Tab hover (no activo):**
   - Background sutil
   - Border-bottom con color más claro

5. **Paneles (tabpanel):**
   - Padding usando variable
   - Animación fade-in al mostrarse (opcional)

#### ✅ Criterios de Aceptación

- [ ] El tablist usa Flexbox con gap
- [ ] Los tabs tienen padding y cursor pointer
- [ ] El tab activo tiene border-bottom de color primario
- [ ] Los tabs inactivos tienen hover
- [ ] Las transiciones son suaves
- [ ] Se usan variables para colores

#### 💡 Pistas

- Usa selector de atributo: `[aria-selected="true"]` para tab activo
- `border-bottom: 3px solid transparent` reserva espacio
- `border-bottom-color: var(--color-primario)` en activo
- Transición en `border-bottom-color` y `background`

#### 🔍 Preguntas de Reflexión

- ¿Cómo funciona el selector `[aria-selected="true"]`?
- ¿Por qué usar `border-bottom` en lugar de `border`?

---

### 📝 TAREA 3.6: Modal

**Ubicación:** En `styles.css`, crear estilos para el modal

#### 🎯 Objetivo
Estilizar el modal con overlay y animación de entrada.

#### 📋 Requisitos Específicos

El modal debe tener:

1. **Overlay (contenedor del modal):**
   - Position fixed
   - Top, left, right, bottom: 0 (pantalla completa)
   - Background rgba oscuro (overlay semitransparente)
   - Display flex para centrar el modal
   - Justify-content y align-items center
   - Z-index muy alto (9999)
   - Cuando tiene atributo `hidden`: display none

2. **Contenido del modal (role="document"):**
   - Background usando variable
   - Border-radius usando variable
   - Padding usando variable
   - Max-width (ej: 600px)
   - Max-height (ej: 90vh)
   - Overflow-y auto (scroll si es muy largo)
   - Box-shadow pronunciada

3. **Header del modal:**
   - Display flex
   - Justify-content space-between
   - Align-items center
   - Border-bottom sutil
   - Padding-bottom
   - Margin-bottom

4. **Botón de cerrar:**
   - Background transparente
   - Border: none
   - Font-size grande
   - Cursor pointer
   - Hover con transform rotate

5. **Animación (opcional):**
   - Fade-in del overlay
   - Scale-in del contenido

#### ✅ Criterios de Aceptación

- [ ] El overlay usa position fixed y cubre toda la pantalla
- [ ] El modal está centrado con Flexbox
- [ ] Tiene background semitransparente oscuro
- [ ] El contenido tiene max-width y max-height
- [ ] El header tiene display flex con space-between
- [ ] El botón de cerrar tiene hover
- [ ] Cuando tiene `hidden` no se muestra

#### 💡 Pistas

- `position: fixed` + `top: 0; left: 0; right: 0; bottom: 0` = pantalla completa
- `background: rgba(0, 0, 0, 0.5)` = overlay semitransparente
- `overflow-y: auto` permite scroll si el contenido es largo
- `[hidden]` selector para cuando tiene atributo hidden

#### 🔍 Preguntas de Reflexión

- ¿Por qué usar `position: fixed` en lugar de `absolute`?
- ¿Cómo funciona `rgba()` para transparencia?
- ¿Por qué usar `max-height` en el modal?

---

### ✅ Checklist de Validación del Módulo CSS-3

Antes de continuar al Módulo 4, verifica:

#### Cards
- [ ] Las cards tienen box-shadow, border-radius, padding
- [ ] Hay efecto hover con transform
- [ ] Las imágenes tienen border-radius y object-fit
- [ ] El layout interno usa Flexbox

#### Galería
- [ ] Usa CSS Grid con auto-fit/auto-fill
- [ ] Es responsive sin media queries
- [ ] Tiene gap consistente

#### Botones
- [ ] Hay al menos 3 variantes de botones
- [ ] Los estados hover, active, focus están estilizados
- [ ] El estado disabled tiene opacidad reducida

#### Formularios
- [ ] Inputs, selects, textareas tienen estilos consistentes
- [ ] El estado focus tiene outline personalizado
- [ ] Los fieldsets tienen border y padding
- [ ] Los labels tienen display block

#### Tabs
- [ ] El tablist usa Flexbox
- [ ] El tab activo tiene border-bottom de color
- [ ] Los tabs tienen hover

#### Modal
- [ ] El overlay cubre toda la pantalla
- [ ] El modal está centrado
- [ ] Tiene max-width y max-height
- [ ] El botón de cerrar tiene hover

---

## 📦 MÓDULO CSS-4: Responsive Design
**Duración:** 2-3 horas

### 🎓 Temas a Practicar
- ✅ Media queries
- ✅ Mobile-first approach
- ✅ Flexbox/Grid responsive

---

### 📝 TAREA 4.1: Media Queries para Mobile

**Ubicación:** Al final de `styles.css`

#### 🎯 Objetivo
Hacer la aplicación completamente responsive usando media queries.

#### 📋 Requisitos Específicos

Define breakpoints para:

1. **Mobile (< 768px):**
   - Header: cambiar a columna (flex-direction: column)
   - Navegación: centrar, reducir gap
   - Footer: 1 columna (grid-template-columns: 1fr)
   - Padding reducido en secciones
   - Font-size ligeramente menor en headings
   - Cards: padding reducido

2. **Tablet (768px - 1024px):**
   - Footer: 2 columnas
   - Mantener la mayoría de estilos desktop

3. **Desktop (> 1024px):**
   - Estilos por defecto (ya definidos)

#### ✅ Criterios de Aceptación

- [ ] Hay al menos 2 media queries (mobile y tablet)
- [ ] Se usa `max-width` para mobile (mobile-first invertido) o `min-width`
- [ ] El header es responsive (columna en móvil)
- [ ] El footer es responsive (1 col móvil, 2 col tablet, 4 col desktop)
- [ ] Los paddings se reducen en móvil
- [ ] Los font-sizes se ajustan en móvil

#### 💡 Pistas

- `@media (max-width: 767px)` para móviles
- `@media (min-width: 768px) and (max-width: 1023px)` para tablets
- `flex-direction: column` en header para móvil
- `grid-template-columns: 1fr` para 1 columna
- Reduce paddings en 30-50% en móvil

#### 🔍 Preguntas de Reflexión

- ¿Qué es mobile-first y por qué es importante?
- ¿Cuál es la diferencia entre `max-width` y `min-width` en media queries?
- ¿Por qué reducir paddings en móvil?

---

### 📝 TAREA 4.2: Optimizaciones para Móvil

**Ubicación:** Dentro de las media queries en `styles.css`

#### 🎯 Objetivo
Optimizar la experiencia móvil con ajustes específicos.

#### 📋 Requisitos Específicos

En móvil:

1. **Botones:**
   - Padding mayor (área de toque más grande)
   - Width 100% en algunos casos
   - Margin-bottom para separación

2. **Formularios:**
   - Inputs con font-size mínimo 16px (evita zoom en iOS)
   - Botones de formulario width 100%

3. **Modal:**
   - Max-width 95% (más espacio en pantalla)
   - Padding reducido

4. **Tabs:**
   - Scroll horizontal si no caben (overflow-x: auto)
   - Flex-wrap: nowrap

#### ✅ Criterios de Aceptación

- [ ] Los botones tienen padding mayor en móvil
- [ ] Los inputs tienen font-size mínimo 16px
- [ ] El modal tiene max-width 95% en móvil
- [ ] Los tabs tienen scroll horizontal si no caben

#### 💡 Pistas

- `font-size: 16px` en inputs evita zoom automático en iOS
- `min-height: 44px` es el tamaño mínimo recomendado para botones táctiles
- `overflow-x: auto` permite scroll horizontal
- `flex-wrap: nowrap` evita que los tabs se envuelvan

---

### ✅ Checklist de Validación del Módulo CSS-4

Antes de continuar al Módulo 5, verifica:

#### Media Queries
- [ ] Hay media queries para mobile y tablet
- [ ] El header cambia a columna en móvil
- [ ] El footer tiene 1 columna en móvil, 2 en tablet
- [ ] Los paddings se reducen en móvil

#### Optimizaciones Móviles
- [ ] Los botones tienen área de toque adecuada
- [ ] Los inputs tienen font-size mínimo 16px
- [ ] El modal es responsive
- [ ] Los tabs tienen scroll horizontal

#### Pruebas
- [ ] La aplicación se ve bien en móvil (< 768px)
- [ ] La aplicación se ve bien en tablet (768-1024px)
- [ ] La aplicación se ve bien en desktop (> 1024px)

---

## 📦 MÓDULO CSS-5: Interactividad y Dark Mode
**Duración:** 2-3 horas

### 🎓 Temas a Practicar
- ✅ prefers-color-scheme (dark mode)
- ✅ Animaciones (@keyframes, animation)
- ✅ Pseudo-elementos (::before, ::after)
- ✅ Accesibilidad (prefers-reduced-motion)

---

### 📝 TAREA 5.1: Dark Mode Automático

**Ubicación:** Al final de `styles.css`

#### 🎯 Objetivo
Implementar dark mode automático que respete las preferencias del sistema.

#### 📋 Requisitos Específicos

1. **Media query para dark mode:**
   - Usar `@media (prefers-color-scheme: dark)`
   - Redefinir variables de color en `:root`

2. **Variables a redefinir:**
   - Fondo principal: oscuro (ej: #1a1a1a)
   - Fondo secundario: ligeramente más claro (ej: #2a2a2a)
   - Texto principal: claro (ej: #e0e0e0)
   - Texto secundario: gris claro (ej: #a0a0a0)
   - Ajustar colores primarios para mejor contraste

3. **Elementos específicos:**
   - Cards: fondo oscuro, sombra más sutil
   - Inputs: fondo oscuro, border más claro
   - Modal: fondo oscuro

#### ✅ Criterios de Aceptación

- [ ] Hay un media query `@media (prefers-color-scheme: dark)`
- [ ] Se redefinen variables de color en `:root` dentro del media query
- [ ] Los colores de fondo y texto se invierten apropiadamente
- [ ] El contraste es suficiente para legibilidad
- [ ] Los colores primarios se ajustan si es necesario

#### 💡 Pistas

- `@media (prefers-color-scheme: dark)` detecta preferencia del sistema
- Redefine variables dentro del media query: `:root { --color-fondo: #1a1a1a; }`
- Usa colores HSL para ajustar fácilmente: `hsl(220, 90%, 70%)` en dark mode
- Verifica contraste con herramientas de accesibilidad

#### 🔍 Preguntas de Reflexión

- ¿Cómo detecta el navegador la preferencia de dark mode del usuario?
- ¿Por qué redefinir variables en lugar de crear estilos nuevos?
- ¿Qué consideraciones de contraste hay en dark mode?

---

### 📝 TAREA 5.2: Animaciones Sutiles

**Ubicación:** En `styles.css`, crear @keyframes y aplicar animaciones

#### 🎯 Objetivo
Agregar animaciones sutiles que mejoren la experiencia sin ser intrusivas.

#### 📋 Requisitos Específicos

Crea las siguientes animaciones:

1. **Fade-in al cargar:**
   - @keyframes fadeIn: de opacidad 0 a 1
   - Aplicar a secciones principales
   - Duración: 0.5-0.8s

2. **Slide-in para cards:**
   - @keyframes slideIn: de translateY(20px) a translateY(0)
   - Combinar con fade-in
   - Aplicar a las cards
   - Duración: 0.6s

3. **Pulse para botones (opcional):**
   - @keyframes pulse: escala de 1 a 1.05 y vuelta
   - Aplicar en hover de botones primarios

4. **Spin para loading (opcional):**
   - @keyframes spin: rotación de 0deg a 360deg
   - Útil para indicadores de carga futuros

#### ✅ Criterios de Aceptación

- [ ] Hay al menos 2 @keyframes definidos
- [ ] Se usa `animation` en elementos apropiados
- [ ] Las animaciones son sutiles (no distraen)
- [ ] Las duraciones son razonables (0.3s - 1s)
- [ ] Se usa `animation-fill-mode: forwards` si es necesario

#### 💡 Pistas

- `@keyframes nombre { from { ... } to { ... } }`
- `animation: nombre duración timing-function`
- `animation-delay` para escalonar animaciones
- `animation-fill-mode: forwards` mantiene el estado final

#### 🔍 Preguntas de Reflexión

- ¿Cuándo usar `from/to` vs porcentajes en @keyframes?
- ¿Qué hace `animation-fill-mode: forwards`?
- ¿Cómo afectan las animaciones a la accesibilidad?

---

### 📝 TAREA 5.3: Respeto por Preferencias de Movimiento

**Ubicación:** Al final de `styles.css`

#### 🎯 Objetivo
Respetar la preferencia de usuarios que prefieren movimiento reducido.

#### 📋 Requisitos Específicos

1. **Media query:**
   - Usar `@media (prefers-reduced-motion: reduce)`
   - Desactivar o reducir animaciones

2. **Dentro del media query:**
   - Establecer `animation: none` para elementos animados
   - Reducir `transition-duration` a 0.01s (casi instantáneo)
   - Desactivar transforms en hover (o reducir)

#### ✅ Criterios de Aceptación

- [ ] Hay un media query `@media (prefers-reduced-motion: reduce)`
- [ ] Las animaciones se desactivan o reducen significativamente
- [ ] Las transiciones son casi instantáneas
- [ ] La funcionalidad se mantiene sin animaciones

#### 💡 Pistas

- `@media (prefers-reduced-motion: reduce)` detecta preferencia
- `animation: none` desactiva animaciones
- `transition-duration: 0.01s` hace transiciones casi instantáneas
- Mantén cambios visuales (colores, etc.) pero sin movimiento

#### 🔍 Preguntas de Reflexión

- ¿Por qué algunos usuarios prefieren movimiento reducido?
- ¿Qué diferencia hay entre desactivar animaciones y reducir duración?
- ¿Cómo afecta esto a la accesibilidad?

---

### 📝 TAREA 5.4: Pseudo-elementos Decorativos (Opcional)

**Ubicación:** En `styles.css`, usar ::before y ::after

#### 🎯 Objetivo
Usar pseudo-elementos para agregar detalles visuales sin HTML adicional.

#### 📋 Requisitos Específicos

Ejemplos de uso:

1. **Iconos decorativos:**
   - Agregar ::before a headings con content
   - Usar emojis o símbolos Unicode

2. **Separadores:**
   - Usar ::after en secciones para líneas decorativas

3. **Efectos de hover:**
   - Usar ::before para overlay en cards al hover

#### ✅ Criterios de Aceptación

- [ ] Se usan ::before o ::after en al menos 2 elementos
- [ ] Se usa la propiedad `content`
- [ ] Los pseudo-elementos tienen position si es necesario
- [ ] Son puramente decorativos (no contenido importante)

#### 💡 Pistas

- `::before` y `::after` requieren `content: ""` para existir
- Usa `position: absolute` para posicionar pseudo-elementos
- `content: "→"` para símbolos Unicode
- Marca como decorativo con `aria-hidden="true"` si es necesario

---

### ✅ Checklist Final de la Fase 2 (CSS Completo)

#### Sistema de Diseño
- [ ] Variables CSS definidas (20+)
- [ ] Reset CSS implementado
- [ ] Tipografía base configurada
- [ ] Colores consistentes

#### Layouts
- [ ] Header con Flexbox y sticky
- [ ] Footer con Grid (4 columnas desktop)
- [ ] Contenedor centrado (.container)
- [ ] Secciones con padding consistente

#### Componentes
- [ ] Cards estilizadas con hover effects
- [ ] Galería con Grid responsive
- [ ] Botones con 3+ variantes
- [ ] Formularios completamente estilizados
- [ ] Sistema de tabs funcional
- [ ] Modal con overlay

#### Responsive
- [ ] Media queries para mobile, tablet, desktop
- [ ] Header responsive (columna en móvil)
- [ ] Footer responsive (1/2/4 columnas)
- [ ] Optimizaciones móviles (font-size, padding)

#### Avanzado
- [ ] Dark mode automático (prefers-color-scheme)
- [ ] Animaciones sutiles (@keyframes)
- [ ] Respeto por reduced-motion
- [ ] Pseudo-elementos decorativos (opcional)

#### Validación
- [ ] El CSS es válido (sin errores de sintaxis)
- [ ] La aplicación se ve bien en todos los tamaños
- [ ] El dark mode funciona correctamente
- [ ] Las animaciones son sutiles y apropiadas
- [ ] La accesibilidad se mantiene

---

## 🚀 Próximos Pasos

1. ✅ Completa los 5 módulos de CSS
2. ✅ Prueba en diferentes tamaños de pantalla
3. ✅ Prueba en modo claro y oscuro
4. ✅ Valida la accesibilidad (contraste, focus, reduced-motion)
5. ✅ Comparte tu código para revisión
6. ⏭️ **Continúa con la Fase 3: JavaScript** (interactividad y funcionalidad)
