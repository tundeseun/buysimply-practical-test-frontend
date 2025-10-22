# Team Achieve — Login (Vue 3 + Vite)

A responsive login page that matches the attached design. Built with Vue 3 and vanilla CSS (no UI frameworks).

## Quick start

```bash
# 1) Install dependencies
npm install

# 2) Start a dev server
npm run dev

# 3) Build for production (optional)
npm run build
npm run preview
```

The app opens on http://localhost:5173 (or the next available port).

## Project structure

```
team-achieve-login/
├─ index.html
├─ package.json
├─ vite.config.js
├─ src/
│  ├─ main.js
│  ├─ styles.css
│  ├─ App.vue
│  ├─ assets/
│  │  ├─ logo.svg
│  │  └─ hero.svg
│  └─ components/
│     └─ Login.vue
```

## Notes

- The **left panel** (logo, image, caption) hides on mobile screens to match the provided mobile mock.
- The **password field** includes a show/hide toggle.
- Form validation is minimal and runs before the simulated submit.
- Replace `src/assets/hero.svg` with your preferred photo if desired; dimensions are flexible.
