# ADR.md

## ADR-001 — GitHub Pages + Jekyll como plataforma única

- **Status:** Accepted
- **Contexto:** el repo tuvo un intento de pipeline Parcel/npm (`src/index.md`) nunca completado; las devDeps npm quedaron sin uso real.
- **Decisión:** el sitio se sirve exclusivamente vía GitHub Pages (Jekyll, tema cayman) desde `master`. npm queda solo para tooling futuro.
- **Consecuencias:** no hay build propio; `package.json` scripts legados no funcionan. Plugins declarados en `_config.yml` (`optional-front-matter`, `default-layout`, `seo-tag`, `titles-from-headings`) replican el set que Pages activa por defecto, permitiendo builds locales fieles.

## ADR-002 — Contenido sin front matter

- **Status:** Accepted
- **Contexto:** todos los `.md` se escribieron sin front matter YAML.
- **Decisión:** mantenerlos así; `jekyll-optional-front-matter` + `jekyll-default-layout` + `jekyll-titles-from-headings` les dan render, layout `default` y título desde el H1.
- **Consecuencias:** links internos deben usar la extensión `.html` destino; agregar una página = crear `.md` sin config extra.
