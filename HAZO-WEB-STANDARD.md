# 🏗️ HAZO Web Projects - Standard Setup

## Checklist para cada nuevo proyecto

Este es el **estándar mínimo** que debe tener todo sitio web de HAZO.

---

## 1️⃣ **Favicon**

### Qué es
- Icono pequeño (16x16, 32x32, 64x64px) que aparece en la pestaña del navegador
- También se usa como apple-touch-icon en mobile

### Cómo hacerlo
1. Crear un SVG con la **primera letra del cliente** en una tipografía elegante
2. Guardar como `/favicon.svg` en la raíz del proyecto
3. Linkear en el `<head>`:

```html
<link rel="icon" type="image/svg+xml" href="/favicon.svg">
<link rel="apple-touch-icon" href="/favicon.svg">
```

### Tipografías recomendadas (Google Fonts)
- **Formal/Elegante**: Great Vibes, Playfair Display, Bodoni Moda
- **Moderna**: Poppins, Inter, DM Sans
- **Creative**: Caveat, Righteous, Fredoka

---

## 2️⃣ **Open Graph Meta Tags** (para compartir en redes)

### Qué es
- Metadatos que controlan cómo se ve el sitio cuando lo compartes en WhatsApp, Facebook, LinkedIn, Twitter, etc.
- **Imagen recomendada**: 1200x630px (ratio 1.91:1)

### Meta tags obligatorios

```html
<!-- Título y descripción -->
<title>Nombre del Proyecto</title>
<meta name="description" content="Descripción corta del negocio">

<!-- Open Graph -->
<meta property="og:type" content="website">
<meta property="og:title" content="Nombre del Proyecto">
<meta property="og:description" content="Descripción corta">
<meta property="og:image" content="https://ejemplo.com/og-preview.png">
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
<meta property="og:url" content="https://ejemplo.com">
<meta property="og:site_name" content="Nombre del Proyecto">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Nombre del Proyecto">
<meta name="twitter:description" content="Descripción corta">
<meta name="twitter:image" content="https://ejemplo.com/og-preview.png">

<!-- Canonical URL -->
<link rel="canonical" href="https://ejemplo.com">
```

### Cómo crear la imagen OG
- **Tamaño**: 1200x630px
- **Formato**: PNG o JPG
- **Ubicación**: `/public/og-preview.png`
- **Contenido**: Logo/inicial del cliente + nombre + tagline corto

**Herramientas recomendadas:**
- Figma (template design)
- Canva (si es rápido)
- Script Python con Pillow (automatizado)

---

## 3️⃣ **Google Analytics 4 (GA4)**

### Qué es
- Herramienta gratuita de Google para trackear visitors, comportamiento, conversiones, etc.
- Essential para entender cómo el sitio se está desempeñando

### Setup rápido

1. Ir a **Google Analytics** (analytics.google.com)
2. Click **Admin** → **Create Property**
3. Nombre: "Nombre del Proyecto"
4. Timezone: America/Mexico_City (o el del cliente)
5. Copiar el **Measurement ID** (formato: `G-XXXXXXXXXX`)

### Agregar al HTML

```html
<!-- Google Analytics 4 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());
    gtag('config', 'G-XXXXXXXXXX');
</script>
```

**Ubicación en el HTML**: Al final del `<head>` o después del favicon.

### Verificar que funciona
1. Visita el sitio live
2. Abre **DevTools** → **Console**
3. Busca mensajes de `gtag` o `Google Analytics`
4. En GA4, ve a **Real-time** → deberías ver una sesión activa

---

## 4️⃣ **Canonical URL**

### Qué es
- Le dice a Google cuál es la versión "oficial" del sitio
- Evita duplicados y mejora SEO

### Cómo hacerlo

```html
<link rel="canonical" href="https://ejemplo.com">
```

---

## 📋 **Checklist de implementación**

Para cada nuevo proyecto, verificar:

- [ ] Favicon creado y linkeado
- [ ] Meta tags OG completos (title, description, image, url)
- [ ] Imagen OG 1200x630px en `/public/og-preview.png`
- [ ] Twitter Card meta tags agregados
- [ ] GA4 Measurement ID obtenido
- [ ] Script GA4 en el `<head>`
- [ ] Canonical URL agregada
- [ ] Testear que GA4 funciona (Real-time en analytics.google.com)
- [ ] Testear preview al compartir en WhatsApp/LinkedIn/Twitter

---

## 🔗 **Template HTML Base**

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Título y descripción -->
    <title>Nombre del Proyecto</title>
    <meta name="description" content="Descripción corta">
    
    <!-- Favicon -->
    <link rel="icon" type="image/svg+xml" href="/favicon.svg">
    <link rel="apple-touch-icon" href="/favicon.svg">
    
    <!-- Open Graph -->
    <meta property="og:type" content="website">
    <meta property="og:title" content="Nombre del Proyecto">
    <meta property="og:description" content="Descripción corta">
    <meta property="og:image" content="https://ejemplo.com/og-preview.png">
    <meta property="og:image:width" content="1200">
    <meta property="og:image:height" content="630">
    <meta property="og:url" content="https://ejemplo.com">
    <meta property="og:site_name" content="Nombre del Proyecto">
    
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Nombre del Proyecto">
    <meta name="twitter:description" content="Descripción corta">
    <meta name="twitter:image" content="https://ejemplo.com/og-preview.png">
    
    <!-- Canonical -->
    <link rel="canonical" href="https://ejemplo.com">
    
    <!-- Google Analytics 4 -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
    <script>
        window.dataLayer = window.dataLayer || [];
        function gtag(){dataLayer.push(arguments);}
        gtag('js', new Date());
        gtag('config', 'G-XXXXXXXXXX');
    </script>
</head>
<body>
    <!-- Contenido aquí -->
</body>
</html>
```

---

## 🚀 **Next Steps**

1. **Duplicar este template** para cada nuevo proyecto
2. **Personalizar** favicon, meta tags y GA4 ID
3. **Crear la imagen OG** (1200x630)
4. **Subir a GitHub**
5. **Deployar a Cloudflare Pages**
6. **Verificar** que GA4 trackea en Real-time

---

## 📊 **Recursos**

- [Open Graph Debugger](https://developers.facebook.com/tools/debug/og/object/)
- [Twitter Card Validator](https://cards-dev.twitter.com/validator)
- [Google Analytics Setup](https://support.google.com/analytics/answer/10089681)
- [Favicon Generator](https://favicon.io/)
