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

Tecnologías: HTML + CSS + JavaScript vanilla. Sin dependencias externas.

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
