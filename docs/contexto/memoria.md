# Memoria Activa del Proyecto: EcoRio (mem_save)

* **Última actualización:** 2026-09-22
* **Proyecto:** EcoRio — Puntos de Reciclaje y Conexión con EcoEmpresas en Río Cuarto
* **Estado del Contexto:** Inicial Consolidado y Validado (Listo para Master Context)

---

## 📌 CONSOLIDACIÓN DE LAS 14 RESPUESTAS (BASE DE CONOCIMIENTO)

### Bloque 1: Identidad, Temática y Glosario
1. **Nombre y Propósito:**
   - **Nombre:** `EcoRio`
   - **Misión:** Promover el cuidado del medioambiente y reciclaje en la ciudad de Río Cuarto (Córdoba).
   - **Propósito:** Mostrar los Puntos Verdes y centros de reciclaje en la ciudad y actuar como nexo con empresas locales e industrias que compran o procesan materiales reciclables, impulsando la economía circular y la rentabilidad sustentable.
2. **Glosario Clave:**
   - `PuntoVerde`: Estación fija o móvil donde los ciudadanos depositan materiales clasificados.
   - `EcoEmpresa`: Empresa o industria interesada en adquirir materiales reciclables por volumen.
   - `EcoTaller`: Espacio formativo o centro de concientización ambiental.
   - `Recoleccion`: Cronograma y logística de retiro de materiales.
   - `Mapa`: Visualización geográfica interactiva o referencial de ubicaciones en Río Cuarto.
   - `Reciclaje`: Clasificación y recuperación de plásticos, vidrio, cartón, metales y RAEE.

### Bloque 2: Estructura, Secciones y Contenido
3. **Estructura Wireframe (Top-to-Bottom):**
   - 1. `Navbar`: Logo `EcoRio`, enlaces de anclaje, botón selector de tema (Modo Claro/Oscuro) y menú hamburguesa en mobile.
   - 2. `Hero (Portada)`: Encabezado ecológico llamativo, propuesta de valor para Río Cuarto y CTA principal ("Explorar Puntos Verdes").
   - 3. `Catálogo de Puntos Verdes`: Grilla interactiva de 6 tarjetas con filtros de reciclaje.
   - 4. `Formulario de Contacto / EcoEmpresas`: Formulario para conectar vecinos y empresas con feedback visual de envío.
   - 5. `Footer`: Identidad, enlaces rápidos, derechos y redes comunitarias.
4. **Tarjetas (Cards) de Puntos Verdes:**
   - **Estructura:** Foto de portada, Sector / Calle (Río Cuarto), Disponibilidad (Días y horarios), Categoría de materiales, Breve descripción (2 líneas) y Botón "Ver detalles".
   - **Datos de muestra (6 ubicaciones representativas de Río Cuarto):**
     1. *Punto Verde Plaza Roca (Centro)* — Vidrio, Papel y Plásticos.
     2. *EcoPunto Parque Sarmiento (Banda Norte)* — Botellas PET, Tapitas y Latas de Aluminio.
     3. *Estación Ambiental Andino (Sur)* — Cartón, Papel, Telas y Envases Tetra.
     4. *Punto Limpio UNRC (Campus Universitario)* — RAEE (Electrónicos menores), Pilas y Metales.
     5. *Punto Verde Alberdi (Plaza Otegui)* — Plásticos duros, Polietileno y Vidrios.
     6. *EcoIsla Costanera del Río Cuarto* — Reciclables mixtos y tapitas solidarias.
5. **Formulario:**
   - Campos: Nombre completo, Correo electrónico, Asunto, Mensaje.
   - Botón: "Enviar Consulta" con validación y modal/toast verde de confirmación inmediata.

### Bloque 3: Estilo Visual y Diseño Responsive
6. **Paleta de Colores y Modo:**
   - Selector activo: Inicia en **Modo Oscuro** con toggle a **Modo Claro**.
   - Gama cromática: Verdes esmeralda/bosque (`#059669`, `#10b981`, `#34d399`), fondos oscuros pizarra (`#0f172a`, `#1e293b`), fondos claros limpios (`#f8fafc`, `#ffffff`).
   - Contraste: Texto blanco sobre fondos oscuros; texto gris muy oscuro (`#0f172a`) sobre fondos claros.
7. **Tipografía:**
   - Google Fonts: `Poppins` / `Inter` con jerarquía clara y sans-serif fallback.
8. **Responsive Design:**
   - Mobile First: 1 columna en smartphones, 2 columnas en tablets (`md:grid-cols-2`), 3 columnas en desktop (`lg:grid-cols-3`).
   - Navegación móvil con menú hamburguesa colapsable y botones de acción con área táctil accesible.
9. **Efectos Microinteractivos (Hover):**
   - Botones con transición de color y escala sutil.
   - Tarjetas con elevación flotante (`hover:-translate-y-1.5 hover:shadow-2xl`) y zoom suave en la imagen (`group-hover:scale-105`).

### Bloque 4: Decisiones Técnicas y Restricciones
10. **Framework CSS:** TailwindCSS v3 vía CDN (`<script src="https://cdn.tailwindcss.com"></script>`).
11. **Interactividad Visual:**
    - Modal flotante con detalles completos del Punto Verde al pulsar "Ver detalles".
    - Toggle de Modo Claro / Modo Oscuro con persistencia en `localStorage`.
    - Alerta/banner interactivo de éxito al enviar el formulario (sin recargar la página).
12. **Límites Estrictos (Lo que NO existe):**
    - ❌ Cero frameworks pesados (React, Vue, Angular).
    - ❌ Cero backend (Node.js, Express, Python).
    - ❌ Cero bases de datos externas (SQL, Firebase).
    - ❌ Cero estilos inline desordenados (`style='...'`).
    - ✅ Todo en HTML5 semántico puro + TailwindCSS + JavaScript moderno autocontenido.

### Bloque 5: Flujo de Trabajo y Aseguramiento de Calidad
13. **Metodología:**
    - Paso 1: Esqueleto semántico HTML5.
    - Paso 2: Maquetado visual y layout responsivo con TailwindCSS.
    - Paso 3: Interactividad, lógica de tarjetas, modal, tema claro/oscuro y validación en JS.
    - DoD Checklist: Validación responsiva (DevTools F12), accesibilidad (textos legibles y botones reales), cero errores en consola.
14. **Gotchas Blindados:**
    - Prevención de scroll horizontal con `overflow-x-hidden`.
    - Imágenes con atributo `alt` semántico y placeholder resiliente.
    - Elementos interactivos implementados exclusivamente con etiquetas `<button>`.
