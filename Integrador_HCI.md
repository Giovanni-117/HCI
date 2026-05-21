# Documento Integrador — Proyecto HCI: Sistema ECFCA (Caso de Estudio Técnico Extenso)

Este documento presenta una síntesis exhaustiva y detallada del desarrollo del sistema de Registro y Seguimiento Académico (ECFCA), estructurado específicamente bajo las métricas de evaluación de la asignatura.

---

## 1. Resumen de los avances realizados entre las entregas. Cambios más significativos, reajustes.

El proyecto evolucionó significativamente desde su conceptualización hasta el producto final, destacando los siguientes reajustes clave:
*   **Fase de Cimentación:** Se inició con un prototipo funcional (v0) centrado en la viabilidad técnica del registro, pero presentaba alta fricción para los usuarios nuevos, obligándolos a iniciar sesión antes de conocer la oferta.
*   **Reajustes Significativos (Identidad Visual):** Se integró la Guía de Diseño Visual de la UADY para dotar al sistema de autoridad institucional, sustituyendo el tono genérico inicial por paletas (Azul y Oro) y tipografía institucionales (Lucida Bright).
*   **Cambio Estructural Crítico:** Tras las primeras evaluaciones, el cambio más significativo fue la implementación del patrón **"Lazy Registration"** (Registro Perezoso). Esto permitió abrir el catálogo de cursos a usuarios no registrados, eliminando el bloqueo inicial y mejorando drásticamente la retención.
*   **Refinamiento (Desarrollo Web):** La visibilidad de los "Llamados a la Acción" (CTAs) fue reajustada incrementando drásticamente el contraste para evitar confusiones operativas. Basado en el desarrollo técnico (repositorio `HCIdemo`), se implementaron botones de navegación más grandes, una nueva tarjeta destacada para los cursos, y un *Hero* dinámico que mejora la primera impresión y corrige los flujos de sesión.

---

## 2. Resumen del Producto en términos de las fases de desarrollo basados en la Metodología de Diseño Centrado en el Usuario

El producto se concibió colocando al usuario objetivo en el centro de todas las decisiones arquitectónicas.
*   **Investigación de Usuarios:** Se enfocó en profesionales de 30-45 años, caracterizados por tener poco tiempo y una baja tolerancia a la fricción tecnológica.
*   **Arquitectura Cognitiva:** Guiados por la metodología, se implementaron patrones de interfaz que alivian la carga mental:
    *   *Breadcrumbs (Migas de pan):* Para orientar al usuario en todo momento.
    *   *Clear Primary Actions:* Uso de colores institucionales de alto contraste para destacar la acción principal en cada pantalla.
*   **Validación Teórica:** Se comprendió que las entrevistas directas son útiles, pero es vital contrastar lo que el usuario *dice* con lo que realmente *hace* en el sistema.

---

## 3. Presentación de cada una de las etapas con detalles de la implementación

El proyecto fluyó a través de ramas dedicadas en Git, reflejando transiciones claras entre etapas y prototipos:

*   **Etapa 1 (Conceptualización):** 
    *   *Proceso:* Definición clara de la aplicación, plan del proyecto y perfiles de usuario.
    *   *Productos:* Primer prototipo funcional (v0). 
    *   *Resultados:* Estructura técnica viable pero con diseño visual deficiente y bloqueos de navegación.
*   **Etapa 2 (Estructuración Visual y Requisitos):**
    *   *Proceso:* Definición de la metodología de participantes y Requisitos No Funcionales (RNF).
    *   *Productos:* Integración de la normativa visual UADY.
    *   *Transición:* Del prototipo genérico (v0) a una interfaz que proyecta seriedad institucional.
*   **Etapa 3 (Implementación Lógica y Desarrollo Técnico):**
    *   *Proceso:* Desarrollo e integración del Front-End con la lógica asíncrona.
    *   *Productos:* Aplicación web construida con **Next.js 16**, **React 19**, **Tailwind CSS v4** y componentes accesibles de **Radix UI**. Se implementaron validaciones estrictas de formularios utilizando **Zod** y **React Hook Form**.
    *   *Resultados:* Un ecosistema técnico robusto, con componentes de carga de archivos, interfaces dinámicas (tarjetas destacadas y Hero animado) y navegación rápida y accesible.
*   **Etapas 4 y 5 (Pruebas y Consolidación):**
    *   *Proceso:* Ejecución empírica de pruebas y refinamiento.
    *   *Productos:* Extenso Documento de Pruebas RNF.
    *   *Resultados:* Sistema final corregido y optimizado para el usuario profesional.

---

## 4. Pruebas de Usabilidad

El equipo desarrolló un plan de pruebas para medir empíricamente la usabilidad del sistema, utilizando matrices de validación concretas.

**Materiales y Métricas Utilizadas:**
*   **Escala SUS (System Usability Scale):** Objetivo > 70 puntos y > 70% de éxito en la primera sesión sin ayuda.
*   **WAVE (Accesibilidad):** Objetivo de cero errores críticos Nivel A.

**Análisis y Resultados (Hallazgos Críticos basados en los Participantes Reales):**
La prueba de usabilidad contó con la participación de un grupo demográficamente diverso (edades entre 23 y 58 años, perfiles desde altamente técnicos hasta casuales/moderados).

A continuación se presenta la matriz consolidada de resultados y observaciones cualitativas obtenidas durante la ejecución de las 4 tareas principales:

### Resultados Consolidados por Tarea

| ID | Tarea | Resumen Cuantitativo (Tiempos y Errores) | Observaciones Cualitativas y Fricción (Think Aloud) |
| :--- | :--- | :--- | :--- |
| **T1** | Registro de Usuario | **Cumplimiento:** Alto (algunos con ayuda).<br>**Tiempo:** 48s (Mín) a 160s (Máx).<br>**Errores comunes:** Formato de matrícula y contraseñas. | • El botón de registro fue difícil de localizar inicialmente para varios usuarios.<br>• Falta de claridad en el formato esperado para la "Matrícula".<br>• Confusión entre el uso de correo personal o institucional.<br>• Ausencia de *feedback* visual (animación/mensaje) al concluir exitosamente el registro. |
| **T2** | Inicio de Sesión | **Cumplimiento:** 100% (Muy alto).<br>**Tiempo:** 12s (Mín) a 60s (Máx).<br>**Errores comunes:** Confusión de credenciales (correo). | • Tarea fluida y sin vacilaciones graves.<br>• El layout se percibió como limpio y correcto.<br>• Algunos usuarios esperaban redirección directa a un dashboard o "Mi perfil" tras iniciar sesión. |
| **T3** | Inscripción a Curso | **Cumplimiento:** Moderado (hubo abandonos y ayuda).<br>**Tiempo:** 55s (Mín) a 280s (Máx).<br>**Errores comunes:** Clics en zonas muertas de la tarjeta. | • Jerarquía visual saturada en la tarjeta del curso; el botón de "Inscribirse" no resaltaba lo suficiente.<br>• Demanda por herramientas de búsqueda por nombre, filtros por fecha o categoría.<br>• Confusión sobre el significado de los colores de estatus (verde = ¿disponible o inscrito?). |
| **T4** | Visualización de Estatus | **Cumplimiento:** Alto a Parcial.<br>**Tiempo:** 12s (Mín) a 88s (Máx).<br>**Errores comunes:** Navegación a pestañas incorrectas. | • Difícil localización inicial del área para consultar las inscripciones.<br>• Ambigüedad en la interpretación de los íconos (el reloj se confundió; el verde y gris eran similares).<br>• Los usuarios más técnicos solicitaron opciones para exportar historial o filtrar estatus. |

**Conclusiones de la Prueba:**
Los datos demostraron que si bien el "Happy Path" funciona adecuadamente para usuarios técnicos (como Carlos), la interfaz carece de apoyos cognitivos suficientes (mensajes de éxito, formatos guiados, filtros de búsqueda y diferenciación de colores) que penalizaron severamente a usuarios de mayor edad o perfil menos tecnológico (Candy, Sofía, Martha), lo que confirma la necesidad de integrar validaciones en tiempo real y divulgación progresiva.

---

## 5. Lecciones Aprendidas (Conclusiones)

**Contraste Teórico vs. Implementación:**
*   Se comprobó que la regla heurística "Menos es Más" de Nielsen puede ser contraproducente si no está fundamentada en la investigación de usuarios. Una interfaz excesivamente minimalista sin claridad genera barreras masivas para usuarios no tecnológicos.
*   El diseño debe priorizar la "Mayor Claridad" sobre el minimalismo puro.

**Errores Cometidos y Mejoras:**
*   *Error inicial:* Forzar el registro antes de proveer valor (bloqueo de login). Se solucionó abriendo el catálogo. En futuras implementaciones, siempre se debe priorizar el patrón de *Divulgación Progresiva*.
*   *Mejora futura:* Incorporar controles *hover* más descriptivos para reducir la carga cognitiva al navegar el catálogo.

**Aprendizajes y Adquisición de Habilidades:**
*   El objetivo de la asignatura se cumplió al comprender que el rol del desarrollador no es solo "construir pantallas", sino intervenir, contextualizar y dotar de accesibilidad y empatía a la interfaz para un contexto institucional. Se adquirieron sólidas habilidades prácticas en metodologías de pruebas (SUS, Think Aloud) y herramientas de accesibilidad (WAVE).

---

## 6. Presentación del Avance

A lo largo del proyecto, la presentación de la información evolucionó para reflejar la madurez técnica del equipo:
*   **Material y Formato:** Se utilizaron prototipos navegables desplegados en vivo, complementados con documentación de requerimientos alojada directamente en Markdown dentro del repositorio. Existió soporte multimedia (como la creación de videos de presentación en las entregas iniciales).
*   **Uso del Tiempo y Atención:** Las demostraciones se centraron en evidenciar el flujo de usuario (*Happy Path*) frente a la audiencia, garantizando una presentación estructurada que contrastaba la fricción anterior con las soluciones interactivas actuales.

---

## 7. Trabajo en Equipo

El monitoreo y proceso de trabajo se gestionó rigurosamente a través del repositorio Git, utilizando un flujo estructurado de ramas por entregas (`1st-Delivery` a `5th-Delivery`) que garantizó un desarrollo paralelo y revisiones efectivas.

**Roles y Porcentajes de Contribución Objetiva:**

*   **Samuel Blanco (~40%):** Liderazgo en el desarrollo web. Responsable de la ejecución técnica de prototipos (v0 y final), configuración del entorno y traducciones al inglés.
*   **Adriel Yerbes (~25%):** Gestión de entregas, consolidación de la bitácora, manejo de documentación metodológica y sincronización de los RNF.
*   **Aldo (~20%):** Arquitectura de pruebas. Autor principal del documento extendido de pruebas de Requisitos No Funcionales y análisis teórico de patrones de interfaz.
*   **Sebastián Leal (~15%):** Bases metodológicas. Encargado de la definición teórica temprana, metodología de participantes y heurísticas.

