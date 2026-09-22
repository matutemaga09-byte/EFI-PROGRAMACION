# Glosario y Lenguaje Ubicuo — EcoRio

Este documento establece el glosario de términos del negocio y componentes de interfaz del proyecto **EcoRio**. Garantiza la coherencia léxica entre el código, los identificadores del DOM y los textos mostrados al usuario final.

---

## 1. Términos de Negocio y Dominio Ecológico

* **EcoRio:** Nombre del proyecto y marca de la plataforma de reciclaje y sustentabilidad para Río Cuarto, Córdoba.
* **PuntoVerde (Punto Verde):** Espacio geográfico o estación municipal/comunitaria equipada con contenedores diferenciados para que los ciudadanos depositen materiales clasificados.
* **EcoEmpresa:** Industria, empresa manufacturera o taller de Río Cuarto y la región que adquiere materiales reciclables (plásticos, chatarra, cartón, vidrio) como insumo para sus procesos productivos.
* **EcoTaller:** Espacio de capacitación, concientización y formación comunitaria en separación en origen y compostaje.
* **Recolección:** Logística, rutas y frecuencias de retiro de residuos valorizables desde los Puntos Verdes hacia los acopios o plantas de reciclaje.
* **Mapa / Sector:** Clasificación territorial de los puntos en los barrios principales de Río Cuarto (Centro, Banda Norte, Alberdi, Campus UNRC, Costanera, etc.).
* **Reciclaje:** Proceso de transformación y recuperación de residuos para su reincorporación al ciclo económico.
* **Economía Circular:** Modelo económico que busca reducir el desecho al mínimo mediante la reutilización, reparación y reciclaje continuo de materiales.

---

## 2. Componentes de Interfaz y Terminología Técnica

* **Navbar:** Barra de navegación superior fija (`sticky`) que contiene el imagotipo de EcoRio, enlaces internos, el selector de modo oscuro/claro y el botón hamburguesa en dispositivos móviles.
* **ThemeToggle:** Botón interactivo con icono dual (Sol / Luna) que alterna entre Modo Oscuro y Modo Claro.
* **HeroSection:** Bloque introductorio de alto impacto con título, descripción del impacto ambiental en Río Cuarto y llamada a la acción principal (*CTA*).
* **CardPuntoVerde:** Tarjeta interactiva individual que sintetiza la información básica de una estación: foto, sector/calle, categoría de materiales, horarios de disponibilidad y botón de detalle.
* **ModalDetalle:** Ventana modal emergente accesible que se superpone a la página con información exhaustiva del Punto Verde seleccionado (dirección exacta, días y horarios, lista completa de materiales admitidos y recomendaciones de entrega).
* **ContactoForm:** Formulario interactivo para que vecinos o EcoEmpresas envíen consultas sobre retiro, compra de materiales o adhesión de nuevos puntos.
* **AlertSuccess (Toast Verde):** Notificación visual que confirma al usuario el despacho exitoso de su consulta sin recargar la página.
* **Footer:** Sección de cierre con enlaces informativos, créditos y enlaces a canales comunitarios.
