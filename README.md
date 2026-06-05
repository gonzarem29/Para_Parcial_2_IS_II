# IS-II · Parcial 2

Plataforma interactiva de estudio para el **Segundo Parcial de Ingeniería de Software II** (Cátedra B, UBP).

## Contenido

- **Métricas y Mediciones** — Puntos de Función, Halstead, ERD, IMS, Integridad
- **Planificación y Estimación** — Use Case Points, COCOMO II
- **Administración del Riesgo** — Categorías de riesgo, estrategias
- **Gestión del Cambio y Calidad** — Versionado semántico, proceso de cambio
- **Simulacro de Parcial** — 9 ejercicios teórico-prácticos con verificación automática
- **Teoría expandida** — Explicación detallada de cada tema con toggle interactivo
- **Soluciones integradas** — Ejercicios prácticos con solución expandible y verificación numérica
- **Calculadora de métricas** — Panel interactivo para IMS, UCP, PF, Halstead, ERD e Integridad con dos modos de uso

## Calculadora de métricas

La página incluye una calculadora interactiva integrada en la sección de práctica con dos modos:

- **Por ejercicio**: seleccioná la métrica (IMS, UCP, PF, Halstead, ERD, Integridad), completá los campos y obtené el resultado paso a paso con las fórmulas visibles
- **Calculadora libre**: teclado numérico incorporado para expresiones matemáticas arbitrarias

La calculadora se muestra como panel lateral en desktop (≥1024px) y como bottom sheet overlay en mobile con botón FAB flotante. Persiste los valores ingresados en sessionStorage.

Tecnologías: HTML + CSS + JavaScript vanilla + Three.js (CDN).

## Diseño maximalista (v2.0)

La interfaz se rediseñó siguiendo las tendencias **Maximalismo 2026** y **Democratized Fancy Animations**:

- **4 Actos narrativos**: El Laboratorio (hero), Los Planos (contenido), La Simulación (examen), El Archivo (footer)
- **Three.js 3D background**: icosaedro wireframe rotatorio + campo de partículas (CDN, lazy load)
- **Animaciones 3D scroll**: tarjetas con perspectiva `rotateX(12deg)` al hacer scroll
- **Efecto blueprint**: barrido de luz al hover en tarjetas de contenido
- **Línea de escaneo**: barra sci-fi en el contenedor de progreso
- **CRT scan**: superposición de líneas en la calculadora
- **Boot overlay secuencia CLI**: simulación de arranque del laboratorio al cargar
- **Divisores SVG animados**: ondas SMIL entre cada acto
- **Paleta maximalista**: acentos rojo (`--maxi-accent1`), amarillo (`--maxi-accent2`), púrpura (`--maxi-accent3`), teal (`--maxi-accent4`)
- **prefers-reduced-motion**: todas las animaciones se desactivan respetando accesibilidad

## Novedades de esta versión

- **Calculadora de métricas**: panel interactivo con fórmulas, campos dinámicos y resultados paso a paso
- **Dos modos de uso**: "Por ejercicio" con campos predefinidos y "Calculadora libre" con teclado numérico
- **Diseño responsive**: sidebar sticky en desktop, bottom sheet con FAB en mobile
- **Persistencia de datos**: sessionStorage para valores ingresados y modo seleccionado
- **Event delegation**: sin inline onclick handlers, todo con event listeners
- **Teoría por tema**: cada tópico ahora incluye una explicación teórica completa accesible mediante un toggle (▶)
- **Verificación de respuestas teóricas**: las preguntas del simulacro se evalúan por palabras clave y devuelven feedback
- **Verificación numérica**: los ejercicios prácticos (IMS, UCP, PF, Halstead, ERD/Integridad) validan los valores ingresados
- **Soluciones expandibles**: cada ejercicio incluye una solución detallada con cálculos paso a paso
- **Confeti al completar**: efecto visual al alcanzar el 100% de temas aprendidos

## Tecnologías

HTML + CSS + JavaScript vanilla. Sin dependencias externas.

## Uso

La página es completamente autónoma. Podés:

- Marcar temas como aprendidos (se guardan en localStorage)
- Explorar las guías paso a paso con fórmulas y tablas
- Resolver el simulacro de parcial y verificar tus respuestas
- Usar la calculadora de métricas para resolver ejercicios paso a paso
- Seguir tu progreso general con la barra de progreso

## Acceso online

Disponible en GitHub Pages:  
[https://gonzarem29.github.io/Para_Parcial_2_IS_II/](https://gonzarem29.github.io/Para_Parcial_2_IS_II/)
