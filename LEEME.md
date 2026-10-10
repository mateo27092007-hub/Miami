# NASFECO US INTERNATIONAL · Miami

Web de dos experiencias Waterdrop (X12 y X16) con el servicio NASFECO, en inglés (`index.html`) y español (`es.html`).
Sigue la **Guía para desarrollar la web de NASFECO US International** (Escritorio › Cosas nasfeco, 8/10/2026) y su demo navegable.

## Ver la página (sin publicar)
Doble clic en `ABRIR-PAGINA.bat`: abre http://127.0.0.1:8765/es.html solo en esta computadora. Cerrar esa ventana la apaga.
Hace falta el servidor local: abriendo el .html directo, YouTube bloquea los Shorts ("Error 153").

## Dónde se cambia cada cosa
- **Precios, modelos, colores de llave, fotos:** `MODELS` en `_build/build_miami.py` (X12 $2,499 · X16 $3,499, impuestos incluidos).
- **Textos:** el mismo archivo, con `L("inglés", "español")`. Después: `python _build/build_miami.py`.
- **Diseño:** `css/site.css` (paleta de la guía: azul noche #081F2A, dorado #D5B581; letra Plus Jakarta Sans, cambiada a pedido porque la DM Serif se veía pobre).
- **Comportamiento:** `js/site.js` (selector X12/X16, punto de la llave, fichas, comparador, guía de elección, valoración, kit, cuidado, concierge, Shorts).
- **WhatsApp (temporal, Ecuador):** `WA_NUM` en el generador.

## Páginas (como la tienda de Ecuador)
- **Inicio** (`es.html` / `index.html`): portada con el equipo en 3D que gira al bajar · equipos X12 y X16 (tarjetas que abren su página) · tú eliges / NASFECO hace todo · **Así instala NASFECO** (3D que avanza al bajar) · **Tu bienvenida** (kit en 3D saliendo de la caja) · qué incluye · ¿Cabe en tu mueble? (3D + calculadora) · Shorts · preguntas · cierre.
- **X12** (`x12-es.html` / `x12.html`) y **X16** (`x16-es.html` / `x16.html`): foto o 3D, colores (equipo blanco/negro, llave plateada/negra), precio todo incluido, lo que hace, instalación 3D, kit 3D, qué incluye, medidor 3D, ficha técnica y enlace al otro equipo.

## Colores y 3D
- Fotos oficiales: X12 blanco y X16 negro (cada uno con llave plateada o negra). Las otras combinaciones (X12 negro, X16 blanco) se muestran con el modelo 3D. Confirmar disponibilidad real con Waterdrop.
- Modelo 3D (`js/x3d.js`, `js/x3d-init.js`): hecho en código con las medidas oficiales 18.2 × 6.25 × 16.72 in (iguales en X12 y X16). Si llega el archivo 3D oficial, se cambia ahí.
- Fondo vivo (agua y luz, líneas que fluyen y halo que sigue el mouse): `js/bg.js`.
- Short de cada producto (debajo de fotos y precio): `PSHORT` en el generador.
- Instalación y kit en 3D: `js/x3d-scenes.js` (animaciones ilustrativas).
- **Video real de instalación** (p. ej. hecho en Google Flow): guárdalo como `assets/video/instalacion.mp4` (y si quieres una portada, `assets/video/instalacion.jpg`) y ejecuta `python _build/build_miami.py`; aparece solo debajo de la animación.
- Prototipos de portada: `prototipos/` (no se publican).

## Valoración
3 pasos (experiencia → cocina → contacto) con validación. Al final se abre WhatsApp con la solicitud escrita o se descarga un resumen. No se guarda nada en un servidor, no se cobra y no se reserva cita hasta que NASFECO confirme.

## Pendiente según la guía (sección 10) — no publicar sin confirmar
Referencias exactas de X12/X16 y garantía en EE. UU. · qué cubre la instalación estándar · los 2 cartuchos (modelo, calendario) · modelo/acabado de Owala, bolso y toalla (fotos reales) · número y canal de contacto en EE. UU. · medios y momento de pago · Inner Circle.
Las escenas de cocina y el kit son ambientaciones ilustrativas (así lo indica la página).

## Publicar (Cloudflare)
Repositorio propio (no el de Ecuador) → `npx wrangler deploy`; `wrangler.jsonc` usa `nasfeco-miami`. La página lleva `noindex` hasta que NASFECO autorice el lanzamiento.
`_build/`, `_archivo/` y `ABRIR-PAGINA.bat` no se publican (`.assetsignore`).
Versiones anteriores: `_archivo/tienda-v3` (tienda X12 de octubre) y `_archivo/assets-sin-uso` (fotos y videos que ya no se usan).
