# Essential Files for Repository

This document lists all the important files you need to include in your repository for the Animated Image Carousel project.

## 📂 Required Files

### Core Application Files

1. **`/App.tsx`** - Main carousel component with all animation logic
2. **`/README.md`** - Project documentation
3. **`/package.json`** - Dependencies and scripts (see below)

### Components

4. **`/components/ui/button.tsx`** - Button component used for controls
5. **`/components/ui/utils.ts`** - Utility functions (cn helper)

### Styles

6. **`/styles/globals.css`** - Global styles and Tailwind configuration

### Configuration Files

7. **`/tsconfig.json`** - TypeScript configuration (see below)
8. **`/index.html`** - HTML entry point (see below)
9. **`/vite.config.ts`** - Vite configuration (see below)

### Assets (Optional)

10. **`/imports/`** - Default images (if you want to include them)
    - The carousel will work with any images you provide

---

## 📄 Configuration File Contents

### `package.json`

```json
{
  "name": "animated-image-carousel",
  "version": "1.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "tsc && vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^18.3.1",
    "react-dom": "^18.3.1",
    "motion": "^11.15.0",
    "lucide-react": "^0.468.0",
    "@radix-ui/react-slot": "^1.1.2",
    "class-variance-authority": "^0.7.1",
    "clsx": "^2.1.1",
    "tailwind-merge": "^2.7.0"
  },
  "devDependencies": {
    "@types/react": "^18.3.18",
    "@types/react-dom": "^18.3.5",
    "@vitejs/plugin-react": "^4.3.4",
    "typescript": "^5.7.3",
    "vite": "^6.0.11",
    "tailwindcss": "^4.0.0",
    "@tailwindcss/vite": "^4.0.0"
  }
}
```

### `tsconfig.json`

```json
{
  "compilerOptions": {
    "target": "ES2020",
    "useDefineForClassFields": true,
    "lib": ["ES2020", "DOM", "DOM.Iterable"],
    "module": "ESNext",
    "skipLibCheck": true,
    "moduleResolution": "bundler",
    "allowImportingTsExtensions": true,
    "isolatedModules": true,
    "moduleDetection": "force",
    "noEmit": true,
    "jsx": "react-jsx",
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noFallthroughCasesInSwitch": true,
    "noUncheckedSideEffectImports": true
  },
  "include": ["**/*.ts", "**/*.tsx"]
}
```

### `vite.config.ts`

```typescript
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';
import tailwindcss from '@tailwindcss/vite';

export default defineConfig({
  plugins: [react(), tailwindcss()],
  resolve: {
    alias: {
      '@': '/src'
    }
  }
});
```

### `index.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Animated Image Carousel</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/main.tsx"></script>
  </body>
</html>
```

### `main.tsx`

```typescript
import { StrictMode } from 'react';
import { createRoot } from 'react-dom/client';
import App from './App';
import './styles/globals.css';

createRoot(document.getElementById('root')!).render(
  <StrictMode>
    <App />
  </StrictMode>
);
```

---

## 🚀 Quick Start After Cloning

Once you have all files in your repository:

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build
```

---

## 📝 Optional Files

These files are recommended but not required:

- **`.gitignore`** - Ignore node_modules, dist, etc.
- **`LICENSE`** - Project license (e.g., MIT)
- **`.prettierrc`** - Code formatting configuration
- **`.eslintrc`** - Linting configuration

### Example `.gitignore`

```
# Dependencies
node_modules/

# Build output
dist/
build/

# Environment
.env
.env.local

# IDE
.vscode/
.idea/
*.swp
*.swo

# OS
.DS_Store
Thumbs.db

# Logs
npm-debug.log*
yarn-debug.log*
yarn-error.log*
```

---

## ✅ Minimum Required Structure

At minimum, your repository should have:

```
animated-image-carousel/
├── App.tsx
├── main.tsx
├── index.html
├── package.json
├── tsconfig.json
├── vite.config.ts
├── README.md
├── components/
│   └── ui/
│       ├── button.tsx
│       └── utils.ts
└── styles/
    └── globals.css
```

This is the minimal setup needed to run the carousel successfully!
