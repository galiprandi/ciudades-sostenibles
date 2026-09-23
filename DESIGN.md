# DESIGN.md

- **Tema:** `jekyll-theme-cayman` (GitHub Pages). Header verde/azul del tema.
- **Layout:** `_layouts/default.html` (override del tema). Header con `page.title`/`page.description`, footer con link de edición en GitHub.
- **CSS:** `assets/css/style.scss` — solo `@import "{{ site.theme }}"` + overrides puntuales.
- **Tokens:** `theme-color: #157878` (meta), manifest `theme_color: #2196f3`, `background_color: #159957`.
- **PWA:** `manifest.json` + íconos en `assets/images/icons/` (72→512px + favicon.ico).
- Sin sistema de componentes propio; el contenido es markdown puro estilizado por el tema.
