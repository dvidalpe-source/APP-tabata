# Cuerda & calorías — PWA

App de cronómetro para salto de soga con cálculo de calorías en tiempo real, lista para convertirse en app instalable con [PWABuilder](https://www.pwabuilder.com/).

## Archivos incluidos

- `index.html` — la app (HTML, CSS y JS en un solo archivo)
- `manifest.json` — metadatos de la app (nombre, ícono, colores) que la hacen instalable
- `service-worker.js` — permite que funcione offline y cargue rápido
- `icon-192.png`, `icon-512.png`, `icon-512-maskable.png` — íconos de la app

Todos están listos, no necesitas tocarlos.

## Paso 1 — Publicar la app con HTTPS

PWABuilder necesita una URL pública con HTTPS para poder analizarla (no funciona con archivos locales). La forma más simple es GitHub Pages:

1. Crea una cuenta en [github.com](https://github.com) si no tienes una.
2. Crea un repositorio nuevo (botón verde "New"), por ejemplo `jump-rope-app`.
3. Sube **todos los archivos de esta carpeta** (los 6 archivos) con "Add file" → "Upload files" → arrastra todos → "Commit changes".
4. Ve a **Settings → Pages**, en "Branch" selecciona `main` y `/root`, guarda.
5. Espera 1-2 minutos. Tu URL será algo como:
   `https://tu-usuario.github.io/jump-rope-app/`
6. Abre esa URL y confirma que la app carga bien.

## Paso 2 — Empaquetarla con PWA Builder

1. Ve a [pwabuilder.com](https://www.pwabuilder.com/).
2. Pega la URL de tu app publicada y dale a "Start".
3. PWABuilder analiza la app y te muestra un puntaje para Manifest, Service Worker e íconos — ya deberían salir en verde porque los archivos vienen incluidos.
4. Click en "Package for stores" (o "Build my PWA").
5. Elige la plataforma:
   - **Android** → genera un paquete `.aab`/`.apk` para subir a Google Play.
   - **Windows** → genera un paquete `.msix` para Microsoft Store.
   - **iOS** → genera un proyecto Xcode (necesitas Mac para compilarlo).
6. Descarga el paquete generado y sigue las instrucciones de PWABuilder para subirlo a la tienda correspondiente.

Si solo quieres usarla tú, no necesitas subirla a ninguna tienda: con publicarla (Paso 1) ya puedes instalarla directo desde el navegador del celular (Chrome en Android te mostrará un botón "Instalar"; en iPhone usa "Agregar a pantalla de inicio" desde Safari).

## Probar localmente antes de publicar

Como la app ahora usa `manifest.json` y un service worker con rutas relativas, ábrela sirviéndola desde un servidor local en vez de doble click. Si tienes Python instalado, desde esta carpeta:

```
python3 -m http.server 8000
```

y abre `http://localhost:8000` en el navegador.
