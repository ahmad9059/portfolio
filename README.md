<div align="center">

  <img src="public/static/logos/logo_full.svg" alt="Logo" height="72" />

  <h1>Ahmad — Developer Portfolio</h1>
  <p>Next.js + TypeScript + Tailwind CSS</p>

  <p>
    <a href="#getting-started"><b>Getting Started</b></a>
    ·
    <a href="#features"><b>Features</b></a>
    ·
    <a href="#project-structure"><b>Structure</b></a>
    ·
    <a href="#scripts"><b>Scripts</b></a>
    ·
    <a href="#deploy"><b>Deploy</b></a>
  </p>

</div>

---

### Preview

This repository contains my personal portfolio site built with Next.js 12, TypeScript, and Tailwind CSS (JIT). It showcases projects, designs, skills, testimonials, and includes small interactive touches and SVG illustrations.

### Tech Stack

- **Framework**: Next.js 12 (pages router), SWC minification
- **Language**: TypeScript (TS 4.x)
- **UI**: Tailwind CSS 3 (JIT) + `@tailwindcss/forms`
- **Content**: MD/MDX tooling via `next-mdx-remote`, `contentlayer` (scaffolded), `gray-matter`
- **Utilities**: `swr`, `react-scroll`, `reading-time`
- **Syntax Highlighting**: `rehype-highlight` / Prism via `rehype-prism-plus`

### Features

- **Responsive, fast, and accessible** UI with Tailwind
- **Projects and Designs** sections with reusable components
- **SVG illustrations** and subtle animations
- **Type-safe** components and utilities
- **SEO-friendly** with custom `_document` and meta assets
- **Simple content model** powered by data files under `data/`

### Project Structure

```text
public/             # static assets (favicons, hero images, svg doodles, project previews)
pages/              # Next.js pages (pages router)
  _app.tsx
  _document.tsx
  index.tsx         # Home
  designs.tsx       # Designs index
  projects.tsx      # Projects index
  projects/tag/[tag].tsx
components/         # UI components grouped by domain
  global/           # Layout, navbar, footer, section titles
  home/             # Hero, CTA, Skills, Projects, Testimonials
  projects/         # ProjectCard and related UI
  designs/          # Designs listing UI
  utility/          # Page wrapper
data/               # Content sources (TS data objects)
styles/             # Global CSS (Tailwind entry)
utils/              # Helpers
types/              # Shared types
tailwind.config.js  # Tailwind setup (JIT, theme, plugins)
postcss.config.js   # PostCSS + autoprefixer
next.config.js      # Next config (redirects, swcMinify)
tsconfig.json       # TS paths and compiler options
```

### Getting Started

Prerequisites:

- Node.js 16+
- `yarn` (recommended) or `npm`/`pnpm`

Install dependencies:

```bash
yarn install
# or
npm install
```

Run the development server:

```bash
yarn dev
# or
npm run dev
```

Open `http://localhost:3000` to view the site.

### Scripts

```json
{
  "dev": "next dev",
  "build": "next build",
  "start": "next start",
  "serve": "next serve"
}
```

- **dev**: Start the local development server on port 3000
- **build**: Create a production build
- **start**: Run the production server (after build)
- **serve**: Static export/serve utility when needed

### Styling

- Tailwind is configured in `tailwind.config.js` with JIT mode and a customized theme.
- Global styles live in `styles/main.css`.
- Component-driven styling with utility classes and a few custom animations.

### Content

- Content is sourced from TypeScript files under `data/`:
  - `data/global.ts`
  - `data/content/home.ts`, `data/content/projects.ts`, `data/content/designs.ts`
- Images and icons live under `public/static/` and are referenced by components.

### Development Notes

- TypeScript is configured with base url and path aliases like `@/components/*`, `@/data/*`, and `@/utils/*`.
- `next.config.js` includes a redirect from `/blog` to `/`.
- SWC minification is enabled for faster builds.

### Deploy

You can deploy this project on platforms like Vercel or Netlify.

Vercel (recommended):

1. Push your repository to GitHub/GitLab/Bitbucket
2. Import the repo in Vercel
3. Framework Preset: Next.js
4. Build Command: `yarn build` (or `npm run build`)
5. Output: `.next`

Node server (self-host):

```bash
yarn build
yarn start
```

### Customization

- Update navigation, footer, and layout in `components/global/`
- Edit sections in `components/home/` and `components/projects/`
- Modify theme colors and fonts in `tailwind.config.js`
- Replace images in `public/static/`

### Acknowledgements

- Tailwind CSS team and plugin authors
- Next.js team
- Rehype/Remark ecosystem

### License

This project is private for personal portfolio use unless a license is added.
