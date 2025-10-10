# Optimización de Imágenes

## Instrucciones para la Optimización

1. Instalar herramientas necesarias:
   - Instalar Node.js desde https://nodejs.org/
   - Ejecutar: `npm install -g sharp-cli`

2. Convertir imágenes a WebP:
   ```powershell
   # Para imágenes del carrusel
   sharp -i "img/inicio/*.{jpg,JPG,png}" -o "img/inicio/[name].webp" --webp
   
   # Para logos
   sharp -i "img/logos/*.{jpg,JPG,png}" -o "img/logos/[name].webp" --webp
   
   # Para imágenes de municipios
   sharp -i "img/*//*.{jpg,JPG,png}" -o "img/[folder]/[name].webp" --webp
   ```

3. Optimizar JPG/PNG existentes:
   ```powershell
   # Optimizar JPGs
   sharp -i "img/**/*.{jpg,JPG}" -o "img/[folder]/[name].jpg" --jpeg "{quality: 85}"
   
   # Optimizar PNGs
   sharp -i "img/**/*.png" -o "img/[folder]/[name].png" --png "{quality: 85}"
   ```

## Recomendaciones de Formato

- **Fotografías**: Usar WebP con fallback a JPG optimizado
- **Logos/Iconos**: Usar WebP con fallback a PNG optimizado
- **Imágenes de fondo**: Usar WebP con fallback a JPG optimizado

## Dimensiones Recomendadas

- Carrusel: 800x600px
- Logos: 250x100px (o proporción similar)
- Galerías: 800x600px máximo
- Thumbnails: 400x300px

## Comprobación de Rendimiento

1. Usar Chrome DevTools:
   - Abrir DevTools (F12)
   - Ir a la pestaña "Network"
   - Filtrar por "Img"
   - Verificar tamaños y tiempos de carga

2. Validar con Lighthouse:
   - En Chrome DevTools
   - Pestaña "Lighthouse"
   - Ejecutar análisis de Performance
   - Revisar sugerencias de optimización de imágenes