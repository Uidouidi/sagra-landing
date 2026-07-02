# SAGRA · Brand Spec
> 采集日期 / Fecha de captura: 2026-07-02
> 资产来源 / Orígenes: `Downloads\SAGRA\sagra.svg` (SVG A4 con paths de logo, fuente Bebas), `SAGRA.png` (wordmark raster), `info/sagra_resumen.md`, `Recursos/SAGRA manifesto y backstory.md`, `reestructuracion/260410_todo_definitivo.md`
> 资产完整度 / Completitud: **Parcial** — logo y tipografía confirmados; fotos de producto NO (placeholders)

## 🎯 核心资产 (activos de primera clase)

### Logo / Wordmark
- **Tipografía de marca confirmada**: **Bebas Neue** (14 referencias en `sagra.svg`). Wordmark "SAGRA" en Bebas Neue caps.
- Wordmark raster oficial: `Downloads\SAGRA\SAGRA.png` (11 KB, "SAGRA" sans-serif pesada, **negro sobre blanco, NO transparente**, landscape). Copia de referencia en `assets/SAGRA.png`.
- **Decisión de uso en web**: renderizar el wordmark "SAGRA" en Bebas Neue vía Google Font (más nítido y escalable que el PNG de 11 KB con fondo blanco). El PNG queda como referencia/fallback.
- Usar el wordmark en: hero, footer.
- 禁用变形 / 禁: no estirar, no cambiar color del wordmark (es tinta negra), no agregar trazo/sombra.

### 产品图 / Fotos de producto (实体产品必填 — faltan)
- **Frasco 300g**: fotos existentes en `Downloads\SAGRA\Fotos\Frasco\` son casuales WhatsApp (fondo madera/ventana, bokeh). **No alcanzan el umbral 8/10** del protocolo → placeholder hasta tener shot de producto controlado.
- **Pote de Cartón 2kg**: **no existen fotos**. Plan del fundador: generar desde el JSON profile de las imágenes del frasco. → placeholder.
- **Gastronómica 9kg**: **no existen fotos**. (Balde de 10 L, producto neto 9.2 kg por densidad de la grasa, vendido como 9 kg.) → placeholder.
- **Estrategia**: placeholders honestos en el HTML (tarjeta neutral con wordmark + nombre de presentación), con ruta de reemplazo documentada en `DEPLOY.md` y comentarios del HTML.

## 🎨 辅助资产 (activos auxiliares)

### 色板 / Paleta (monocromo — single-ink, fiel a la etiqueta y al manifesto)
- **Ink / Tinta**: `#111111` (negro rico, levemente más suave que `#000` para lectura premium)
- **Paper / Papel**: `#F6F2EC` (papel cálido, no blanco frío — evoca noble/verdad, no rústico)
- **Muted / Secundario**: `#7A7268` (gris cálido para meta/caption)
- **Hairline**: `#D9D2C6` (filete sobre papel)
- **Sin acento cromático**: la marca es single-ink. La jerarquía se logra con peso/tamaño tipográfico, filetes y whitespace, NO con color. Es la opción más fiel y más anti-slop.
- 禁用色 / 禁: violetas/AI-gradient, verdes "healthy", ocres rústicos, neón. Todo cromático = slop para esta marca.

### 字型 / Tipografía
- **Display / Wordmark**: `"Bebas Neue", "Arial Narrow", sans-serif` (Google Font)
- **Body / UI**: `"Hanken Grotesk", "Source Sans 3", system-ui, sans-serif` (Google Font — premium, Söhne-adjacent, no-slop, legible en mobile)
- **Mono**: no aplica (sin datos/HUD)
- Reglas: `font-synthesis: none`; `text-wrap: pretty` en párrafos, `balance` en títulos; body 17px / line-height 1.7 (español = Latín, no CJK); caption 13px; display con `clamp()` fluido.
- 禁: Inter como display (slop), system sans como body (cara inconsistente), faux italic.

### 签名细节 / Detalles "120%"
- Wordmark Bebas Neue a gran escala en hero, tratado como sello/proclama.
- Filetes hairline (`#D9D2C6`) como reglas de manifiesto entre secciones.
- Labels en small-caps con tracking amplio (`letter-spacing: 0.14em`) — tono de edicto.
- "La grasa no miente" como pull-quote tipográfico (la verdad proclamada).

### 禁区 / 禁
- No rústico (kraft marrón, texturas madera en UI, tipografía "hecha a mano").
- No "healthy/positivity" (verdes, gradientes frescos, emojis hoja/corazón).
- No solemnidad fría (negro puro sobre gris frío, cathedral vibes) — la cercanía humana importa.
- No iconografía decorativa (cada bullet con icono = slop).
- No SVG dibujando el frasco/pote (usar foto real o placeholder honesto).

### 气质关键词 / Palabras de tono
Noble · Implacable · Verdadero · Cálido (no frío) · Editorial
