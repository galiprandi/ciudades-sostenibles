# AGENTS.md

Sitio estático **Jekyll** servido por **GitHub Pages** desde `master` (raíz). Deploy = `git push origin master`; Pages rebuildea solo (~1 min).

## Comandos

- Build local (reproduce Pages 1:1, vía Docker):
  `docker run --rm -v "$PWD:/srv/jekyll" -e JEKYLL_ENV=production jekyll/jekyll:pages jekyll build`
- Salida: `_site/`. Para servir respetando `baseurl`, montar `_site` bajo `/ciudades-sostenibles/`.
- Deps npm (`marked`, `cssnano`) son devDependencies **no usadas por el sitio**; scripts `dev`/`build` de package.json apuntan a `src/` inexistente (legado Parcel, no usar).

## Reglas operativas

- Los `.md` del sitio **no llevan front matter**: Pages los renderiza vía `jekyll-optional-front-matter` (declarado en `_config.yml`).
- Links internos a posts: apuntar a `.html`, no `.md` (el `.md` se sirve como `text/markdown` crudo).
- URLs en layouts: usar `relative_url`/`absolute_url` (baseurl = `/ciudades-sostenibles`).
- Verificación post-deploy: `build_revision` en el `?v=` de `style.css` debe igualar el SHA pusheado.
