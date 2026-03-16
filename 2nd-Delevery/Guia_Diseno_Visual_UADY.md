# Guía de Diseño Visual del Sistema
## Alineación con la Identidad Institucional de la Universidad Autónoma de Yucatán

> Este documento describe la apariencia visual del sistema de gestión de eventos universitarios, definiendo cómo cada elemento de la interfaz debe expresar y reforzar la identidad de la UADY, con base en el **Manual de Identidad Universitaria 2023**.

---

# 1. ESPÍRITU VISUAL DEL SISTEMA

El sistema debe sentirse como una **extensión digital de la UADY**. Cualquier persona que lo use debe reconocer de inmediato que pertenece a la institución, sin necesidad de leer el nombre completo. La sobriedad académica, la autoridad institucional y la calidez humana del lema *"Luz, Ciencia y Verdad"* deben permear cada pantalla.

La paleta azul-dorado no es solo decoración: el **azul** transmite confianza, seriedad y pertenencia institucional; el **dorado** connota distinción, logro y relevancia — exactamente lo que representa participar en un evento universitario. El sistema debe usar estos colores con inteligencia: el azul como estructura y el dorado como énfasis.

---

# 2. FUNDAMENTOS DE COLOR

## 2.1 Los dos colores que lo gobiernan todo

```
┌─────────────────────────────────────────────────────────────┐
│  AZUL INSTITUCIONAL          DORADO INSTITUCIONAL           │
│  Pantone 295 C               Pantone 1245 C                 │
│  #192E4C                     #C89211                        │
│  RGB: 25, 46, 76             RGB: 200, 146, 17              │
│  CMYK: 100/81/41/42          CMYK: 19/41/98/8               │
│                                                             │
│  USO: Fondos, headers,       USO: Acentos, énfasis,        │
│  botones primarios,          hover, indicadores activos,    │
│  navegación, cards           lema, focus ring               │
└─────────────────────────────────────────────────────────────┘
```

## 2.2 Variaciones tonales del azul

El azul institucional se puede aclarar progresivamente para construir profundidad visual sin salir de la identidad:

| Token | HEX | Descripción visual |
|-------|-----|--------------------|
| `--azul-100` | `#192E4C` | Azul pleno. Fondos de secciones principales, navbar, footers, cabeceras de tarjetas |
| `--azul-80` | `#476080` | Azul medio. Textos secundarios sobre fondos claros, iconos de apoyo |
| `--azul-60` | `#7892AA` | Azul claro-medio. Bordes de componentes, separadores, líneas divisorias |
| `--azul-20` | `#D8E1EA` | Azul muy claro. Fondos de filas alternas en tablas, fondo de inputs deshabilitados |
| `--azul-10` | `#EBF0F5` | Azul casi blanco. Fondo general de la aplicación en modo claro, fondo de secciones secundarias |

## 2.3 Variaciones tonales del dorado

| Token | HEX | Descripción visual |
|-------|-----|--------------------|
| `--dorado-100` | `#C89211` | Dorado pleno. Acentos, lema, indicadores activos en el stepper, hover de botones |
| `--dorado-80` | `#D6A833` | Dorado claro. Badges, etiquetas, hover suave en modo oscuro |
| `--dorado-20` | `#F5E9C8` | Dorado suave. Fondo de notificaciones de advertencia, fondo de chips "en proceso" |

## 2.4 Colores semánticos de estado

Estos colores complementan la paleta para comunicar estados del sistema. Se eligen para respetar la convención universal de colores de estado y, al mismo tiempo, no competir visualmente con el azul y dorado institucionales:

| Estado | Color | HEX | Relación con la paleta UADY |
|--------|-------|-----|----------------------------|
| Éxito | Verde | `#2E7D4F` | Neutro respecto a la paleta; no compite con el azul |
| Advertencia | **Dorado institucional** | `#C89211` | El dorado UADY cumple esta función naturalmente |
| Error / Crítico | Rojo | `#C62828` | Neutro semántico universal |
| Información | **Azul institucional** | `#192E4C` | El azul UADY como color informativo refuerza identidad |

> **Decisión de diseño clave:** La advertencia usa el color dorado institucional `#C89211`. Esto no es casualidad — el dorado connota atención y relevancia sin la alarma del rojo, y al mismo tiempo refuerza visualmente la identidad de la UADY en cada interacción del usuario con el sistema.

## 2.5 Cómo NO usar los colores institucionales

- ❌ El dorado **nunca** como color de texto corrido sobre fondo blanco (contraste insuficiente: 2.9:1)
- ❌ El azul y el dorado juntos en botones del mismo nivel jerárquico (uno debe dominar)
- ❌ Degradados entre ambos colores (prohibido expresamente en el manual de identidad)
- ❌ Efectos de brillo, biselado o sombra sobre elementos con color institucional
- ❌ Colores externos a la paleta sin aprobación de la CGCI

---

# 3. TIPOGRAFÍA

## 3.1 La fuente institucional: Lucida Bright

La UADY ha elegido **Lucida Bright** como su tipografía oficial para todos sus materiales. Es una fuente serif de corte clásico que transmite la seriedad académica de la institución. El sistema digital la usa como columna vertebral tipográfica.

```
Lucida Bright Regular    → Logotipo "UADY", etiquetas de nav, texto de interfaz general
Lucida Bright Demibold   → Encabezados H1–H3, labels de formularios, nombres de sección
Lucida Bright Italic     → Notas al margen, citas dentro del cuerpo de texto
Lucida Bright Demibold Italic → Lema "Luz, Ciencia y Verdad", citas institucionales
```

## 3.2 Escala tipográfica del sistema

| Nivel | Tamaño | Variante | Color | Uso |
|-------|--------|----------|-------|-----|
| Display / H1 | 32 px | Demibold | `#192E4C` | Título principal de cada vista (ej. "Mis Eventos", "Nueva Inscripción") |
| H2 | 24 px | Demibold | `#192E4C` | Cabeceras de sección dentro de una vista |
| H3 | 20 px | Demibold | `#476080` | Subtítulos, nombres de grupos en formularios |
| Cuerpo grande | 18 px | Regular | `#3A3A3A` | Párrafos de introducción, instrucciones destacadas |
| Cuerpo | 16 px | Regular | `#3A3A3A` | Todo el texto de contenido estándar |
| Texto pequeño | 14 px | Regular | `#476080` | Metadatos, fechas, ayudas contextuales |
| Label / Badge | 12 px | Demibold | Variable | Etiquetas de estado, chips, categorías |

## 3.3 Regla de jerarquía tipográfica en pantalla

Una vista típica del sistema nunca debe mezclar más de **tres niveles tipográficos simultáneos** en la misma área visual. La jerarquía se construye así:

```
[ H1 en azul pleno         ]  ← Título de la vista: 1 único por página
  [ H2 en azul pleno       ]  ← Sección: 2–4 por página
    [ Cuerpo en gris oscuro ]  ← Contenido: sin límite
    [ Texto pequeño en azul ]  ← Metadatos de apoyo
```

El **dorado solo aparece** en etiquetas de estado activo, badges, el indicador de foco de teclado, y en elementos que referencian el lema o la identidad formal de la institución.

---

# 4. LA FIRMA INSTITUCIONAL EN LA INTERFAZ

## 4.1 Estructura de la firma

La firma institucional se compone de tres elementos inseparables:

```
[ Escudo (Isotipo) ] [ UADY ] [ UNIVERSIDAD AUTÓNOMA DE YUCATÁN ]
      Azul              Azul          Dorado
```

En fondo oscuro azul (navbar), todos los elementos pasan a **blanco**.

## 4.2 Ubicación en el sistema

La firma institucional **siempre ocupa el cuadrante superior izquierdo** de la pantalla, dentro del navbar. Es el primer elemento visual que el usuario ve al cargar cualquier vista. Su presencia constante ancla toda la experiencia dentro del universo institucional de la UADY.

```
┌──────────────────────────────────────────────────────────────────┐
│ [Escudo][UADY]  Inicio  Eventos  Mis Inscripciones  Perfil  🔔  │  ← Navbar azul #192E4C
└──────────────────────────────────────────────────────────────────┘
```

- En **pantallas ≥ 1024px:** Firma institucional completa (escudo + UADY + descriptivo)
- En **tablets 768–1023px:** Escudo + "UADY" sin descriptivo
- En **móvil < 768px:** Solo el escudo (isotipo), centrado o a la izquierda

## 4.3 Qué NO puede aparecer junto a la firma

- Ningún elemento gráfico puede colocarse a la izquierda de la firma institucional
- Ningún elemento puede superar la altura de la firma en su cuadrante
- La textura de arcos NO puede sobreponerse directamente al área de la firma
- El área de seguridad alrededor de la firma es de 2X libre en todas direcciones (donde X = altura del descriptivo "UNIVERSIDAD AUTÓNOMA DE YUCATÁN")

---

# 5. LA TEXTURA DE ARCOS — GRÁFICO DE ACOMPAÑAMIENTO 2023

El gráfico de acompañamiento oficial de la identidad UADY 2023 es una **textura abstracta inspirada en los arcos del Centro Cultural Universitario**, el edificio más icónico de la institución. Es el único elemento decorativo autorizado del sistema.

## 5.1 Cómo se ve

La textura reproduce la silueta de los arcos coloniales del edificio central de forma abstracta y geométrica. Crea ritmo visual sin distraer del contenido. Se aplica siempre en los colores institucionales.

## 5.2 Reglas de uso por contexto

| Pantalla / Componente | Versión | Opacidad | Posición |
|----------------------|---------|----------|----------|
| Pantalla de login / bienvenida | Azul + Dorado (completa) | 100% | Mitad derecha del fondo, fuera del área del formulario |
| Header de sección (hero) | Solo azul | 25–30% | Parte derecha del banner, nunca sobre texto |
| Footer institucional | Solo dorado | 15% | Franja decorativa en la parte inferior |
| Cards de eventos destacados | Solo azul | 8–10% | Fondo interior de la card, muy sutil |
| Correos institucionales | Solo dorado | 20% | Franja en el footer del correo |
| Fondo del dashboard | No se usa | — | No aplica — demasiado ruido visual |

> La textura es **decorativa, nunca funcional**. Nunca debe confundirse con un elemento interactivo ni reducir la legibilidad del contenido superpuesto.

---

# 6. DESCRIPCIÓN VISUAL DE LOS COMPONENTES PRINCIPALES

## 6.1 Navbar (Barra de navegación principal)

La navbar es la pieza más institucional del sistema. Su apariencia transmite inmediatamente que se está dentro de un producto oficial de la UADY.

**Aspecto visual:**
- Fondo: azul institucional sólido `#192E4C`
- Altura: 64px en desktop, 56px en móvil
- Firma institucional: a la izquierda, en versión blanca
- Links de navegación: tipografía Lucida Bright Regular 15px, color blanco al 85%
- Link activo: color blanco 100% + línea inferior de 3px en dorado `#C89211`
- Link hover: color blanco 100% + transición suave 200ms
- Icono de notificaciones y avatar de perfil: a la derecha, en blanco
- En móvil: menú hamburguesa en blanco; al abrir, panel lateral con fondo `#192E4C`

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
 [🛡 UADY]   Inicio   Eventos   Inscripciones   Ayuda   [🔔] [👤]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
             ̄ ̄ ̄ ̄ ̄ ̄ ← línea dorada bajo sección activa
```

## 6.2 Botones

Los botones son los principales puntos de interacción y deben comunicar con claridad la jerarquía de acción usando la paleta institucional.

### Botón Primario (acción principal)
- **Reposo:** Fondo `#192E4C`, texto blanco, border-radius 6px, padding 12×24px
- **Hover:** Fondo `#C89211`, texto `#192E4C` — el dorado aparece para señalar que la acción está disponible
- **Focus:** Borde exterior de 3px en `#C89211` (accesibilidad de teclado)
- **Activo (click):** Fondo `#0D1B2E` (azul más oscuro), escala ligera 0.98
- **Deshabilitado:** Fondo `#CCCCCC`, texto `#888888`, cursor not-allowed

### Botón Secundario (acción alternativa)
- **Reposo:** Fondo transparente, borde 2px `#192E4C`, texto `#192E4C`
- **Hover:** Fondo `#EBF0F5` (azul 10%), borde `#192E4C`
- **Focus:** Borde exterior adicional 3px `#C89211`

### Botón de Texto / Link acción
- **Reposo:** Sin fondo ni borde, texto `#192E4C`, underline
- **Hover:** Texto `#C89211`, underline

### Botón Destructivo (eliminar, cancelar inscripción)
- **Reposo:** Fondo `#C62828`, texto blanco
- **Hover:** Fondo `#B71C1C`, texto blanco
- Siempre acompañado de un modal de confirmación (RNF-UI-023)

## 6.3 Formularios e Inputs

Los formularios son la parte más usada del sistema. Su diseño debe ser limpio, claro y coherente con la identidad.

**Input en reposo:**
- Borde inferior o contorno: 1px `#CCCCCC`
- Label: Lucida Bright Demibold 14px, color `#192E4C`
- Placeholder: Regular 16px, color `#999999`
- Fondo: blanco `#FFFFFF`

**Input enfocado (activo):**
- Borde o contorno: 2px `#C89211` (dorado institucional)
- Label: "flota" hacia arriba, se mantiene en `#192E4C`
- El dorado en el borde activo es intencional: refuerza identidad mientras señala el campo activo

**Input con error:**
- Borde: 2px `#C62828`
- Mensaje de error debajo: texto 13px color `#C62828`, con ícono ⚠ a la izquierda
- Fondo de input: `#FFF5F5` suave

**Input con éxito (válido):**
- Borde: 2px `#2E7D4F`
- Ícono de check verde a la derecha del campo

**Campos obligatorios:**
- Asterisco `*` en color dorado `#C89211` junto al label
- El dorado del asterisco es coherente con su uso semántico como advertencia/atención

**Agrupación de campos (fieldset):**
- Cada grupo de campos relacionados se enmarca con un `fieldset`
- El `legend` usa Lucida Bright Demibold 16px color `#192E4C`
- Línea separadora entre grupos: 1px `#D8E1EA`

## 6.4 Tarjetas (Cards) de eventos

Las cards son los elementos de presentación más frecuentes en el dashboard y en el catálogo de eventos.

```
┌──────────────────────────────────────────┐
│  ▓▓▓▓ Franja color según estado ▓▓▓▓▓▓▓  │  ← 6px franja superior (azul/dorado/gris)
│                                          │
│  TÍTULO DEL EVENTO                       │  ← Lucida Bright Demibold 18px, azul #192E4C
│  Facultad de Ingeniería · 20 Mar 2026    │  ← Regular 14px, azul-80 #476080
│                                          │
│  ░░░░░░░░░░░░░ textura arcos sutil ░░░  │  ← Azul al 8% de opacidad, fondo
│                                          │
│  [Chip: PRÓXIMO]          Cupo: 45/80    │  ← Chip dorado, texto azul
│                                          │
│  [    Inscribirse    ]   Ver detalle →   │  ← Botón primario azul + link dorado
└──────────────────────────────────────────┘
```

**Colores de la franja superior según estado del evento:**
- Próximo (disponible): `#192E4C` (azul institucional)
- En curso: `#C89211` (dorado institucional)
- Finalizado: `#7892AA` (azul-60, tono apagado)
- Cancelado: `#CCCCCC` (gris neutro)

**Chip de estado:**
| Estado | Fondo | Texto | Descripción visual |
|--------|-------|-------|-------------------|
| Próximo | `#EBF0F5` | `#192E4C` | Azul suave institucional |
| En curso | `#F5E9C8` | `#C89211` | Dorado suave — evento vivo |
| Inscrito | `#EBF0F5` | `#2E7D4F` | Verde sobre fondo azul claro |
| Finalizado | `#F5F5F5` | `#7892AA` | Gris apagado |

## 6.5 Stepper de progreso (inscripción multi-paso)

El stepper guía al usuario a través del proceso de inscripción y debe ser inmediatamente legible.

```
  ●━━━━━━━━━━━◎━━━━━━━━━━━○━━━━━━━━━━━○
  1           2           3           4
  Datos     Documentos   Pago      Confirmación
  ✓ listo   ← aquí       pendiente  pendiente
```

- **Paso completado (●):** Círculo relleno `#192E4C`, checkmark blanco en el interior
- **Paso actual (◎):** Círculo borde 3px `#C89211`, número `#192E4C` en el interior, label en Demibold
- **Paso pendiente (○):** Círculo borde 1px `#CCCCCC`, número `#999999`
- **Línea conectora:** `#D8E1EA` para tramos pendientes → `#192E4C` para tramos completados

## 6.6 Notificaciones / Toasts

Las notificaciones aparecen en la esquina superior derecha y desaparecen automáticamente a los 5–7 segundos.

```
┌──────────────────────────────────────────┐
│  ✓  Su inscripción fue enviada con éxito │  ← Fondo #2E7D4F, texto blanco
│     Revise su correo para confirmación   │     Icono check blanco a la izquierda
│                                    [✕]  │     X en blanco para cerrar
└──────────────────────────────────────────┘

┌──────────────────────────────────────────┐
│  ⚠  El plazo de inscripción cierra hoy  │  ← Fondo #C89211 (dorado UADY), texto #192E4C
│     Completa tu solicitud antes de hoy  │     Usa el dorado institucional como advertencia
│                                    [✕]  │
└──────────────────────────────────────────┘

┌──────────────────────────────────────────┐
│  ✗  Error al procesar el pago           │  ← Fondo #C62828, texto blanco
│     Verifique sus datos e intente again │
│                                    [✕]  │
└──────────────────────────────────────────┘

┌──────────────────────────────────────────┐
│  ℹ  Nuevo evento disponible en tu área  │  ← Fondo #192E4C (azul UADY), texto blanco
│     Conferencia de Ingeniería · 25 Mar  │     El azul institucional como info
│                                    [✕]  │
└──────────────────────────────────────────┘
```

## 6.7 Modales de confirmación

Los modales se usan para acciones críticas. Son sobrios, claros y reflejan la formalidad institucional.

```
┌─────────────────────────────────────────────────────┐
│ ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓ │
│  Confirmar inscripción                        [✕]  │  ← Header azul #192E4C, texto blanco
│ ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓ │
│                                                     │
│  ¿Confirmas tu inscripción al evento?               │  ← Cuerpo: texto azul #192E4C
│                                                     │
│  Congreso Internacional de Ingeniería 2026          │  ← Nombre en Demibold azul
│  Fecha: 25 de marzo de 2026                         │
│  Costo: $150.00 MXN                                 │
│                                                     │
│              [ Cancelar ]   [ Confirmar inscripción ]│  ← Botón sec. + botón primario azul
└─────────────────────────────────────────────────────┘
```

## 6.8 Dashboard personal — "Mis Eventos"

La vista principal del usuario autenticado. Es el corazón de la experiencia y donde la identidad visual debe brillar de forma coherente.

**Estructura general de la vista:**

```
┌──────────────────────────────────────────────────────────────────┐
│ [Navbar azul con firma UADY]                                    │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│  Bienvenido, Samuel                    [+ Nueva inscripción]     │
│  Lucida Bright Regular 18px azul                                 │
│                                                                  │
│  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐             │
│  │ 3 Próximos   │ │ 1 En curso   │ │ 12 Pasados   │             │
│  │ eventos      │ │ evento       │ │ eventos      │             │
│  │ azul #192E4C │ │ dor.#C89211  │ │ gris #7892AA │             │
│  └──────────────┘ └──────────────┘ └──────────────┘             │
│                                                                  │
│  MIS EVENTOS PRÓXIMOS                                            │
│  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐             │
│  │ [Card azul]  │ │ [Card dorado]│ │ [Card azul]  │             │
│  │ Congreso...  │ │ Taller...    │ │ Seminario... │             │
│  └──────────────┘ └──────────────┘ └──────────────┘             │
│                                                                  │
│ [Footer con textura arcos dorado sutil + firma secundaria UADY] │
└──────────────────────────────────────────────────────────────────┘
```

## 6.9 Vista de estado de solicitud (Tracker)

Es el componente donde el dorado tiene mayor protagonismo. Representa el avance del usuario hacia su objetivo: participar en un evento universitario.

```
  ESTADO DE TU INSCRIPCIÓN — Congreso Internacional 2026

  ●━━━━━━━━━━━━●━━━━━━━━━━━◎━━━━━━━━━━━○
  Enviada      Revisión    Aprobada    Constancia
  12 Mar       14 Mar    ← Aquí         Pendiente

  Estado actual:  [ ◎  En revisión por la coordinación ]
                    Fondo dorado suave #F5E9C8, texto #C89211 Demibold

  Tiempo estimado de respuesta: 2–3 días hábiles
```

## 6.10 Pantalla de login / bienvenida

La pantalla de ingreso es la primera impresión del sistema. Debe comunicar pertenencia institucional desde el primer segundo.

```
┌────────────────────────────┬─────────────────────────────────┐
│                            │                                 │
│   PANEL DE INICIO          │  [ Textura arcos azul+dorado ]  │
│                            │                                 │
│  [Firma institucional      │  Patrón de arcos del Centro     │
│   completa en azul]        │  Cultural Universitario al      │
│                            │  100%, llenando el lado derecho │
│  "Luz, Ciencia y Verdad"   │  de la pantalla con la textura  │
│  (dorado, Demibold Italic) │  gráfica 2023                   │
│                            │                                 │
│  ┌──────────────────────┐  │                                 │
│  │  Correo institucional │  │                                 │
│  └──────────────────────┘  │                                 │
│  ┌──────────────────────┐  │                                 │
│  │  Contraseña          │  │                                 │
│  └──────────────────────┘  │                                 │
│                            │                                 │
│  [   Iniciar sesión    ]   │                                 │
│  (botón azul pleno)        │                                 │
│                            │                                 │
└────────────────────────────┴─────────────────────────────────┘
```

---

# 7. MODO OSCURO Y MODO CLARO

La identidad UADY contempla ambos modos. El azul institucional, paradójicamente, funciona tanto como fondo oscuro como como elemento sobre fondo claro.

| Elemento de interfaz | Modo Claro | Modo Oscuro |
|---------------------|-----------|-------------|
| Fondo de página | `#EBF0F5` (azul-10) | `#192E4C` (azul pleno) |
| Texto principal | `#3A3A3A` | `#FFFFFF` |
| Texto secundario | `#476080` (azul-80) | `rgba(255,255,255,0.75)` |
| Navbar | `#192E4C` + texto blanco | `#0D1B2E` + texto blanco |
| Cards / Paneles | `#FFFFFF` borde `#D8E1EA` | `#233650` borde `#476080` |
| Inputs en reposo | Borde `#CCCCCC`, fondo `#FFF` | Borde `#476080`, fondo `#1E3A5C` |
| Inputs enfocados | Borde dorado `#C89211` | Borde dorado `#C89211` (igual) |
| Botón primario | Fondo `#192E4C`, texto blanco | Fondo `#C89211`, texto `#192E4C` |
| Botón secundario | Borde `#192E4C`, texto `#192E4C` | Borde `#C89211`, texto `#C89211` |
| Links / Acciones | `#C89211` hover `#192E4C` | `#D6A833` hover `#FFFFFF` |
| Footer | `#192E4C` | `#0D1B2E` |

---

# 8. FOOTER INSTITUCIONAL

El footer cierra cada vista y reafirma la identidad de la UADY. Sigue los mismos principios que el navbar.

```
┌──────────────────────────────────────────────────────────────────┐
│ ░░░░░░░░░░░░░░░░░░ [textura arcos dorado 15%] ░░░░░░░░░░░░░░░░ │  ← Franja decorativa sutil
├──────────────────────────────────────────────────────────────────┤
│ [Firma secundaria:        │ Aviso de privacidad │ Contacto     │
│  Escudo + UADY + Lema]   │ Términos de uso     │ uady.mx      │
│ "Luz, Ciencia y Verdad"  │                     │              │
│  en dorado               │                     │              │
├──────────────────────────────────────────────────────────────────┤
│  © 2026 Universidad Autónoma de Yucatán — Todos los derechos reservados  │
│  Fondo: #192E4C / Texto: rgba(255,255,255,0.65) / Tamaño: 13px │
└──────────────────────────────────────────────────────────────────┘
```

---

# 9. FAVICON E ICONOS DE APLICACIÓN

| Plataforma | Elemento a usar | Tamaño |
|-----------|-----------------|--------|
| Favicon en navegador | Isotipo (escudo UADY) en SVG | 32×32, 16×16 px |
| Ícono de App Web (PWA) | Escudo UADY sobre fondo azul `#192E4C` | 192×192, 512×512 px |
| Apple Touch Icon | Escudo UADY sobre fondo azul con padding | 180×180 px |
| Open Graph / Twitter Card | Firma institucional completa + fondo azul con textura arcos | 1200×630 px |

---

# 10. VARIABLES CSS — DESIGN TOKENS UADY

```css
:root {
  /* ── COLORES INSTITUCIONALES ── */
  --uady-azul:          #192E4C;  /* Pantone 295 C */
  --uady-dorado:        #C89211;  /* Pantone 1245 C */

  /* ── VARIACIONES TONALES ── */
  --uady-azul-80:       #476080;
  --uady-azul-60:       #7892AA;
  --uady-azul-20:       #D8E1EA;
  --uady-azul-10:       #EBF0F5;
  --uady-dorado-80:     #D6A833;
  --uady-dorado-20:     #F5E9C8;

  /* ── NEUTROS ── */
  --uady-blanco:        #FFFFFF;
  --uady-negro:         #000000;
  --uady-gris-texto:    #3A3A3A;
  --uady-gris-borde:    #CCCCCC;
  --uady-gris-meta:     #476080;

  /* ── SEMÁNTICOS ── */
  --color-exito:        #2E7D4F;
  --color-advertencia:  #C89211;  /* = dorado UADY */
  --color-error:        #C62828;
  --color-info:         #192E4C;  /* = azul UADY */

  /* ── TIPOGRAFÍA ── */
  --font-principal: 'Lucida Bright', Georgia, 'Times New Roman', serif;
  --font-weight-regular:  400;
  --font-weight-semibold: 600;

  /* ── ESCALA TIPOGRÁFICA ── */
  --text-display:  2rem;      /* 32px */
  --text-h2:       1.5rem;    /* 24px */
  --text-h3:       1.25rem;   /* 20px */
  --text-body-lg:  1.125rem;  /* 18px */
  --text-body:     1rem;      /* 16px */
  --text-small:    0.875rem;  /* 14px */
  --text-label:    0.75rem;   /* 12px */

  /* ── ESPACIADO ── */
  --space-xs:   0.25rem;  /* 4px  */
  --space-sm:   0.5rem;   /* 8px  */
  --space-md:   1rem;     /* 16px */
  --space-lg:   1.5rem;   /* 24px */
  --space-xl:   2rem;     /* 32px */
  --space-xxl:  3rem;     /* 48px */

  /* ── BORDES ── */
  --radius-sm:   4px;
  --radius-md:   6px;
  --radius-lg:   12px;
  --radius-full: 9999px; /* para chips y badges */

  /* ── SOMBRAS ── */
  --shadow-card: 0 2px 8px rgba(25, 46, 76, 0.12);
  --shadow-modal: 0 8px 32px rgba(25, 46, 76, 0.24);
  --shadow-navbar: 0 2px 4px rgba(25, 46, 76, 0.20);

  /* ── TRANSICIONES ── */
  --transition-fast:   150ms ease;
  --transition-normal: 250ms ease;
  --transition-slow:   400ms ease;

  /* ── FOCUS (accesibilidad) ── */
  --focus-ring: 0 0 0 3px #C89211;  /* Dorado como focus ring */
}
```

---

# 11. ELEMENTOS GRÁFICOS PROHIBIDOS

El Manual de Identidad UADY 2023 deroga expresamente dos elementos que estuvieron vigentes en versiones anteriores. Ninguno debe aparecer en este sistema:

| Elemento derogado | Descripción | Motivo |
|------------------|-------------|--------|
| **"Arcos"** (2004) | Siluetas de los arcos del edificio central en formato vectorial estilizado | Derogado en 2023; reemplazado por la nueva textura de arcos |
| **"Integración" / Triángulos** (2011) | Triángulos ensamblables en composiciones geométricas | Derogado en 2023 en favor de la textura de arcos 2023 |

> Si existen recursos digitales en el sistema que aún usen alguno de estos elementos, deben ser actualizados en el primer ciclo de mantenimiento.

---

# 12. CHECKLIST VISUAL — REVISIÓN DE CONFORMIDAD UADY

Antes de cada entrega de versión, el equipo de diseño debe verificar los siguientes puntos:

### Identidad y marca
- [ ] Firma institucional presente en cuadrante superior izquierdo en todas las vistas
- [ ] Firma en versión correcta según fondo (color/blanca)
- [ ] Área de seguridad 2X respetada alrededor de la firma
- [ ] Ningún elemento gráfico derogado (arcos 2004, triángulos 2011) presente

### Colores
- [ ] Solo colores del sistema de tokens UADY en uso
- [ ] El dorado `#C89211` NO aparece como texto corrido sobre blanco
- [ ] Ratio de contraste ≥ 4.5:1 en todo el texto de cuerpo (verificado con WebAIM)
- [ ] Texto blanco sobre azul `#192E4C` ≥ 12.7:1 ✓

### Tipografía
- [ ] Lucida Bright como única fuente visible en la interfaz (más Georgia como fallback)
- [ ] No más de 2 familias tipográficas en uso simultáneo
- [ ] Jerarquía H1→H2→H3→Cuerpo respetada en todas las vistas

### Componentes
- [ ] Botones primarios: azul de reposo, dorado en hover
- [ ] Focus ring dorado `#C89211` en todos los elementos interactivos
- [ ] Stepper de progreso usa azul (completado) y dorado (actual)
- [ ] Notificaciones de advertencia usan dorado `#C89211`
- [ ] Franja superior de cards usa color según estado del evento

### Textura de arcos
- [ ] Solo la textura 2023 en uso (no elementos derogados)
- [ ] Textura NO superpuesta sobre texto ni sobre la firma institucional
- [ ] Opacidad correcta según contexto (8–30%)

---

*"Luz, Ciencia y Verdad"*

*Documento elaborado con base en el Manual de Identidad Universitaria UADY 2023.
Cualquier desviación de estos lineamientos requiere autorización de la Coordinación
General de Comunicación Institucional (CGCI) de la Universidad Autónoma de Yucatán.*
