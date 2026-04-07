# 🚀 Cancio.mx - Setup Final (Claude Code)

## Resumen rápido

Tienes que hacer 3 cosas en Claude Code:

1. ✅ Copiar el **favicon.svg** a `/public/`
2. ✅ Generar y copiar la **imagen OG** (1200x630) a `/public/og-preview.png`
3. ✅ Actualizar el **index.html** con meta tags + GA4

---

## Paso 1: Favicon

**Archivo**: `/public/favicon.svg` (el que ya subiste)

En el `<head>` del HTML:
```html
<link rel="icon" type="image/svg+xml" href="/favicon.svg">
<link rel="apple-touch-icon" href="/favicon.svg">
```

**Nota**: El SVG que subiste es perfecto, úsalo tal cual.

---

## Paso 2: Imagen OG (1200x630)

Abre el archivo `og-generator.html` en el navegador → descarga `og-preview.png` → copia a `/public/og-preview.png`

O crea la imagen en **Figma/Canva**:
- **Tamaño**: 1200x630px
- **Fondo**: Gradiente negro a azul oscuro (#0a0a0a a #1a2a4a)
- **Contenido**: 
  - Logo Cancio (cursive, blanco, grande)
  - "Servicios Digitales" (sub-heading)
  - "Presencia Web • Automatización • IA"

---

## Paso 3: Actualizar HTML

Reemplaza el `<head>` de tu `index.html` con esto:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- SEO Básico -->
    <title>Cancio - Servicios Digitales</title>
    <meta name="description" content="Servicios digitales: presencia web, automatización e IA. Transformamos negocios en línea.">
    
    <!-- Favicon -->
    <link rel="icon" type="image/svg+xml" href="/favicon.svg">
    <link rel="apple-touch-icon" href="/favicon.svg">
    
    <!-- Open Graph (Redes Sociales) -->
    <meta property="og:type" content="website">
    <meta property="og:title" content="Cancio - Servicios Digitales">
    <meta property="og:description" content="Presencia web, automatización e IA para tu negocio.">
    <meta property="og:image" content="https://cancio.mx/og-preview.png">
    <meta property="og:image:width" content="1200">
    <meta property="og:image:height" content="630">
    <meta property="og:url" content="https://cancio.mx">
    <meta property="og:site_name" content="Cancio">
    
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Cancio - Servicios Digitales">
    <meta name="twitter:description" content="Presencia web, automatización e IA para tu negocio.">
    <meta name="twitter:image" content="https://cancio.mx/og-preview.png">
    
    <!-- Canonical URL -->
    <link rel="canonical" href="https://cancio.mx">
    
    <!-- Google Analytics 4 -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-ZX8C8QJN8G"></script>
    <script>
        window.dataLayer = window.dataLayer || [];
        function gtag(){dataLayer.push(arguments);}
        gtag('js', new Date());
        gtag('config', 'G-ZX8C8QJN8G');
    </script>
</head>
<body>
    <!-- Tu contenido aquí -->
</body>
</html>
```

---

## Paso 4: Git + Deploy

```bash
git add .
git commit -m "Add favicon, OG tags, and GA4 analytics"
git push
```

Cloudflare Pages redeploy automáticamente → en 2-3 minutos estará live.

---

## Paso 5: Verificar

### Favicon
- Visita https://cancio.mx
- Abre DevTools (F12) → Elements
- Verifica que `<link rel="icon" ...>` esté ahí
- Recarga la página → debería aparecer la "C" en la pestaña

### Open Graph Preview
- Ve a [Facebook OG Debugger](https://developers.facebook.com/tools/debug/og/object/)
- Ingresa: `https://cancio.mx`
- Verifica que aparezca:
  - Título: "Cancio - Servicios Digitales"
  - Descripción: "Presencia web, automatización..."
  - Imagen: og-preview.png (1200x630)

### Analytics
- Ve a https://analytics.google.com
- Busca la propiedad "Cancio"
- Abre **Real-time** → debería mostrar 1 sesión activa

---

## 📋 Checklist final

- [ ] `/public/favicon.svg` existe
- [ ] `/public/og-preview.png` existe (1200x630)
- [ ] HTML tiene todos los meta tags OG
- [ ] GA4 script está en el `<head>`
- [ ] Git push hecho
- [ ] Cloudflare Pages redeploy completado
- [ ] Favicon aparece en la pestaña ✓
- [ ] OG Debugger muestra preview correcto ✓
- [ ] GA4 Real-time muestra sesión activa ✓

---

## 🎯 Próximo nivel

Una vez que todo funcione, **documentamos esto como template HAZO estándar** para que todos los proyectos nuevos (Kapturit, Milla & Roxy, etc.) usen la misma estructura.

Archivos base:
- `HAZO-WEB-STANDARD.md` (guía maestra)
- `index-template.html` (template HTML)
- `favicon-generator.svg` (template favicon)

---

**¿Necesitas ayuda con Claude Code o va listo?**
