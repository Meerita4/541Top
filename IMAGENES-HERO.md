# Imágenes del Carrusel Hero

## Cómo agregar tus propias imágenes

### Paso 1: Preparar las imágenes
1. Selecciona 4 imágenes de alta calidad relacionadas con vela/Optimist/ILCA
2. Tamaño recomendado: **1920x1080 píxeles** o mayor
3. Formato recomendado: **JPG** o **WebP** (mejor optimización)
4. Peso recomendado: Máximo 500KB por imagen (optimiza con herramientas como TinyPNG)

### Paso 2: Nombrar las imágenes
Recomiendo usar nombres descriptivos:
- `hero-1.jpg` - Primera imagen (ej: Optimist navegando)
- `hero-2.jpg` - Segunda imagen (ej: ILCA en regata)
- `hero-3.jpg` - Tercera imagen (ej: Entrenamiento en grupo)
- `hero-4.jpg` - Cuarta imagen (ej: Competición)

### Paso 3: Colocar las imágenes
Copia las imágenes en la carpeta: `public/images/hero/`

```
541top/
└── public/
    └── images/
        └── hero/
            ├── hero-1.jpg
            ├── hero-2.jpg
            ├── hero-3.jpg
            └── hero-4.jpg
```

### Paso 4: Actualizar el código
Abre `src/pages/index.astro` y busca las líneas del carrusel (aprox. línea 11-40).

Reemplaza las URLs de Unsplash por tus imágenes locales:

```html
<!-- Slide 1 -->
<div class="hero-slide active absolute inset-0">
  <img 
    src="/images/hero/hero-1.jpg" 
    alt="Entrenamiento de vela Optimist" 
    class="w-full h-full object-cover"
  >
  <div class="absolute inset-0 bg-gradient-to-r from-blue-900/80 via-blue-800/60 to-transparent"></div>
</div>

<!-- Slide 2 -->
<div class="hero-slide absolute inset-0">
  <img 
    src="/images/hero/hero-2.jpg" 
    alt="Entrenamiento ILCA" 
    class="w-full h-full object-cover"
  >
  <div class="absolute inset-0 bg-gradient-to-r from-blue-900/80 via-blue-800/60 to-transparent"></div>
</div>

<!-- Slide 3 -->
<div class="hero-slide absolute inset-0">
  <img 
    src="/images/hero/hero-3.jpg" 
    alt="Entrenamiento en equipo" 
    class="w-full h-full object-cover"
  >
  <div class="absolute inset-0 bg-gradient-to-r from-cyan-900/80 via-blue-800/60 to-transparent"></div>
</div>

<!-- Slide 4 -->
<div class="hero-slide absolute inset-0">
  <img 
    src="/images/hero/hero-4.jpg" 
    alt="Regatas y competición" 
    class="w-full h-full object-cover"
  >
  <div class="absolute inset-0 bg-gradient-to-r from-indigo-900/80 via-blue-800/60 to-transparent"></div>
</div>
```

## Características del Carrusel

✅ **Transiciones suaves** entre imágenes (1.5 segundos)
✅ **Cambio automático** cada 5 segundos
✅ **Navegación manual** con puntos indicadores
✅ **Se pausa** al pasar el mouse
✅ **Overlay oscuro** para mejorar legibilidad del texto
✅ **Responsive** - se adapta a todos los tamaños de pantalla

## Ajustes opcionales

### Cambiar velocidad de transición
En `src/pages/index.astro`, línea ~548:
```javascript
const slideInterval = 5000; // Cambia 5000 por los milisegundos que quieras
```

### Cambiar intensidad del overlay
En cada slide, ajusta el valor `/80` (0-100):
```html
<div class="absolute inset-0 bg-gradient-to-r from-blue-900/80 ..."></div>
                                                            ↑
                                                    Mayor = más oscuro
```

### Optimizar imágenes
Herramientas recomendadas:
- **TinyPNG**: https://tinypng.com/
- **Squoosh**: https://squoosh.app/
- **ImageOptim** (Mac): https://imageoptim.com/

## Actualmente usando

Por defecto, el sitio usa imágenes de demostración de Unsplash de alta calidad relacionadas con vela. Puedes mantenerlas o reemplazarlas con tus propias fotos de 541TOP Sailcoach.
