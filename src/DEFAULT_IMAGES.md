# Default Carousel Images

This document lists the 5 default abstract/artistic images used in the carousel. These images are sourced from Unsplash and are publicly accessible.

## Image URLs

### Image 1: Abstract Colorful Gradient
```
https://images.unsplash.com/photo-1639493115941-a70fcef4f715?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3Nzg4Nzd8MHwxfHNlYXJjaHwxfHxhYnN0cmFjdCUyMGNvbG9yZnVsJTIwZ3JhZGllbnR8ZW58MXx8fHwxNzczMzE3Mjg0fDA&ixlib=rb-4.1.0&q=80&w=1080
```

### Image 2: Artistic Paint Texture
```
https://images.unsplash.com/photo-1697224689275-d2c2827112d6?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3Nzg4Nzd8MHwxfHNlYXJjaHwxfHxhcnRpc3RpYyUyMHBhaW50JTIwdGV4dHVyZXxlbnwxfHx8fDE3NzMzMDMxMDB8MA&ixlib=rb-4.1.0&q=80&w=1080
```

### Image 3: Geometric Abstract Pattern
```
https://images.unsplash.com/photo-1595411425732-e69c1abe2763?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3Nzg4Nzd8MHwxfHNlYXJjaHwxfHxnZW9tZXRyaWMlMjBhYnN0cmFjdCUyMHBhdHRlcm58ZW58MXx8fHwxNzczNDEzMTkxfDA&ixlib=rb-4.1.0&q=80&w=1080
```

### Image 4: Fluid Art Colorful
```
https://images.unsplash.com/photo-1616651181620-9906d6e43fc3?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3Nzg4Nzd8MHwxfHNlYXJjaHwxfHxmbHVpZCUyMGFydCUyMGNvbG9yZnVsfGVufDF8fHx8MTc3MzQxMzE5Mnww&ixlib=rb-4.1.0&q=80&w=1080
```

### Image 5: Vibrant Abstract Shapes
```
https://images.unsplash.com/photo-1723283126735-f24688fcfcc2?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3Nzg4Nzd8MHwxfHNlYXJjaHwxfHx2aWJyYW50JTIwYWJzdHJhY3QlMjBzaGFwZXN8ZW58MXx8fHwxNzczNDEzMTkyfDA&ixlib=rb-4.1.0&q=80&w=1080
```

## Image Specifications

- **Source**: Unsplash
- **Format**: JPEG
- **Quality**: 80
- **Width**: 1080px
- **Color Space**: sRGB (tinysrgb)
- **Crop Method**: Entropy-based (focused on most interesting parts)

## Usage in Code

These URLs are defined in `/App.tsx` in the `defaultImages` array:

```typescript
const defaultImages = [
  'https://images.unsplash.com/photo-1639493115941-a70fcef4f715?...',
  'https://images.unsplash.com/photo-1697224689275-d2c2827112d6?...',
  'https://images.unsplash.com/photo-1595411425732-e69c1abe2763?...',
  'https://images.unsplash.com/photo-1616651181620-9906d6e43fc3?...',
  'https://images.unsplash.com/photo-1723283126735-f24688fcfcc2?...'
];
```

## Replacing Default Images

To use different default images:

1. Find your preferred images on [Unsplash](https://unsplash.com)
2. Get the image URLs (preferably optimized URLs like above)
3. Replace the URLs in the `defaultImages` array in `/App.tsx`

## License

All images are from Unsplash and are free to use under the [Unsplash License](https://unsplash.com/license).

## Attribution

While not required by the Unsplash License, attribution is appreciated:
- Photos from [Unsplash](https://unsplash.com)
