# Publicomp — contexto del proyecto

Estudio digital (Juan Pablo Brito, fundador — no mostrar el nombre en el sitio público, decisión explícita del cliente). Veinte años de trayectoria, de Venezuela a Argentina. Mercado prioritario: Argentina, atención remota.

**Antes de tocar nada**, leé en este orden:
1. [`docs/brief-estrategico-publicomp.md`](docs/brief-estrategico-publicomp.md) — posicionamiento, público objetivo, arquitectura de servicios en 3 capas, tono de voz. Documento "cerrado" salvo excepciones ya anotadas ahí mismo (ver sección de nomenclatura/tagline).
2. [`brand/brand-kit-vigente.md`](brand/brand-kit-vigente.md) — identidad visual vigente: paleta, tipografía, reglas de uso. El PDF original (`brand/Publicomp_BrandKit.pdf`) es la fuente si hay dudas.
3. `docs/territorio-visual-publicomp.md` — **histórico, descartado**. Solo para entender por qué se llegó a la dirección actual. No usar nada de ahí como referencia de diseño vigente.

## Estado del proyecto

- ✅ **Identidad de marca** — resuelta (Brand Kit del cliente, no del territorio visual original).
- ✅ **Sitio web** (`site/index.html`) — landing de una página: hero con el isotipo en 3D + íconos de stack tecnológico orbitando, arquitectura de servicios en 3 capas, proceso, trayectoria, portafolio (2 casos reales), soporte técnico, contacto con formulario de calificación, botón flotante de WhatsApp.
- ✅ **Botón de WhatsApp** — flotante, en el sitio.
- ⏳ **Pendiente, próxima fase**: sistema de gestión interno — clientes, ventas, servicios. Plataforma dual (vista interna del dueño + vista cliente) según lo define el brief en "8. La aplicación". No arrancar sin definir primero: alcance mínimo viable, modelo de datos, y si el hosting/backend ya está decidido. No asumir stack — preguntar.

## Estructura de carpetas

```
Publicomp/
├── CLAUDE.md                  este archivo
├── docs/                      estrategia — brief y territorio visual (histórico)
├── brand/                     Brand Kit oficial — PDF, logo, tarjetas, favicon/íconos
│   └── icons/                 kit de íconos fuente (favicon, apple-touch, android-chrome...)
└── site/                      el sitio web
    ├── index.html             producción — usa rutas relativas a assets/, sin nada embebido
    ├── assets/                imágenes e íconos que usa index.html
    └── artifact-preview.html  build alternativo con la imagen del isotipo embebida en base64,
                                SOLO para publicar como Artifact de Claude (que no puede cargar
                                archivos locales por rutas relativas). No es el archivo real del sitio.
```

**Importante sobre `artifact-preview.html`:** si se sigue iterando el sitio vía Artifact de Claude en una sesión de chat, hay que mantener sincronizados `index.html` (real) y `artifact-preview.html` (preview embebido) — cualquier cambio de contenido/CSS va en ambos; solo cambia cómo se referencia la imagen del isotipo (ruta relativa vs. `data:` URI).

## Reglas de marca — resumen rápido

- Paleta: negro técnico `#07090C`, grafito `#15181D`, carbón `#24282E`, rojo Publicomp `#E50914`, rojo profundo `#8B0008`, plata `#D9DEE4`, blanco `#F5F7FA`.
- Tipografía del sitio: Montserrat (display) + IBM Plex Sans (cuerpo) + JetBrains Mono (datos/labels técnicos).
- Tagline oficial: "Publicidad y Diseño Computarizado" (firma histórica, elevada a tagline — decisión del cliente que revierte la recomendación original del brief; ver nota en `docs/brief-estrategico-publicomp.md`).
- Descriptor comercial: "Diseñamos, construimos y automatizamos" (mapea a las 3 capas de servicio).
- **No inventar** casos de estudio, testimonios, métricas de resultado, ni datos de contacto (email, dominio) que no estén confirmados — el dominio todavía no está registrado.
- **No mostrar el nombre del fundador** en el sitio público (decisión explícita, 2026-09-10).

## Portafolio (casos reales en el sitio)

- **Helen Sofia** — helensofia.com — muebles y electrodomésticos, Tandil/Olavarría.
- **Tu Bazar de Lorena Bocca** — tubazardelorenabocca.com.ar — bazar del hogar, Olavarría.

Solo usar cifras verificables de estos sitios (ej. cantidad de productos/categorías) — nunca inventar métricas de conversión o resultados que no se puedan respaldar.
