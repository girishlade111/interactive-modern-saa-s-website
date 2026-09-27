# Interactive Modern SaaS Website

A modern, interactive **SaaS marketing website** — "Creative Flow Studio" — with an animated hero, product pages, a full blog engine, auth page mockups, a showcase gallery, and interactive "create" studio tools (design system, interactive story, motion graphics, soundscape design). Built with Next.js 15, React Three Fiber, and shadcn-style UI.

> Built by Girish Lade — https://ladestack.in

## What it does

- **Landing page** (`/`) — animated hero, feature cards, CTA sections
- **Create studio** (`/create`) — interactive tools:
  - Design System builder
  - Interactive Story creator
  - Motion Graphics studio
  - Soundscape Design tool
- **Blog** (`/blog`) — static blog with slugs, related posts, tag/calendar metadata
- **Auth mockups** (`/auth/login`, `/auth/signup`) — front-end only, no backend
- **Showcase** (`/showcase`) — project gallery
- **Projects** (`/projects/new`) — new-project flow

Everything is front-end only: blog data lives in `lib/blog-data`, no API routes, no database, no login backend.

## Features

- 3D/interactive visuals with React Three Fiber + drei
- Gesture-driven interactions (`@use-gesture/react`)
- Blog engine with dynamic slugs + related-posts logic
- Dark-mode-ready theming (next-themes)
- Full Radix UI / shadcn component set
- Typography plugin for rich blog content
- Fully static-exportable

## Tech stack

- **Framework:** Next.js 15 (App Router) — static export (`output: 'export'`)
- **3D:** @react-three/fiber, @react-three/drei
- **UI:** React 19, Tailwind CSS 3.4, Radix UI, shadcn-style components
- **Icons:** lucide-react
- **Gestures:** @use-gesture/react
- **Forms:** react-hook-form + zod
- **Fonts:** Geist
- **Language:** TypeScript

## Quick start

### Prerequisites

- Node.js 18+ (20 recommended)
- npm, pnpm, or yarn

### Install & run

```bash
npm install        # or: pnpm install
npm run dev
```

Open http://localhost:3000

### Build (static)

```bash
npm run build
```

Static output goes to `out/`. Serve anywhere:

```bash
npx serve out
```

## Project structure

```
app/
├── page.tsx                     # landing page (hero, features, CTAs)
├── layout.tsx / globals.css
├── auth/login|signup/           # auth page mockups (UI only)
├── blog/                        # blog index + [slug] pages (static params)
├── create/                      # studio tools: design-system, interactive-story,
│                                #   motion-graphics, soundscape-design
├── projects/new/                # new project flow
└── showcase/                    # gallery
components/
├── ui/                          # shadcn-style primitives
└── blog/                        # related-posts etc.
lib/
├── blog-data.ts                 # blog posts data
├── blog-utils.ts                # related posts, helpers
└── utils.ts
public/                          # static assets
```

## Customizing content

- **Blog posts:** edit `lib/blog-data.ts`
- **Copy/sections:** edit the page components under `app/`
- **Theme:** `app/globals.css` + `tailwind.config.ts`

## Environment variables

None required. Fully static — no secrets, no backend services.

## Deployment

Any static host: GitHub Pages, Cloudflare Pages, Netlify, Vercel.

This repo ships as a static export on GitHub Pages — see the repo's Website field.

> Note: `next.config.mjs` uses `basePath: '/interactive-modern-saa-s-website'` for the GitHub Pages subpath deploy. Remove it for root-domain or Vercel deploys.

## Notes

- Generated originally with v0.app and refined for static hosting.
- Next.js 15.2.8 (patched against CVE-2025-55182 / React2Shell).
- The `latest` dependency pins in `package.json` come from the v0 template; pin versions for production use.

---

Built with ❤ by [Girish Lade](https://github.com/girishlade111) — [ladestack.in](https://ladestack.in)
