# MÓDULO HTML-4: Componentes Avanzados y Accesibilidad

## 📚 Introducción

La **accesibilidad web** significa crear sitios que todas las personas puedan usar, independientemente de sus capacidades físicas o cognitivas. HTML semántico es un buen comienzo, pero a veces necesitamos componentes interactivos complejos (modales, pestañas, menús) que HTML básico no puede describir adecuadamente.

Aquí es donde entra **ARIA** (Accessible Rich Internet Applications): un conjunto de atributos especiales que añaden información semántica adicional para tecnologías asistivas como lectores de pantalla.

> **⚠️ REGLA DE ORO DE ARIA:**  
> "No uses ARIA si existe un elemento HTML nativo que haga el trabajo"

---

## 1️⃣ Atributos ARIA: Añadiendo Contexto

Los atributos ARIA proporcionan información adicional sobre elementos interactivos. Piensa en ellos como "etiquetas invisibles" que solo las tecnologías asistivas pueden leer.

### 1.1 `aria-label` - Etiqueta Directa

**¿Qué hace?** Proporciona un nombre accesible directamente al elemento.

**¿Cuándo usarlo?** Cuando un elemento no tiene texto visible pero necesita una descripción.

**Sintaxis:**
```html
<button aria-label="Cerrar ventana">
  ✕
</button>
```

**Explicación:**  
- El botón solo muestra una "✕" visualmente
- Los lectores de pantalla anunciarán: "Cerrar ventana, botón"
- Sin `aria-label`, solo dirían: "Botón" (confuso)

**Ejemplo práctico:**
```html
<button aria-label="Buscar">
  <svg><!-- Icono de lupa --></svg>
</button>

<a href="#main-content" aria-label="Saltar al contenido principal">
  ⬇️
</a>
```

---

### 1.2 `aria-labelledby` - Etiqueta por Referencia

**¿Qué hace?** Conecta un elemento con otro que actúa como su etiqueta.

**¿Cuándo usarlo?** Cuando la etiqueta ya existe en el DOM y quieres reutilizarla.

**Sintaxis:**
```html
<h2 id="dialog-title">Confirmar eliminación</h2>
<div role="dialog" aria-labelledby="dialog-title">
  <p>¿Estás seguro de eliminar este cómic?</p>
  <button>Eliminar</button>
  <button>Cancelar</button>
</div>
```

**Explicación:**  
- El `<div>` con `role="dialog"` usa el `<h2>` como su nombre accesible
- `aria-labelledby` apunta al `id` del elemento etiqueta
- Los lectores de pantalla anunciarán: "Confirmar eliminación, diálogo"

**Diferencia clave con `aria-label`:**
- `aria-label`: texto directo → `aria-label="Mi etiqueta"`
- `aria-labelledby`: referencia a otro elemento → `aria-labelledby="id-del-elemento"`

---

### 1.3 `aria-describedby` - Descripción Adicional

**¿Qué hace?** Conecta un elemento con una descripción más detallada.

**¿Cuándo usarlo?** Para proporcionar instrucciones, ayuda o información complementaria.

**Sintaxis:**
```html
<label for="password">Contraseña</label>
<input 
  type="password" 
  id="password" 
  aria-describedby="password-hint"
>
<p id="password-hint">
  Mínimo 8 caracteres, incluye números y símbolos
</p>
```

**Explicación:**  
- El `<input>` tiene una etiqueta principal ("Contraseña")
- `aria-describedby` añade información extra sin saturar la etiqueta
- Los lectores de pantalla dirán: "Contraseña, campo de texto, Mínimo 8 caracteres..."

**Ejemplo con múltiples descripciones:**
```html
<input 
  type="email" 
  aria-describedby="email-format email-privacy"
>
<span id="email-format">Formato: usuario@dominio.com</span>
<span id="email-privacy">No compartiremos tu email</span>
```

---

### 1.4 `aria-hidden` - Ocultar de Tecnologías Asistivas

**¿Qué hace?** Oculta elementos del árbol de accesibilidad (pero siguen visibles visualmente).

**¿Cuándo usarlo?** Para elementos puramente decorativos o redundantes.

**Sintaxis:**
```html
<button>
  <span aria-hidden="true">🗑️</span>
  Eliminar
</button>
```

**Explicación:**  
- El emoji es decorativo (el texto "Eliminar" ya es claro)
- `aria-hidden="true"` evita que los lectores de pantalla lo anuncien
- Sin esto, dirían: "Papelera de basura, Eliminar, botón" (redundante)

**Caso de uso común - Iconos:**
```html
<a href="/perfil">
  <i class="icon-user" aria-hidden="true"></i>
  Mi Perfil
</a>
```

**⚠️ ADVERTENCIA:**  
Nunca uses `aria-hidden="true"` en elementos interactivos (botones, enlaces) que no tengan texto alternativo. Esto los haría inaccesibles.

```html
<!-- ❌ MAL: El botón es invisible para lectores de pantalla -->
<button aria-hidden="true">
  <svg><!-- Icono --></svg>
</button>

<!-- ✅ BIEN: Icono oculto, botón con etiqueta -->
<button aria-label="Cerrar">
  <svg aria-hidden="true"><!-- Icono --></svg>
</button>
```

---

## 2️⃣ Roles ARIA: Definiendo Propósitos

Los **roles ARIA** definen qué tipo de componente es un elemento. HTML tiene roles implícitos (`<button>` tiene `role="button"`), pero para componentes personalizados necesitamos declararlos explícitamente.

### 2.1 `role="dialog"` - Ventanas Modales

**¿Qué es?** Un cuadro de diálogo que interrumpe el flujo normal de la aplicación.

**¿Cuándo usarlo?** Para modales, alertas, confirmaciones.

**Sintaxis básica:**
```html
<div 
  role="dialog" 
  aria-labelledby="modal-title"
  aria-modal="true"
>
  <h2 id="modal-title">Añadir nuevo cómic</h2>
  <form>
    <label for="comic-name">Nombre:</label>
    <input type="text" id="comic-name">
    <button type="submit">Guardar</button>
    <button type="button">Cancelar</button>
  </form>
</div>
```

**Atributos complementarios:**
- `aria-labelledby`: Conecta con el título del diálogo
- `aria-modal="true"`: Indica que el resto de la página está inerte (no interactiva)
- `aria-describedby`: (Opcional) Para descripción adicional

**Ejemplo completo:**
```html
<div 
  role="dialog" 
  aria-labelledby="delete-title"
  aria-describedby="delete-description"
  aria-modal="true"
>
  <h2 id="delete-title">Confirmar eliminación</h2>
  <p id="delete-description">
    Esta acción no se puede deshacer. El cómic será eliminado permanentemente.
  </p>
  <button>Eliminar</button>
  <button>Cancelar</button>
</div>
```

---

### 2.2 Sistema de Pestañas (Tabs)

Un patrón común en interfaces: contenido organizado en pestañas. Requiere **tres roles** trabajando juntos.

#### **Roles del patrón:**
1. `role="tablist"` - Contenedor de las pestañas
2. `role="tab"` - Cada pestaña individual
3. `role="tabpanel"` - Panel de contenido asociado

**Estructura básica:**
```html
<div role="tablist" aria-label="Categorías de cómics">
  <button role="tab" aria-selected="true" aria-controls="panel-marvel" id="tab-marvel">
    Marvel
  </button>
  <button role="tab" aria-selected="false" aria-controls="panel-dc" id="tab-dc">
    DC
  </button>
  <button role="tab" aria-selected="false" aria-controls="panel-indie" id="tab-indie">
    Independientes
  </button>
</div>

<div role="tabpanel" id="panel-marvel" aria-labelledby="tab-marvel">
  <h3>Cómics de Marvel</h3>
  <!-- Contenido de Marvel -->
</div>

<div role="tabpanel" id="panel-dc" aria-labelledby="tab-dc" hidden>
  <h3>Cómics de DC</h3>
  <!-- Contenido de DC -->
</div>

<div role="tabpanel" id="panel-indie" aria-labelledby="tab-indie" hidden>
  <h3>Cómics Independientes</h3>
  <!-- Contenido Indie -->
</div>
```

**Explicación de atributos:**

| Atributo | Dónde | Propósito |
|----------|-------|-----------|
| `aria-selected="true/false"` | En `role="tab"` | Indica qué pestaña está activa |
| `aria-controls="id-panel"` | En `role="tab"` | Conecta la pestaña con su panel |
| `aria-labelledby="id-tab"` | En `role="tabpanel"` | Conecta el panel con su pestaña |
| `hidden` | En `role="tabpanel"` | Oculta paneles inactivos |

**Comportamiento esperado:**
- Solo una pestaña tiene `aria-selected="true"` a la vez
- Solo un panel está visible (sin `hidden`) a la vez
- La navegación con teclado (flechas) debe cambiar entre pestañas

---

## 3️⃣ Listas de Definición: Pares Término-Descripción

Las **listas de definición** (`<dl>`) son perfectas para presentar información en formato término-descripción. Piensa en ellas como un diccionario o glosario.

### 3.1 Estructura Básica

**Elementos:**
- `<dl>` - **D**efinition **L**ist (contenedor)
- `<dt>` - **D**efinition **T**erm (término)
- `<dd>` - **D**efinition **D**escription (descripción)

**Sintaxis:**
```html
<dl>
  <dt>HTML</dt>
  <dd>Lenguaje de marcado para estructurar contenido web</dd>
  
  <dt>CSS</dt>
  <dd>Lenguaje de estilos para diseñar páginas web</dd>
  
  <dt>JavaScript</dt>
  <dd>Lenguaje de programación para interactividad web</dd>
</dl>
```

---

### 3.2 Patrones de Uso

#### **Patrón 1: Un término, una descripción**
```html
<dl>
  <dt>Autor</dt>
  <dd>Stan Lee</dd>
  
  <dt>Editorial</dt>
  <dd>Marvel Comics</dd>
  
  <dt>Año</dt>
  <dd>1962</dd>
</dl>
```

#### **Patrón 2: Un término, múltiples descripciones**
```html
<dl>
  <dt>Spider-Man</dt>
  <dd>Peter Parker</dd>
  <dd>Miles Morales</dd>
  <dd>Gwen Stacy (Spider-Gwen)</dd>
</dl>
```

#### **Patrón 3: Múltiples términos, una descripción**
```html
<dl>
  <dt>HTML</dt>
  <dt>HyperText Markup Language</dt>
  <dd>Lenguaje estándar para crear páginas web</dd>
</dl>
```

---

### 3.3 Casos de Uso Prácticos

#### **Metadatos de un cómic:**
```html
<article>
  <h2>The Amazing Spider-Man #1</h2>
  <dl>
    <dt>Título original</dt>
    <dd>The Amazing Spider-Man</dd>
    
    <dt>Guionista</dt>
    <dd>Stan Lee</dd>
    
    <dt>Dibujante</dt>
    <dd>Steve Ditko</dd>
    
    <dt>Fecha de publicación</dt>
    <dd>Marzo 1963</dd>
    
    <dt>Editorial</dt>
    <dd>Marvel Comics</dd>
    
    <dt>Páginas</dt>
    <dd>22 páginas</dd>
  </dl>
</article>
```

#### **Glosario de términos:**
```html
<h2>Glosario de Cómics</h2>
<dl>
  <dt>Panel</dt>
  <dd>Recuadro individual que contiene una escena o momento de la historia</dd>
  
  <dt>Viñeta</dt>
  <dd>Sinónimo de panel en el contexto hispanohablante</dd>
  
  <dt>Bocadillo</dt>
  <dd>Globo que contiene los diálogos o pensamientos de los personajes</dd>
  
  <dt>Splash page</dt>
  <dd>Página completa dedicada a una sola imagen impactante</dd>
</dl>
```

#### **Información de contacto:**
```html
<h3>Contacto de la tienda</h3>
<dl>
  <dt>Dirección</dt>
  <dd>Calle Falsa 123, Ciudad de México</dd>
  
  <dt>Teléfono</dt>
  <dd>+52 55 1234 5678</dd>
  
  <dt>Email</dt>
  <dd>contacto@comicstore.com</dd>
  
  <dt>Horario</dt>
  <dd>Lunes a Viernes: 10:00 - 20:00</dd>
  <dd>Sábados: 11:00 - 18:00</dd>
  <dd>Domingos: Cerrado</dd>
</dl>
```

---

### 3.4 Estilización con Grupos

Puedes agrupar pares `<dt>`/`<dd>` usando `<div>` (desde HTML5):

```html
<dl>
  <div>
    <dt>Nombre</dt>
    <dd>Bruce Wayne</dd>
  </div>
  
  <div>
    <dt>Alias</dt>
    <dd>Batman</dd>
  </div>
  
  <div>
    <dt>Ciudad</dt>
    <dd>Gotham City</dd>
  </div>
</dl>
```

**Ventaja:** Facilita aplicar estilos CSS a cada par como unidad.

---

## 📋 Resumen Comparativo

### Atributos ARIA

| Atributo | Propósito | Ejemplo |
|----------|-----------|---------|
| `aria-label` | Etiqueta directa | `<button aria-label="Cerrar">✕</button>` |
| `aria-labelledby` | Etiqueta por referencia | `<div aria-labelledby="titulo-id">` |
| `aria-describedby` | Descripción adicional | `<input aria-describedby="ayuda-id">` |
| `aria-hidden` | Ocultar de lectores de pantalla | `<span aria-hidden="true">🎨</span>` |

### Roles ARIA

| Role | Uso | Atributos clave |
|------|-----|-----------------|
| `dialog` | Ventanas modales | `aria-labelledby`, `aria-modal` |
| `tablist` | Contenedor de pestañas | `aria-label` |
| `tab` | Pestaña individual | `aria-selected`, `aria-controls` |
| `tabpanel` | Panel de contenido | `aria-labelledby` |

### Listas de Definición

| Elemento | Significado | Uso |
|----------|-------------|-----|
| `<dl>` | Definition List | Contenedor principal |
| `<dt>` | Definition Term | Término a definir |
| `<dd>` | Definition Description | Descripción del término |

---

## ✅ Checklist de Buenas Prácticas

**ARIA:**
- [ ] Usa HTML semántico primero, ARIA solo cuando sea necesario
- [ ] Cada `role="dialog"` tiene `aria-labelledby` o `aria-label`
- [ ] Los iconos decorativos tienen `aria-hidden="true"`
- [ ] Los botones con solo iconos tienen `aria-label`
- [ ] Las pestañas tienen `aria-selected` y `aria-controls` correctos

**Listas de Definición:**
- [ ] Usa `<dl>` para pares término-descripción, no para diseño
- [ ] Cada `<dt>` tiene al menos un `<dd>` asociado
- [ ] No uses `<dl>` para listas simples (usa `<ul>` o `<ol>`)

---

## 🎯 Ejercicio Práctico

Crea una tarjeta de cómic que incluya:
1. Un modal de confirmación con `role="dialog"`
2. Un sistema de pestañas para "Sinopsis", "Personajes" y "Reseñas"
3. Una lista de definición con los metadatos del cómic

**Requisitos:**
- Todos los elementos interactivos deben ser accesibles por teclado
- Los iconos decorativos deben estar ocultos para lectores de pantalla
- Las pestañas deben indicar cuál está activa
- El modal debe tener un título accesible

---

## 📚 Recursos Adicionales

- **WAI-ARIA Authoring Practices:** Patrones de diseño accesibles oficiales
- **MDN Web Docs:** Documentación completa de atributos y roles ARIA
- **WebAIM:** Guías y herramientas de accesibilidad web

---

**¡Recuerda!** La accesibilidad no es opcional, es un derecho. Cada atributo ARIA que añades correctamente hace que tu aplicación sea usable por más personas. 🌐♿
