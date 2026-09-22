# Registro de Decisiones de Arquitectura (ADR) — EcoRio

Este registro documenta formalmente todas las decisiones técnicas tomadas en el proyecto. 
Cualquier alteración a estas resoluciones o a las reglas de negocio requiere **justificación técnica y autorización previa obligatoria** (Pilar 4: Control de Guardas).

---

## [ADR-001] Adopción de Stack Vanilla Web + TailwindCSS v3 CDN
* **Fecha y Hora:** 2026-09-22 12:20:00 -03:00
* **Estado:** Aceptado
* **Contexto:** Se requiere construir una plataforma atractiva, moderna y accesible para el trabajo final integrador (EFI), evitando configuraciones complejas de empaquetadores locales (npm/webpack) que ralenticen la visualización directa.
* **Decisión:** Emplear HTML5 semántico puro junto a TailwindCSS v3 cargado vía CDN oficial (`<script src="https://cdn.tailwindcss.com"></script>`) y JavaScript estándar (ES6+).
* **Consecuencias:** Visualización inmediata en cualquier navegador, cero fricción de compilación y cumplimiento del programa académico.

---

## [ADR-002] Implementación de Modo Oscuro Predeterminado con Toggle Persistente
* **Fecha y Hora:** 2026-09-22 12:22:00 -03:00
* **Estado:** Aceptado
* **Contexto:** Se definió que la interfaz arranque por defecto en Modo Oscuro con tonos verdes ecológicos, pero permitiendo al usuario cambiar a Modo Claro con un botón en la barra superior.
* **Decisión:** Habilitar el modo de clase en TailwindCSS (`darkMode: 'class'`). La etiqueta `<html>` incluirá la clase `dark` por defecto. El estado se sincronizará con `localStorage.getItem('ecorio-theme')` para preservar la elección del usuario al recargar.
* **Consecuencias:** Experiencia de usuario pulida y retención de preferencias del usuario sin necesidad de cookies ni backend.

---

## [ADR-003] Desacoplamiento de Datos de Puntos Verdes y Modal Reutilizable
* **Fecha y Hora:** 2026-09-22 12:24:00 -03:00
* **Estado:** Aceptado
* **Contexto:** Se solicitó mostrar 6 Puntos Verdes representativos de Río Cuarto con tarjeta resumida y modal expandido. Duplicar 6 modales en el HTML generaría código repetitivo e ineficiente.
* **Decisión:** Definir un modelo de datos inmutable en JavaScript (`PUNTOS_VERDES_DATA`) que alimente la grilla. Un único componente modal en el DOM actualizará dinámicamente su contenido (título, dirección, horarios, materiales y mapa/indicaciones) según la tarjeta seleccionada.
* **Consecuencias:** Código DRY (Don't Repeat Yourself), mantenimiento ágil y manipulación limpia del DOM.

---

## [ADR-004] Protocolo de Modificación y Control de Guardas
* **Fecha y Hora:** 2026-09-22 12:26:00 -03:00
* **Estado:** Aceptado
* **Contexto:** Es indispensable prevenir la inclusión accidental de librerías no solicitadas o modificaciones destructivas en los requisitos del sitio.
* **Decisión:** Toda incorporación de nuevas librerías, cambios en los campos del formulario o alteración de la paleta de colores requerirá una propuesta formal al usuario con justificación técnica previa antes de aplicarse.
* **Consecuencias:** Blindaje total del alcance del proyecto y control estricto de deuda técnica.
