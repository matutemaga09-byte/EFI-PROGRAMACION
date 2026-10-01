# Convenciones de Código y Diseño — EcoRio

Este documento establece las directivas visuales, arquitectónicas y de marcado que garantizan un código limpio, accesible y homogéneo en todo el proyecto.

---

## 1. Marcado Semántico HTML5
Todo componente de la interfaz debe utilizar la etiqueta adecuada según su rol dentro del árbol de accesibilidad (AOM):

* `<header>`: Encabezado superior contenedor de navegación y marca.
* `<nav>`: Bloque de enlaces principales de navegación.
* `<main>`: Contenedor principal que envuelve el contenido único de la página.
* `<section>`: Bloques temáticos identificables (`#inicio`, `#puntos-verdes`, `#contacto`). Cada section debe incluir un encabezado jerárquico (`<h2>`).
* `<article>`: Tarjetas individuales de Puntos Verdes.
* `<dialog>` o `div[role="dialog"]`: Modal interactivo de detalle con atributos `aria-labelledby`, `aria-modal="true"`.
* `<button>`: Todo elemento accionable por clic que no sea navegación a otra URL. **Prohibido usar `<div>` o `<span>` como botones.**
* `<footer>`: Pie de página institucional y créditos.

---

## 2. Paleta Cromática y Modos (Dark / Light)

El diseño responde a una estética ecológica contemporánea, priorizando contrastes que superan las pautas WCAG AA (ratio > 4.5:1).

### Gama Cromática Principal:
* **Verde Esmeralda Primario:** `emerald-600` (`#059669`) / `emerald-500` (`#10b981`)
* **Verde Acento / Vibrante:** `emerald-400` (`#34d399`) / `emerald-300` (`#6ee7b7`)
* **Verde Profundo / Hover:** `emerald-700` (`#047857`) / `emerald-800` (`#065f46`)

### Modo Oscuro (Predeterminado - Clase `.dark` en `<html>`):
* **Fondo Principal:** `bg-slate-950` (`#020617`) o `bg-slate-900` (`#0f172a`)
* **Contenedores y Tarjetas:** `bg-slate-900/80` con borde `border-slate-800`
* **Texto Primario:** `text-white`
* **Texto Secundario:** `text-slate-400`
* **Badges y Etiquetas:** `bg-emerald-950/60 text-emerald-300 border border-emerald-800`

### Modo Claro (Alternancia reactiva):
* **Fondo Principal:** `bg-emerald-50` (`#ecfdf5`)
* **Secciones Alternas:** `bg-emerald-100/60` (`#d1fae5` al 60%)
* **Contenedores y Tarjetas:** `bg-white` con borde `border-emerald-200` y `shadow-sm shadow-emerald-900/5`
* **Texto Primario:** `text-emerald-950` (`#022c22`)
* **Texto Secundario:** `text-emerald-900/70` (alternativa: `text-slate-600`)
* **Acento / Links:** `text-emerald-700` (`#047857`)
* **Botón Principal:** `bg-emerald-700 hover:bg-emerald-800` con `text-white`
* **Badges y Etiquetas:** `bg-emerald-100 text-emerald-800 border border-emerald-200`

---

## 3. Tipografía y Jerarquía Visual

* **Familia Tipográfica:** Google Fonts **Poppins** (títulos, botones e impacto) e **Inter** (cuerpo de texto, datos y modal), con fallback `sans-serif`.
* **Jerarquía de Encabezados:**
  * `h1`: `text-4xl md:text-6xl font-extrabold tracking-tight` (Hero)
  * `h2`: `text-3xl md:text-4xl font-bold tracking-tight` (Títulos de sección)
  * `h3`: `text-xl font-semibold` (Títulos de tarjetas de Puntos Verdes)
  * `p` / `span`: `text-base` o `text-sm leading-relaxed`

---

## 4. Diseño Responsive y Breakpoints

El diseño es **Mobile-First** con adaptación fluida en los puntos de quiebre estándar de TailwindCSS:

| Dispositivo | Breakpoint | Comportamiento del Layout |
| :--- | :--- | :--- |
| **Móviles** | `< 640px` (Default) | Grilla de tarjetas en **1 sola columna**. Menú colapsado en botón hamburguesa. Botones de acción ocupan el ancho completo (`w-full`) para facilitar el toque táctil. |
| **Tablets** | `md: >= 768px` | Grilla de tarjetas en **2 columnas** (`md:grid-cols-2`). Navegación desktop visible. |
| **Escritorio** | `lg: >= 1024px` | Grilla de tarjetas en **3 columnas** (`lg:grid-cols-3`). Contenedores limitados a `max-w-7xl mx-auto`. |

---

## 5. Microinteracciones y Estados de UI
* **Efecto Hover en Tarjetas:** `hover:-translate-y-1.5 hover:shadow-2xl transition-all duration-300`
* **Zoom en Imágenes:** `group-hover:scale-105 transition-transform duration-500 ease-out`
* **Efecto en Botones:** `hover:brightness-110 active:scale-95 transition-all duration-200`
* **Feedback de Foco:** `focus-visible:ring-2 focus-visible:ring-emerald-500 focus-visible:outline-none`
