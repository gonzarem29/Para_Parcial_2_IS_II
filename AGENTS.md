# AGENTS.md — Contexto de Sesión

Repositorio de estudio interactivo para **IS-II Parcial 2** (UBP, Cátedra B).
Diseño maximalista 4-Actos con Three.js 3D background. Sin dependencias externas (excepto Three.js CDN).

---

## 🎯 Estado Actual del Proyecto

- **index.html**: 611+ líneas, transformado con diseño maximalista 4-Actos
- **GitHub**: `gonzarem29/Para_Parcial_2_IS_II` (branch: main)
- **Online**: https://gonzarem29.github.io/Para_Parcial_2_IS_II/
- **Hosting**: GitHub Pages (static site, sin build step)

---

## 📜 Historial de Sesiones

### Sesión 1 — Transformación Maximalista
- Copiado `index.html` (586-line calculator version) desde desktop
- Añadidas CSS variables maximalistas (`--maxi-accent1..4`, `--maxi-glow`, `--perspective`)
- Creada estructura 4-Actos con divisores SVG animados (SMIL `<animate>`)
  - Acto I "El Laboratorio" — Hero
  - Acto II "Los Planos" — Contenido + Paso a Paso  
  - Acto III "La Simulación" — Examen + Calculadora
  - Acto IV "El Archivo" — Footer archive-style
- Añadido Three.js icosaedro wireframe + partículas vía CDN (r128)
- Añadido `reveal-3d` con perspectiva `rotateX(12deg)` para scroll reveals
- Añadido `blueprint-card` con barrido de luz al hover
- Añadido `scan-line` en contenedor de progreso
- Añadido `crt-panel` en calculadora (scanlines CRT)
- Añadido command-line overlay de arranque (cmd-overlay con typing animation)
- Añadidos act-badges para cada acto
- Merge resuelto con commits remotos (calculator desktop)
- Push a GitHub

### Sesión 2 — Configuración de MCPs
- Instalados y configurados 4 MCPs gratuitos (sin APIs de pago):
  - **Nakkas** (SVG generation) — `npx -y nakkas@latest`
  - **Playwright** (headless browser tests) — Chromium instalado en `C:\Users\gonza\AppData\Local\ms-playwright\chromium-1223`
  - **Aesthetics Wiki** (design references) — `uvx aesthetics-wiki-mcp@latest` (uv v0.11.19 instalado)
  - **BrandKit** (brand identity) — `npx -y brandkit-mcp serve --config brandkit.config.yaml`
- Creado `brand_atomic_system/` con paleta, tipografía, tokens, componentes
- Creado `brandkit.config.yaml`
- **NOTA**: Reiniciar opencode para que los MCPs estén disponibles

### Sesión 3 — Implementación con MCPs
- **Nakkas**: Generados 3 SVGs animados decorativos en `assets/svg/` para los divisores de actos:
  - `divider-act1.svg` (azul — Acto I→II, ondas con dots animados)
  - `divider-act2.svg` (amarillo — Acto II→III, ondas + barras pulsantes)
  - `divider-act4.svg` (teal — Acto III→IV, 3 capas de ondas + bars + dots)
- **Playwright**: Capturadas 3 screenshots del estado actual:
  - `screenshot-hero.png` (viewport inicial)
  - `screenshot-full.png` (full page)
  - `screenshot-mid.png` (sección media)
- **Three.js** refinado:
  - Segundo icosaedro (4un, teal, wireframe, opacidad 0.06) con rotación inversa
  - Partículas: 400 (vs 200 antes), colores por vértice (5 colores de la paleta)
  - Rotación duplicada: mesh1 0.004/0.007 rad/s, mesh2 −0.002/0.003 rad/s
  - Tamaño de partículas: 0.035 (vs 0.025 antes), opacidad 0.5 (vs 0.4)
- **Contenido**: Agregada Clase 13 — Gestión de Configuración (6 topics: SCI, Baseline, control de versiones, control de cambios, auditoría)
- **Accesibilidad**:
  - Skip-to-content link al inicio del body
  - `aria-label` en todos los nav links
  - `role="status" aria-live="polite"` en calc-result
  - Focus visible ya presente

---

## 🏗️ Arquitectura

```
index.html                          # Archivo único (HTML + CSS + JS inline)
opencode.json                       # Config MCPs + opencode
brandkit.config.yaml                # Brand identity config
AGENTS.md                           # Este archivo — contexto de sesión
README.md                           # Documentación pública
assets/
  svg/                              # (vacío) Para SVGs generados con Nakkas
  img/                              # (vacío) Para texturas/imágenes
brand_atomic_system/
  visual/
    colors/palette.css               # Paleta completa
    typography/fonts.css             # Tipografía
    tokens/spacing.css               # Spacing, shadows, radius
    components/cards.css             # Componentes UI
```

---

## 🎨 Paleta de Diseño

```css
/* Base oscura */
--bg: #0b1120
--bg-alt: #0f172a

/* Acentos principales */
--accent1: #4facfe     /* Azul — Acto I (laboratorio) */
--accent2: #34d399     /* Verde — Acto II (planos) */

/* Acentos maximalistas */
--maxi-accent1: #ff6b6b   /* Rojo — peligro/sci-fi */
--maxi-accent2: #ffd93d   /* Amarillo — energía/simulación */
--maxi-accent3: #6c5ce7   /* Púrpura */
--maxi-accent4: #00cec9   /* Teal — Acto IV (archivo) */

/* Efectos */
--maxi-glow: 0 0 30px rgba(79,172,254,0.15), 0 0 60px rgba(79,172,254,0.05)
--perspective: 1200px
```

---

## 📐 Convenciones de Código

- **Single file**: Todo en `index.html` para deploy simple en GitHub Pages
- **Three.js**: CDN con `<script>` síncrono al final del body (no defer)
- **prefers-reduced-motion**: Respeta `@media(prefers-reduced-motion:reduce)` en TODAS las animaciones
- **IDs semánticos**: Prefijo descriptivo (`e5-ims1`, `fb-t1`, `calc-`)
- **Clases CSS**:
  - `reveal` — scroll reveal básico (fade + translateY)
  - `reveal-3d` — scroll reveal con perspectiva 3D (rotateX)
  - `blueprint-card` — barrido de luz al hover
  - `scan-line` — línea de escaneo animada
  - `crt-panel` — scanlines estilo monitor CRT
  - `act-badge act-i/ii/iii/iv` — badges de actos
- **Sin APIs de pago**: Todo gratuito, self-hosted
- **Sin bundlers**: HTML + CSS + JS vanilla

---

## 🔧 MCPs Configurados

| MCP | Comando | Tools | Cómo se usa |
|-----|---------|-------|-------------|
| **Nakkas** | `npx -y nakkas@latest` | `render_svg`, `preview`, `save` | Generar SVG decorativos, flourishes, divisores |
| **Playwright** | `npx -y @playwright/mcp@latest` | Browser automation (`browser_navigate`, `click`, `type`, `snapshot`) | Capturar screenshots, testear layout responsive |
| **Aesthetics Wiki** | `uvx aesthetics-wiki-mcp@latest` | `search_aesthetic`, `get_aesthetic`, `get_aesthetic_images` | Consultar tendencias de diseño |
| **BrandKit** | `npx -y brandkit-mcp serve --config brandkit.config.yaml` | `get_brand_overview`, `get_colors_and_type`, `get_components`, `search_brand` | Gestionar identidad visual |

**Importante**: Los MCPs cargan al INICIO de opencode. Si se modificó `opencode.json`, reiniciar opencode.

---

## 📋 Próximos Pasos (Priorizados)

### Alta prioridad
- [ ] **Probar MCPs**: Usar Nakkas para generar SVG flourishes, Playwright para screenshots
- [ ] **Nakkas**: Generar SVGs decorativos para los divisores de actos (reemplazar o complementar los actuales)
- [ ] **Playwright**: Capturar screenshots de cada acto para documentación
- [ ] **Aesthetics Wiki**: Consultar tendencias maximalistas 2026 para refinar diseño

### Media prioridad
- [ ] Refinar animaciones Three.js (velocidad rotación, opacidad, colores)
- [ ] Añadir más contenido teórico a las clases (Completitud del temario)
- [ ] Mejorar accesibilidad (ARIA labels, focus management)
- [ ] Agregar más ejercicios prácticos al simulacro

### Baja prioridad
- [ ] Generar texturas de fondo con BrandKit + Nakkas
- [ ] Crear variante de tema claro (opcional)
- [ ] Optimizar rendimiento (requestAnimationFrame, lazy loading)

---

## ⚠️ Notas Técnicas

- **Git merge**: La rama `main` local y remota divergieron. Se resolvió con merge manual (se mantuvo la versión local del index.html con diseño maximalista + calculadora, y se fusionó el README.md remoto más detallado).
- **Playwright**: Chromium instalado en `C:\Users\gonza\AppData\Local\ms-playwright\chromium-1223`. Usar el tool `browser_snapshot` para capturar el estado visual de la página.
- **uv**: Instalado vía pip. Usar `uvx` para ejecutar MCPs Python sin instalación permanente.
- **BrandKit**: Los archivos de diseño están en `brand_atomic_system/`. Si se añaden nuevos componentes, actualizar también los archivos CSS ahí.

---

## 🚀 Comandos Rápidos

```bash
# Abrir en navegador
start index.html

# Ver cambios sin commit
git diff

# Subir a GitHub Pages
git add -A
git commit -m "mensaje descriptivo"
git push

# Ver historial
git log --oneline -10
```
