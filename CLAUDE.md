# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML quick-use manual (in Spanish) for the FNIRSI 2C23T oscilloscope/multimeter/DDS signal generator. Produced for UTN (Universidad Tecnológica Nacional). No build system — open `index.html` directly in a browser.

## Structure

| File | Purpose |
|---|---|
| `index.html` | Single-file manual: all CSS in `<style>`, all JS inline `<script>` tags |
| `foto_*.jpg/jpeg/png` | Device photos referenced by the HTML |
| `logo_utn.png` | Institution logo shown in the cover |

Video files are **not tracked** in the repo. The manual expects these files to sit alongside `index.html` at runtime:

```
video_osciloscopio.mp4
video_multimetro.mp4
video_generador.mp4
video_exportacion.mp4
video_uso_general.mp4
```

If a video file is missing, the inline JS in section 13 replaces the `<video>` element with a styled placeholder automatically — no errors thrown.

## Manual Sections

Sections are numbered `01`–`14` inside `<div class="section-title">` elements:

| # | Title |
|---|---|
| 01 | Descripción General |
| 04 | Encendido y Selección de Modo |
| 05 | Modo Osciloscopio |
| 06 | Modo Multímetro |
| 07 | Modo Generador de Señales DDS |
| 08 | Referencia de Botones |
| 09 | Guardado y Exportación de Datos |
| 10 | Configuración del Sistema |
| 11 | Carga y Mantenimiento |
| 12 | Especificaciones Técnicas |
| 13 | Videos de Uso |
| 14 | Resolución de Problemas |

## External Dependencies

- **Google Fonts** (Barlow + Barlow Condensed) — loaded via CDN link in `<head>`. Falls back to system sans-serif if offline.
- No JavaScript libraries, no npm, no bundler.

## Previewing

```bash
# Any of these work:
xdg-open index.html
python3 -m http.server 8080   # then open http://localhost:8080
```

Use a local HTTP server (not `file://`) if videos need to load, since some browsers block media on the `file://` protocol.
