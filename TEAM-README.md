# Sistema de Tarjetas Digitales — Veldrion

Sistema de perfiles digitales para empleados de Veldrion. Cada empleado tiene su propia tarjeta de presentación online con información de contacto y redes sociales.

## 📂 Estructura de archivos

```
veldrion-info/
├── index.html              # Página principal (enlaces Veldrion)
├── equipo/
│   └── index.html          # Índice del equipo (URL: /equipo)
├── carlosplata/
│   └── index.html          # Perfil Carlos (URL: /carlosplata)
├── anarodriguez/
│   └── index.html          # Perfil Ana (URL: /anarodriguez)
├── shared/
│   └── card.css           # CSS compartido para tarjetas
├── assets/
│   ├── logo.svg
│   └── avatars/           # Fotos de empleados
└── styles.css             # CSS de página principal
```

## 🆕 Cómo añadir un nuevo empleado

### Paso 1: Crear carpeta con nombre de usuario

```bash
mkdir nombreapellido
```

**Importante:** El nombre de la carpeta será la URL. Usa minúsculas sin espacios.
- Ejemplo: `carlosplata` → URL será `veld.info/carlosplata`

### Paso 2: Copiar plantilla

```bash
cp carlosplata/index.html nombreapellido/index.html
```

### Paso 3: Editar el HTML

Abre el archivo `nombreapellido/index.html` y actualiza:

1. **`<title>`** - Cambia el nombre en el título
2. **`<meta name="description">`** - Actualiza la descripción
3. **Avatar** - Cambia la URL de la imagen o sube a `/assets/avatars/nombre.jpg`
4. **Nombre y título** - Actualiza nombre, cargo, bio
5. **Email, teléfono, WhatsApp** - Cambia contactos
6. **Redes sociales** - Actualiza URLs de LinkedIn, Twitter, etc.

### Paso 4: Añadir al índice del equipo

Abre `equipo/index.html` y añade una tarjeta nueva dentro de `<div class="team-grid">`:

```html
<a href="/nombreapellido" class="team-card">
  <img class="team-card-avatar" src="https://i.pravatar.cc/300?img=XX" alt="Nombre Apellido" />
  <h2 class="team-card-name">Nombre Apellido</h2>
  <p class="team-card-title">Cargo</p>
  <p class="team-card-email">
    <svg width="14" height="14" fill="none" stroke="currentColor" viewBox="0 0 24 24">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
    </svg>
    email@veldrion.com
  </p>
</a>
```

**Importante:** El `href="/nombreapellido"` debe coincidir con el nombre de la carpeta.

### Paso 4: Subir a GitHub

```bash
git add .
git commit -m "Añadir perfil de [Nombre Apellido]"
git push
```

## 🎨 Personalización

### Cambiar colores

Edita las variables CSS en `shared/card.css`:

```css
:root{
  --orange:#dd5000;        /* Color principal */
  --bg-dark:#0a0a0a;       /* Fondo */
  --bg-card:#161616;       /* Fondo de tarjetas */
  --text:#ffffff;          /* Texto principal */
  --text-muted:#9ca3af;    /* Texto secundario */
}
```

### Usar fotos propias

1. Sube las fotos a `assets/avatars/`
2. Recomendación: formato JPG o WebP, 400x400px, <200KB
3. Actualiza la ruta en el HTML:
   ```html
   <img class="card-avatar" src="/assets/avatars/nombre.jpg" alt="Nombre" />
   ```

## 🔗 URLs del sistema

- **Página principal:** `https://veld.info/` (o GitHub Pages)
- **Índice del equipo:** `https://veld.info/equipo`
- **Perfil individual:** `https://veld.info/nombreapellido`

### Ejemplos:
- `https://veld.info/carlosplata` → Carlos Martínez
- `https://veld.info/anarodriguez` → Ana Rodríguez

**URLs limpias sin .html** - Cada carpeta con `index.html` se sirve automáticamente.

## 📱 Compartir tarjetas

Cada empleado puede compartir su URL directa:
- Por WhatsApp
- En firma de email
- En redes sociales
- Código QR (generar en qr-code-generator.com)

## 🛠️ Tecnologías

- HTML5 + CSS3
- Sin JavaScript (más rápido y ligero)
- Sin dependencias externas
- 100% responsive
- GitHub Pages para hosting

## 💡 Tips

- **Fotos profesionales:** Fondo neutro, buena iluminación
- **Bio concisa:** 2-3 líneas máximo
- **Links actualizados:** Verificar redes sociales y contacto
- **Consistencia:** Usar el mismo estilo para todos

## 📞 Soporte

Para dudas o problemas, contactar a: info@veldrion.com
