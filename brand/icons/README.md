# Conjunto de íconos — Publicomp

Generado a partir de `Brandkit/Logo.png` (el símbolo "P" aislado del Brand Kit oficial).

## Archivos

| Archivo | Tamaño | Fondo | Uso |
|---|---|---|---|
| `favicon.ico` | 16/32/48px | transparente | Pestaña del navegador (compatibilidad general) |
| `favicon-16x16.png` | 16px | transparente | Fallback PNG |
| `favicon-32x32.png` | 32px | transparente | Fallback PNG |
| `apple-touch-icon.png` | 180px | transparente* | iOS — agregar a inicio |
| `android-chrome-192x192.png` | 192px | transparente | Android / PWA |
| `android-chrome-512x512.png` | 512px | transparente | Android / PWA (splash screen) |
| `mstile-150x150.png` | 150px | transparente** | Windows (pin a inicio) |

\* iOS ignora el canal alpha en `apple-touch-icon` y rellena automáticamente con negro sólido al agregar a pantalla de inicio — no es controlable desde el archivo.
\** El color de fondo del tile de Windows lo define `TileColor` en `browserconfig.xml` (`#07090C`), no la imagen — la transparencia acá es el formato correcto.
| `site.webmanifest` | — | — | Metadata PWA, referencia los android-chrome |
| `browserconfig.xml` | — | — | Metadata Windows, referencia el mstile |

## Cómo instalarlo en el sitio

1. Subí todos estos archivos a la **raíz** del sitio (ej. `publicomp.studio/favicon.ico`, no dentro de una subcarpeta) — los paths dentro de `site.webmanifest` y `browserconfig.xml` asumen raíz.
2. Pegá esto dentro del `<head>` de cada página (o en el layout base):

```html
<link rel="icon" href="/favicon.ico" sizes="any">
<link rel="icon" href="/favicon-32x32.png" sizes="32x32" type="image/png">
<link rel="icon" href="/favicon-16x16.png" sizes="16x16" type="image/png">
<link rel="apple-touch-icon" href="/apple-touch-icon.png">
<link rel="manifest" href="/site.webmanifest">
<meta name="msapplication-config" content="/browserconfig.xml">
<meta name="theme-color" content="#07090C">
```

## Nota de calidad — a tener en cuenta

El símbolo fuente (`Logo.png`) tiene acabado cromado/3D con reflejos — funciona muy bien en `apple-touch-icon` y `android-chrome-512` (tamaños grandes), pero en **16px y 32px** (la pestaña del navegador) el detalle se compacta bastante porque es una imagen fotorrealista, no un vector plano. El propio Brand Kit lo anticipa: *"Priorizar versiones planas del logo para tamaños pequeños y reservar los efectos metálicos/3D para piezas grandes o premium"* (sección 06 — Impresión).

Si a 16px no se lee bien en la práctica, la solución sería pedir (o generar) una **versión plana de la P** — mismo dibujo, sin bisel ni reflejo, un solo tono rojo o gris sobre fondo oscuro — específicamente para el favicon chico. Avisame si querés que la arme.

## Íconos de escritorio (.ico / .icns)

Este set cubre web (favicon) y PWA/móvil (apple-touch-icon, android-chrome). Si en algún momento hacen una **app de escritorio** (Electron, .NET, etc.), van a necesitar además:
- Windows: un `.ico` con más resoluciones (16 a 256px) — puedo armarlo con el mismo proceso.
- macOS: un `.icns` — necesita un paso de empaquetado distinto (`iconutil`), también lo puedo generar si llega el momento.
