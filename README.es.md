<!-- l10n-sync: source-file="README.md" -->
🌐 [English](README.md) | Español | [Português (Brasil)](README.pt_BR.md) | [한국어](README.ko.md)

# 🎮 Mona Mayhem

**Taller de VS Code y GitHub Copilot CLI** — Construye una Arena de Batalla de Contribuciones GitHub

Un modelo de taller para crear un sitio web con temática de arcade retro en Astro que compara los gráficos de contribución de GitHub de dos usuarios. Este es el **punto de partida** — crearás la aplicación paso a paso usando GitHub Copilot.

![Mona Mayhem Screenshot](https://github.com/user-attachments/assets/5eca79e2-cb9f-4e93-aa0d-23666ebde3b7)
*Lo que construirás al final del taller*

## 📚 Taller

El taller admite dos rutas; sigue la que mejor se adapte a tu flujo de trabajo:

- **Ruta de VS Code** — Chat, Plan Mode, Agent Mode, agentes en segundo plano y bucles de revisión nativos del editor
- **Ruta de CLI** — `copilot`, contexto con `@file`, `/plan`, ediciones autónomas, `/fleet`, `/delegate` y `/review`

| Parte | Título | Enfoque de Copilot |
|------|--------|--------------------|
| [00](workshop/es/00-overview.md) | Visión General | Selección de la ruta y objetivos de aprendizaje |
| [01](workshop/es/01-setup.md) | Configuración y Context Engineering | Instrucciones, permisos y preparación del entorno |
| [02](workshop/es/02-plan-and-scaffold.md) | Planificar y estructurar | Planificación de la API y la arquitectura de la página |
| [03](workshop/es/03-agent-mode.md) | Construir el juego | Implementación y evolución con agentes |
| [04](workshop/es/04-design-vibes.md) | Tematización design-first | Planificación e implementación visual |
| [05](workshop/es/05-polish.md) | Pulido y trabajo en paralelo | Paralelismo, revisiones y pases de calidad |
| [06](workshop/es/06-bonus.md) | Bonus y extensiones | Ideas extra y experimentos adicionales con Copilot |

## 🚀 Inicio rápido

1. **Crea tu propio repositorio primero** mediante cualquiera de estas opciones:
   - haciendo clic en **Use this template** para crear un nuevo repositorio, o
   - haciendo fork de este repositorio.
2. Elige tu ruta del taller:
   - **VS Code:** clona tu repositorio y ábrelo en VS Code.
   - **GitHub Copilot CLI:** clónalo localmente, instala `copilot` y trabaja desde tu terminal.
3. Sigue la [guía del taller](workshop/es/00-overview.md)

## Requisitos previos

### Compartidos

- GitHub Copilot (Pro, Business o Enterprise)
- Git
- Node.js

### Ruta de VS Code

- VS Code v1.107+
- Extensión de GitHub Copilot iniciada sesión

### Ruta de CLI

- GitHub Copilot CLI (`copilot`)
- Node.js 22+ si planeas instalar la CLI con `npm install -g @github/copilot`
- O Homebrew / WinGet si prefieres un gestor de paquetes nativo

## Stack tecnológico

- **Framework**: [Astro](https://astro.build/) v6
- **Runtime**: Node.js con el adaptador [@astrojs/node](https://docs.astro.build/en/guides/integrations-guide/node/)
- **Fuente**: Press Start 2P (fuente retro arcade)
- **API**: API de gráficos de contribuciones de GitHub

## Notas de despliegue

### Configuración actual de GitHub Pages

El flujo de trabajo en `.github/workflows/deploy.yml` despliega actualmente contenido estático del taller en `docs/` y `workshop/` a GitHub Pages. No compila ni despliega la aplicación Astro desde `src/`.

### Si quieres desplegar la app Astro en GitHub Pages

GitHub Pages es un alojamiento estático, así que la app de Astro debe usar salida estática.

1. Cambia `output` en `astro.config.mjs` de `server` a `static`.
2. Elimina el adaptador Node (`@astrojs/node`) de `astro.config.mjs` y `package.json`.
3. Actualiza el flujo de trabajo de GitHub Actions para ejecutar `npm ci` y `npm run build`, y luego subir `dist/` como artefacto de Pages.
4. Si despliegas en una página de proyecto (`https://<user>.github.io/<repo>/`), configura `site` y `base` en `astro.config.mjs`.

Si planeas mantener rutas de API ejecutándose en producción, usa una plataforma con servidor en lugar de GitHub Pages (por ejemplo, Vercel, Netlify o un host Node).

## Licencia

MIT
