# Contexto: Landing SAGRA (Layer 2)

> **Regla de la carpeta**: Proyecto de landing page estática para SAGRA. Destino del QR impreso en los frascos/potes. Autocontenida, sin build step, deployada en GitHub Pages.

## Qué es
Landing page de producto, una sola página HTML estática, mobile-first (el tráfico viene de escaneos QR), en español. Muestra las **tres presentaciones actuales** de SAGRA:
1. **Frasco de vidrio 300g** (minorista / góndola)
2. **Pote de Cartón 2kg** (mayorista / family) — NO llamar "cuñete"; denominación oficial: Pote de Cartón de 2kg.
3. **Gastronómica 9kg** (profesional / foodservice) — balde de 10 L, producto neto 9.2 kg (densidad de la grasa < 1), vendido como 9 kg. SKU interno `balde_10kg` (mal nombrado: refiere al envase de 10 L, no al peso).

Fuente de verdad de las presentaciones: `reestructuracion/260410_todo_definitivo.md` (D3: lingote bajado, pote 2kg activo) y `reestructuracion/260518_snapshot_sistema_sheets.md` (SKUs `fr300` + `cuñete_2000` + `balde_10kg` — ver corrección de peso en ese archivo).

## Reglas de contenido (definidas con el fundador)
- **Sin precios**: es página de info para quien escanea el QR, no de venta.
- **Sin links de compra**: solo Instagram en footer (por ahora).
- **No rústico / no "healthy empalagoso"**: estética noble, premium, implacable. Alineada al manifesto ("La grasa no miente", ángel/justicia, verdad).
- **Orden de secciones**: hero corto → presentaciones (la carne, primero porque el usuario viene de una presentación física) → info del producto → footer.

## Cómo se ejecuta / deploya
- **Sin build**: `index.html` es un único archivo con CSS inline. Se abre directo en el navegador.
- **Fuentes**: Google Fonts vía `<link>` (Bebas Neue + Hanken Grotesk). Requiere internet (la página vive en GitHub Pages, así que está garantizado).
- **Deploy**: ver `DEPLOY.md` — GitHub Pages, repo público `sagra-landing` (cuenta GitHub personal del fundador).
- **URL final**: `https://uidouidi.github.io/sagra-landing/`

## Skill usada
`huashu-design` (en `C:\Users\Uidi\.config\opencode\skills\huashu-design\`). Tarea de marca concreta → se fue por §1.a Brand Asset Protocol + standard workflow (NO Fallback de 3 variaciones, porque el fundador dio contexto de diseño claro). Filosofía anti-slop aplicada a HTML plano (sin React/deck/animation machinery, prohibido por el prompt).

## Estado
- [x] Brand spec definido (`brand-spec.md`)
- [x] `index.html` construido con las 3 presentaciones
- [x] Fotos reales en `assets/` (frasco-300g.png, pote-2kg.png, gastronomica-9kg.jpg)
- [x] Deploy en GitHub Pages → `https://uidouidi.github.io/sagra-landing/`
- [x] QR apuntando a la URL final (qr.html genera los 4: principal + 3 por presentación)

## Archivos
- `prompt.md` — el prompt/spec original que originó el proyecto
- `brand-spec.md` — spec de marca (paleta, tipografía, assets, 禁区) output del protocolo
- `index.html` — la landing (entregable principal)
- `DEPLOY.md` — guía paso a paso de deploy en GitHub Pages
- `assets/` — logo (SAGRA.png) y fotos de las 3 presentaciones
