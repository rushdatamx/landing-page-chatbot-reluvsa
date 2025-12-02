# Landing Page - Refaccionaria de Llantas

Landing page de alta conversión para refaccionarias de llantas con redirección a WhatsApp.

## Stack Tecnológico

- **Framework**: Astro
- **Estilos**: Tailwind CSS v4
- **Tracking**: Facebook Pixel + Google Analytics 4
- **Deploy**: Compatible con Vercel, Netlify, etc.

## Comandos

```bash
# Instalar dependencias
npm install

# Iniciar servidor de desarrollo
npm run dev

# Construir para producción
npm run build

# Vista previa del build
npm run preview
```

## Personalización

### 1. Datos del Negocio

Debes personalizar los siguientes archivos con la información real del cliente:

| Archivo | Qué personalizar |
|---------|------------------|
| `src/layouts/Layout.astro` | Nombre, teléfono, ciudad, FB Pixel ID, GA ID |
| `src/components/Header.astro` | Nombre del negocio, número de WhatsApp, logo |
| `src/components/Hero.astro` | Años de experiencia, número de clientes, ciudad |
| `src/components/SocialProof.astro` | Estadísticas, testimonios reales |
| `src/components/Services.astro` | Tipos de vehículos, marcas de llantas |
| `src/components/FAQ.astro` | Preguntas frecuentes específicas |
| `src/components/Footer.astro` | Dirección, horarios, redes sociales |
| `src/components/WhatsAppButton.astro` | Número de WhatsApp |
| `src/pages/privacidad.astro` | Datos legales del negocio |

### 2. Colores de Marca

Edita el archivo `src/styles/global.css` para cambiar los colores:

```css
@theme {
  --color-primary-500: #3b82f6;  /* Color principal */
  --color-primary-600: #2563eb;  /* Hover */
  /* ... más colores */
}
```

### 3. Logo

Reemplaza o actualiza:
- `public/favicon.svg` - Favicon del sitio
- Agrega tu logo en `public/images/logo.png`
- Actualiza la referencia en `Header.astro`

### 4. Imágenes

Agrega imágenes en la carpeta `public/images/`:
- `og-image.jpg` - Imagen para compartir en redes (1200x630px recomendado)
- Logo del negocio
- Fotos de testimonios (opcional)

### 5. Tracking

#### Facebook Pixel
1. Obtén tu Pixel ID de Facebook Business Manager
2. Reemplaza `[FB_PIXEL_ID]` en `Layout.astro`

#### Google Analytics 4
1. Crea una propiedad en Google Analytics
2. Reemplaza `[GA_ID]` con tu ID (formato: G-XXXXXXXXXX)

## Estructura del Proyecto

```
/
├── src/
│   ├── components/
│   │   ├── Header.astro        # Navegación superior
│   │   ├── Hero.astro          # Sección principal
│   │   ├── Benefits.astro      # Beneficios con iconos
│   │   ├── SocialProof.astro   # Testimonios y estadísticas
│   │   ├── Services.astro      # Tipos de vehículos/marcas
│   │   ├── Process.astro       # 3 pasos para cotizar
│   │   ├── FAQ.astro           # Preguntas frecuentes
│   │   ├── Footer.astro        # Pie de página
│   │   └── WhatsAppButton.astro # Botón flotante
│   ├── layouts/
│   │   └── Layout.astro        # Layout con meta tags y tracking
│   ├── pages/
│   │   ├── index.astro         # Página principal
│   │   └── privacidad.astro    # Aviso de privacidad
│   └── styles/
│       └── global.css          # Estilos globales y colores
├── public/
│   ├── images/                 # Imágenes estáticas
│   └── favicon.svg             # Favicon
└── package.json
```

## Deploy

### Vercel (Recomendado)
```bash
npm i -g vercel
vercel
```

### Netlify
```bash
npm i -g netlify-cli
netlify deploy --prod
```

## Checklist Pre-Launch

- [ ] Reemplazar todos los `[PLACEHOLDER]` con datos reales
- [ ] Agregar logo del negocio
- [ ] Configurar número de WhatsApp correcto
- [ ] Agregar testimonios reales (con permiso)
- [ ] Configurar Facebook Pixel
- [ ] Configurar Google Analytics
- [ ] Crear imagen og-image.jpg para redes
- [ ] Probar todos los links de WhatsApp
- [ ] Revisar en móvil
- [ ] Verificar velocidad de carga (< 3s)

## Soporte

Creado para uso con chatbots de WhatsApp. Optimizado para campañas de Facebook Ads y Google Ads.
