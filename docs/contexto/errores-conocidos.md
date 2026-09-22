# Errores Conocidos y Gotchas del Maquetado — EcoRio

Este documento cataloga las fallas y trampas comunes de maquetado web (*gotchas*) y establece las soluciones y patrones preventivos para blindar el desarrollo de **EcoRio**.

---

## 1. Gotchas Críticos de Maquetado y Diseño Responsive

### ⚠️ Gotcha 1: Scroll Horizontal Roto en Pantallas Móviles
* **Causa:** Uso de anchos fijos en píxeles mayores al viewport del celular, márgenes negativos desbordados o padding en elementos con `width: 100%` sin `box-sizing: border-box`.
* **Impacto:** La página se mueve lateralmente en teléfonos, dejando márgenes blancos indeseados y arruinando la experiencia táctil.
* **Solución Obligatoria:**
  1. Aplicar `overflow-x-hidden` en el elemento `<body>`.
  2. Usar contenedores con clases de Tailwind como `w-full max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`.
  3. No definir nunca valores fijos como `w-[500px]` en elementos que deban mostrarse en pantallas pequeñas.

---

### ⚠️ Gotcha 2: Uso de `<div>` o `<span>` para Elementos Cliqueables
* **Causa:** Asignar controladores `onclick` a contenedores genéricos en vez de botones o enlaces.
* **Impacto:** Los usuarios de navegación por teclado (tecla `Tab` / `Enter`) y los lectores de pantalla para personas con discapacidad visual no pueden detectar ni accionar el elemento.
* **Solución Obligatoria:**
  1. Todo elemento de acción dentro de la misma pantalla DEBE ser un `<button type="button">`.
  2. Si es un botón con solo un ícono (como el selector de tema o el cierre de modal), incluir siempre `aria-label="Alternar modo claro u oscuro"` o `aria-label="Cerrar modal"`.
  3. Todo enlace a otra sección debe ser una etiqueta `<a>` con atributo `href="#id-seccion"`.

---

### ⚠️ Gotcha 3: Contraste Ilegible en Modo Oscuro y Modo Claro
* **Causa:** Reutilizar colores intermedios (como `text-gray-500`) sin verificar cómo contrastan sobre fondos oscuros (`#0f172a`) y fondos claros (`#f8fafc`).
* **Impacto:** El texto se vuelve casi invisible para el usuario o genera fatiga visual.
* **Solución Obligatoria:**
  * En **Modo Oscuro**: Fondos oscuros profundos (`bg-slate-900`) combinados exclusivamente con texto blanco (`text-white`), grises claros (`text-slate-300`) y acentos verdes brillantes (`text-emerald-400`).
  * En **Modo Claro**: Fondos claros (`bg-slate-50`) combinados con textos oscuros (`text-slate-900`), subtítulos legibles (`text-slate-600`) y verdes bosque (`text-emerald-700`).

---

### ⚠️ Gotcha 4: Fallo de Carga de Imágenes Externas
* **Causa:** Utilizar URLs de fotos de Unsplash u otras fuentes externas que pueden fallar por problemas de conectividad o caducidad del enlace.
* **Impacto:** La tarjeta queda rota con un ícono de imagen dañada.
* **Solución Obligatoria:**
  1. Todas las etiquetas `<img>` deben contar con un atributo `alt` descriptivo (ej: `alt="Punto Verde Plaza Roca en Río Cuarto"`).
  2. Implementar un fallback de respaldo mediante el evento `onerror` para cargar un fondo degradado con icono ecológico SVG si el enlace externo no responde.

---

### ⚠️ Gotcha 5: Bloqueo de Scroll al Cerrar Modales
* **Causa:** Modificar el `document.body.style.overflow = 'hidden'` al abrir un modal y no restablecerlo limpiamente al cerrarlo con la tecla `Escape` o al hacer clic fuera del diálogo.
* **Impacto:** La página queda bloqueada impidiendo que el usuario pueda seguir desplazándose.
* **Solución Obligatoria:**
  * Centralizar la apertura y cierre en funciones JS idempotentes (`openModal()` y `closeModal()`) que garanticen la remoción de la clase bloqueante en cualquier vía de salida.
