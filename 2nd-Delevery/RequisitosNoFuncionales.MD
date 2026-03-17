# Requisitos No Funcionales
## Interfaz de Usuario y HCI - Público General

---

## 1. USABILIDAD

### RNF-UI-001: Tiempo de Completitud de Inscripción
El sistema debe permitir que un usuario complete el proceso completo de solicitud de inscripción (CU-PG-004) en un máximo de 15 minutos, asumiendo que el usuario tiene todos los documentos requeridos preparados.

**Métrica de verificación:** Tiempo promedio medido en pruebas de usabilidad con 10 usuarios.
**Criterio de aceptación:** 80% de usuarios completan el proceso en 15 minutos o menos.

### RNF-UI-002: Curva de Aprendizaje
Un usuario nuevo sin capacitación previa debe poder completar exitosamente las siguientes tareas en su primer uso:
- Crear cuenta (CU-PG-002)
- Solicitar inscripción a un evento (CU-PG-004)
- Consultar estado de solicitud (CU-PG-007)

**Métrica de verificación:** Tasa de éxito en primera interacción sin ayuda externa.
**Criterio de aceptación:** 90% de usuarios completan tareas sin asistencia.

### RNF-UI-003: Tasa de Error
La tasa de errores de usuario durante el llenado de formularios debe ser inferior al 5% por campo.

**Métrica de verificación:** Número de errores capturados por validaciones / total de campos completados.
**Criterio de aceptación:** Tasa de error < 5% en pruebas con 20 usuarios.

### RNF-UI-004: Claridad de Mensajes de Error
Todos los mensajes de error deben:
- Indicar claramente qué está mal
- Explicar cómo corregirlo
- Estar redactados en lenguaje no técnico

**Métrica de verificación:** Evaluación heurística según principios de Nielsen.
**Criterio de aceptación:** 100% de mensajes de error cumplen los tres criterios.

### RNF-UI-005: Recuperación de Errores
El usuario debe poder deshacer o corregir cualquier acción antes de la confirmación final.

**Métrica de verificación:** Verificación funcional de flujos.
**Criterio de aceptación:** Todas las acciones críticas tienen confirmación previa.

---

## 2. ACCESIBILIDAD

### RNF-UI-006: Conformidad WCAG 2.1 Nivel AA
La interfaz debe cumplir con las pautas WCAG 2.1 nivel AA como mínimo.

**Métrica de verificación:** Auditoría con herramientas automatizadas (WAVE, Axe) y revisión manual.
**Criterio de aceptación:** 0 errores críticos de nivel A y AA en auditoría.

### RNF-UI-007: Contraste de Color
Todos los textos deben tener una relación de contraste mínima de:
- 4.5:1 para texto normal
- 3:1 para texto grande (18pt o 14pt negrita)

**Métrica de verificación:** Análisis con herramienta de contraste (WebAIM Contrast Checker).
**Criterio de aceptación:** 100% de textos cumplen ratios mínimos.

### RNF-UI-008: Navegación por Teclado
Todas las funcionalidades del sistema deben ser accesibles usando únicamente el teclado, sin requerir mouse.

**Métrica de verificación:** Prueba manual de navegación completa por teclado.
**Criterio de aceptación:** 100% de funcionalidades accesibles vía teclado con orden lógico de tabulación.

### RNF-UI-009: Tamaño de Objetivos Táctiles
Los elementos interactivos (botones, enlaces, campos de formulario) deben tener un área mínima de 44x44 píxeles en dispositivos móviles.

**Métrica de verificación:** Medición de elementos en inspector de navegador.
**Criterio de aceptación:** 100% de elementos interactivos cumplen tamaño mínimo.

### RNF-UI-010: Etiquetado Semántico
Todos los formularios deben utilizar etiquetas HTML semánticas apropiadas (label, fieldset, legend) asociadas correctamente a sus controles.

**Métrica de verificación:** Revisión de código HTML y prueba con lector de pantalla.
**Criterio de aceptación:** 100% de campos de formulario tienen etiquetas asociadas correctamente.

---

## 3. RENDIMIENTO DE INTERFAZ

### RNF-UI-011: Tiempo de Carga Inicial
La página de inicio de sesión debe cargar completamente en menos de 2 segundos con conexión 3G.

**Métrica de verificación:** Lighthouse Performance Score, pruebas en Chrome DevTools con throttling 3G.
**Criterio de aceptación:** Tiempo de carga < 2 segundos en 90% de las pruebas.

### RNF-UI-012: Tiempo de Respuesta de Interfaz
Las interacciones de usuario (clicks, navegación entre vistas) deben proporcionar feedback visual en menos de 100 milisegundos.

**Métrica de verificación:** Medición de tiempo entre evento y renderizado de respuesta.
**Criterio de aceptación:** 95% de interacciones responden en < 100ms.

### RNF-UI-013: Carga Progresiva
El sistema debe mostrar contenido principal antes de 1 segundo, incluso si elementos secundarios aún están cargando.

**Métrica de verificación:** First Contentful Paint (FCP) en Lighthouse.
**Criterio de aceptación:** FCP < 1 segundo en conexión 3G.

### RNF-UI-014: Indicadores de Carga
Cualquier operación que tome más de 1 segundo debe mostrar un indicador visual de progreso o carga.

**Métrica de verificación:** Revisión manual de flujos.
**Criterio de aceptación:** 100% de operaciones > 1s tienen indicador visual.

---

## 4. DISEÑO RESPONSIVO

### RNF-UI-015: Breakpoints Soportados
El sistema debe proporcionar experiencias optimizadas para los siguientes rangos de viewport:
- Móvil: 320px - 767px
- Tablet: 768px - 1023px
- Desktop: 1024px en adelante

**Métrica de verificación:** Pruebas visuales en dispositivos reales y emuladores.
**Criterio de aceptación:** Layout funcional y legible en todos los breakpoints sin scroll horizontal.

### RNF-UI-016: Adaptación de Contenido
Los elementos de interfaz deben reorganizarse (no solo redimensionarse) apropiadamente según el tamaño de pantalla.

**Métrica de verificación:** Revisión visual en diferentes dispositivos.
**Criterio de aceptación:** Navegación, formularios y tablas se adaptan sin pérdida de funcionalidad.

### RNF-UI-017: Imágenes Responsivas
Las imágenes deben cargarse en resoluciones apropiadas según el dispositivo para optimizar tiempo de carga.

**Métrica de verificación:** Verificación de implementación de srcset/picture.
**Criterio de aceptación:** Imágenes utilizan srcset o picture element.

### RNF-UI-018: Touch-Friendly en Móvil
Los elementos interactivos en móvil deben tener espaciado suficiente para evitar clicks accidentales (mínimo 8px de separación).

**Métrica de verificación:** Revisión visual y pruebas en dispositivos táctiles.
**Criterio de aceptación:** Separación mínima de 8px entre elementos interactivos adyacentes.

---

## 5. CONSISTENCIA VISUAL

### RNF-UI-019: Sistema de Diseño
Todos los componentes visuales deben seguir un sistema de diseño consistente con paleta de colores, tipografía y espaciado definidos.

**Métrica de verificación:** Auditoría de diseño, revisión de guía de estilos.
**Criterio de aceptación:** 100% de pantallas utilizan únicamente componentes del sistema de diseño.

### RNF-UI-020: Tipografía
El sistema debe utilizar máximo 2 familias tipográficas con tamaños de fuente definidos en una escala consistente.

**Métrica de verificación:** Inspección de CSS.
**Criterio de aceptación:** No más de 2 font-families y máximo 6 tamaños de texto diferentes.

### RNF-UI-021: Paleta de Colores
El sistema debe utilizar una paleta definida de máximo 8 colores primarios más sus variaciones tonales.

**Métrica de verificación:** Inspección de CSS y variables de color.
**Criterio de aceptación:** Todos los colores utilizados están definidos en la paleta del sistema.

### RNF-UI-022: Iconografía Consistente
Los iconos deben provenir de una sola biblioteca y mantener peso visual y estilo consistentes.

**Métrica de verificación:** Revisión visual de todos los iconos.
**Criterio de aceptación:** 100% de iconos de la misma biblioteca con estilo consistente.

---

## 6. FEEDBACK E INTERACCIÓN

### RNF-UI-023: Confirmación de Acciones
Todas las acciones críticas (enviar solicitud, realizar pago, eliminar información) deben requerir confirmación explícita del usuario.

**Métrica de verificación:** Revisión de flujos de usuario.
**Criterio de aceptación:** 100% de acciones destructivas o críticas tienen modal de confirmación.

### RNF-UI-024: Estados Visuales de Elementos Interactivos
Todos los elementos interactivos deben tener estados visuales diferenciados para:
- Default
- Hover
- Focus
- Active
- Disabled

**Métrica de verificación:** Inspección visual de componentes.
**Criterio de aceptación:** Todos los botones y enlaces implementan los 5 estados.

### RNF-UI-025: Feedback de Formularios
Los campos de formulario deben proporcionar validación en tiempo real (inline) además de validación al envío.

**Métrica de verificación:** Prueba funcional de formularios.
**Criterio de aceptación:** Validación inline en 100% de campos con restricciones.

### RNF-UI-026: Mensajes de Éxito
Todas las acciones exitosas deben mostrar un mensaje de confirmación visual claramente identificable.

**Métrica de verificación:** Revisión de flujos completos.
**Criterio de aceptación:** Mensaje de éxito visible durante mínimo 3 segundos o hasta que usuario lo cierre.

### RNF-UI-027: Progress Indicators
Los procesos de múltiples pasos (como inscripción) deben mostrar indicador visual de progreso mostrando paso actual y pasos restantes.

**Métrica de verificación:** Revisión de flujos multi-paso.
**Criterio de aceptación:** Barra o stepper de progreso visible en todos los flujos de más de 2 pasos.

---

## 7. NAVEGACIÓN

### RNF-UI-028: Profundidad de Navegación
Cualquier funcionalidad del sistema debe ser accesible en máximo 3 clics desde el dashboard principal.

**Métrica de verificación:** Mapeo de sitemap y conteo de clics.
**Criterio de aceptación:** 100% de funcionalidades accesibles en ≤ 3 clics.

### RNF-UI-029: Breadcrumbs
Las páginas de contenido profundo deben incluir breadcrumbs que indiquen la ubicación actual y permitan navegación rápida a niveles superiores.

**Métrica de verificación:** Revisión de vistas de nivel 3 o superior.
**Criterio de aceptación:** Breadcrumbs presentes en todas las vistas de nivel 3+.

### RNF-UI-030: Navegación Consistente
El menú principal de navegación debe mantener la misma posición y estructura en todas las páginas del sistema.

**Métrica de verificación:** Revisión visual de navegación en diferentes vistas.
**Criterio de aceptación:** Navegación en misma posición y con mismos elementos en 100% de vistas.

### RNF-UI-031: Indicador de Ubicación Actual
El elemento de navegación correspondiente a la página actual debe estar visualmente diferenciado (active state).

**Métrica de verificación:** Inspección visual de navegación.
**Criterio de aceptación:** Estado activo visible en 100% de las páginas.

---

## 8. CONTENIDO Y LEGIBILIDAD

### RNF-UI-032: Longitud de Línea
Las líneas de texto no deben exceder 80 caracteres (aproximadamente 600px) para óptima legibilidad.

**Métrica de verificación:** Medición de ancho de contenedores de texto.
**Criterio de aceptación:** Bloques de texto principales tienen max-width de 600-800px.

### RNF-UI-033: Espaciado de Línea
El interlineado (line-height) del texto de cuerpo debe ser mínimo 1.5 veces el tamaño de fuente.

**Métrica de verificación:** Inspección de CSS.
**Criterio de aceptación:** line-height ≥ 1.5 en todos los párrafos.

### RNF-UI-034: Jerarquía Visual
El sistema debe utilizar tamaño, peso y color de texto para establecer jerarquía clara de información.

**Métrica de verificación:** Evaluación heurística de jerarquía.
**Criterio de aceptación:** Diferenciación clara entre H1, H2, H3 y texto de cuerpo en todas las vistas.

### RNF-UI-035: Lenguaje Claro
Las instrucciones y etiquetas deben estar redactadas en lenguaje simple, evitando jerga técnica o administrativa.

**Métrica de verificación:** Revisión de contenido con usuarios no técnicos.
**Criterio de aceptación:** 90% de usuarios entienden instrucciones sin necesidad de aclaración.

---

## 9. ESPECÍFICOS DE CASOS DE USO

### RNF-UI-036: Tracking Visual de Estado (CU-PG-007)
La vista de "Estado de Solicitudes" debe incluir representación visual tipo stepper o barra de progreso mostrando claramente:
- Etapa actual
- Etapas completadas
- Etapas pendientes

**Métrica de verificación:** Prueba de usuario - identificación de estado actual.
**Criterio de aceptación:** 95% de usuarios identifican correctamente la etapa actual sin leer texto explicativo.

### RNF-UI-037: Carga de Documentos (CU-PG-006)
El componente de carga de archivos debe:
- Mostrar preview de archivos antes de subir
- Indicar formatos aceptados claramente
- Mostrar progreso de carga si archivo > 1MB
- Confirmar carga exitosa con marca visual

**Métrica de verificación:** Prueba funcional del componente.
**Criterio de aceptación:** Cumple los 4 requisitos en pruebas.

### RNF-UI-038: Formulario de Inscripción (CU-PG-004)
El formulario de solicitud de inscripción debe:
- Agrupar campos relacionados visualmente
- Indicar campos obligatorios con asterisco (*)
- Mostrar contador de caracteres en campos con límite
- Permitir guardar progreso

**Métrica de verificación:** Evaluación heurística y prueba de usuario.
**Criterio de aceptación:** Cumple los 4 requisitos y usuarios completan formulario sin abandonar.

### RNF-UI-039: Dashboard Personal (CU-PG-009)
La vista "Mis Eventos" debe presentar información en formato de tarjetas (cards) con:
- Título del evento claramente visible
- Estado visual (próximo/en curso/finalizado)
- Fechas destacadas
- Acción primaria obvia (acceder/descargar constancia)

**Métrica de verificación:** Evaluación visual y eye-tracking si disponible.
**Criterio de aceptación:** Usuarios identifican información clave en < 3 segundos.

### RNF-UI-040: Proceso de Pago (CU-PG-005)
El flujo de pago debe:
- Mostrar resumen de compra antes de pagar
- Indicar métodos de pago aceptados con iconos reconocibles
- Mostrar indicadores de seguridad (candado SSL)
- Confirmar pago exitoso con pantalla dedicada

**Métrica de verificación:** Prueba de usuario en ambiente de pruebas.
**Criterio de aceptación:** 0 abandonos por confusión en pruebas con 10 usuarios.

---

## 10. NOTIFICACIONES Y ALERTAS

### RNF-UI-041: Jerarquía de Notificaciones
El sistema debe diferenciar visualmente entre:
- Éxito (verde)
- Advertencia (amarillo/naranja)
- Error (rojo)
- Información (azul)

**Métrica de verificación:** Revisión de sistema de notificaciones.
**Criterio de aceptación:** Colores consistentes según tipo en 100% de notificaciones.

### RNF-UI-042: Posición de Notificaciones
Las notificaciones temporales deben aparecer en ubicación consistente (ej: superior derecha) sin bloquear contenido crítico.

**Métrica de verificación:** Prueba visual de notificaciones.
**Criterio de aceptación:** Notificaciones en misma posición y no bloquean elementos interactivos.

### RNF-UI-043: Duración de Notificaciones
Las notificaciones no críticas deben desaparecer automáticamente después de 5-7 segundos, con opción de cerrar manualmente.

**Métrica de verificación:** Prueba temporal de notificaciones.
**Criterio de aceptación:** Auto-dismiss en 5-7 segundos más botón de cerrar.

---

## 11. TABLA RESUMEN DE VERIFICACIÓN

| ID | Categoría | Requisito | Método de Verificación | Criterio Cuantificable |
|----|-----------|-----------|------------------------|------------------------|
| RNF-UI-001 | Usabilidad | Tiempo inscripción | Prueba usuario | ≤ 15 minutos (80%) |
| RNF-UI-002 | Usabilidad | Curva aprendizaje | Tasa de éxito | ≥ 90% sin ayuda |
| RNF-UI-006 | Accesibilidad | WCAG 2.1 AA | Auditoría WAVE/Axe | 0 errores A/AA |
| RNF-UI-007 | Accesibilidad | Contraste color | WebAIM Checker | 4.5:1 (texto) |
| RNF-UI-009 | Accesibilidad | Área táctil | Medición px | ≥ 44x44px |
| RNF-UI-011 | Rendimiento | Carga inicial | Lighthouse | < 2 segundos |
| RNF-UI-012 | Rendimiento | Respuesta UI | Medición tiempo | < 100ms (95%) |
| RNF-UI-015 | Responsivo | Breakpoints | Prueba visual | 320-767-1024px |
| RNF-UI-028 | Navegación | Profundidad | Conteo clics | ≤ 3 clics |
| RNF-UI-036 | Específico | Tracking visual | Prueba usuario | 95% identifican estado |

---

## NOTAS DE IMPLEMENTACIÓN

**Priorización Sugerida:**
- Críticos (implementar primero): RNF-UI-001, 002, 006, 007, 011, 028, 036
- Importantes (siguiente fase): RNF-UI-009, 012, 015, 023, 027
- Deseables (refinamiento): RNF-UI-020, 021, 032, 033

**Herramientas de Verificación Recomendadas:**
- WAVE (accesibilidad)
- Lighthouse (rendimiento, accesibilidad)
- WebAIM Contrast Checker (contraste)
- BrowserStack (responsivo)
- Hotjar o similar (pruebas de usuario)