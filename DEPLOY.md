# Deploy de la landing SAGRA en GitHub Pages

Guía paso a paso, asumiendo poca experiencia con git/GitHub. La landing es estática (un solo `index.html`), así que el deploy es gratis y simple.

---

## 0. Requisitos (una sola vez)

1. **Cuenta de GitHub** — usá tu cuenta personal (no hace falta una cuenta separada para SAGRA). El repo se llamará `sagra-landing` y el slug ya carga la marca.
2. **Git instalado** — comprobalo abriendo PowerShell y corriendo:
   ```powershell
   git --version
   ```
   Si dice "no se reconoce", descargalo de <https://git-scm.com/download/win> e instalalo (deja las opciones por defecto). Reinicia PowerShell después.

> Nota: si en algún momento SAGRA crece o entra gente, podés crear un **org** gratuito de GitHub (no una segunda cuenta personal) y transferir este repo en 5 min, sin migrar nada. No lo hagas ahora.

---

## 1. Crear el repositorio en GitHub

1. Andá a <https://github.com/new> (sesionado con tu cuenta).
2. **Repository name**: `sagra-landing`
3. **Description** (opcional): `Landing page de SAGRA — grasa de pella refinada`
4. Elegí **Public** (GitHub Pages gratis requiere repo público).
5. **No** tildes "Add a README", ".gitignore" ni "license" (lo vamos a hacer todo desde la carpeta local).
6. Click **Create repository**.

GitHub te muestra una página con comandos. Ignorala (la adaptamos abajo).

---

## 2. Subir la landing al repo (desde PowerShell)

En PowerShell, parate en la carpeta de la landing y subila:

```powershell
# Reemplazá TU-USUARIO por tu usuario de GitHub
$repo = "https://github.com/TU-USUARIO/sagra-landing.git"

cd "C:\Users\Uidi\.gemini\antigravity\playground\SAGRA\proyectos\landing"

# Inicializá git en esta carpeta
git init
git branch -M main

# Subí la landing completa (index + assets con las 3 fotos + docs)
git add index.html
git add assets/
git add DEPLOY.md
git add brand-spec.md
git commit -m "Landing SAGRA inicial"

# Conectá con el repo remoto y subí
git remote add origin $repo
git push -u origin main
```

> Si te pide credenciales: GitHub ya no acepta contraseña. Usá un **Personal Access Token** (Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token, tildá `repo`) como contraseña, o mejor instalá **GitHub Desktop** (<https://desktop.github.com>) que maneja la auth por vos y después podés seguir usándolo para subir cambios.

---

## 3. Activar GitHub Pages

1. En GitHub, abrí el repo `sagra-landing`.
2. Andá a **Settings** → **Pages** (menú izquierdo).
3. En **Source**, elegí **Deploy from a branch**.
4. Branch: `main`, carpeta: `/root` → click **Save**.
5. Esperá 1–2 minutos (GitHub construye y publica el sitio).

---

## 4. Obtener la URL final

Volvé a **Settings → Pages** — arriba va a aparecer:

```
Your site is live at https://TU-USUARIO.github.io/sagra-landing/
```

Esa es la URL que va en los QR impresos en los frascos/potes. Anotala y documentala en `proyectos/landing/_context.md` (campo "URL final").

---

## 5. Actualizar la landing después (cuando cambies algo)

Cualquier cambio a `index.html` o fotos:

```powershell
cd "C:\Users\Uidi\.gemini\antigravity\playground\SAGRA\proyectos\landing"
git add .
git commit -m "Mensaje corto del cambio"
git push
```

GitHub Pages republisha solo en 1–2 min. No hay build, no hay servidor.

---

## 6. Estado de las fotos

Las tres presentaciones ya tienen foto real en `assets/`:

| Presentación | Archivo |
|---|---|
| Frasco 300 g | `assets/frasco-300g.png` ✅ |
| Pote 2 kg | `assets/pote-2kg.png` ✅ |
| Gastronómica 9 kg | `assets/gastronomica-9kg.jpg` ✅ |

Si en el futuro querés cambiar alguna foto, simplemente reemplazá el archivo en `assets/` con el mismo nombre. Si cambiás la extensión (.png ↔ .jpg), actualizá el `src` en el `<img>` correspondiente del `index.html`.

---

## 7. QR que apunta a la landing

- **1 QR único** → URL del paso 4. Recomendado para empezar (un solo QR para ambas presentaciones, la landing muestra las dos).
- **3 QR separados** (opcional, futuro): uno por presentación, apuntando a `…/sagra-landing/#frasco-300g`, `…/sagra-landing/#pote-2kg` o `…/sagra-landing/#gastronomica-9kg`. Los anchors ya están en el HTML, no hace falta cambiar nada para que funcionen.

Para generar el QR: cualquier generador online (ej. <https://www.qrcode-monkey.com/>) o el script `src/qr_generator.py` del workspace SAGRA.

---

## Checklist final
- [ ] Git instalado
- [ ] Repo `sagra-landing` creado (público)
- [ ] `index.html` + `assets/` + `brand-spec.md` pusheados
- [ ] GitHub Pages activado (branch `main`, `/root`)
- [ ] URL anotada en `_context.md`
- [ ] Fotos reales en assets (las 3 presentaciones)
- [ ] Instagram real en el footer (buscar `PERSONALIZAR` en `index.html`)
- [ ] QR generado apuntando a la URL final
