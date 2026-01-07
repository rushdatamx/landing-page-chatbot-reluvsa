# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Landing page de alta conversión para Reluvsa Autopartes, una refaccionaria de llantas en Cd. Victoria, Tamaulipas, México. La página redirige usuarios a WhatsApp donde un chatbot de IA procesa cotizaciones y pagos.

## Tech Stack

- **Framework**: Astro 5
- **Estilos**: Tailwind CSS v4 (usando `@tailwindcss/vite` y `@theme` para colores)
- **Tracking**: Google Ads + Google Analytics 4 + Facebook Pixel
- **Deploy**: Compatible con Vercel, Netlify

## Commands

```bash
npm run dev      # Servidor de desarrollo
npm run build    # Build de producción
npm run preview  # Vista previa del build
```

## Architecture

- `src/layouts/Layout.astro` - Layout base con meta tags, tracking scripts (GA4, Google Ads, FB Pixel), y Schema.org LocalBusiness
- `src/pages/index.astro` - Página principal que compone todos los componentes de sección
- `src/styles/global.css` - Colores de marca usando `@theme` de Tailwind v4
- `src/components/` - Secciones independientes (Hero, Benefits, Services, SocialProof, Process, FAQ, Footer, Header, WhatsAppButton)

## Configuration

**Fuente principal de configuración**: `src/layouts/Layout.astro` contiene el objeto `config` con:
- `siteName`, `phone`, `city`, `siteUrl`
- `fbPixelId`, `gaId`, `gadsId` (tracking IDs)

**Otros componentes** también tienen `const config` local para datos específicos (buscar `const config` en cada archivo).

### Colores de Marca

Definidos en `src/styles/global.css` usando `@theme`:
- `--color-primary-*`: Amarillo (#FFD700)
- `--color-secondary-*`: Rojo (#E31837)
- `--color-whatsapp`: Verde WhatsApp (#25D366)

## Key Patterns

- **WhatsApp URLs**: `https://wa.me/{phone}?text={encodedMessage}`
- **Tracking de clics WhatsApp**: Auto-detecta links a `wa.me` y dispara:
  - Google Ads conversion (`AW-636802231/whatsapp_click`)
  - GA4 event (`whatsapp_click`)
  - FB Pixel event (`Contact`)
- **Responsive**: Mobile-first con breakpoints `sm:`, `md:`, `lg:`

## Related Systems

Parte del ecosistema RELUVSA:
- **Chatbot WhatsApp** (Supabase Edge Functions + OpenAI)
- **Dashboard de administración** (Next.js, repo separado)
- **Pagos** (Stripe payment links)
