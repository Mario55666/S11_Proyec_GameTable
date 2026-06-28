# Generador de Prompts Ludonarrativos

## Cuento Infantil → Juego de Mesa Educativo

> **Versión 2.0** — Proyecto Ilustrador · Instituto de Diseño y Comunicación (IDC)  
> **Docente:** Mg. Mario Quiroz Martínez  
> **Unidad didáctica:** Proyecto Ilustrador · Año 2026

---

## 1. ¿Qué es este proyecto?

El **Generador de Prompts Ludonarrativos** es una herramienta web de un solo archivo HTML (`single-file`) que permite a estudiantes de diseño e ilustración transformar un **cuento infantil** en una **propuesta completa de juego de mesa educativo**.

A partir de un formulario estructurado, el sistema:

1. **Infierela mecánica principal** de juego de mesa más adecuada mediante reglas de correspondencia narrativa-mecánica (basadas en el índice de BoardGameGeek).
2. **Sugiere mecánicas complementarias** que enriquecen la experiencia lúdica.
3. **Genera un prompt detallado** para inteligencia artificial o briefing de diseño, con reglas, premios, castigos narrativos, despiece de piezas y referencias visuales.
4. **Exporta** el resultado en formato PDF e CSV con branding institucional IDC.

---

## 2. Versión 2.0 — Mejoras integradas

Esta versión incorpora los principios de **Neuroeducación** (Francisco Mora, 2018) y las reglas de calidad del modelo **DUA-Experiencial (MPI-DUAE)** del IDC.

### 🧠 Neuroeducación (Mora, 2018)

| Principio | Implementación en la herramienta |
|-----------|-----------------------------------|
| **Emoción como vehículo del aprendizaje** | Nuevo campo *"Emoción central del cuento"* que guía toda la mecánica inferida. El prompt generado instruye a la IA para que la emoción sea el eje conductor del juego. |
| **Curiosidad y atención** | Barra de progreso visual por secciones; contador de palabras en tiempo real; el prompt instruye que el setup genere asombro en los primeros 60 segundos. |
| **Tiempos cerebrales de atención** | El prompt generado especifica ritmo por fases de 3-5 minutos, adaptado a la edad infantil. |
| **Repetición y equivocación** | Validación suave del resumen narrativo: si es muy corto, se ofrece **refuerzo de 5 pasos pedagógicos** en lugar de alertas agresivas. |
| **Neuroética / Educación en valores** | Nuevo campo *"Valor o habilidad socioemocional a desarrollar"* que se traduce en reglas, premios y dinámica de turno dentro del prompt generado. |
| **Adaptación por desarrollo cerebral** | El prompt incluye directrices diferenciadas por rango de edad: motoridad/sensorialidad (3-5), cooperación (6-8), autonomía estratégica (9-12). |

### 🎨 DUA-Experiencial (MPI-DUAE) — Skill `gamificacion-dua-idc`

| Regla del modelo | Implementación |
|------------------|----------------|
| **Registro de participantes al inicio** | Formulario de identificación con validación `oninput` en tiempo real. |
| **Sin `localStorage`** | Estado gestionado en memoria (JS vanilla); el archivo funciona offline y en sandbox. |
| **Color de error suave** | Validación con fondo `#fff3e0` (ámbar cálido) en lugar de rojo intenso; protege la red afectiva. |
| **Refuerzo por error de 5 pasos** | Cuando el resumen es muy breve, el sistema muestra 5 pasos de guía narrativa (personaje → objetivo → obstáculo → aliado → desenlace). |
| **Justificación pedagógica visible** | Cada sección del formulario incluye un *tooltip pedagógico* que explica el *porqué* del campo en términos de diseño lúdico o neuroeducación. |
| **Footer institucional correcto** | Preserva `Mg. Mario Quiroz Martínez` con tilde, unidad didáctica e IDC. |
| **Branding IDC** | Paleta institucional `#f3a100`, `#0072b9`, `#555553` y logotipo IDC en header y footer. |

### 🎮 Funcionalidades técnicas nuevas

- **Barra de progreso visual** con 5 pasos animados que se completan al llenar el formulario.
- **Contador de palabras en tiempo real** para el resumen del cuento.
- **Validación suave** con mensajes contextualizados (no alertas binarias).
- **Campos de emoción y valor** integrados en el prompt generado y en la exportación CSV/PDF.
- **Sección de principios de neuroeducación** dentro del propio prompt para IA, elevando la calidad de la respuesta generada.

---

## 3. Estructura del archivo

```
generador-prompt-mecanicas-cuento-infantil-v2.html
├── CSS embebido (single-file, sin dependencias externas críticas)
│   ├── Variables de diseño (light/dark mode)
│   ├── Componentes de UI (formularios, tarjetas, chips, botones)
│   ├── Estilos de progreso, validación y pedagogía
│   └── Media queries responsivas
├── HTML semántico
│   ├── Header IDC + branding
│   ├── Hero con mapa conceptual
│   ├── Formulario en 5 secciones + barra de progreso
│   └── Panel de resultados con exportación
└── JavaScript vanilla
    ├── Base de datos de mecánicas BGG (30+ mecánicas)
    ├── Motor de inferencia de mecánica principal
    ├── Motor de sugerencia de mecánicas secundarias
    ├── Generador de prompt con neuroeducación
    ├── Validación en tiempo real y progreso
    ├── Exportación PDF (window.print) y CSV
    └── Cambio de tema claro/oscuro
```

---

## 4. Cómo usar la herramienta

### Requisitos

- Navegador moderno (Chrome, Firefox, Edge, Safari).
- No requiere servidor ni instalación. Funciona offline abriendo el archivo `.html` directamente.

### Pasos

1. **Abre** el archivo `generador-prompt-mecanicas-cuento-infantil-v2.html` en tu navegador.
2. **Completa la sección 1 (Identificación):** equipo, nombre del proyecto y responsable. Observa la validación en tiempo real.
3. **Completa la sección 2 (Historia):**
   - Selecciona la **emoción central** del cuento (nuevo en v2).
   - Elige el rango de edad y duración.
   - Escribe el **resumen narrativo**. El contador de palabras y la validación suave te guiarán.
4. **Completa la sección 3 (Experiencia):** objetivo, interacción, azar y tensión narrativa.
5. **Completa la sección 4 (Materiales):** estilo visual, paleta, recursos y componentes prioritarios.
6. **Completa la sección 5 (Pedagogía):**
   - Selecciona el **valor socioemocional** a desarrollar (nuevo en v2).
   - Define competencias, modo de uso y funcionalidad esperada.
7. **Haz clic en "Generar prompt".** El sistema inferirá la mecánica principal, mostrará referencias BGG y redactará el prompt completo.
8. **Exporta** el resultado en PDF o CSV si lo necesitas para tu entrega académica.

### Botón "Cargar ejemplo"

Usa este botón para prellenar el formulario con un caso de prueba (*La liebre que llevaba estrellas*) y ver cómo funciona el sistema completo sin escribir datos.

---

## 5. Bases teóricas

### 5.1 Neuroeducación

> *"Sólo se puede aprender aquello que se ama."* — Francisco Mora Teruel, 2018.

La herramienta aplica los principios de [*Neuroeducación*](https://www.alianzaeditorial.es/libro/neuroeducacion-francisco-mora-teruel/) para diseñar juegos que respeten el funcionamiento cerebral del niño:

- La **emoción** enciende la atención y la curiosidad.
- La **memoria** se consolida mediante repetición significativa.
- El **desarrollo cerebral** es asincrónico: cada edad tiene ventanas plásticas diferentes.
- Los **valores** (neuroética) deben entronizarse en el cerebro mediante experiencias lúdicas, no instrucciones abstractas.

### 5.2 DUA-Experiencial (MPI-DUAE)

El modelo **MPI-DUAE** (Diseño Universal para el Aprendizaje 3.0 + Ciclo Experiencial de Kolb) asegura que el diseño de la herramienta active múltiples redes cerebrales:

| Red DUA | Activación en la herramienta |
|---------|------------------------------|
| **Reconocimiento** | Visualización de mecánicas, mapa conceptual, iconografía BGG. |
| **Estratégica** | Elección de tensión narrativa, interacción, azar y componentes. |
| **Afectiva** | Campo de emoción, valor socioemocional, color de error suave, refuerzo positivo. |
| **Ciclo de Kolb** | CE (Experiencia Concreta): resumen del cuento → OR (Observación Reflexiva): inferencia de mecánica → CA (Conceptualización Abstracta): prompt generado → EA (Experimentación Activa): exportación y prototipado. |

### 5.3 Diseño de Juegos de Mesa

La base de mecánicas se alinea con el sistema de clasificación de **BoardGameGeek** (BGG), la mayor base de datos de juegos de mesa del mundo. Cada mecánica incluye:

- Descripción funcional
- URL de referencia visual en BGG
- Materiales afines
- Condiciones de inferencia (tensión narrativa + interacción + componentes)

---

## 6. Skills de Kimi utilizados en este proyecto

| Skill | Rol en el proyecto | Fase |
|-------|-------------------|------|
| **`gamificacion-dua-idc`** | Marco pedagógico DUA-Experiencial; reglas de validación suave, color de error, branding IDC, footer institucional. | Fase 2 (Enriquecimiento del formulario) |
| **`humanizer`** | Verificación de tildes en español y tono natural de los textos de ayuda. | Fase 2 (Revisión de texto) |
| **`general-writing`** | Redacción de la sección de neuroeducación en el prompt generado. | Fase 3 (Mejora del prompt) |
| **`docx`** | *(Pendiente Fase 4)* Exportación nativa a Word con formato institucional. | Fase 4 (Exportación profesional) |
| **`pdf`** | *(Pendiente Fase 4)* Generación de PDF con maquetación controlada (alternativa a `window.print`). | Fase 4 (Exportación profesional) |
| **`data-viz-renderer`** | *(Pendiente Fase 4)* Infografía del mapa historia↔mecánica. | Fase 4 (Enriquecimiento visual) |
| **`swarm-coding`** | *(Pendiente Fase 5)* Modularización si el proyecto escala a plataforma. | Fase 5 (Escalabilidad) |

> **Nota:** El skill `ad-creative` fue **verificado como NO aplicable** al dominio pedagógico-lúdico; está diseñado para copy publicitario de rendimiento (Google Ads, Meta, etc.) y no cubre narrativa infantil, mecánicas de juego ni pedagogía.

---

## 7. Roadmap y próximas fases

| Fase | Objetivo | Estado |
|------|----------|--------|
| **1 — Diagnóstico** | Análisis de brechas y alineación de skills | ✅ Completado |
| **2 — Enriquecimiento del formulario** | Integrar DUA + Neuroeducación en la UX | ✅ **Completado (v2.0)** |
| **3 — Mejora del prompt generado** | Rúbrica de evaluación, diagrama de estructura del turno | ⏳ Pendiente |
| **4 — Exportación profesional** | `.docx` nativo, `.pdf` maquetado, infografía | ⏳ Pendiente |
| **5 — Escalabilidad** | Dashboard de proyectos, modularización JS | ⏳ Futuro |

---

## 8. Créditos y referencias

- **Autor de la herramienta:** Mg. Mario Quiroz Martínez
- **Institución:** Instituto de Diseño y Comunicación (IDC) — Instituto de Educación Superior Público
- **Unidad didáctica:** Proyecto Ilustrador · Año 2026
- **Branding IDC:** Paleta `#f3a100` · `#0072b9` · `#555553`
- **Referencia bibliográfica neuroeducación:** Mora Teruel, F. (2018). *Neuroeducación. Sólo se puede aprender aquello que se ama*. Alianza Editorial.
- **Referencia mecánicas:** [BoardGameGeek](https://boardgamegeek.com/) — Sistema de clasificación de mecánicas de juegos de mesa.

---

## 9. Licencia y uso

Este recurso ha sido desarrollado para uso académico dentro del Instituto de Diseño y Comunicación (IDC). El archivo es **single-file HTML** sin dependencias de runtime: puede copiarse, distribuirse y ejecutarse offline en cualquier navegador moderno.

---

*Documentación generada el 2026-06-20.*
