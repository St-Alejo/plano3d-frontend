# Plano 3D · frontend

La app web de Plano 3D: toma la foto de un plano, corrígelo en el editor 2D y recorre tu casa en 3D
(orbitar, caminar, modos de obra, simulación, exportar a GLB/OBJ/Blender y fotos realistas con IA).
React 19 + Vite + Tailwind v4 + three.js (react-three-fiber).

## Correr en local

```bash
npm ci
npm run dev              # → http://localhost:5173 (hace proxy de /api a http://localhost:8000)
```

Necesita el [backend](https://github.com/St-Alejo/plano3d-backend) corriendo en el puerto 8000.

Para apuntar a una API en otro dominio: `VITE_API_URL=https://mi-api.example.com npm run build`.

## Pruebas

```bash
npm run lint && npm run typecheck && npm test
npx playwright test      # e2e, con el backend arriba
```

## Despliegue

Cada push a `main` publica en **Azure Static Web Apps** (plan Free). La URL de la API sale de la variable del
repositorio `VITE_API_URL`; el token, del secreto `AZURE_STATIC_WEB_APPS_API_TOKEN`.

El historial completo del proyecto (antes de separarlo) está en [plano3d](https://github.com/St-Alejo/plano3d).
