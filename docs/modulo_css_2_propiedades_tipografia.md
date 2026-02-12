# MÓDULO CSS-2: Propiedades de Tipografía

## 📚 Introducción

La **tipografía** es uno de los aspectos más importantes del diseño web. Controla cómo se ve y se lee el texto en tu sitio. Una buena tipografía mejora la legibilidad, establece jerarquía visual y comunica la personalidad de tu marca.

**Regla de oro:** El 95% del diseño web es tipografía. Si tu tipografía es buena, tu diseño será bueno.

En este módulo aprenderás las propiedades CSS esenciales para controlar la apariencia del texto, aplicando el principio 80/20: las propiedades que usarás el 80% del tiempo.

---

## 1️⃣ `font-family` - Familia de Fuentes

### Concepto

Define qué **tipo de letra** (fuente) se usará para mostrar el texto. Es como elegir entre escribir con letra Arial, Times New Roman, o Comic Sans.

### Sintaxis

```css
selector {
  font-family: fuente-preferida, fuente-respaldo, tipo-genérico;
}
```

### Valores

**1. Fuentes específicas** (entre comillas si tienen espacios):
```css
font-family: Arial;
font-family: "Times New Roman";
font-family: "Helvetica Neue";
```

**2. Tipos genéricos** (siempre al final como respaldo):
- `serif`: Fuentes con serifas (decoraciones en los extremos)
- `sans-serif`: Fuentes sin serifas (limpias, modernas)
- `monospace`: Fuentes de ancho fijo (para código)
- `cursive`: Fuentes cursivas/script
- `fantasy`: Fuentes decorativas

### Ejemplos Prácticos

```css
/* Fuente simple con respaldo */
body {
  font-family: Arial, sans-serif;
}

/* Múltiples respaldos */
h1 {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}

/* Fuentes del sistema (moderno) */
body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", 
               Roboto, "Helvetica Neue", Arial, sans-serif;
}

/* Fuente de Google Fonts */
body {
  font-family: 'Inter', sans-serif;
}

/* Fuente monoespaciada para código */
code {
  font-family: "Courier New", Courier, monospace;
}
```

### Buenas Prácticas

✅ **BIEN:**
```css
/* Siempre incluye un tipo genérico al final */
font-family: "Georgia", serif;

/* Usa comillas para nombres con espacios */
font-family: "Times New Roman", serif;
```

❌ **MAL:**
```css
/* Sin tipo genérico de respaldo */
font-family: "Georgia";

/* Sin comillas en nombre con espacios */
font-family: Times New Roman, serif;
```

### Cuándo Usar

- **`serif`**: Textos largos, blogs, contenido editorial (más tradicional)
- **`sans-serif`**: Interfaces, títulos, contenido moderno (más limpio)
- **`monospace`**: Código, datos tabulares, terminales

---

## 2️⃣ `font-size` - Tamaño de Fuente

### Concepto

Controla el **tamaño** del texto. Determina qué tan grande o pequeño se ve el texto en pantalla.

### Sintaxis

```css
selector {
  font-size: valor;
}
```

### Unidades Comunes

| Unidad | Tipo | Descripción | Uso |
|--------|------|-------------|-----|
| `px` | Absoluta | Píxeles | Preciso, pero no escala con zoom del navegador |
| `em` | Relativa | Relativo al padre | Escalable, pero puede acumularse |
| `rem` | Relativa | Relativo al root (html) | **Recomendado**: escalable y predecible |
| `%` | Relativa | Porcentaje del padre | Similar a `em` |
| `vw/vh` | Viewport | Relativo al viewport | Tipografía fluida/responsive |

### Ejemplos Prácticos

```css
/* Píxeles (absoluto) */
p {
  font-size: 16px;
}

/* REM (recomendado) */
html {
  font-size: 16px; /* Base */
}

h1 {
  font-size: 2rem; /* 32px (16 × 2) */
}

p {
  font-size: 1rem; /* 16px (16 × 1) */
}

small {
  font-size: 0.875rem; /* 14px (16 × 0.875) */
}

/* EM (relativo al padre) */
.parent {
  font-size: 20px;
}

.child {
  font-size: 0.8em; /* 16px (20 × 0.8) */
}

/* Porcentaje */
p {
  font-size: 100%; /* Igual que el padre */
}

/* Viewport (responsive) */
h1 {
  font-size: 5vw; /* 5% del ancho del viewport */
}
```

### Comparación: em vs rem

```css
html {
  font-size: 16px;
}

.parent {
  font-size: 20px;
}

.child-em {
  font-size: 2em; /* 40px (20 × 2) - relativo al padre */
}

.child-rem {
  font-size: 2rem; /* 32px (16 × 2) - relativo al html */
}
```

**Problema con `em` (acumulación):**
```css
.level-1 {
  font-size: 1.2em; /* 19.2px si el padre es 16px */
}

.level-2 {
  font-size: 1.2em; /* 23.04px (19.2 × 1.2) - se acumula */
}

.level-3 {
  font-size: 1.2em; /* 27.65px (23.04 × 1.2) - sigue acumulándose */
}
```

**Solución con `rem`:**
```css
.level-1 {
  font-size: 1.2rem; /* Siempre 19.2px */
}

.level-2 {
  font-size: 1.2rem; /* Siempre 19.2px */
}

.level-3 {
  font-size: 1.2rem; /* Siempre 19.2px */
}
```

### Escala Tipográfica Recomendada

```css
:root {
  --font-size-xs: 0.75rem;    /* 12px */
  --font-size-sm: 0.875rem;   /* 14px */
  --font-size-base: 1rem;     /* 16px */
  --font-size-lg: 1.125rem;   /* 18px */
  --font-size-xl: 1.25rem;    /* 20px */
  --font-size-2xl: 1.5rem;    /* 24px */
  --font-size-3xl: 1.875rem;  /* 30px */
  --font-size-4xl: 2.25rem;   /* 36px */
}

body {
  font-size: var(--font-size-base);
}

h1 {
  font-size: var(--font-size-4xl);
}

h2 {
  font-size: var(--font-size-3xl);
}
```

### Buenas Prácticas

✅ **BIEN:**
```css
/* Usa rem para tamaños de fuente */
html {
  font-size: 16px;
}

p {
  font-size: 1rem;
}

/* Usa em para espaciado relativo al texto */
p {
  font-size: 1rem;
  margin-bottom: 1.5em; /* Escala con el tamaño del texto */
}
```

❌ **MAL:**
```css
/* Píxeles en todos lados (no escala) */
p {
  font-size: 16px;
  margin-bottom: 24px;
}
```

---

## 3️⃣ `font-weight` - Peso de Fuente

### Concepto

Controla el **grosor** o "peso" del texto. Determina qué tan gruesas o delgadas son las letras.

### Sintaxis

```css
selector {
  font-weight: valor;
}
```

### Valores

**Palabras clave:**
- `normal`: Peso normal (equivale a 400)
- `bold`: Negrita (equivale a 700)
- `lighter`: Más delgado que el padre
- `bolder`: Más grueso que el padre

**Valores numéricos (100-900):**
```css
font-weight: 100;  /* Thin */
font-weight: 200;  /* Extra Light */
font-weight: 300;  /* Light */
font-weight: 400;  /* Normal (por defecto) */
font-weight: 500;  /* Medium */
font-weight: 600;  /* Semi Bold */
font-weight: 700;  /* Bold */
font-weight: 800;  /* Extra Bold */
font-weight: 900;  /* Black */
```

### Ejemplos Prácticos

```css
/* Palabras clave */
p {
  font-weight: normal; /* 400 */
}

strong {
  font-weight: bold; /* 700 */
}

/* Valores numéricos */
h1 {
  font-weight: 700; /* Negrita */
}

h2 {
  font-weight: 600; /* Semi-negrita */
}

.subtitle {
  font-weight: 500; /* Medium */
}

body {
  font-weight: 400; /* Normal */
}

.light-text {
  font-weight: 300; /* Ligero */
}
```

### Con Variables CSS

```css
:root {
  --font-weight-light: 300;
  --font-weight-normal: 400;
  --font-weight-medium: 500;
  --font-weight-semibold: 600;
  --font-weight-bold: 700;
}

h1 {
  font-weight: var(--font-weight-bold);
}

.card-title {
  font-weight: var(--font-weight-semibold);
}

p {
  font-weight: var(--font-weight-normal);
}
```

### Importante: Disponibilidad de Pesos

⚠️ **No todas las fuentes tienen todos los pesos disponibles.**

```css
/* Si la fuente solo tiene 400 y 700 */
body {
  font-family: Arial, sans-serif;
  font-weight: 500; /* Se renderizará como 400 o 700 (el más cercano) */
}
```

**Con Google Fonts, especifica los pesos que necesitas:**
```html
<!-- Solo carga los pesos que usarás -->
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
```

### Buenas Prácticas

✅ **BIEN:**
```css
/* Usa valores numéricos para más control */
h1 {
  font-weight: 700;
}

/* Define pesos como variables */
:root {
  --font-weight-heading: 600;
}
```

❌ **MAL:**
```css
/* No abuses de los pesos extremos */
p {
  font-weight: 900; /* Demasiado grueso para texto de lectura */
}
```

---

## 4️⃣ `font-style` - Estilo de Fuente

### Concepto

Controla si el texto es **normal, cursiva o oblicuo**. Principalmente se usa para énfasis o citas.

### Sintaxis

```css
selector {
  font-style: valor;
}
```

### Valores

- `normal`: Texto normal (por defecto)
- `italic`: Cursiva (versión diseñada de la fuente)
- `oblique`: Oblicuo (versión inclinada del texto normal)

### Ejemplos Prácticos

```css
/* Cursiva */
em {
  font-style: italic;
}

blockquote {
  font-style: italic;
}

/* Remover cursiva */
address {
  font-style: normal; /* <address> es cursiva por defecto */
}

/* Oblicuo (raro) */
.slanted {
  font-style: oblique;
}
```

### Diferencia: italic vs oblique

```css
/* Italic: usa la versión cursiva diseñada de la fuente */
.italic {
  font-style: italic;
}

/* Oblique: inclina el texto normal (si no hay versión cursiva) */
.oblique {
  font-style: oblique;
}
```

**En la práctica:** Casi siempre usarás `italic`. `oblique` es raro y solo se usa cuando la fuente no tiene versión cursiva.

### Casos de Uso

```css
/* Citas */
blockquote {
  font-style: italic;
  border-left: 4px solid #ccc;
  padding-left: 1rem;
}

/* Énfasis semántico */
em {
  font-style: italic;
}

/* Remover cursiva de elementos que la tienen por defecto */
cite {
  font-style: normal;
}
```

---

## 5️⃣ `line-height` - Altura de Línea

### Concepto

Controla el **espacio vertical entre líneas de texto**. Es crucial para la legibilidad. Piensa en ello como el "interlineado" en un procesador de textos.

### Sintaxis

```css
selector {
  line-height: valor;
}
```

### Valores

**Sin unidad (recomendado):**
```css
line-height: 1.5; /* 1.5 veces el tamaño de la fuente */
```

**Con unidad:**
```css
line-height: 24px;  /* Píxeles */
line-height: 1.5em; /* Em */
line-height: 150%;  /* Porcentaje */
```

### ¿Por Qué Sin Unidad es Mejor?

```css
/* CON unidad (problema de herencia) */
.parent {
  font-size: 16px;
  line-height: 24px; /* Fijo en 24px */
}

.child {
  font-size: 32px;
  /* Hereda 24px - ¡demasiado pequeño! */
}

/* SIN unidad (escala correctamente) */
.parent {
  font-size: 16px;
  line-height: 1.5; /* 24px (16 × 1.5) */
}

.child {
  font-size: 32px;
  line-height: 1.5; /* 48px (32 × 1.5) - ¡perfecto! */
}
```

### Ejemplos Prácticos

```css
/* Texto de lectura (párrafos) */
p {
  line-height: 1.6; /* Espacioso, fácil de leer */
}

/* Títulos */
h1, h2, h3 {
  line-height: 1.2; /* Más compacto */
}

/* Texto pequeño */
small {
  line-height: 1.4;
}

/* Botones (centrado vertical) */
button {
  line-height: 1;
}
```

### Reglas Generales

| Tipo de Texto | Line Height | Razón |
|---------------|-------------|-------|
| **Títulos grandes** | 1.1 - 1.3 | Evita espacio excesivo |
| **Texto de lectura** | 1.5 - 1.8 | Mejora legibilidad |
| **Texto pequeño** | 1.4 - 1.5 | Compensa tamaño reducido |
| **Botones/UI** | 1 - 1.2 | Control preciso de altura |

### Con Variables CSS

```css
:root {
  --line-height-none: 1;
  --line-height-tight: 1.25;
  --line-height-normal: 1.5;
  --line-height-relaxed: 1.75;
  --line-height-loose: 2;
}

h1 {
  line-height: var(--line-height-tight);
}

p {
  line-height: var(--line-height-normal);
}

.spacious-text {
  line-height: var(--line-height-relaxed);
}
```

### Buenas Prácticas

✅ **BIEN:**
```css
/* Sin unidad para escalabilidad */
body {
  line-height: 1.5;
}

/* Ajusta según el contexto */
h1 {
  line-height: 1.2;
}

p {
  line-height: 1.6;
}
```

❌ **MAL:**
```css
/* Con unidad fija (no escala) */
body {
  line-height: 24px;
}

/* Demasiado compacto para lectura */
p {
  line-height: 1;
}
```

---

## 6️⃣ `letter-spacing` - Espaciado entre Letras

### Concepto

Controla el **espacio horizontal entre caracteres** (también llamado "tracking" en diseño). Afecta la densidad visual del texto.

### Sintaxis

```css
selector {
  letter-spacing: valor;
}
```

### Valores

```css
letter-spacing: normal;      /* Por defecto (0) */
letter-spacing: 0.05em;      /* Más espacio */
letter-spacing: -0.02em;     /* Menos espacio */
letter-spacing: 2px;         /* Píxeles */
```

### Ejemplos Prácticos

```css
/* Títulos grandes (reducir espacio) */
h1 {
  font-size: 3rem;
  letter-spacing: -0.02em; /* Más compacto */
}

/* Texto en mayúsculas (aumentar espacio) */
.uppercase {
  text-transform: uppercase;
  letter-spacing: 0.1em; /* Más legible */
}

/* Subtítulos */
.subtitle {
  letter-spacing: 0.05em;
}

/* Texto normal (sin cambios) */
p {
  letter-spacing: normal;
}
```

### Reglas Generales

| Contexto | Letter Spacing | Razón |
|----------|----------------|-------|
| **Títulos grandes** | -0.02em a -0.05em | Evita que se vean espaciados |
| **Mayúsculas** | 0.05em a 0.15em | Mejora legibilidad |
| **Texto pequeño** | 0.01em a 0.03em | Compensa tamaño reducido |
| **Texto normal** | normal (0) | Diseño de la fuente es óptimo |

### Casos de Uso

```css
/* Etiquetas/badges en mayúsculas */
.badge {
  text-transform: uppercase;
  font-size: 0.75rem;
  letter-spacing: 0.1em;
  font-weight: 600;
}

/* Logo o marca */
.logo {
  font-size: 2rem;
  letter-spacing: -0.03em;
  font-weight: 700;
}

/* Navegación */
nav a {
  text-transform: uppercase;
  font-size: 0.875rem;
  letter-spacing: 0.05em;
}
```

### Con Variables CSS

```css
:root {
  --letter-spacing-tighter: -0.05em;
  --letter-spacing-tight: -0.025em;
  --letter-spacing-normal: 0;
  --letter-spacing-wide: 0.025em;
  --letter-spacing-wider: 0.05em;
  --letter-spacing-widest: 0.1em;
}

h1 {
  letter-spacing: var(--letter-spacing-tight);
}

.uppercase-label {
  letter-spacing: var(--letter-spacing-wider);
}
```

### Buenas Prácticas

✅ **BIEN:**
```css
/* Usa em para escalabilidad */
h1 {
  letter-spacing: -0.02em;
}

/* Aumenta espacio en mayúsculas */
.uppercase {
  text-transform: uppercase;
  letter-spacing: 0.1em;
}
```

❌ **MAL:**
```css
/* No exageres el espaciado */
p {
  letter-spacing: 0.5em; /* Demasiado espaciado */
}

/* No uses valores fijos grandes */
h1 {
  letter-spacing: 10px; /* No escala */
}
```

---

## 7️⃣ `text-align` - Alineación de Texto

### Concepto

Controla la **alineación horizontal** del texto dentro de su contenedor.

### Sintaxis

```css
selector {
  text-align: valor;
}
```

### Valores

- `left`: Alineado a la izquierda (por defecto en idiomas LTR)
- `right`: Alineado a la derecha
- `center`: Centrado
- `justify`: Justificado (alineado a ambos lados)
- `start`: Inicio del contenedor (según dirección del texto)
- `end`: Final del contenedor (según dirección del texto)

### Ejemplos Prácticos

```css
/* Izquierda (por defecto) */
p {
  text-align: left;
}

/* Centrado */
h1 {
  text-align: center;
}

.hero-title {
  text-align: center;
}

/* Derecha */
.price {
  text-align: right;
}

/* Justificado */
.article-text {
  text-align: justify;
}
```

### Casos de Uso

```css
/* Encabezado de página */
.page-header {
  text-align: center;
}

/* Precios en tabla */
.price-column {
  text-align: right;
}

/* Navegación */
nav {
  text-align: center;
}

/* Artículo de blog */
article p {
  text-align: left; /* Más legible que justify en web */
}
```

### Justify: Úsalo con Cuidado

⚠️ **Problema con `justify` en web:**
```css
/* Puede crear espacios irregulares */
p {
  text-align: justify; /* Puede verse mal en líneas cortas */
}
```

**Mejor con `text-align-last`:**
```css
p {
  text-align: justify;
  text-align-last: left; /* Última línea a la izquierda */
}
```

### Buenas Prácticas

✅ **BIEN:**
```css
/* Usa left para texto de lectura */
article p {
  text-align: left;
}

/* Usa center para títulos/heros */
.hero h1 {
  text-align: center;
}

/* Usa right para números/precios */
.price {
  text-align: right;
}
```

❌ **MAL:**
```css
/* No centres texto de lectura largo */
article p {
  text-align: center; /* Difícil de leer */
}

/* No justifiques en web (generalmente) */
p {
  text-align: justify; /* Espacios irregulares */
}
```

---

## 8️⃣ `text-decoration` - Decoración de Texto

### Concepto

Controla las **líneas decorativas** en el texto (subrayado, tachado, etc.).

### Sintaxis

```css
selector {
  text-decoration: line style color;
}
```

### Valores de `text-decoration-line`

- `none`: Sin decoración
- `underline`: Subrayado
- `overline`: Línea superior
- `line-through`: Tachado

### Ejemplos Prácticos

```css
/* Remover subrayado de enlaces */
a {
  text-decoration: none;
}

/* Subrayar al hover */
a:hover {
  text-decoration: underline;
}

/* Texto tachado */
.old-price {
  text-decoration: line-through;
}

/* Múltiples decoraciones */
.special {
  text-decoration: underline overline;
}
```

### Propiedades Individuales

```css
/* Línea */
text-decoration-line: underline;

/* Estilo */
text-decoration-style: solid;    /* Sólida */
text-decoration-style: double;   /* Doble */
text-decoration-style: dotted;   /* Punteada */
text-decoration-style: dashed;   /* Discontinua */
text-decoration-style: wavy;     /* Ondulada */

/* Color */
text-decoration-color: red;

/* Grosor */
text-decoration-thickness: 2px;
```

### Ejemplos Avanzados

```css
/* Subrayado personalizado */
a {
  text-decoration: underline;
  text-decoration-color: #3498db;
  text-decoration-thickness: 2px;
  text-decoration-style: solid;
}

/* Subrayado ondulado (error) */
.error {
  text-decoration: underline wavy red;
}

/* Precio tachado */
.old-price {
  text-decoration: line-through;
  color: #999;
}

.new-price {
  color: #e74c3c;
  font-weight: 600;
}
```

### Casos de Uso

```css
/* Enlaces sin subrayado por defecto */
a {
  text-decoration: none;
  color: #3498db;
}

/* Subrayado al hover */
a:hover {
  text-decoration: underline;
}

/* Precio original tachado */
.product-price del {
  text-decoration: line-through;
  color: #999;
}

/* Énfasis con subrayado */
.highlight {
  text-decoration: underline;
  text-decoration-color: #f39c12;
  text-decoration-thickness: 3px;
}
```

### Buenas Prácticas

✅ **BIEN:**
```css
/* Indica enlaces de alguna forma */
a {
  text-decoration: none;
  color: blue;
}

a:hover {
  text-decoration: underline;
}

/* Usa line-through para precios viejos */
.old-price {
  text-decoration: line-through;
}
```

❌ **MAL:**
```css
/* No quites el subrayado sin otra indicación visual */
a {
  text-decoration: none;
  color: inherit; /* Indistinguible del texto normal */
}
```

---

## 9️⃣ `text-transform` - Transformación de Texto

### Concepto

Controla la **capitalización** del texto sin cambiar el HTML.

### Sintaxis

```css
selector {
  text-transform: valor;
}
```

### Valores

- `none`: Sin transformación (por defecto)
- `uppercase`: TODAS MAYÚSCULAS
- `lowercase`: todas minúsculas
- `capitalize`: Primera Letra De Cada Palabra

### Ejemplos Prácticos

```css
/* Mayúsculas */
.button {
  text-transform: uppercase;
}

nav a {
  text-transform: uppercase;
}

/* Minúsculas */
.email {
  text-transform: lowercase;
}

/* Capitalizar */
.title {
  text-transform: capitalize;
}

/* Sin transformación */
.normal {
  text-transform: none;
}
```

### Casos de Uso

```css
/* Navegación */
nav a {
  text-transform: uppercase;
  font-size: 0.875rem;
  letter-spacing: 0.05em;
  font-weight: 600;
}

/* Badges/etiquetas */
.badge {
  text-transform: uppercase;
  font-size: 0.75rem;
  letter-spacing: 0.1em;
}

/* Nombres propios */
.author-name {
  text-transform: capitalize;
}

/* Emails (siempre minúsculas) */
.email-display {
  text-transform: lowercase;
}
```

### Importante: Combinar con `letter-spacing`

```css
/* Mayúsculas SIEMPRE con letter-spacing */
.uppercase-text {
  text-transform: uppercase;
  letter-spacing: 0.1em; /* Mejora legibilidad */
}
```

### Buenas Prácticas

✅ **BIEN:**
```css
/* Usa uppercase con letter-spacing */
.label {
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

/* Usa lowercase para emails */
.email {
  text-transform: lowercase;
}
```

❌ **MAL:**
```css
/* No uses uppercase sin letter-spacing */
.text {
  text-transform: uppercase; /* Se ve apretado */
}

/* No uses capitalize en todo el texto */
p {
  text-transform: capitalize; /* Se Ve Raro En Párrafos */
}
```

---

## 🔟 `color` - Color de Texto

### Concepto

Define el **color** del texto. Es una de las propiedades más básicas pero esenciales.

### Sintaxis

```css
selector {
  color: valor;
}
```

### Formatos de Color

```css
/* Nombre de color */
color: red;
color: dodgerblue;

/* Hexadecimal */
color: #333333;
color: #3498db;

/* RGB */
color: rgb(52, 152, 219);
color: rgba(52, 152, 219, 0.8); /* Con opacidad */

/* HSL (recomendado) */
color: hsl(204, 70%, 53%);
color: hsla(204, 70%, 53%, 0.8); /* Con opacidad */
```

### Ejemplos Prácticos

```css
/* Texto principal */
body {
  color: #333333;
}

/* Texto secundario */
.secondary-text {
  color: #6c757d;
}

/* Texto muted/deshabilitado */
.muted {
  color: #adb5bd;
}

/* Enlaces */
a {
  color: #3498db;
}

a:hover {
  color: #2980b9;
}

/* Texto de error */
.error {
  color: #e74c3c;
}

/* Texto de éxito */
.success {
  color: #28a745;
}
```

### Con Variables CSS

```css
:root {
  --color-text-primary: #212529;
  --color-text-secondary: #6c757d;
  --color-text-muted: #adb5bd;
  --color-link: #3498db;
  --color-link-hover: #2980b9;
  --color-success: #28a745;
  --color-danger: #e74c3c;
}

body {
  color: var(--color-text-primary);
}

.subtitle {
  color: var(--color-text-secondary);
}

a {
  color: var(--color-link);
}

a:hover {
  color: var(--color-link-hover);
}
```

### Contraste y Accesibilidad

⚠️ **Importante:** Asegura suficiente contraste entre texto y fondo.

**Ratios mínimos (WCAG):**
- Texto normal: 4.5:1
- Texto grande (18px+ o 14px+ bold): 3:1

```css
/* ✅ BIEN: Buen contraste */
body {
  background-color: #ffffff;
  color: #212529; /* Ratio: 16.1:1 */
}

/* ❌ MAL: Poco contraste */
body {
  background-color: #ffffff;
  color: #cccccc; /* Ratio: 1.6:1 - Ilegible */
}
```

### Buenas Prácticas

✅ **BIEN:**
```css
/* Define colores como variables */
:root {
  --color-text: #333;
}

body {
  color: var(--color-text);
}

/* Usa colores semánticos */
.error {
  color: var(--color-danger);
}
```

❌ **MAL:**
```css
/* No uses colores muy claros en fondo blanco */
p {
  color: #ddd; /* Poco contraste */
}

/* No uses colores puros sin considerar legibilidad */
body {
  background: yellow;
  color: lime; /* Horrible */
}
```

---

## 📋 Resumen de Propiedades

| Propiedad | Qué Controla | Valor Recomendado | Uso Principal |
|-----------|--------------|-------------------|---------------|
| `font-family` | Tipo de letra | System fonts o Google Fonts | Todo el sitio |
| `font-size` | Tamaño del texto | `rem` (1rem = 16px) | Jerarquía visual |
| `font-weight` | Grosor del texto | 400 (normal), 600-700 (títulos) | Énfasis |
| `font-style` | Cursiva/normal | `italic` para énfasis | Citas, énfasis |
| `line-height` | Espacio entre líneas | 1.5-1.6 (texto), 1.2 (títulos) | Legibilidad |
| `letter-spacing` | Espacio entre letras | 0.05em-0.1em (mayúsculas) | Mayúsculas, títulos |
| `text-align` | Alineación horizontal | `left` (lectura), `center` (títulos) | Diseño |
| `text-decoration` | Subrayado/tachado | `none` (enlaces), `underline` (hover) | Enlaces, precios |
| `text-transform` | Mayúsculas/minúsculas | `uppercase` (navegación) | UI, etiquetas |
| `color` | Color del texto | HSL o variables CSS | Todo el sitio |

---

## 🎨 Ejemplo Completo: Sistema Tipográfico

```css
/* ===== VARIABLES ===== */
:root {
  /* Familias */
  --font-family-base: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  --font-family-heading: "Georgia", serif;
  
  /* Tamaños */
  --font-size-xs: 0.75rem;
  --font-size-sm: 0.875rem;
  --font-size-base: 1rem;
  --font-size-lg: 1.125rem;
  --font-size-xl: 1.25rem;
  --font-size-2xl: 1.5rem;
  --font-size-3xl: 1.875rem;
  --font-size-4xl: 2.25rem;
  
  /* Pesos */
  --font-weight-normal: 400;
  --font-weight-medium: 500;
  --font-weight-semibold: 600;
  --font-weight-bold: 700;
  
  /* Line heights */
  --line-height-tight: 1.25;
  --line-height-normal: 1.5;
  --line-height-relaxed: 1.75;
  
  /* Letter spacing */
  --letter-spacing-tight: -0.025em;
  --letter-spacing-normal: 0;
  --letter-spacing-wide: 0.05em;
  
  /* Colores */
  --color-text-primary: #212529;
  --color-text-secondary: #6c757d;
  --color-text-muted: #adb5bd;
  --color-link: #3498db;
  --color-link-hover: #2980b9;
}

/* ===== ESTILOS BASE ===== */
body {
  font-family: var(--font-family-base);
  font-size: var(--font-size-base);
  font-weight: var(--font-weight-normal);
  line-height: var(--line-height-normal);
  color: var(--color-text-primary);
}

/* ===== HEADINGS ===== */
h1, h2, h3, h4, h5, h6 {
  font-family: var(--font-family-heading);
  font-weight: var(--font-weight-bold);
  line-height: var(--line-height-tight);
  letter-spacing: var(--letter-spacing-tight);
  margin-top: 0;
  margin-bottom: 0.5em;
}

h1 {
  font-size: var(--font-size-4xl);
}

h2 {
  font-size: var(--font-size-3xl);
}

h3 {
  font-size: var(--font-size-2xl);
}

h4 {
  font-size: var(--font-size-xl);
}

/* ===== PÁRRAFOS ===== */
p {
  margin-top: 0;
  margin-bottom: 1em;
}

.lead {
  font-size: var(--font-size-lg);
  font-weight: var(--font-weight-normal);
  line-height: var(--line-height-relaxed);
}

.small-text {
  font-size: var(--font-size-sm);
  color: var(--color-text-secondary);
}

/* ===== ENLACES ===== */
a {
  color: var(--color-link);
  text-decoration: none;
}

a:hover {
  color: var(--color-link-hover);
  text-decoration: underline;
}

/* ===== COMPONENTES ===== */
.button {
  font-family: var(--font-family-base);
  font-size: var(--font-size-sm);
  font-weight: var(--font-weight-semibold);
  text-transform: uppercase;
  letter-spacing: var(--letter-spacing-wide);
  text-align: center;
}

.badge {
  font-size: var(--font-size-xs);
  font-weight: var(--font-weight-semibold);
  text-transform: uppercase;
  letter-spacing: var(--letter-spacing-wide);
}

.quote {
  font-style: italic;
  font-size: var(--font-size-lg);
  line-height: var(--line-height-relaxed);
  color: var(--color-text-secondary);
}
```

---

## ✅ Checklist de Buenas Prácticas

**Font Family:**
- [ ] Incluye fuentes de respaldo (font stack)
- [ ] Termina con tipo genérico (`serif`, `sans-serif`)
- [ ] Limita a 2-3 familias de fuentes

**Font Size:**
- [ ] Usa `rem` para escalabilidad
- [ ] Define tamaño base en `html` (16px)
- [ ] Crea escala tipográfica consistente

**Font Weight:**
- [ ] Usa valores numéricos (400, 600, 700)
- [ ] Solo carga pesos que necesitas (Google Fonts)
- [ ] Define pesos como variables CSS

**Line Height:**
- [ ] Usa valores sin unidad (1.5, 1.6)
- [ ] 1.5-1.8 para texto de lectura
- [ ] 1.1-1.3 para títulos

**Letter Spacing:**
- [ ] Usa `em` para escalabilidad
- [ ] Aumenta en texto en mayúsculas (0.05em-0.1em)
- [ ] Reduce en títulos grandes (-0.02em a -0.05em)

**Color:**
- [ ] Define colores como variables CSS
- [ ] Asegura contraste suficiente (4.5:1 mínimo)
- [ ] Usa colores semánticos (success, danger, etc.)

**General:**
- [ ] Mantén consistencia en todo el sitio
- [ ] Prueba legibilidad en diferentes dispositivos
- [ ] Considera accesibilidad (contraste, tamaños)

---

## 🎯 Ejercicio Práctico

Crea un sistema tipográfico completo para ComicTracker que incluya:

1. **Variables CSS** para:
   - 2 familias de fuentes (base y headings)
   - Escala de 6 tamaños
   - 4 pesos de fuente
   - 3 line-heights
   - 3 letter-spacings
   - 5 colores de texto

2. **Estilos para:**
   - Body (fuente base)
   - Headings (h1-h4)
   - Párrafos normales y lead
   - Enlaces (normal y hover)
   - Componentes: botones, badges, citas

3. **Requisitos:**
   - Todo usando variables CSS
   - Valores en `rem` para tamaños
   - Line-height sin unidad
   - Buen contraste de colores
   - Código organizado y comentado

---

## 📚 Recursos Adicionales

- **MDN Web Docs - CSS Fonts:** Documentación completa
- **Type Scale:** Calculadora de escalas tipográficas
- **Google Fonts:** Biblioteca de fuentes gratuitas
- **WebAIM Contrast Checker:** Verifica contraste de colores
- **Modular Scale:** Generador de escalas armónicas

---

**¡Recuerda!** La tipografía es el 95% del diseño web. Dominar estas propiedades te permitirá crear interfaces legibles, atractivas y profesionales. 📝✨
