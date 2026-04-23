# Closet Virtual — Prototipo

Prototipo funcional de una web app para gestión de armario personal: inventario de prendas, composición de outfits, calendario de uso, ciclo de lavado, perfil de estilo y recomendaciones con IA.

> Este repositorio contiene un **prototipo de un solo archivo HTML** con persistencia local (`localStorage`). No es la versión final del producto, sino una maqueta funcional para validar la UX y el modelo de datos antes de construir la aplicación en Next.js.

**Autor:** Samuel Ortega
**Tipo:** Trabajo de clase · prototipo funcional
**Stack del prototipo:** HTML + CSS + JavaScript vanilla (sin frameworks, sin backend)

---

## Ver la app

**Online (GitHub Pages):** https://samtho.github.io/closet-virtual-prototype/

**Local:** descarga el repositorio y abre `index.html` directamente en cualquier navegador moderno (Chrome, Safari, Firefox, Edge). No requiere instalación de dependencias.

---

## Qué hace

Siete secciones conectadas entre sí:

1. **Inventario** — CRUD de prendas con foto, tipos, colores, materiales, estilos, formalidad y estado
2. **Outfits** — composición de prendas con tags de clima, momento del día, actividad y formalidad
3. **Calendario** — planificación de outfits futuros y registro de uso diario
4. **Ciclo de lavado** — umbrales editables por tipo de prenda; paso automático a "pendiente de lavado"
5. **Perfil y estilo** — estilos preferidos, colorimetría estacional y formalidad por contexto
6. **Recomendaciones** — motor de reglas + integración con Open-Meteo + narrador opcional con IA
7. **Ajustes** — editor de paleta, API keys, export/import de datos, tour guiado

## Cómo usarlo

1. Abre `index.html` en el navegador
2. La primera vez se lanza un **tour guiado de 7 pasos** que explica cada sección
3. Se cargan **10 prendas de ejemplo** (4 con fotos reales del autor, 6 con ilustraciones SVG generadas)
4. Navega las tabs y prueba el flujo: crea una prenda, compón un outfit, asígnalo a un día, regístralo como usado

## Personalización

Desde la tab **Ajustes** puedes:

- Cambiar la **paleta de colores** (3 presets: Dark Teal, Cartografía, Teal + Black Cherry) o editar los 6 slots manualmente
- Configurar **API keys** de Claude, Gemini u OpenAI para activar el etiquetado automático y el narrador de recomendaciones
- **Exportar / importar** todos tus datos en JSON
- **Recargar** los datos de ejemplo o **borrar** todo

## Uso de IA

Este proyecto fue construido colaborando con **Claude** (Anthropic) en modo agente:

- Diseño del modelo de datos y los vocabularios cerrados
- Implementación de la capa de persistencia y motor de reglas
- Generación de ilustraciones SVG sintéticas para prendas sin foto
- Redacción de textos del onboarding y recomendaciones

La app también puede **llamar a Claude, Gemini u OpenAI en runtime** desde el propio navegador para:

- Sugerir tags automáticos al subir una foto de prenda
- Narrar por qué un outfit funciona para el día de hoy (tono, clima, perfil)

> Las API keys se guardan en `localStorage` del navegador. Es un prototipo, no se debe usar con claves sensibles.

## Estructura

```
closet-virtual-prototype/
├── index.html       # App completa en un único archivo
├── README.md        # Este archivo
└── LICENSE          # MIT
```

Todo (HTML + CSS + JS + imágenes base64) vive en `index.html`. ~210 KB.

## Limitaciones conocidas

- **Persistencia solo local:** los datos viven en `localStorage` del navegador; limpiar caché los borra (usa Export/Import para backup)
- **CORS con APIs de IA:** llamar a Claude/OpenAI desde `file://` suele bloquearse por CORS. Gemini suele funcionar. En producción se resolverá con backend proxy.
- **Sin autenticación ni multiusuario:** cada navegador tiene su propio armario

## Próximos pasos

Este prototipo es la base para una futura aplicación en **Next.js 15 + Prisma + PostgreSQL** con autenticación, almacenamiento de imágenes y las features de IA generativa completas (análisis de look, try-on virtual).

---

## Licencia

MIT — ver `LICENSE`.
