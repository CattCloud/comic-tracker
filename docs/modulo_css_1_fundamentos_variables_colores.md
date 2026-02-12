# MÓDULO CSS-1: Variables, Colores y Tipografía

## 📚 Introducción

**CSS (Cascading Style Sheets)** es el lenguaje que da estilo y diseño a las páginas web. Si HTML es la estructura de una casa, CSS es la decoración: colores, fuentes, espaciado, diseño visual.

**Analogía:** HTML dice "esto es un título", CSS dice "este título es azul, grande y está centrado".

En este módulo aprenderás tres fundamentos esenciales:
1. **Variables CSS**: Reutilizar valores y mantener consistencia
2. **Colores y Tipografía**: Crear paletas y jerarquías visuales
3. **Reset/Normalize**: Partir de una base consistente entre navegadores

---

## 1️⃣ Variables CSS (Custom Properties)

Las **variables CSS** (también llamadas Custom Properties) permiten almacenar valores que puedes reutilizar en todo tu CSS.

### 1.1 ¿Por Qué Usar Variables?

**Sin variables (❌ Problema):**
```css
.header {
  background-color: #3498db;
}

.button {
  background-color: #3498db;
}

.link {
  color: #3498db;
}

/* Si quieres cambiar el azul, debes editar 3 lugares */
```

**Con variables (✅ Solución):**
```css
:root {
  --color-primary: #3498db;
}

.header {
  background-color: var(--color-primary);
}

.button {
  background-color: var(--color-primary);
}

.link {
  color: var(--color-primary);
}

/* Cambias una vez, afecta todo */
```

---

### 1.2 Sintaxis Básica

#### **Declarar una variable:**
```css
:root {
  --nombre-variable: valor;
}
```

- `:root` es el selector más común (afecta todo el documento)
- Los nombres **deben** empezar con `--`
- Son **case-sensitive** (`--Color` ≠ `--color`)

#### **Usar una variable:**
```css
.elemento {
  propiedad: var(--nombre-variable);
}
```

**Ejemplo completo:**
```css
:root {
  --color-primary: #e74c3c;
  --spacing-small: 8px;
  --font-size-large: 24px;
}

.card {
  color: var(--color-primary);
  padding: var(--spacing-small);
  font-size: var(--font-size-large);
}
```

---

### 1.3 Scope (Alcance) de Variables

Las variables se heredan en cascada, como cualquier propiedad CSS.

```css
:root {
  --color: blue;
}

.container {
  --color: red; /* Sobrescribe dentro de .container */
}

.global {
  color: var(--color); /* Azul */
}

.container .local {
  color: var(--color); /* Rojo (hereda de .container) */
}
```

**Ejemplo práctico - Temas:**
```css
/* Tema claro (por defecto) */
:root {
  --bg-color: #ffffff;
  --text-color: #333333;
}

/* Tema oscuro */
.dark-theme {
  --bg-color: #1a1a1a;
  --text-color: #f0f0f0;
}

body {
  background-color: var(--bg-color);
  color: var(--text-color);
}
```

---

### 1.4 Valores por Defecto (Fallback)

Puedes proporcionar un valor de respaldo si la variable no está definida:

```css
.elemento {
  color: var(--color-primary, #000000);
  /*                         ^^^^^^^^
                             Fallback: si --color-primary no existe, usa negro */
}
```

**Ejemplo con múltiples fallbacks:**
```css
.elemento {
  color: var(--color-brand, var(--color-primary, #333));
  /* Intenta: --color-brand → --color-primary → #333 */
}
```

---

### 1.5 Sistema de Diseño con Variables

Un patrón común es crear un **sistema de tokens de diseño**:

```css
:root {
  /* ===== COLORES ===== */
  /* Paleta base */
  --color-primary: #3498db;
  --color-secondary: #2ecc71;
  --color-accent: #e74c3c;
  
  /* Grises */
  --color-gray-100: #f8f9fa;
  --color-gray-200: #e9ecef;
  --color-gray-300: #dee2e6;
  --color-gray-700: #495057;
  --color-gray-900: #212529;
  
  /* Semánticos */
  --color-success: #28a745;
  --color-warning: #ffc107;
  --color-danger: #dc3545;
  --color-info: #17a2b8;
  
  /* Texto */
  --color-text-primary: #212529;
  --color-text-secondary: #6c757d;
  --color-text-muted: #adb5bd;
  
  /* Fondos */
  --color-bg-primary: #ffffff;
  --color-bg-secondary: #f8f9fa;
  
  /* ===== ESPACIADO ===== */
  --spacing-xs: 4px;
  --spacing-sm: 8px;
  --spacing-md: 16px;
  --spacing-lg: 24px;
  --spacing-xl: 32px;
  --spacing-2xl: 48px;
  
  /* ===== TIPOGRAFÍA ===== */
  /* Familias */
  --font-family-base: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  --font-family-heading: "Georgia", serif;
  --font-family-mono: "Courier New", monospace;
  
  /* Tamaños */
  --font-size-xs: 12px;
  --font-size-sm: 14px;
  --font-size-base: 16px;
  --font-size-lg: 18px;
  --font-size-xl: 20px;
  --font-size-2xl: 24px;
  --font-size-3xl: 30px;
  --font-size-4xl: 36px;
  
  /* Pesos */
  --font-weight-normal: 400;
  --font-weight-medium: 500;
  --font-weight-semibold: 600;
  --font-weight-bold: 700;
  
  /* Alturas de línea */
  --line-height-tight: 1.25;
  --line-height-normal: 1.5;
  --line-height-relaxed: 1.75;
  
  /* ===== BORDES ===== */
  --border-radius-sm: 4px;
  --border-radius-md: 8px;
  --border-radius-lg: 12px;
  --border-radius-full: 9999px;
  
  --border-width-thin: 1px;
  --border-width-medium: 2px;
  --border-width-thick: 4px;
  
  /* ===== SOMBRAS ===== */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 10px 15px rgba(0, 0, 0, 0.1);
  --shadow-xl: 0 20px 25px rgba(0, 0, 0, 0.15);
  
  /* ===== TRANSICIONES ===== */
  --transition-fast: 150ms ease-in-out;
  --transition-base: 250ms ease-in-out;
  --transition-slow: 350ms ease-in-out;
  
  /* ===== Z-INDEX ===== */
  --z-dropdown: 1000;
  --z-sticky: 1020;
  --z-fixed: 1030;
  --z-modal-backdrop: 1040;
  --z-modal: 1050;
  --z-tooltip: 1070;
}
```

**Uso del sistema:**
```css
.card {
  background-color: var(--color-bg-primary);
  padding: var(--spacing-md);
  border-radius: var(--border-radius-md);
  box-shadow: var(--shadow-md);
  transition: box-shadow var(--transition-base);
}

.card:hover {
  box-shadow: var(--shadow-lg);
}

.button-primary {
  background-color: var(--color-primary);
  color: white;
  padding: var(--spacing-sm) var(--spacing-md);
  border-radius: var(--border-radius-sm);
  font-weight: var(--font-weight-semibold);
}
```

---

### 1.6 Variables con Calc()

Puedes combinar variables con cálculos:

```css
:root {
  --spacing-base: 8px;
}

.elemento {
  margin: calc(var(--spacing-base) * 2); /* 16px */
  padding: calc(var(--spacing-base) / 2); /* 4px */
}
```

**Ejemplo - Escala de espaciado:**
```css
:root {
  --spacing-unit: 8px;
  --spacing-1: calc(var(--spacing-unit) * 1); /* 8px */
  --spacing-2: calc(var(--spacing-unit) * 2); /* 16px */
  --spacing-3: calc(var(--spacing-unit) * 3); /* 24px */
  --spacing-4: calc(var(--spacing-unit) * 4); /* 32px */
}
```

---

### 1.7 Manipulación con JavaScript

Las variables CSS pueden modificarse dinámicamente:

```javascript
// Leer variable
const root = document.documentElement;
const primaryColor = getComputedStyle(root).getPropertyValue('--color-primary');

// Cambiar variable
root.style.setProperty('--color-primary', '#e74c3c');
```

**Ejemplo - Cambio de tema:**
```javascript
function toggleTheme() {
  const root = document.documentElement;
  const isDark = root.classList.contains('dark-theme');
  
  if (isDark) {
    root.classList.remove('dark-theme');
  } else {
    root.classList.add('dark-theme');
  }
}
```

---

## 2️⃣ Colores y Tipografía

### 2.1 Formatos de Color en CSS

CSS soporta múltiples formas de especificar colores:

#### **1. Nombres de colores**
```css
.elemento {
  color: red;
  background-color: dodgerblue;
  border-color: transparent;
}
```

**Limitaciones:** Solo 140 colores predefinidos, nombres poco descriptivos.

#### **2. Hexadecimal (Hex)**
```css
.elemento {
  color: #ff0000;        /* Rojo */
  color: #f00;           /* Rojo (forma corta) */
  color: #ff000080;      /* Rojo con 50% opacidad (8 dígitos) */
}
```

**Formato:** `#RRGGBB` o `#RGB`
- RR = Rojo (00-FF)
- GG = Verde (00-FF)
- BB = Azul (00-FF)

**Ejemplos:**
```css
--color-black: #000000;   /* Negro */
--color-white: #ffffff;   /* Blanco */
--color-gray: #808080;    /* Gris */
--color-blue: #3498db;    /* Azul */
```

#### **3. RGB / RGBA**
```css
.elemento {
  color: rgb(255, 0, 0);           /* Rojo */
  color: rgba(255, 0, 0, 0.5);     /* Rojo con 50% opacidad */
  color: rgb(255 0 0 / 0.5);       /* Sintaxis moderna */
}
```

**Formato:** `rgb(red, green, blue)` o `rgba(red, green, blue, alpha)`
- Valores: 0-255 o 0%-100%
- Alpha: 0 (transparente) - 1 (opaco)

#### **4. HSL / HSLA (Recomendado para diseño)**
```css
.elemento {
  color: hsl(0, 100%, 50%);        /* Rojo */
  color: hsla(0, 100%, 50%, 0.5);  /* Rojo con 50% opacidad */
  color: hsl(0 100% 50% / 0.5);    /* Sintaxis moderna */
}
```

**Formato:** `hsl(hue, saturation, lightness)`
- **Hue (Matiz):** 0-360 (rueda de color)
  - 0° = Rojo
  - 120° = Verde
  - 240° = Azul
- **Saturation (Saturación):** 0%-100% (gris a color puro)
- **Lightness (Luminosidad):** 0%-100% (negro a blanco)

**Ventaja de HSL:** Fácil crear variaciones de un color.

```css
:root {
  --hue-primary: 210; /* Azul */
  
  /* Variaciones del mismo color */
  --color-primary-dark: hsl(var(--hue-primary), 70%, 40%);
  --color-primary: hsl(var(--hue-primary), 70%, 50%);
  --color-primary-light: hsl(var(--hue-primary), 70%, 60%);
  --color-primary-lighter: hsl(var(--hue-primary), 70%, 90%);
}
```

---

### 2.2 Creación de Paletas de Colores

#### **Patrón 1: Color primario + variaciones**

```css
:root {
  /* Color base */
  --primary-hue: 210;
  --primary-saturation: 70%;
  
  /* Escala de luminosidad */
  --color-primary-50: hsl(var(--primary-hue), var(--primary-saturation), 95%);
  --color-primary-100: hsl(var(--primary-hue), var(--primary-saturation), 90%);
  --color-primary-200: hsl(var(--primary-hue), var(--primary-saturation), 80%);
  --color-primary-300: hsl(var(--primary-hue), var(--primary-saturation), 70%);
  --color-primary-400: hsl(var(--primary-hue), var(--primary-saturation), 60%);
  --color-primary-500: hsl(var(--primary-hue), var(--primary-saturation), 50%); /* Base */
  --color-primary-600: hsl(var(--primary-hue), var(--primary-saturation), 40%);
  --color-primary-700: hsl(var(--primary-hue), var(--primary-saturation), 30%);
  --color-primary-800: hsl(var(--primary-hue), var(--primary-saturation), 20%);
  --color-primary-900: hsl(var(--primary-hue), var(--primary-saturation), 10%);
}
```

#### **Patrón 2: Escala de grises**

```css
:root {
  --color-gray-50: #f9fafb;
  --color-gray-100: #f3f4f6;
  --color-gray-200: #e5e7eb;
  --color-gray-300: #d1d5db;
  --color-gray-400: #9ca3af;
  --color-gray-500: #6b7280;
  --color-gray-600: #4b5563;
  --color-gray-700: #374151;
  --color-gray-800: #1f2937;
  --color-gray-900: #111827;
}
```

#### **Patrón 3: Colores semánticos**

```css
:root {
  /* Estados */
  --color-success: #10b981;      /* Verde */
  --color-success-light: #d1fae5;
  --color-success-dark: #065f46;
  
  --color-warning: #f59e0b;      /* Naranja */
  --color-warning-light: #fef3c7;
  --color-warning-dark: #92400e;
  
  --color-danger: #ef4444;       /* Rojo */
  --color-danger-light: #fee2e2;
  --color-danger-dark: #991b1b;
  
  --color-info: #3b82f6;         /* Azul */
  --color-info-light: #dbeafe;
  --color-info-dark: #1e3a8a;
}
```

---

### 2.3 Tipografía - Familias de Fuentes

#### **Font Stacks (Pilas de fuentes)**

Siempre proporciona fuentes de respaldo:

```css
body {
  font-family: "Fuente Preferida", "Fuente Respaldo", tipo-genérico;
}
```

**Tipos genéricos:**
- `serif`: Con serifas (Georgia, Times)
- `sans-serif`: Sin serifas (Arial, Helvetica)
- `monospace`: Ancho fijo (Courier, Consolas)
- `cursive`: Cursiva/script
- `fantasy`: Decorativa

#### **System Font Stack (Fuentes del sistema)**

Usa las fuentes nativas del sistema operativo para mejor rendimiento:

```css
:root {
  --font-family-system: -apple-system, BlinkMacSystemFont, "Segoe UI", 
                        Roboto, "Helvetica Neue", Arial, sans-serif;
}

body {
  font-family: var(--font-family-system);
}
```

**Ventajas:**
- Carga instantánea (no descarga fuentes)
- Apariencia nativa del SO
- Mejor rendimiento

#### **Google Fonts**

```html
<!-- En el HTML -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
```

```css
/* En el CSS */
:root {
  --font-family-base: 'Inter', sans-serif;
}

body {
  font-family: var(--font-family-base);
}
```

**Buenas prácticas:**
- Limita a 2-3 familias de fuentes
- Carga solo los pesos que necesitas
- Usa `font-display: swap` para evitar FOIT (Flash of Invisible Text)

---

### 2.4 Escala Tipográfica

Una escala consistente mejora la jerarquía visual:

#### **Escala basada en ratio (1.25 - Mayor Tercera)**

```css
:root {
  --font-size-base: 16px;
  --ratio: 1.25;
  
  --font-size-xs: calc(var(--font-size-base) / var(--ratio) / var(--ratio));   /* 10.24px */
  --font-size-sm: calc(var(--font-size-base) / var(--ratio));                  /* 12.8px */
  --font-size-base: 16px;                                                       /* 16px */
  --font-size-lg: calc(var(--font-size-base) * var(--ratio));                  /* 20px */
  --font-size-xl: calc(var(--font-size-base) * var(--ratio) * var(--ratio));   /* 25px */
  --font-size-2xl: calc(var(--font-size-xl) * var(--ratio));                   /* 31.25px */
  --font-size-3xl: calc(var(--font-size-2xl) * var(--ratio));                  /* 39.06px */
  --font-size-4xl: calc(var(--font-size-3xl) * var(--ratio));                  /* 48.83px */
}
```

#### **Escala fija (más simple)**

```css
:root {
  --font-size-xs: 12px;
  --font-size-sm: 14px;
  --font-size-base: 16px;
  --font-size-lg: 18px;
  --font-size-xl: 20px;
  --font-size-2xl: 24px;
  --font-size-3xl: 30px;
  --font-size-4xl: 36px;
  --font-size-5xl: 48px;
  --font-size-6xl: 60px;
}
```

---

### 2.5 Pesos de Fuente (Font Weight)

```css
:root {
  --font-weight-thin: 100;
  --font-weight-extralight: 200;
  --font-weight-light: 300;
  --font-weight-normal: 400;      /* Por defecto */
  --font-weight-medium: 500;
  --font-weight-semibold: 600;
  --font-weight-bold: 700;        /* Negrita */
  --font-weight-extrabold: 800;
  --font-weight-black: 900;
}
```

**Uso:**
```css
h1 {
  font-weight: var(--font-weight-bold);
}

.subtitle {
  font-weight: var(--font-weight-medium);
}

body {
  font-weight: var(--font-weight-normal);
}
```

---

### 2.6 Altura de Línea (Line Height)

Controla el espacio vertical entre líneas de texto:

```css
:root {
  --line-height-none: 1;
  --line-height-tight: 1.25;
  --line-height-snug: 1.375;
  --line-height-normal: 1.5;      /* Recomendado para texto */
  --line-height-relaxed: 1.625;
  --line-height-loose: 2;
}
```

**Reglas generales:**
- **Títulos:** 1.1 - 1.3 (tight)
- **Texto de lectura:** 1.5 - 1.75 (normal/relaxed)
- **Texto pequeño:** 1.4 - 1.5

```css
h1, h2, h3 {
  line-height: var(--line-height-tight);
}

p, li {
  line-height: var(--line-height-normal);
}
```

---

### 2.7 Espaciado de Letras (Letter Spacing)

```css
:root {
  --letter-spacing-tighter: -0.05em;
  --letter-spacing-tight: -0.025em;
  --letter-spacing-normal: 0;
  --letter-spacing-wide: 0.025em;
  --letter-spacing-wider: 0.05em;
  --letter-spacing-widest: 0.1em;
}
```

**Uso:**
```css
h1 {
  letter-spacing: var(--letter-spacing-tight); /* Títulos grandes */
}

.uppercase-label {
  text-transform: uppercase;
  letter-spacing: var(--letter-spacing-wide); /* Mayúsculas necesitan más espacio */
}
```

---

### 2.8 Ejemplo Completo - Sistema Tipográfico

```css
:root {
  /* Familias */
  --font-family-base: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  --font-family-heading: "Georgia", "Times New Roman", serif;
  
  /* Tamaños */
  --font-size-xs: 12px;
  --font-size-sm: 14px;
  --font-size-base: 16px;
  --font-size-lg: 18px;
  --font-size-xl: 20px;
  --font-size-2xl: 24px;
  --font-size-3xl: 30px;
  --font-size-4xl: 36px;
  
  /* Pesos */
  --font-weight-normal: 400;
  --font-weight-medium: 500;
  --font-weight-semibold: 600;
  --font-weight-bold: 700;
  
  /* Alturas de línea */
  --line-height-tight: 1.25;
  --line-height-normal: 1.5;
  --line-height-relaxed: 1.75;
}

/* Aplicación */
body {
  font-family: var(--font-family-base);
  font-size: var(--font-size-base);
  font-weight: var(--font-weight-normal);
  line-height: var(--line-height-normal);
}

h1 {
  font-family: var(--font-family-heading);
  font-size: var(--font-size-4xl);
  font-weight: var(--font-weight-bold);
  line-height: var(--line-height-tight);
}

h2 {
  font-family: var(--font-family-heading);
  font-size: var(--font-size-3xl);
  font-weight: var(--font-weight-semibold);
  line-height: var(--line-height-tight);
}

.small-text {
  font-size: var(--font-size-sm);
  color: var(--color-text-secondary);
}
```

---

## 3️⃣ Reset/Normalize CSS

Los navegadores aplican estilos por defecto diferentes. **Reset** y **Normalize** son técnicas para crear una base consistente.

### 3.1 ¿Cuál es la Diferencia?

| Enfoque | Reset CSS | Normalize CSS |
|---------|-----------|---------------|
| **Filosofía** | Elimina TODOS los estilos | Preserva estilos útiles |
| **Resultado** | Tabla rasa (todo igual) | Base consistente y sensata |
| **Tamaño** | Más pequeño | Más grande |
| **Uso** | Cuando quieres control total | Cuando quieres una base razonable |

---

### 3.2 Reset CSS Básico

Elimina márgenes, paddings y estilos por defecto:

```css
/* Reset CSS básico */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 16px;
}

body {
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

img, picture, video, canvas, svg {
  display: block;
  max-width: 100%;
}

input, button, textarea, select {
  font: inherit;
}

p, h1, h2, h3, h4, h5, h6 {
  overflow-wrap: break-word;
}
```

---

### 3.3 Reset CSS Moderno (Recomendado)

Basado en las mejores prácticas actuales:

```css
/* ===== RESET CSS MODERNO ===== */

/* 1. Box-sizing universal */
*,
*::before,
*::after {
  box-sizing: border-box;
}

/* 2. Eliminar márgenes por defecto */
* {
  margin: 0;
  padding: 0;
}

/* 3. Configuración del documento */
html {
  /* Permitir scroll suave */
  scroll-behavior: smooth;
  
  /* Tamaño base de fuente */
  font-size: 16px;
}

/* 4. Configuración del body */
body {
  /* Altura mínima de viewport */
  min-height: 100vh;
  
  /* Altura de línea legible */
  line-height: 1.5;
  
  /* Suavizado de fuentes */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  /* Renderizado de texto optimizado */
  text-rendering: optimizeSpeed;
}

/* 5. Medios (imágenes, videos) */
img,
picture,
video,
canvas,
svg {
  /* Bloque para evitar espacio extra */
  display: block;
  
  /* Responsive por defecto */
  max-width: 100%;
  height: auto;
}

/* 6. Formularios heredan tipografía */
input,
button,
textarea,
select {
  font: inherit;
  color: inherit;
}

/* 7. Eliminar estilos de botón */
button {
  background: none;
  border: none;
  cursor: pointer;
}

/* 8. Eliminar estilos de lista */
ul[role="list"],
ol[role="list"] {
  list-style: none;
}

/* 9. Prevenir desbordamiento de texto */
p,
h1,
h2,
h3,
h4,
h5,
h6 {
  overflow-wrap: break-word;
}

/* 10. Mejorar legibilidad de enlaces */
a {
  text-decoration-skip-ink: auto;
}

/* 11. Eliminar animaciones para usuarios que las prefieren reducidas */
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

---

### 3.4 Normalize CSS (Alternativa)

Si prefieres **Normalize.css**, puedes incluirlo desde un CDN:

```html
<!-- En el HTML, antes de tu CSS -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/normalize/8.0.1/normalize.min.css">
```

O descargarlo e incluirlo localmente:

```html
<link rel="stylesheet" href="css/normalize.css">
<link rel="stylesheet" href="css/styles.css">
```

---

### 3.5 Reset + Base Styles (Patrón Recomendado)

Combina un reset con estilos base para tu proyecto:

```css
/* ===== 1. RESET ===== */
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
}

body {
  min-height: 100vh;
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
}

img, picture, video, canvas, svg {
  display: block;
  max-width: 100%;
}

input, button, textarea, select {
  font: inherit;
}

/* ===== 2. VARIABLES ===== */
:root {
  --color-primary: #3498db;
  --color-text: #333333;
  --color-bg: #ffffff;
  
  --font-family-base: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  --font-size-base: 16px;
  
  --spacing-sm: 8px;
  --spacing-md: 16px;
  --spacing-lg: 24px;
}

/* ===== 3. ESTILOS BASE ===== */
body {
  font-family: var(--font-family-base);
  font-size: var(--font-size-base);
  color: var(--color-text);
  background-color: var(--color-bg);
}

h1, h2, h3, h4, h5, h6 {
  font-weight: 600;
  line-height: 1.25;
  margin-bottom: var(--spacing-sm);
}

p {
  margin-bottom: var(--spacing-md);
}

a {
  color: var(--color-primary);
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

ul, ol {
  padding-left: var(--spacing-lg);
  margin-bottom: var(--spacing-md);
}
```

---

## 📋 Estructura de Archivos CSS Recomendada

```
css/
├── 1-reset.css          # Reset o Normalize
├── 2-variables.css      # Variables CSS (tokens de diseño)
├── 3-base.css           # Estilos base (body, headings, links)
├── 4-components.css     # Componentes reutilizables
└── 5-utilities.css      # Clases de utilidad
```

**En el HTML:**
```html
<link rel="stylesheet" href="css/1-reset.css">
<link rel="stylesheet" href="css/2-variables.css">
<link rel="stylesheet" href="css/3-base.css">
<link rel="stylesheet" href="css/4-components.css">
<link rel="stylesheet" href="css/5-utilities.css">
```

**O un solo archivo:**
```css
/* styles.css */
@import url('1-reset.css');
@import url('2-variables.css');
@import url('3-base.css');
@import url('4-components.css');
@import url('5-utilities.css');
```

---

## ✅ Checklist de Buenas Prácticas

**Variables CSS:**
- [ ] Definir variables en `:root` para alcance global
- [ ] Usar nomenclatura descriptiva (`--color-primary`, no `--azul`)
- [ ] Agrupar variables por categoría (colores, espaciado, tipografía)
- [ ] Proporcionar fallbacks cuando sea apropiado

**Colores:**
- [ ] Usar HSL para facilitar variaciones
- [ ] Crear paleta con escala de luminosidad (50-900)
- [ ] Definir colores semánticos (success, warning, danger)
- [ ] Separar colores de marca de colores funcionales

**Tipografía:**
- [ ] Limitar a 2-3 familias de fuentes
- [ ] Crear escala tipográfica consistente
- [ ] Definir pesos de fuente como variables
- [ ] Usar line-height apropiado (1.25 títulos, 1.5 texto)
- [ ] Incluir fuentes de respaldo (font stacks)

**Reset/Normalize:**
- [ ] Incluir reset o normalize al inicio
- [ ] Usar `box-sizing: border-box` universal
- [ ] Configurar estilos base del body
- [ ] Hacer imágenes responsive por defecto
- [ ] Considerar `prefers-reduced-motion`

---

## 🎯 Ejercicio Práctico

Crea un sistema de diseño básico para ComicTracker que incluya:

1. **Variables de color:**
   - Paleta primaria (azul) con 5 variaciones
   - Escala de grises (7 tonos)
   - Colores semánticos (success, warning, danger)

2. **Variables tipográficas:**
   - 2 familias de fuentes (base y headings)
   - Escala de tamaños (6 niveles)
   - 3 pesos de fuente

3. **Variables de espaciado:**
   - Escala de 5 niveles (xs a xl)

4. **Reset CSS moderno**

5. **Estilos base:**
   - Body con fuente y color
   - Headings (h1-h3)
   - Párrafos y enlaces

**Requisitos:**
- Todo usando variables CSS
- Colores en formato HSL
- Reset incluido
- Código organizado y comentado

---

## 📚 Recursos Adicionales

- **MDN - CSS Custom Properties:** Documentación oficial de variables
- **Coolors.co:** Generador de paletas de colores
- **Type Scale:** Calculadora de escalas tipográficas
- **Modern CSS Reset (Andy Bell):** Reset CSS moderno y bien documentado
- **Google Fonts:** Biblioteca de fuentes gratuitas

---

**¡Recuerda!** Un sistema de diseño consistente con variables CSS facilita el mantenimiento, permite cambios rápidos de tema, y mejora la coherencia visual de tu aplicación. 🎨✨
