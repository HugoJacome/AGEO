# Tarjeta de Presentación — Ing. Alberto Escobar Oñate (AGEO Constructora)

Cliente: **Alberto Guillermo Escobar Oñate** — Ingeniero Civil, AGEO Constructora
Ciudad: Ambato (Huachi Grande) — Ecuador
Ficha de levantamiento: 28 de septiembre de 2026 · Plan: **Combo Tarjeta NFC + Perfil Digital ($30 + IVA)**, 1 tarjeta

## Datos usados

| Campo | Valor |
|---|---|
| Celular / WhatsApp | 098 727 1384 |
| Correo | a_g_e_o@hotmail.com |
| Dirección | Huachi Grande · Ambato (enlace de búsqueda en Maps, no pin exacto) |
| Horario | Lunes a viernes (sin horas) |
| Mensaje de WhatsApp | «Buen día, estoy interesado en recibir información sobre sus servicios.» (corregida la errata «sercicios») |
| TikTok | [@albertogescobar](https://www.tiktok.com/@albertogescobar) |
| Facebook | «Alberto Escobar Oñate» (sin enlace, ver pendientes) |
| Color | Azul marino + azul y naranja del logo |
| Impreso en la tarjeta | ING. ALBERTO ESCOBAR O. · Ingeniero Civil |
| Dominio previsto | `ageo.evowebec.com` |

> **Pendiente de confirmar con el cliente:**
> - **Enlace real de Facebook.** Solo dio el nombre; el botón abre una búsqueda en Facebook. Cambiarlo por la URL del perfil o página.
> - **Biografía.** No envió; se puso una línea neutra propuesta: «Ingeniería civil y construcción en Ambato, Tungurahua». Igual la franja de la cabecera («Ingeniería · Construcción»).
> - **Horas de atención** de lunes a viernes, y si atiende sábados.
> - **Enlace de Google Maps** de la oficina u obra (ahora es una búsqueda de «Huachi Grande, Ambato»).
> - Solo marcó el botón de WhatsApp; se añadieron Guardar contacto, Llamar y Correo porque son los básicos. Quitar si no los quiere.
> - Sin foto: la insignia usa el logo circular.

## Contenido de la carpeta

```
AGEO/
├── index.html                  → tarjeta digital (la que abre el NFC/QR)
├── alberto-escobar.vcf         → contacto descargable
├── CNAME                       → ageo.evowebec.com
├── QR-AgeoConstructora.png     → QR azul marino para posts y material digital
├── img/
│   ├── logo-original.png            → tal como lo envió el cliente (con aro y fondo blanco)
│   ├── logo-circular.png            → logo con aro, fuera del círculo transparente (insignia)
│   ├── logo-emblema.png             → edificio + AGEO + CONSTRUCTORA, a color, fondo transparente
│   ├── logo-emblema-blanco.png      → emblema todo blanco
│   └── logo-emblema-blanco-naranja.png → blanco con los acentos naranjas (para fondo marino)
└── nfc/
    ├── nfc-frontal-evolis.html      → plantilla editable del frente
    ├── nfc-posterior-evolis.html    → plantilla editable del reverso
    ├── NFC-AGEO-Frontal-Evolis.png   ← ARCHIVO PARA IMPRIMIR (frente)
    ├── NFC-AGEO-Posterior-Evolis.png ← ARCHIVO PARA IMPRIMIR (reverso)
    ├── qr-ageo.png                  → QR negro de alto contraste del reverso
    └── fonts/                       → Montserrat y Josefin Sans locales (el PNG sale igual sin internet)
```

## Impresión de la tarjeta NFC (Evolis)

- Medida: **1012 × 638 px = 85,6 × 54 mm a 300 dpi** (CR80).
- Frente azul marino a sangre completa (#0B2545) con el emblema en blanco y naranja: sacar prueba antes, la cobertura oscura total es la que más exige a la cinta.
- El reverso es blanco con banda marina inferior; QR negro sobre blanco.

## Programación del chip NFC

Grabar el registro **URL**: `https://ageo.evowebec.com` (mismo destino del QR).

## Para publicar

1. Crear el repositorio (p. ej. `HugoJacome/ageo-tarjeta`) y subir la carpeta.
2. Activar GitHub Pages: Settings → Pages → *Deploy from a branch* → `main` → `/ (root)`.
3. DNS: crear `ageo.evowebec.com` como CNAME a `hugojacome.github.io`.

## Regenerar los PNG después de editar

```bash
chrome-headless-shell --headless --disable-gpu --hide-scrollbars \
  --allow-file-access-from-files --force-device-scale-factor=1 \
  --window-size=1012,638 --virtual-time-budget=6000 \
  --screenshot=NFC-AGEO-Frontal-Evolis.png nfc-frontal-evolis.html
```

(igual para el reverso, cambiando los dos nombres de archivo)
