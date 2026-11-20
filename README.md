# Astro: optimized font fallbacks drop bold and italic

A minimal reproduction for Astro's Fonts API. With `optimizedFallbacks` on (the default), every fallback face Astro generates for `fallbacks: ["monospace"]` is `local("Courier New")` in its regular face, including the faces declared bold and italic. `<strong>` and `<em>` therefore render regular and upright while the web font loads, and for good when web fonts are blocked.

1. `npm install`, then `npm run build`.
2. Read the `fallback: Courier New` `@font-face` rules in `dist/index.html`.
3. To see the rendering, run `npm run dev`, block `*.woff2` in the browser's network request blocking, and reload.

With `optimizedFallbacks: false` in the font's entry in `astro.config.mjs`, the same lines render bold and italic.
