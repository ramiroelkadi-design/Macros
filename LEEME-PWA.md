# Macros del día: versión instalable (PWA)

Carpeta lista para subir a cualquier hosting estático con HTTPS. Archivos: `index.html` (la app), `manifest.webmanifest`, `sw.js` (funciona sin conexión) y los íconos.

## Publicar en tu dominio
1. Elegí un hosting estático gratuito: Netlify (arrastrar la carpeta en "Deploys"), Cloudflare Pages o GitHub Pages.
2. Subí **todo el contenido de esta carpeta** a la raíz del sitio (tiene que servirse por HTTPS).
3. Si tenés dominio propio, apuntalo desde el panel del hosting (Custom domain).

## Instalar en el celular
Abrí la URL en Chrome para Android → menú ⋮ → "Instalar app" (o "Agregar a la pantalla principal"). Se abre a pantalla completa y funciona sin internet.

## Tener en cuenta
- **Datos:** `localStorage` es por dominio. La app instalada arranca vacía: exportá desde el artifact (Copia de seguridad) e importá en la nueva.
- **Estimación con Claude:** la capacidad `sample` existe solo dentro de claude.ai. En la versión instalada, los alimentos que no estén en la base local no se estiman; hay que cargarlos a mano ("pizza 300 kcal 12 p 30 c 10 g"). Para recuperarla habría que usar tu propia API key de Anthropic, guardada en el celular.
- **Actualizar:** al cambiar `index.html`, subí también `sw.js` con otro número en `const V='macros-v1'` (por ejemplo `macros-v2`) para que el celular tome la versión nueva.
- **Chrome borra datos del sitio** si limpiás "datos de navegación"; hacé copias de seguridad cada tanto.

## TWA (solo si querés publicarla en Google Play)
Con la PWA ya online, usá PWABuilder.com (pegás la URL y descarga el paquete Android) o Bubblewrap. Requiere cuenta de Play Console y publicar `/.well-known/assetlinks.json` en tu dominio. Si solo es para vos, instalar desde Chrome alcanza.
