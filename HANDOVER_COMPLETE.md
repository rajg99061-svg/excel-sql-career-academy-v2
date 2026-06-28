# Excel SQL Career Academy — Complete Project Handover Document
### AI-to-AI Transfer: Claude → Google Gemini
### Document Version: 1.0 | Date: June 2025

---

> **IMPORTANT FOR GEMINI:** This is a complete, lossless handover document. Every design decision, file, component, data structure, and future plan is documented below. Do not ask the user to re-explain anything covered here. Your job is to continue development exactly where it left off, matching the existing code style, design language, and architectural decisions.

---

## TABLE OF CONTENTS

1. [Project Vision & Identity](#1-project-vision--identity)
2. [Original Project Idea & Goals](#2-original-project-idea--goals)
3. [Development History & Session Log](#3-development-history--session-log)
4. [Complete Project Tree](#4-complete-project-tree)
5. [All Dependencies & Packages](#5-all-dependencies--packages)
6. [Build, Run & Deployment Instructions](#6-build-run--deployment-instructions)
7. [Architecture Overview](#7-architecture-overview)
8. [Routing Architecture](#8-routing-architecture)
9. [State Management Approach](#9-state-management-approach)
10. [Design System](#10-design-system)
11. [Styling Architecture & Tailwind Setup](#11-styling-architecture--tailwind-setup)
12. [Glassmorphism Implementation](#12-glassmorphism-implementation)
13. [Animation Strategy](#13-animation-strategy)
14. [Responsive Design Strategy](#14-responsive-design-strategy)
15. [Every File — Purpose & Full Code](#15-every-file--purpose--full-code)
16. [Every React Component — Purpose & Props](#16-every-react-component--purpose--props)
17. [Data Architecture](#17-data-architecture)
18. [Features Completed](#18-features-completed)
19. [Features Partially Completed](#19-features-partially-completed)
20. [Features Pending / Planned](#20-features-pending--planned)
21. [Complete Development Roadmap](#21-complete-development-roadmap)
22. [Excel Learning Module — Full Specification](#22-excel-learning-module--full-specification)
23. [SQL Learning Module — Full Specification](#23-sql-learning-module--full-specification)
24. [Quiz System — Full Specification](#24-quiz-system--full-specification)
25. [Progress Tracker — Full Specification](#25-progress-tracker--full-specification)
26. [Search System — Full Specification](#26-search-system--full-specification)
27. [Interview Preparation Module](#27-interview-preparation-module)
28. [Planned Features — Detailed Specs](#28-planned-features--detailed-specs)
29. [Known Issues & Bugs](#29-known-issues--bugs)
30. [Implementation Decisions Log](#30-implementation-decisions-log)
31. [Environment Variables](#31-environment-variables)
32. [GitHub & Vercel Setup](#32-github--vercel-setup)
33. [Exact Next Development Steps](#33-exact-next-development-steps)
34. [Critical Notes for Gemini](#34-critical-notes-for-gemini)

---

## 1. PROJECT VISION & IDENTITY

### Name
**Excel SQL Career Academy**

### Tagline
*"Master Excel & SQL — from zero to hired."*

### Brand Identity
- **Logo:** Square with gradient fill (#22d3ee → #a78bfa), white "XS" text in font-black
- **Logo subtext:** "Excel SQL / CAREER ACADEMY" (two lines)
- **Domain intent:** A premium dark-mode learning platform targeting people who want to break into data analyst or data-related careers by mastering Microsoft Excel and SQL

### Target Audience
1. Complete beginners with no Excel/SQL knowledge
2. Intermediate users who know basics but want to deepen skills
3. Professionals preparing for data analyst job interviews
4. Career-changers transitioning into data roles
5. Students looking for structured, project-ready curriculum

### Core Value Proposition
- Structured, phase-based learning paths (not random YouTube-style lessons)
- Real interview questions with model answers
- Adaptive per-lesson quizzes (not just one global quiz)
- Progress tracking that persists
- Premium UI that makes studying feel motivating, not boring
- Free to use on the web — no paywall for core content

---

## 2. ORIGINAL PROJECT IDEA & GOALS

### Session 1 — Initial Creation
The user asked for a **premium modern learning website** called "Excel SQL Career Academy" with:
- Dark theme
- Glassmorphism UI
- Modern hero section
- Excel Learning Roadmap
- SQL Learning Roadmap
- Interactive Quiz Section
- Progress Tracker
- Interview Questions Section
- Mobile Responsive Design
- React + TypeScript + Tailwind CSS

This was first delivered as a **single JSX file artifact** rendered in the Claude UI (not a project). The user downloaded the `.jsx` file.

### Session 2 — Full Vite Project
The user asked to generate a **complete Vite + React + TypeScript + Tailwind CSS project** with:
- `package.json`
- `vite.config.ts`
- `tsconfig.json`
- `tailwind.config.js`
- `postcss.config.js`
- `src/App.tsx`
- `src/main.tsx`
- All required files
- **A ZIP download ready for GitHub and Vercel deployment**

The first JSX artifact was split into proper TypeScript files with full project architecture.

### Session 3 — Feature Expansion
The user said: *"Continue working on the existing project. Do NOT create a new project. Do NOT change the current UI or design."* and asked to add:
1. Complete Excel Learning section with structured lessons, explanations, examples, practice exercises and quizzes
2. Complete SQL Learning section with structured lessons, explanations, examples, practice exercises and quizzes
3. Search for all lessons
4. Progress Tracker
5. Navigation for all learning modules
6. Keep the current website design exactly as it is

This session created the comprehensive `lessons.ts` data file (1,368 lines) with full lesson content, but the **UI components for the lesson viewer, search, and module navigation were NOT yet built** — the data exists but has no frontend attached yet.

### Session 4 — This Handover
The user asked for this complete handover document to migrate from Claude to Google Gemini.

---

## 3. DEVELOPMENT HISTORY & SESSION LOG

| Session | What Was Built | Status |
|---------|---------------|--------|
| 1 | Single-file JSX artifact with all 5 sections | ✅ Complete |
| 2 | Full Vite project, ZIP download, proper TS architecture | ✅ Complete |
| 3 | lessons.ts data file (1,368 lines), types extended, searchLessons() function | ✅ Data done, ⚠️ UI not wired |
| 4 | This handover document | ✅ |

**Critical gap:** The `src/components/sections/learning/` directory was created but is currently **empty**. The lesson viewer UI components do not exist yet. The `lessons.ts` data is ready and correct but has no frontend components consuming it.

---

## 4. COMPLETE PROJECT TREE

```
excel-sql-academy/
├── .eslintrc.cjs                          # ESLint config (TS + React Hooks rules)
├── .gitignore                             # Git ignore (node_modules, dist, .env)
├── README.md                              # Setup & deployment guide
├── HANDOVER.md                            # THIS FILE
├── index.html                             # Entry HTML, Google Fonts, OG meta tags
├── package.json                           # All npm dependencies & scripts
├── postcss.config.js                      # PostCSS: tailwindcss + autoprefixer
├── tailwind.config.js                     # Tailwind theme extension & content paths
├── tsconfig.json                          # TypeScript compiler options (strict)
├── tsconfig.node.json                     # TS config for Vite build tool only
├── vercel.json                            # Vercel SPA rewrite rules + cache headers
├── vite.config.ts                         # Vite config: React plugin, chunk splitting
│
├── public/
│   └── favicon.svg                        # Gradient XS logo SVG icon
│
└── src/
    ├── App.tsx                            # Root: navigation state, section renderer
    ├── main.tsx                           # ReactDOM.createRoot entry point
    ├── index.css                          # Tailwind directives + global styles
    │
    ├── types/
    │   └── index.ts                       # All shared TypeScript interfaces & types
    │
    ├── data/
    │   ├── roadmaps.ts                    # EXCEL_ROADMAP & SQL_ROADMAP phase arrays
    │   ├── quiz.ts                        # 8 global quiz questions (QuizQuestion[])
    │   ├── interview.ts                   # 8 interview Q&As (InterviewQuestion[])
    │   └── lessons.ts                     # 1,368 lines: all lesson data + searchLessons()
    │
    └── components/
        ├── NavBar.tsx                     # Fixed top nav, mobile hamburger, scroll blur
        ├── Footer.tsx                     # Simple footer with logo + copyright
        │
        ├── ui/
        │   ├── GlassCard.tsx              # Reusable glassmorphism card wrapper
        │   └── Badge.tsx                  # Excel/SQL category pill badge
        │
        └── sections/
            ├── HeroSection.tsx            # Homepage: hero, animated counters, CTAs
            ├── RoadmapSection.tsx         # Tabbed Excel/SQL phase roadmap
            ├── QuizSection.tsx            # 8-question global quiz with scoring
            ├── ProgressSection.tsx        # Clickable topic checklist + SVG rings
            ├── InterviewSection.tsx       # Accordion interview Q&A with filter
            └── learning/                  # ⚠️ DIRECTORY EXISTS BUT IS EMPTY
                                           # LearningSection.tsx — TO BE BUILT
                                           # LessonViewer.tsx — TO BE BUILT
                                           # SearchSection.tsx — TO BE BUILT
                                           # ModuleNav.tsx — TO BE BUILT
```

---

## 5. ALL DEPENDENCIES & PACKAGES

### Runtime Dependencies (`dependencies`)
```json
{
  "react": "^18.2.0",
  "react-dom": "^18.2.0"
}
```

### Dev Dependencies (`devDependencies`)
```json
{
  "@types/react": "^18.2.66",
  "@types/react-dom": "^18.2.22",
  "@typescript-eslint/eslint-plugin": "^7.2.0",
  "@typescript-eslint/parser": "^7.2.0",
  "@vitejs/plugin-react": "^4.2.1",
  "autoprefixer": "^10.4.19",
  "eslint": "^8.57.0",
  "eslint-plugin-react-hooks": "^4.6.0",
  "eslint-plugin-react-refresh": "^0.4.6",
  "postcss": "^8.4.38",
  "tailwindcss": "^3.4.3",
  "typescript": "^5.2.2",
  "vite": "^5.2.0"
}
```

### Packages NOT Yet Installed (Needed for Future Features)
```
react-router-dom         → if migrating from state-based routing to URL routing
framer-motion            → if adding more sophisticated animations
zustand                  → if upgrading from prop-drilling to global state
@supabase/supabase-js    → if adding auth + persistent user data
react-syntax-highlighter → for code block rendering in lessons (highly recommended)
prism-react-renderer     → alternative syntax highlighter
date-fns                 → for certificate timestamp formatting
jspdf or react-pdf       → for certificate PDF generation
```

**Note:** Currently zero external UI libraries are used. All UI is hand-coded with Tailwind CSS utility classes and inline styles. Keep this approach unless adding a specific package for a concrete reason.

---

## 6. BUILD, RUN & DEPLOYMENT INSTRUCTIONS

### Prerequisites
- Node.js 18 or higher (LTS recommended)
- npm 9+ (comes with Node.js)
- Git

### Local Development
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/excel-sql-academy.git
cd excel-sql-academy

# Install dependencies
npm install

# Start dev server (http://localhost:5173)
npm run dev

# Type check
npx tsc --noEmit

# Lint
npm run lint

# Build for production
npm run build

# Preview production build locally
npm run preview
```

### Production Build Output
- Output folder: `dist/`
- Assets are hashed for cache busting
- Vendor chunk (react + react-dom) is split separately
- No source maps in production (sourcemap: false)

### Vercel Deployment

**Option A: Vercel CLI**
```bash
npm i -g vercel
vercel login
vercel                    # follow prompts
vercel --prod             # deploy to production
```

**Option B: GitHub Integration (Recommended)**
1. Push code to GitHub
2. Go to https://vercel.com/new
3. Import the repository
4. Framework preset: **Vite**
5. Build command: `npm run build`
6. Output directory: `dist`
7. Install command: `npm install`
8. Click Deploy

**The `vercel.json` file handles:**
- SPA routing: all routes rewrite to `/index.html` (prevents 404 on refresh)
- Asset caching: `/assets/**` gets `Cache-Control: public, max-age=31536000, immutable`

### GitHub Setup
```bash
git init
git add .
git commit -m "Initial commit: Excel SQL Career Academy"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/excel-sql-academy.git
git push -u origin main
```

---

## 7. ARCHITECTURE OVERVIEW

### Framework & Stack
| Layer | Technology | Reason |
|-------|-----------|--------|
| UI Library | React 18 | Chosen by user; component model fits the section-based SPA |
| Language | TypeScript (strict) | Type safety across all data models and props |
| Styling | Tailwind CSS 3.4 | Utility-first, dark mode friendly, no runtime overhead |
| Build Tool | Vite 5 | Fast HMR, ESM-native, excellent React/TS support |
| CSS Processing | PostCSS + Autoprefixer | Required by Tailwind; adds vendor prefixes automatically |
| Deployment | Vercel | Zero-config for Vite SPAs |

### Application Type
Single Page Application (SPA). No server-side rendering. No API routes. All data is static TypeScript arrays. No database connection currently.

### Component Pattern
- Functional components only (no class components)
- React hooks only (useState, useEffect)
- No Context API yet (state lives in App.tsx and is passed as props)
- No external state library (Zustand/Redux not yet needed)

---

## 8. ROUTING ARCHITECTURE

### Current Implementation: State-Based Routing
There is **no react-router-dom** in this project. Navigation is implemented via a single `active` state variable in `App.tsx`.

```typescript
// In App.tsx
const [active, setActive] = useState<NavSection>('Home');

// NavSection type in types/index.ts:
export type NavSection = 'Home' | 'Roadmap' | 'Quiz' | 'Progress' | 'Interview';
```

`setActive` is passed as a prop to `NavBar` and `HeroSection`. When the user clicks a nav link or CTA button, `setActive` is called with the section name, and `App.tsx` renders the appropriate section component.

```typescript
// In App.tsx renderSection()
switch (active) {
  case 'Home':      return <HeroSection setActive={setActive} />;
  case 'Roadmap':   return <RoadmapSection />;
  case 'Quiz':      return <QuizSection />;
  case 'Progress':  return <ProgressSection />;
  case 'Interview': return <InterviewSection />;
}
```

### Why No react-router-dom?
This was an intentional early decision — the project started as a single-file artifact and the state-based approach was preserved to keep things simple. The user has not asked for URL-based routing.

### Future Routing Decision (For Gemini to Decide)
When the Learning section (Excel Lessons, SQL Lessons) is added, you will need nested navigation: Module → Lesson. This can be done two ways:

**Option A (Extend current pattern):** Add more NavSection values and sub-state:
```typescript
type NavSection = 'Home' | 'Roadmap' | 'Quiz' | 'Progress' | 'Interview' | 'Learn';
// Plus sub-state in LearningSection: activeModule, activeLesson
```

**Option B (Add react-router-dom):** Full URL routing. URLs like `/learn/excel/excel-formulas`. Better for SEO, bookmarking, and sharing lesson links. Recommended for v2.

**Recommendation: Use Option A for now** (to keep the session 3 request of "keep current navigation"), then migrate to react-router in a planned v2 upgrade.

---

## 9. STATE MANAGEMENT APPROACH

### Current State Location

| State | Location | Type | Description |
|-------|----------|------|-------------|
| `active` (nav section) | `App.tsx` | `NavSection` | Which section is rendered |
| `counter` (hero stats) | `HeroSection.tsx` | `{students, lessons, companies}` | Animated number counters |
| `tab` (Excel/SQL) | `RoadmapSection.tsx` | `'excel' \| 'sql'` | Active roadmap tab |
| `qi, selected, score, done, answers` | `QuizSection.tsx` | Multiple | Quiz flow state |
| `topics, filter` | `ProgressSection.tsx` | `TrackedTopic[], string` | Topic completion state |
| `open, filter` | `InterviewSection.tsx` | `number \| null, string` | Accordion + filter |

### Known State Issues
1. **Progress state is NOT persisted.** Refreshing the page resets all checked topics to their initial `done` values from `roadmaps.ts`. This is a known issue (see section 29).
2. **Quiz state resets on nav.** Navigating away from the Quiz section and back resets the quiz to question 1.
3. **No global state.** Every section manages its own state independently. No cross-section state sharing currently.

### Future State Management
When adding user auth and persistent progress, upgrade to one of:
- **Zustand** (recommended: minimal boilerplate, TypeScript-first)
- **React Context + useReducer** (built-in, good for medium complexity)
- **Supabase** for server-side state persistence after auth

---

## 10. DESIGN SYSTEM

### Color Palette

| Token | Hex | Usage |
|-------|-----|-------|
| Brand Cyan | `#22d3ee` | Primary accent, Excel track color, CTAs |
| Brand Purple | `#a78bfa` | Secondary accent, gradient end point |
| Brand Pink | `#f472b6` | Excel Advanced phase, tertiary accent |
| Brand Emerald | `#34d399` | SQL Core phase, SQL track color |
| Brand Orange | `#fb923c` | SQL Intermediate phase |
| Brand Rose | `#f43f5e` | SQL Expert phase, error states |
| Background Dark 1 | `#0f1729` | Top-left of radial gradient |
| Background Dark 2 | `#080b14` | Mid background |
| Background Dark 3 | `#050710` | Darkest background corner |
| White | `rgba(255,255,255,X)` | Text at various opacities |

### Background
The body background is a fixed radial gradient (set in `index.css`):
```css
background: radial-gradient(ellipse at 20% 0%, #0f1729 0%, #080b14 40%, #050710 100%);
```
This should NEVER be changed — it defines the "cosmic dark" aesthetic of the entire site.

### Opacity Scale for White Text
| Usage | Class | Value |
|-------|-------|-------|
| Primary text (headings) | `text-white` | 100% |
| Body/secondary text | `text-white/70` | 70% |
| Muted text | `text-white/50` | 50% |
| Placeholder / labels | `text-white/40` | 40% |
| Very dim / disabled | `text-white/30` | 30% |
| Ultra dim | `text-white/25` | 25% |

### Primary Gradient (CTAs & Logo)
```css
background: linear-gradient(135deg, #22d3ee, #a78bfa);
box-shadow: 0 4px 32px rgba(34, 211, 238, 0.35);
```
This exact gradient is used for: primary CTA buttons, the logo square, the gradient text in the headline.

### Gradient Text
```tsx
style={{
  background: 'linear-gradient(90deg, #22d3ee, #a78bfa)',
  WebkitBackgroundClip: 'text',
  WebkitTextFillColor: 'transparent',
  backgroundClip: 'text',
}}
```

### Typography

| Element | Tailwind Class | Notes |
|---------|--------------|-------|
| Font family | `font-sans` → Inter | Loaded from Google Fonts |
| Hero H1 | `text-5xl sm:text-6xl md:text-7xl font-black leading-[0.95] tracking-tight` | "font-black" = weight 900 |
| Hero subheading | `text-4xl sm:text-5xl md:text-6xl font-light` | Muted white/60 |
| Section H2 | `text-4xl sm:text-5xl font-black` | All section titles |
| Section eyebrow | `text-sm uppercase tracking-widest font-semibold text-white/40` | Above H2 |
| Card titles | `text-lg font-bold` or `text-sm font-semibold` | |
| Body text | `text-white/50 text-lg leading-relaxed` | Section descriptions |
| Small body | `text-white/40 text-xs` | Card descriptions |
| Code/mono | No custom monospace yet — needs `font-mono` added | TODO |

### Font Loading (in `index.html`)
```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet" />
```
All 7 weights are loaded: 300 (light), 400 (regular), 500 (medium), 600 (semibold), 700 (bold), 800 (extrabold), 900 (black).

### Border Radius
All cards, buttons, and containers use large border radius for the modern feel:
- Cards: `rounded-2xl` (16px)
- Buttons: `rounded-2xl` or `rounded-xl`
- Inner elements: `rounded-xl` (12px) or `rounded-lg` (8px)
- Pills/badges: `rounded-full`

### Spacing
- Section padding: `px-4 py-20` on desktop
- Max width content: `max-w-7xl mx-auto` or `max-w-4xl`/`max-w-3xl` for narrower sections
- Card padding: `p-6 sm:p-8` or `p-8 sm:p-12` for hero-style cards

---

## 11. STYLING ARCHITECTURE & TAILWIND SETUP

### PostCSS Config (`postcss.config.js`)
```js
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
```

### Tailwind Config (`tailwind.config.js`)
```js
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {
      fontFamily: { sans: ['Inter', 'system-ui', 'sans-serif'] },
      colors: {
        brand: {
          cyan: '#22d3ee',
          purple: '#a78bfa',
          pink: '#f472b6',
          emerald: '#34d399',
          orange: '#fb923c',
          rose: '#f43f5e',
        },
      },
      animation: { 'pulse-slow': 'pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite' },
      backdropBlur: { xs: '2px' },
    },
  },
  plugins: [],
}
```

### Custom CSS Classes (in `index.css` `@layer utilities`)
```css
.glass          → glassmorphism card style (see section 12)
.gradient-text  → #22d3ee → #a78bfa text gradient
.gradient-btn   → #22d3ee → #a78bfa button gradient with glow
```

### Styling Philosophy
1. **Tailwind-first:** All layout, spacing, and color via Tailwind utility classes
2. **Inline styles for dynamic values:** Hex colors with opacity (e.g., `${phase.color}15`), conic-gradient for score ring, computed values not expressible in Tailwind
3. **No CSS Modules:** Not used
4. **No styled-components / emotion:** Not used
5. **No Tailwind plugins used** (except core Tailwind)
6. **No `@apply` overuse:** Only 3 custom utility classes in the entire project

---

## 12. GLASSMORPHISM IMPLEMENTATION

The glassmorphism effect is the defining visual of this project. It must be applied consistently.

### GlassCard Component (Canonical Implementation)
```tsx
// src/components/ui/GlassCard.tsx
<div
  className={`rounded-2xl border border-white/10 ${className}`}
  style={{
    background: 'rgba(255,255,255,0.04)',        // 4% white = very subtle frosted glass
    backdropFilter: 'blur(16px)',                 // The blur effect
    WebkitBackdropFilter: 'blur(16px)',           // Safari prefix (essential)
    boxShadow: '0 4px 32px rgba(0,0,0,0.3), inset 0 1px 0 rgba(255,255,255,0.08)',
    //          ↑ drop shadow              ↑ top edge light (simulates glass edge)
  }}
>
```

### Glass Effect Formula
```
background: rgba(255,255,255,0.04)   ← NEVER go above 0.08 or it looks washed out
backdrop-filter: blur(16px)          ← 16px is the sweet spot; 20px+ is too heavy
border: 1px solid rgba(255,255,255,0.10) ← subtle white border
box-shadow: 0 4px 32px rgba(0,0,0,0.30) ← outer drop shadow
box-shadow: inset 0 1px 0 rgba(255,255,255,0.08) ← inner top rim highlight
```

### Critical Notes
- **Always include `-webkit-backdrop-filter`** alongside `backdrop-filter` — Safari requires it
- The background MUST be transparent/translucent for the blur to show through
- Glass cards look best against the dark gradient background. Don't use them on white backgrounds.
- The `border-white/10` class = `1px solid rgba(255,255,255,0.1)` — keep this consistent

### Ambient Background Orbs (Hero Section)
Large blurred circles create depth behind glass cards:
```tsx
// Cyan orb (top-left)
background: 'radial-gradient(circle, #22d3ee 0%, transparent 70%)'
width: 600px, height: 600px, opacity: 0.20, filter: blur(80px)

// Purple orb (bottom-right)
background: 'radial-gradient(circle, #a78bfa 0%, transparent 70%)'
width: 500px, height: 500px, opacity: 0.15, filter: blur(80px)

// Pink orb (center)
background: 'radial-gradient(circle, #f472b6 0%, transparent 70%)'
width: 300px, height: 300px, opacity: 0.10, filter: blur(60px)
```

### Dot/Grid Overlay (Hero Section)
```tsx
background-image: linear-gradient(rgba(255,255,255,0.5) 1px, transparent 1px),
                  linear-gradient(90deg, rgba(255,255,255,0.5) 1px, transparent 1px)
background-size: 60px 60px
opacity: 0.03
```

---

## 13. ANIMATION STRATEGY

### Principles
1. Subtle — animations enhance, not distract
2. Performance-first — CSS transitions only (no JS animation loops except the counter)
3. Duration 200ms for interactive states, 300-700ms for progress/data animations

### Implemented Animations

| Animation | Implementation | Where |
|-----------|---------------|-------|
| Hero counter count-up | `setInterval` in `useEffect`, cubic-ease-out formula | HeroSection |
| Pulsing dot | `animate-pulse` Tailwind class | Hero eyebrow pill |
| NavBar blur-in on scroll | CSS `transition-all duration-300` + `backdropFilter` toggle | NavBar |
| Button hover scale | `hover:scale-105 transition-all duration-200` | All CTA buttons |
| Progress bar fill | `transition: width 700ms ease` inline | ProgressSection |
| SVG progress ring | `transition: stroke-dasharray 0.8s ease` inline | ProgressSection circles |
| Topic card glow on complete | Color change via `${topic.color}` inline style | ProgressSection |
| Quiz option reveal | Instant color class swap on answer | QuizSection |
| Accordion arrow rotation | `transform: rotate(180deg)` | InterviewSection |
| Mobile hamburger | CSS transform `rotate-45`, `translate-y-2` | NavBar |
| Roadmap hover border | `hover:border-white/20` transition | RoadmapSection |

### Counter Animation (Hero — Key Pattern)
```typescript
useEffect(() => {
  const targets = { students: 12400, lessons: 340, companies: 280 };
  const duration = 1800;  // ms total
  const steps = 60;       // frames
  let step = 0;
  const timer = setInterval(() => {
    step++;
    const p = step / steps;
    const ease = 1 - Math.pow(1 - p, 3);  // cubic ease-out
    setCounter({
      students: Math.floor(targets.students * ease),
      // ...
    });
    if (step >= steps) clearInterval(timer);
  }, duration / steps);
  return () => clearInterval(timer);
}, []);
```

---

## 14. RESPONSIVE DESIGN STRATEGY

### Breakpoints Used (Tailwind defaults)
| Prefix | Min-width | Usage |
|--------|-----------|-------|
| (none) | 0px | Mobile-first base styles |
| `sm:` | 640px | Tablet adjustments |
| `md:` | 768px | Desktop nav appears |
| `lg:` | 1024px | Rarely used |
| `xl:` | 1280px | Rarely used |

### Mobile Patterns
- **NavBar:** `hidden md:flex` for desktop nav; hamburger + slide-down menu on mobile
- **Hero stats:** `grid-cols-3` — stays 3 columns even on mobile (cards shrink to fit)
- **Roadmap topics:** `sm:grid-cols-3` → single column on mobile, 3 on sm+
- **Progress overview:** `grid-cols-1 sm:grid-cols-3` → stacked on mobile
- **Interview CTAs:** `flex-col sm:flex-row`
- **Typography:** All headings use responsive font size e.g. `text-5xl sm:text-6xl md:text-7xl`

### Mobile Nav Implementation
```tsx
// Desktop: horizontal nav bar (hidden on mobile with 'hidden md:flex')
// Mobile: hamburger button (visible only on mobile 'md:hidden')
// Opens vertical dropdown with the same section links
```

---

## 15. EVERY FILE — PURPOSE & FULL CODE

### `index.html`
**Purpose:** HTML entry point. Sets meta tags, loads Google Fonts, mounts the React app.
**Key details:**
- `theme-color: #080b14` for mobile browser chrome
- Open Graph tags for social sharing
- Inter font loaded with all 7 weights (300–900)
- `<div id="root">` is the React mount point

### `src/main.tsx`
**Purpose:** React entry point. Creates the root and renders `<App />` in StrictMode.
```tsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.tsx'
import './index.css'

ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode><App /></React.StrictMode>,
)
```

### `src/App.tsx`
**Purpose:** Root component. Owns the `active` navigation state. Renders `<NavBar>`, the active section, and `<Footer>`. Scrolls to top on every section change.
```tsx
export default function App() {
  const [active, setActive] = useState<NavSection>('Home');
  
  useEffect(() => {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }, [active]);

  const renderSection = () => { switch(active) { ... } };

  return (
    <div className="min-h-screen text-white font-sans">
      <NavBar active={active} setActive={setActive} />
      <main>{renderSection()}</main>
      <Footer />
    </div>
  );
}
```

### `src/index.css`
**Purpose:** Global styles and Tailwind directives.
**Contains:**
- `@tailwind base/components/utilities` directives
- `body` background gradient (the cosmic dark)
- Custom utility classes: `.glass`, `.gradient-text`, `.gradient-btn`
- Custom scrollbar styling (6px, subtle)
- Text selection color (cyan tint)

### `src/types/index.ts`
**Purpose:** Centralised TypeScript type definitions shared across the project.
**Current types:**
```typescript
interface Topic { title, done, desc }
interface Phase { phase, color, topics: Topic[] }
interface QuizQuestion { id, category, question, options, answer, explanation }
interface InterviewQuestion { cat, q, a, icon }
interface TrackedTopic extends Topic { phase, track, color }
type NavSection = 'Home' | 'Roadmap' | 'Quiz' | 'Progress' | 'Interview'
```
**Needs to be extended** when Learning section is added to include `'Learn'` in `NavSection`.

### `src/data/roadmaps.ts`
**Purpose:** Static data for the Roadmap section. Defines the 3-phase structure for each track.
**Exports:** `EXCEL_ROADMAP: Phase[]`, `SQL_ROADMAP: Phase[]`
**Excel phases:** Foundation (`#22d3ee`), Intermediate (`#a78bfa`), Advanced (`#f472b6`)
**SQL phases:** Core SQL (`#34d399`), Intermediate SQL (`#fb923c`), Expert SQL (`#f43f5e`)
**Each topic has:** `title, done (boolean), desc`

### `src/data/quiz.ts`
**Purpose:** Global quiz questions (used in the main Quiz section).
**Exports:** `QUIZ_QUESTIONS: QuizQuestion[]` — 8 questions (4 Excel, 4 SQL)
**Structure per question:** `{ id, category, question, options: string[], answer: number (0-indexed), explanation }`

### `src/data/interview.ts`
**Purpose:** Interview Q&A data for the Interview section.
**Exports:** `INTERVIEW_QS: InterviewQuestion[]` — 8 questions (4 Excel, 4 SQL)
**Structure:** `{ cat: 'Excel' | 'SQL', q, a, icon: string (emoji) }`

### `src/data/lessons.ts`
**Purpose:** The comprehensive lesson content database. 1,368 lines.
**This is the largest and most complex data file in the project.**

**Exports:**
- `interface Exercise { prompt, hint, answer }`
- `interface LessonQuiz { question, options, answer, explanation }`
- `interface Lesson { id, title, duration, difficulty, summary, objectives, explanation, syntaxBlock?, examples, exercises, quiz, tags }`
- `interface LessonModule { id, title, icon, color, track, phase, lessons }`
- `EXCEL_MODULES: LessonModule[]` — 3 modules, 7 lessons total
- `SQL_MODULES: LessonModule[]` — 3 modules, 7 lessons total
- `ALL_MODULES: LessonModule[]` — combined array for search
- `function searchLessons(query: string): { lesson: Lesson; module: LessonModule }[]`

**Excel Modules & Lessons:**
| Module | Phase | Color | Lessons |
|--------|-------|-------|---------|
| Excel Foundation | Phase 1 | `#22d3ee` | Interface & Navigation, Formulas & Core Functions, Data Formatting |
| Excel Intermediate | Phase 2 | `#a78bfa` | PivotTables, Advanced Formulas (INDEX/MATCH & XLOOKUP) |
| Excel Advanced | Phase 3 | `#f472b6` | Power Query (ETL), VBA & Macros |

**SQL Modules & Lessons:**
| Module | Phase | Color | Lessons |
|--------|-------|-------|---------|
| Core SQL | Phase 1 | `#34d399` | SELECT & WHERE, JOINs, Aggregation & GROUP BY |
| Intermediate SQL | Phase 2 | `#fb923c` | CTEs & Subqueries, Window Functions |
| Expert SQL | Phase 3 | `#f43f5e` | Query Optimization & Indexes, Stored Procedures & Transactions |

**Each Lesson contains:**
- `id` — unique slug (e.g., `'excel-interface'`, `'sql-joins'`)
- `title` — display name
- `duration` — estimated time string (e.g., `'20 min'`)
- `difficulty` — `'Beginner' | 'Intermediate' | 'Advanced'`
- `summary` — 1-sentence description
- `objectives` — array of 4-5 learning outcome strings
- `explanation` — long-form markdown-style text (uses `**bold**` and backtick formatting)
- `syntaxBlock?` — optional syntax reference block (plain text/code)
- `examples` — array of `{ title, code, description }` code examples
- `exercises` — array of `{ prompt, hint, answer }` practice exercises
- `quiz` — array of `{ question, options, answer, explanation }` per-lesson quiz questions
- `tags` — array of searchable keywords

**`searchLessons()` function:**
```typescript
export function searchLessons(query: string): { lesson: Lesson; module: LessonModule }[] {
  // Searches: title, summary, explanation, tags, objectives
  // Case-insensitive, simple substring match
  // Returns empty array for empty query
}
```

### `src/components/NavBar.tsx`
**Purpose:** Fixed top navigation bar. Scrolls background appears on scroll. Hamburger menu for mobile.
**Props:** `{ active: NavSection, setActive: (s: NavSection) => void }`
**Key behaviors:**
- `useEffect` with scroll listener: sets `scrolled` state when `window.scrollY > 30`
- When `scrolled`: applies `rgba(10,10,20,0.85)` background + `blur(20px)` + border-bottom
- When NOT scrolled: transparent background (hero bleeds behind it)
- Desktop: horizontal links + CTA button
- Mobile: hamburger (3 lines → X animation) + full-width dropdown
- `SECTIONS` constant = `['Home', 'Roadmap', 'Quiz', 'Progress', 'Interview']` — **must be updated when new sections added**
- Active section has `bg-white/10` highlight
- CTA button ("Take Quiz →") has gradient background
- **Needs `'Learn'` added to SECTIONS array when learning section is built**

### `src/components/Footer.tsx`
**Purpose:** Simple footer with logo and copyright. No links.
**Content:** Logo (gradient XS square + text), copyright line
**No props.** Pure display component.

### `src/components/ui/GlassCard.tsx`
**Purpose:** Reusable glass card container. The most-used UI primitive.
**Props:** `{ children, className?: string, onClick?: () => void }`
**Usage:** Wrap any card content with `<GlassCard className="p-6">...</GlassCard>`
**Style:** See section 12 for full glassmorphism spec.

### `src/components/ui/Badge.tsx`
**Purpose:** Small colored category pill (Excel = cyan, SQL = emerald).
**Props:** `{ children, color?: 'excel' | 'sql' | 'default' }`
**Usage:** `<Badge color="excel">Excel</Badge>`
**Colors:**
- `excel` → `bg-cyan-500/20 text-cyan-300 border-cyan-500/30`
- `sql` → `bg-emerald-500/20 text-emerald-300 border-emerald-500/30`
- `default` → `bg-white/10 text-white/70 border-white/20`

### `src/components/sections/HeroSection.tsx`
**Purpose:** The landing page. Full-viewport with animated stats, CTAs, and ambient effects.
**Props:** `{ setActive: (s: NavSection) => void }`
**Key elements:**
- 3 ambient orbs (cyan, purple, pink) — absolutely positioned, pointer-events-none
- Grid overlay (60px grid, 3% opacity)
- Eyebrow pill with pulsing dot
- H1 with gradient text span
- Two CTA buttons: "Start Learning →" (gradient, calls `setActive('Roadmap')`) and "Take Free Quiz" (ghost, calls `setActive('Quiz')`)
- 3 animated counter stat cards
- 6 tech stack pills

### `src/components/sections/RoadmapSection.tsx`
**Purpose:** Phased learning roadmap for Excel and SQL.
**Props:** None
**State:** `tab: 'excel' | 'sql'` for tab switching
**Data:** `EXCEL_ROADMAP` and `SQL_ROADMAP` from `data/roadmaps.ts`
**Structure:** Tab toggle → 3 phase cards → 3 topic cards per phase
**Visual:** Phase dot with glow shadow, topic completion indicator (circle/checkmark)

### `src/components/sections/QuizSection.tsx`
**Purpose:** 8-question global quiz with A/B/C/D options and scoring.
**Props:** None
**State:** `qi` (question index), `selected` (chosen answer), `score`, `done`, `answers[]`
**Flow:** Question → Choose option → Show explanation → Next → Results screen
**Results screen:** Conic-gradient score ring, answer strip (cyan/red dots), retake button
**Data:** `QUIZ_QUESTIONS` from `data/quiz.ts`
**Quiz state RESETS on nav away** — known issue, not a bug per requirements

### `src/components/sections/ProgressSection.tsx`
**Purpose:** Topic completion tracker with SVG progress rings and checklist.
**Props:** None
**State:** `topics: TrackedTopic[]` (all topics with done toggle), `filter: 'All' | 'Excel' | 'SQL'`
**Data source:** Flattened from `EXCEL_ROADMAP` and `SQL_ROADMAP`
**Key feature:** `CircleProgress` SVG component with animated `stroke-dasharray`
**Critical issue:** State not persisted — refresh resets all checkboxes (see section 29)

### `src/components/sections/InterviewSection.tsx`
**Purpose:** Accordion Q&A for interview prep.
**Props:** None
**State:** `open: number | null` (which accordion is open), `filter: 'All' | 'Excel' | 'SQL'`
**Data:** `INTERVIEW_QS` from `data/interview.ts`
**Behavior:** Click question → shows answer panel; click again → hides
**Bottom CTA:** Two buttons (non-functional currently, wired to nothing)

---

## 16. EVERY REACT COMPONENT — PURPOSE & PROPS

| Component | File | Props | Purpose |
|-----------|------|-------|---------|
| `App` | `App.tsx` | none | Root. Nav state. Section switcher. |
| `NavBar` | `NavBar.tsx` | `{active, setActive}` | Fixed navigation bar |
| `Footer` | `Footer.tsx` | none | Simple footer |
| `GlassCard` | `ui/GlassCard.tsx` | `{children, className?, onClick?}` | Glass card primitive |
| `Badge` | `ui/Badge.tsx` | `{children, color?}` | Category pill |
| `HeroSection` | `sections/HeroSection.tsx` | `{setActive}` | Landing hero |
| `RoadmapSection` | `sections/RoadmapSection.tsx` | none | Learning roadmap |
| `QuizSection` | `sections/QuizSection.tsx` | none | Global quiz |
| `ProgressSection` | `sections/ProgressSection.tsx` | none | Topic tracker |
| `InterviewSection` | `sections/InterviewSection.tsx` | none | Interview Q&A |
| `CircleProgress` *(local)* | inside ProgressSection | `{val, max, color, label}` | SVG donut ring |

### Components That Need To Be Built (Session 3 Incomplete)

| Component | File | Purpose |
|-----------|------|---------|
| `LearningSection` | `sections/learning/LearningSection.tsx` | Module/lesson browser with sidebar |
| `LessonViewer` | `sections/learning/LessonViewer.tsx` | Full lesson display: explanation, examples, exercises, quiz |
| `SearchSection` | `sections/learning/SearchSection.tsx` | Search bar + results from `searchLessons()` |
| `ModuleCard` | `sections/learning/ModuleCard.tsx` | Card for each learning module |
| `LessonCard` | `sections/learning/LessonCard.tsx` | Card for individual lesson in module list |
| `ExercisePanel` | `sections/learning/ExercisePanel.tsx` | Practice exercise with hint/reveal answer |
| `CodeBlock` | `ui/CodeBlock.tsx` | Styled code display for examples and syntax |

---

## 17. DATA ARCHITECTURE

### Current Data Flow
```
Static TypeScript arrays (in /src/data/) → Props → React components → DOM
```
No API calls. No database. No server. All data is bundled at build time.

### Data Files Summary
| File | Size | Records | Purpose |
|------|------|---------|---------|
| `roadmaps.ts` | ~60 lines | 6 phases, 18 topics | Roadmap display & progress tracking |
| `quiz.ts` | ~79 lines | 8 questions | Global quiz section |
| `interview.ts` | ~53 lines | 8 Q&As | Interview section |
| `lessons.ts` | 1,368 lines | 4 modules (7+7), 14 lessons | Learning section content |

### TypeScript Interface Hierarchy
```
LessonModule
  ├── id: string
  ├── title: string
  ├── icon: string (emoji)
  ├── color: string (hex)
  ├── track: 'Excel' | 'SQL'
  ├── phase: string
  └── lessons: Lesson[]
       ├── id: string
       ├── title: string
       ├── duration: string
       ├── difficulty: 'Beginner' | 'Intermediate' | 'Advanced'
       ├── summary: string
       ├── objectives: string[]
       ├── explanation: string (markdown-style text)
       ├── syntaxBlock?: string
       ├── examples: { title, code, description }[]
       ├── exercises: Exercise[]
       │    └── { prompt, hint, answer }
       └── quiz: LessonQuiz[]
            └── { question, options, answer, explanation }
```

### Data to Add (Future)
When the following planned features are built, new data files/structures needed:
```
/src/data/certificates.ts     → certificate templates and conditions
/src/data/projects.ts         → practice project specifications
/src/data/resumeTemplates.ts  → resume template configs
```

---

## 18. FEATURES COMPLETED

### ✅ Visual Design & UI Framework
- Dark theme with cosmic gradient background
- Full glassmorphism card system (GlassCard component)
- Ambient orb effects on hero section
- Grid overlay decorative element
- Responsive design (mobile hamburger, fluid typography)
- Custom scrollbar styling
- Text selection color
- Inter font with all weights
- Brand color palette defined in Tailwind config

### ✅ Navigation
- Fixed top navbar with scroll-triggered blur
- Active section highlighting
- Mobile hamburger menu with animation
- Logo click → Home
- "Take Quiz" CTA button in navbar

### ✅ Hero Section
- Full-viewport hero
- Animated counter stats (cubic ease-out, 1.8s)
- Gradient headline text
- Two CTA buttons wired to nav
- Tech stack pills
- Ambient background orbs

### ✅ Roadmap Section
- Excel roadmap: 3 phases, 9 topics
- SQL roadmap: 3 phases, 9 topics
- Tab toggle (Excel / SQL)
- Phase cards with colored phase indicator + glow
- Topic completion indicators (checkmark / empty circle)
- Hover effects on topic cards

### ✅ Global Quiz Section
- 8-question multiple choice quiz
- Question progress indicator (colored bars)
- Category badge (Excel/SQL)
- A/B/C/D options with letters
- Instant feedback on selection (green correct, red wrong)
- Explanation reveal on answer
- Score tracking (score/total counter)
- Results screen with conic-gradient score ring
- Answer strip visualization
- Retake functionality

### ✅ Progress Tracker
- Flattened topic list from roadmap data
- Filter: All / Excel / SQL
- Click-to-toggle completion
- Animated SVG donut rings (Excel, SQL, Overall)
- Overall horizontal progress bar
- Phase and description metadata per topic
- Color-coded by track and phase

### ✅ Interview Questions Section
- 8 questions (4 Excel, 4 SQL)
- Filter: All / Excel / SQL
- Accordion expand/collapse with arrow animation
- Category badges
- Bottom CTA card

### ✅ Footer
- Logo + copyright
- Responsive layout

### ✅ Project Infrastructure
- Complete Vite 5 + React 18 + TypeScript 5 setup
- Tailwind CSS 3.4 with PostCSS
- ESLint configured
- TypeScript strict mode
- `vercel.json` for SPA routing
- `.gitignore`
- `README.md`
- ZIP download for GitHub/Vercel deployment

### ✅ Lesson Data (Session 3 — Data Complete, UI Missing)
- `lessons.ts`: 1,368 lines of comprehensive lesson content
- 3 Excel modules with 7 lessons total
- 3 SQL modules with 7 lessons total
- Each lesson has: explanation, syntax block, 2-3 code examples, 2-3 exercises, 2-3 quiz questions
- `searchLessons()` function for full-text search
- `ALL_MODULES` combined export

---

## 19. FEATURES PARTIALLY COMPLETED

### ⚠️ Excel & SQL Learning Sections (Session 3)
**What's done:**
- All lesson data written (1,368 lines in `lessons.ts`)
- TypeScript interfaces defined (Exercise, LessonQuiz, Lesson, LessonModule)
- `searchLessons()` function implemented
- `ALL_MODULES` export ready
- `src/components/sections/learning/` directory created

**What's missing (the UI):**
- `LearningSection.tsx` — the browse/navigation page
- `LessonViewer.tsx` — the lesson reading/interaction page
- `SearchSection.tsx` — the search UI
- `ModuleCard.tsx` — module card component
- `LessonCard.tsx` — lesson card component
- `ExercisePanel.tsx` — exercise with hint/reveal
- `CodeBlock.tsx` — code display component
- Adding `'Learn'` to `NavSection` type
- Adding `'Learn'` to NavBar `SECTIONS` array
- Wiring up `LearningSection` in `App.tsx`

### ⚠️ Progress Tracker Persistence
**What's done:** Full UI with toggle, rings, filters
**What's missing:** `localStorage` persistence (page refresh resets all checkboxes)

### ⚠️ Interview Section Bottom Buttons
**What's done:** Two buttons rendered ("View Full Roadmap", "Practice More Quizzes")
**What's missing:** Both buttons have no `onClick` handler — they do nothing

---

## 20. FEATURES PENDING / PLANNED

The following features were discussed or implied as future additions but not yet built:

| Feature | Priority | Complexity |
|---------|----------|-----------|
| Lesson viewer UI | 🔴 High (blocked) | Medium |
| Search UI | 🔴 High | Low |
| localStorage progress persistence | 🔴 High | Low |
| `react-syntax-highlighter` for code blocks | 🟡 Medium | Low |
| Per-lesson quizzes | 🟡 Medium | Medium |
| User authentication (login/signup) | 🟡 Medium | High |
| Persistent progress (Supabase) | 🟡 Medium | High |
| Certificate system | 🟢 Low | Medium |
| Leaderboard | 🟢 Low | High |
| AI Tutor (LLM integration) | 🟢 Low | Very High |
| Resume builder | 🟢 Low | Very High |
| Admin panel | 🟢 Low | Very High |
| Practice projects | 🟢 Low | Medium |
| Dark/Light mode toggle | 🟢 Low | Low |
| Notification system | 🟢 Low | Medium |

---

## 21. COMPLETE DEVELOPMENT ROADMAP

### Phase 1 — Complete Core Learning (Current Priority)
1. Build `LearningSection.tsx` — module browser with sidebar navigation
2. Build `LessonViewer.tsx` — lesson content display with all sections
3. Build `SearchSection.tsx` — search UI using existing `searchLessons()`
4. Build `CodeBlock.tsx` — styled code display (add `react-syntax-highlighter`)
5. Build `ExercisePanel.tsx` — practice exercises with hint/reveal
6. Wire up lesson per-quiz (each lesson already has `quiz` array in data)
7. Add `'Learn'` and `'Search'` to NavSection type and NavBar
8. Fix localStorage persistence for progress tracker
9. Fix the two non-functional buttons in InterviewSection

### Phase 2 — Polish & Enhancement
1. Add more lessons (currently 14 total — aim for 30+)
2. Add Charts & Dashboards Excel lesson (missing from Phase 2 data)
3. Add Data Manipulation SQL lesson (missing from Intermediate SQL)
4. Add Database Design SQL lesson (missing from Expert SQL)
5. Add `react-syntax-highlighter` for code blocks
6. Add per-lesson difficulty filter in Learn section
7. Add estimated total progress time counter
8. Add keyboard navigation for quiz (1-4 keys for options, Enter for next)
9. Add smooth page transitions (fade)

### Phase 3 — User Accounts & Persistence
1. Set up Supabase project (free tier)
2. Add Auth: email/password + Google OAuth
3. Persist lesson completion to Supabase
4. User profile page (name, join date, track choice)
5. Email verification flow

### Phase 4 — Advanced Features
1. Certificate system: PDF cert on 100% track completion
2. Leaderboard: top learners by lessons completed
3. Streaks: daily learning streak counter
4. AI Tutor: Anthropic/OpenAI API for contextual Q&A
5. Resume builder: guided resume with data analyst template
6. Admin panel: add/edit lessons from UI

---

## 22. EXCEL LEARNING MODULE — FULL SPECIFICATION

### Module 1: Excel Foundation (Phase 1, `#22d3ee`)
**ID:** `excel-foundation`

#### Lesson 1: Interface & Navigation (`excel-interface`, 15 min, Beginner)
- Covers: Ribbon, Name Box, Formula Bar, worksheets, cell addressing
- Reference types: A1, $A$1, $A1, A$1, Sheet2!A1
- Navigation shortcuts: Ctrl+End, Ctrl+Home, Ctrl+Arrow, Ctrl+Shift+Arrow, F2
- 3 exercises | 3 quiz questions
- Tags: interface, navigation, cells, shortcuts, ribbon

#### Lesson 2: Formulas & Core Functions (`excel-formulas`, 25 min, Beginner)
- Covers: Arithmetic operators, SUM, AVERAGE, MIN, MAX, COUNT, COUNTA, IF (nested), IFS, COUNTIF, SUMIF, AVERAGEIF, VLOOKUP
- Examples: SUM/AVG/MIN/MAX, nested IF vs IFS, VLOOKUP with exact match
- 3 exercises | 3 quiz questions
- Tags: SUM, AVERAGE, IF, COUNTIF, VLOOKUP, formulas, functions

#### Lesson 3: Data Formatting (`excel-formatting`, 20 min, Beginner)
- Covers: Number, currency, date, percentage formats; custom format codes; conditional formatting rules; data bars; color scales
- Custom format syntax: `[Color][condition]format`
- Examples: Common custom formats, CF highlight rules, formula-based CF
- 2 exercises | 2 quiz questions
- Tags: formatting, conditional formatting, number format, color scale, data bars

### Module 2: Excel Intermediate (Phase 2, `#a78bfa`)
**ID:** `excel-intermediate`

#### Lesson 4: PivotTables (`excel-pivottables`, 30 min, Intermediate)
- Covers: Flat data requirements, 4 field areas (Rows/Columns/Values/Filters), Value Field Settings, Show Values As, Slicers, Report Connections, Refresh, Calculated Fields
- Examples: Step-by-step PivotTable build, Show Values As options
- DAX syntax block for calculated fields
- 2 exercises | 2 quiz questions
- Tags: PivotTable, pivot, summarise, slicer, calculated field, aggregate

#### Lesson 5: Advanced Formulas (`excel-advanced-formulas`, 35 min, Intermediate)
- Covers: VLOOKUP limitations, INDEX function, MATCH function, INDEX/MATCH combined, XLOOKUP (365+), two-way lookup, IFERROR, IFNA
- Syntax block: INDEX/MATCH, XLOOKUP, IFERROR
- Examples: INDEX/MATCH vs VLOOKUP comparison, XLOOKUP with fallback, Two-way matrix lookup
- 2 exercises | 2 quiz questions
- Tags: INDEX, MATCH, XLOOKUP, VLOOKUP, lookup, IFERROR, two-way lookup

### Module 3: Excel Advanced (Phase 3, `#f472b6`)
**ID:** `excel-advanced`

#### Lesson 6: Power Query (`excel-power-query`, 40 min, Advanced)
- Covers: ETL concept, Query Editor, Steps pane, M language, Load options (worksheet vs Data Model)
- M syntax block with real generated code example
- Examples: CSV cleaning step-by-step, Unpivot wide-to-tall transformation, Folder combine
- 2 exercises | 2 quiz questions
- Tags: Power Query, ETL, M language, unpivot, merge, transform, data cleaning

#### Lesson 7: VBA & Macros (`excel-vba`, 45 min, Advanced)
- Covers: VBA Editor (Alt+F11), Sub vs Function, Object model hierarchy, Record macros, Option Explicit, Dim, For loops, If/Else
- Syntax block: Hello World, FormatReport, Function DoubleIt examples
- Examples: Find last row pattern (essential), Error handling with On Error GoTo
- 2 exercises | 2 quiz questions
- Tags: VBA, macros, automation, Sub, Function, loop, UDF

### Lessons Still Needed (Not Yet in Data)
- Charts & Dashboards (was in roadmap Phase 2 but missing from lessons.ts)
- Power Pivot & DAX (was in roadmap Phase 3 but missing from lessons.ts)

---

## 23. SQL LEARNING MODULE — FULL SPECIFICATION

### Module 1: Core SQL (Phase 1, `#34d399`)
**ID:** `sql-core`

#### Lesson 1: SELECT & Filtering (`sql-select`, 20 min, Beginner)
- Covers: SELECT syntax, logical execution order (FROM→WHERE→GROUP→HAVING→SELECT→ORDER→LIMIT), comparison operators, BETWEEN, IN, LIKE (%, _), IS NULL / IS NOT NULL
- Examples: Basic SELECT with WHERE, IN/BETWEEN/LIKE/IS NULL combined
- 3 exercises | 3 quiz questions
- Tags: SELECT, WHERE, LIKE, IN, BETWEEN, IS NULL, ORDER BY, filtering

#### Lesson 2: JOINs (`sql-joins`, 30 min, Beginner)
- Covers: Primary key, foreign key, INNER JOIN, LEFT JOIN (anti-join pattern), RIGHT JOIN, FULL OUTER JOIN, CROSS JOIN, table aliases, three-table join
- Examples: INNER JOIN customers+orders, LEFT JOIN anti-join, Three-table join
- 2 exercises | 2 quiz questions
- Tags: JOIN, INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL OUTER JOIN, foreign key, primary key

#### Lesson 3: Aggregation (`sql-aggregation`, 25 min, Beginner)
- Covers: COUNT(*) vs COUNT(col), SUM, AVG, MIN, MAX, GROUP BY, WHERE vs HAVING distinction, NULL in aggregates
- Examples: GROUP BY with multiple aggregates, HAVING filter on groups
- 2 exercises | 2 quiz questions
- Tags: GROUP BY, HAVING, COUNT, SUM, AVG, MIN, MAX, aggregation

### Module 2: Intermediate SQL (Phase 2, `#fb923c`)
**ID:** `sql-intermediate`

#### Lesson 4: CTEs & Subqueries (`sql-ctes`, 30 min, Intermediate)
- Covers: Non-correlated vs correlated subqueries, subquery in SELECT/FROM/WHERE, WITH clause CTE, chaining CTEs, recursive CTE for hierarchies
- Examples: Subquery vs CTE comparison, Recursive CTE employee org chart
- 2 exercises | 2 quiz questions
- Tags: CTE, WITH, subquery, correlated, derived table, recursive, modular SQL

#### Lesson 5: Window Functions (`sql-window-functions`, 35 min, Intermediate)
- Covers: OVER() clause, PARTITION BY, ORDER BY in OVER, ROW_NUMBER, RANK, DENSE_RANK, NTILE, LAG, LEAD, running totals, frame clauses (ROWS BETWEEN)
- Examples: ROW_NUMBER vs RANK vs DENSE_RANK, LAG for month-over-month, Running total
- 2 exercises | 2 quiz questions
- Tags: window function, OVER, PARTITION BY, ROW_NUMBER, RANK, LAG, LEAD, running total

### Module 3: Expert SQL (Phase 3, `#f43f5e`)
**ID:** `sql-advanced`

#### Lesson 6: Query Optimization (`sql-optimization`, 40 min, Advanced)
- Covers: Execution plan reading, EXPLAIN/EXPLAIN ANALYZE, Seq Scan vs Index Scan, B-tree indexes, when indexes help/hurt, index anti-patterns (function wrapping, leading wildcard, type mismatch), covering indexes
- Examples: Index-breaking vs index-friendly patterns, Reading PostgreSQL execution plan
- 2 exercises | 2 quiz questions
- Tags: optimization, index, execution plan, B-tree, query performance, EXPLAIN, slow query

#### Lesson 7: Stored Procedures (`sql-stored-procedures`, 35 min, Advanced)
- Covers: Stored procedure benefits (performance, security, reusability), Variables DECLARE/SET, IF/ELSE, WHILE, CASE in SELECT, ACID transactions, BEGIN/COMMIT/ROLLBACK, TRY/CATCH
- Syntax block: SQL Server CREATE PROCEDURE syntax, transaction pattern
- Examples: Bank transfer procedure with full error handling, Control flow examples
- 2 exercises | 2 quiz questions
- Tags: stored procedure, transaction, ACID, COMMIT, ROLLBACK, TRY CATCH, control flow

### Lessons Still Needed (Not Yet in Data)
- Data Manipulation: INSERT, UPDATE, DELETE, UPSERT (was in roadmap Intermediate SQL)
- Database Design: Normalization, ERD, constraints (was in roadmap Expert SQL)

---

## 24. QUIZ SYSTEM — FULL SPECIFICATION

### Current Global Quiz (QuizSection)
- 8 questions from `data/quiz.ts`
- Question navigation: progress dots + question counter
- No timer
- Single-choice (A/B/C/D)
- Instant answer reveal + explanation
- Results: conic-gradient ring, score, message, answer strip, retake
- State resets on nav away (known issue)

### Per-Lesson Quiz (Data Ready, UI Not Built)
Every lesson has a `quiz: LessonQuiz[]` array. These need a quiz UI component inside `LessonViewer`. Should show:
- Quiz question at end of lesson
- Same A/B/C/D pattern as global quiz
- "Lesson Complete" state when all quiz questions answered
- Score contribution to overall progress

### Quiz Data Structure
```typescript
interface LessonQuiz {
  question: string;
  options: string[];
  answer: number;     // 0-indexed correct answer
  explanation: string;
}
```

### Planned Quiz Enhancements
- Shuffle question order (optional)
- Time limit option
- Streak counter
- Wrong answer → show related lesson reference
- Export quiz results as PDF

---

## 25. PROGRESS TRACKER — FULL SPECIFICATION

### Current Implementation
- Data: 18 topics from roadmaps (9 Excel + 9 SQL)
- Toggle: click to mark done/undone
- Filter: All / Excel / SQL buttons
- Visual: 3 SVG donut rings (Excel, SQL, Overall), horizontal progress bar
- State: React `useState` (RESETS ON REFRESH — known issue)

### Known Issues
1. **Not persisted** — localStorage not implemented
2. **Not connected to lessons** — completing a lesson doesn't auto-update progress
3. **Manual only** — user manually ticks topics

### Planned Progress Architecture
```typescript
// What progress should track (future):
interface UserProgress {
  completedLessons: string[];     // lesson IDs
  completedTopics: string[];      // topic titles
  quizScores: Record<string, number>; // lessonId → score %
  lastActive: Date;
  currentStreak: number;
  totalTimeSpent: number;         // minutes
}
```

### Persistence Plan
**Short-term:** `localStorage` (no auth required)
```typescript
// Save
localStorage.setItem('excel-sql-progress', JSON.stringify(topics));

// Load
const saved = localStorage.getItem('excel-sql-progress');
const initial = saved ? JSON.parse(saved) : buildTopics();
```

**Long-term:** Supabase `user_progress` table with row per user per topic

---

## 26. SEARCH SYSTEM — FULL SPECIFICATION

### Current Implementation
- `searchLessons(query)` function exists in `lessons.ts`
- Returns `{ lesson: Lesson, module: LessonModule }[]`
- Searches: title, summary, explanation, tags, objectives
- Case-insensitive substring match
- Empty query returns `[]`

### What Still Needs Building
A `SearchSection.tsx` component with:
- Search input bar (large, glass-style, with search icon)
- Debounced search (250ms delay, use `useEffect` with timeout)
- Result cards showing: module name, lesson title, difficulty badge, duration, matching tags
- Click result → navigate to that lesson in LearningSection
- Empty state message
- "X results for query" counter
- Highlighted matching text in results (optional enhancement)

### Search Component Spec
```typescript
// State needed:
const [query, setQuery] = useState('');
const [results, setResults] = useState<{ lesson: Lesson; module: LessonModule }[]>([]);

// Debounce pattern:
useEffect(() => {
  const timer = setTimeout(() => {
    setResults(searchLessons(query));
  }, 250);
  return () => clearTimeout(timer);
}, [query]);
```

### Navigation Integration
Search results need to trigger lesson viewing. Options:
1. Pass `setActiveLesson` prop from App.tsx through to SearchSection
2. Use a global state manager (Zustand)
3. Use URL params with react-router

---

## 27. INTERVIEW PREPARATION MODULE

### Current State
- 8 questions in `data/interview.ts`
- Accordion UI with Excel/SQL filter
- Reveal-on-click answers
- Bottom CTA card (buttons non-functional)

### Content Coverage
| # | Category | Question |
|---|----------|---------|
| 1 | Excel | VLOOKUP vs INDEX/MATCH |
| 2 | SQL | DELETE vs TRUNCATE vs DROP |
| 3 | Excel | Building a dynamic dashboard |
| 4 | SQL | CTE vs subquery |
| 5 | SQL | How indexes affect performance |
| 6 | Excel | DAX vs regular formulas |
| 7 | SQL | Window functions |
| 8 | Excel | Large datasets in Excel |

### Planned Enhancements
- Add 20+ more questions (currently only 8)
- Star/bookmark questions
- "I knew this" / "Still learning" self-rating per question
- Practice mode: hide question, type your answer, compare to model answer
- Company filter (FAANG, startups, banks, etc.)
- Difficulty levels per question

---

## 28. PLANNED FEATURES — DETAILED SPECS

### A. Login / Signup
- Email + password registration
- Google OAuth (one-click)
- "Guest mode" — use without account but progress not saved
- Forgot password flow
- Profile page: name, avatar, track selection, join date
- **Technology:** Supabase Auth (free tier, generous limits)

### B. Certificate System
- Triggered when user completes 100% of Excel track or SQL track
- Certificate contains: user name, track name, date, unique ID
- PDF download (use `jspdf` or `react-pdf`)
- Shareable URL (e.g., `/certificate/abc123`)
- LinkedIn "Add to profile" button
- **Design:** Dark certificate matching the site aesthetic, gradient border, signature graphic

### C. Leaderboard
- Top 10 learners by total lessons completed this week/month/all-time
- Requires auth + Supabase
- Points system: lesson complete = 10pts, quiz 100% = 5pts bonus, daily streak = 3pts/day
- Filter: All-time / This Month / This Week
- Your rank highlighted

### D. AI Tutor
- Chat widget (bottom-right corner, floating)
- Powered by Anthropic Claude API (or OpenAI GPT-4o)
- Context-aware: knows which lesson the user is on
- System prompt includes the current lesson's explanation and examples
- Can answer: "I don't understand PARTITION BY", "Give me another example of CTEs"
- Rate limited to prevent abuse
- **API key management:** Supabase Edge Functions (server-side) to hide API key

### E. Resume Builder
- Multi-step form wizard
- Sections: Personal info, Skills (pre-populated from completed lessons), Experience, Education
- Auto-populates data skills based on track completion
- Template: "Data Analyst" focused, ATS-friendly
- PDF export
- LinkedIn-ready formatting

### F. Admin Panel
- Route: `/admin` (protected, admin role in Supabase)
- Add/edit/delete lessons
- View user stats (total users, active this week, lesson completion rates)
- Send announcement emails
- Manage quiz questions
- **Note:** This is a v3 feature, not near-term

### G. Practice Projects
- Real-world mini-projects to apply skills
- Excel project: "Build a Monthly Sales Dashboard"
- SQL project: "Analyze an E-commerce Database"
- Each project has: description, starter data, step-by-step hints, example solution
- No auto-grading (honor system) — manually mark as complete
- Adds to progress tracker

---

## 29. KNOWN ISSUES & BUGS

| # | Issue | Severity | Location | Fix |
|---|-------|----------|----------|-----|
| 1 | Progress not persisted on refresh | 🔴 High | `ProgressSection.tsx` | Add `localStorage` save/load |
| 2 | Quiz resets on nav away | 🟡 Medium | `QuizSection.tsx` | Lift state to `App.tsx` or add confirmation |
| 3 | Interview CTA buttons non-functional | 🟡 Medium | `InterviewSection.tsx` | Add `onClick` handlers with `setActive` |
| 4 | `NavSection` type doesn't include `'Learn'` | 🔴 Blocking | `types/index.ts` | Add `'Learn'` when building learning UI |
| 5 | `NavBar` SECTIONS doesn't include Learn | 🔴 Blocking | `NavBar.tsx` | Add `'Learn'` to the array |
| 6 | No code syntax highlighting | 🟡 Medium | `lessons.ts` examples | Install `react-syntax-highlighter` |
| 7 | Lesson `explanation` uses `**bold**` markdown but is rendered as plain text | 🟡 Medium | Future `LessonViewer` | Need a markdown renderer or custom bold parser |
| 8 | `lessons.ts` has no Charts/Dashboards or Data Manipulation or Database Design lessons | 🟡 Medium | `lessons.ts` | Add 3 more lessons |
| 9 | Badge component imports `React` but not explicitly | 🟢 Low | `Badge.tsx` | Add `import React from 'react'` at top |
| 10 | No loading state anywhere | 🟢 Low | All sections | Not needed yet (no async data) |
| 11 | No error boundary | 🟢 Low | `App.tsx` | Add `<ErrorBoundary>` wrapper |
| 12 | `window.scrollTo` in useEffect causes brief visual jump on section change | 🟢 Low | `App.tsx` | Use `document.getElementById('root').scrollTo` or add opacity transition |

---

## 30. IMPLEMENTATION DECISIONS LOG

| Decision | Choice Made | Reason |
|----------|-------------|--------|
| Framework | React 18 | User specified React |
| Language | TypeScript strict | Type safety; user asked for TS |
| Build tool | Vite 5 | Fastest for React/TS; standard choice |
| Styling | Tailwind CSS 3 | User specified; utility-first perfect for dark theme |
| Routing | State-based (no react-router) | Simplest; project started as single file |
| State management | Local useState | No global state needed yet |
| Data storage | Static TypeScript arrays | No backend needed; data is small |
| Design aesthetic | Dark glassmorphism | User described "dark theme" + "glassmorphism" |
| Font | Inter | Best dark-mode tech font; all weights available free |
| Background | Radial gradient (not image) | CSS-only, no asset loading, crisp at all sizes |
| Ambient orbs | CSS radial gradients with blur | No SVG/image needed; pure CSS |
| Code blocks | Plain `<pre>` tags currently | `react-syntax-highlighter` not yet installed |
| Quiz flow | Linear (Q1→Q2→Q3…→Results) | Simple; no branching needed |
| Progress persistence | None (resets on refresh) | Not yet requested; known issue |
| Lesson content | TypeScript data file | All in one file for simplicity; could split later |
| Search | Substring match | Simple; no Fuse.js/Lunr needed yet |
| Deployment | Vercel | Best DX for Vite; free tier generous |
| CSS custom utilities | Minimal (3 classes) | Prefer Tailwind; custom classes only where necessary |
| Animation library | None (CSS transitions only) | Keeps bundle small; sufficient for current needs |
| Icon library | Emojis only | Zero dependency; works everywhere; matches playful tone |

---

## 31. ENVIRONMENT VARIABLES

### Current Status
**There are ZERO environment variables in this project.** No `.env` file exists or is needed.

The project is a fully static SPA with no API calls, no keys, and no server communication.

### Future Environment Variables (When Added)
```env
# .env.local (never commit to git)
VITE_SUPABASE_URL=https://xxxx.supabase.co
VITE_SUPABASE_ANON_KEY=your_anon_key_here
VITE_ANTHROPIC_API_KEY=sk-ant-...     # Only if AI tutor is client-side (not recommended)

# In Vercel dashboard (Environment Variables section):
VITE_SUPABASE_URL
VITE_SUPABASE_ANON_KEY
```

**Critical:** Vite exposes only variables prefixed with `VITE_` to the client bundle. Never put secret keys in `VITE_` variables — they become public. Use Supabase Edge Functions for any server-side API calls.

### `.env.example` File to Create
```env
# Copy this to .env.local and fill in values
VITE_SUPABASE_URL=
VITE_SUPABASE_ANON_KEY=
```

---

## 32. GITHUB & VERCEL SETUP

### GitHub Repository Setup
```bash
# Initialize (if not already)
cd excel-sql-academy
git init
git add .
git commit -m "feat: initial project setup - Excel SQL Career Academy"

# Create repo on GitHub (via CLI with gh)
gh repo create excel-sql-career-academy --public
git remote add origin https://github.com/YOUR_USERNAME/excel-sql-career-academy.git
git branch -M main
git push -u origin main

# Recommended branch structure:
# main → production (Vercel auto-deploys)
# develop → staging (Vercel preview)
# feature/xxx → feature branches
```

### Recommended `.gitignore` (already exists)
```
node_modules/
dist/
dist-ssr/
.env
.env.local
.DS_Store
```

### Vercel Setup via CLI
```bash
npm i -g vercel
vercel login
cd excel-sql-academy
vercel                     # initial setup wizard
# Framework: Vite (auto-detected)
# Build: npm run build (auto-detected)
# Output: dist (auto-detected)
vercel --prod              # deploy to production URL
```

### Vercel Setup via Dashboard
1. Go to https://vercel.com/new
2. "Import Git Repository" → connect GitHub
3. Select `excel-sql-career-academy`
4. Vercel auto-detects Vite framework
5. Override build command if needed: `npm run build`
6. Output directory: `dist`
7. Click Deploy
8. Set custom domain in Domain settings

### Vercel Project Settings
```json
// vercel.json (already in project)
{
  "rewrites": [{ "source": "/(.*)", "destination": "/index.html" }],
  "headers": [{
    "source": "/assets/(.*)",
    "headers": [{ "key": "Cache-Control", "value": "public, max-age=31536000, immutable" }]
  }]
}
```

---

## 33. EXACT NEXT DEVELOPMENT STEPS

Follow these steps IN ORDER. Do not skip steps or re-architect anything unless explicitly asked.

### Step 1: Fix the NavSection Type (5 minutes)
**File:** `src/types/index.ts`
```typescript
// Change this line:
export type NavSection = 'Home' | 'Roadmap' | 'Quiz' | 'Progress' | 'Interview';

// To this:
export type NavSection = 'Home' | 'Roadmap' | 'Quiz' | 'Progress' | 'Interview' | 'Learn' | 'Search';
```

### Step 2: Update NavBar (5 minutes)
**File:** `src/components/NavBar.tsx`
```typescript
// Change:
const SECTIONS: NavSection[] = ['Home', 'Roadmap', 'Quiz', 'Progress', 'Interview'];

// To:
const SECTIONS: NavSection[] = ['Home', 'Roadmap', 'Learn', 'Quiz', 'Progress', 'Interview'];
// Note: 'Learn' goes between Roadmap and Quiz in the nav order
```

### Step 3: Add CodeBlock UI Component (15 minutes)
**New File:** `src/components/ui/CodeBlock.tsx`
Install syntax highlighter first:
```bash
npm install react-syntax-highlighter
npm install @types/react-syntax-highlighter -D
```
Build a dark-themed code block that renders lesson `syntaxBlock` and `examples[].code` fields. Use the `atomOneDark` or `vscDarkPlus` theme to match the site aesthetic.

### Step 4: Build LearningSection (45 minutes)
**New File:** `src/components/sections/learning/LearningSection.tsx`
This is the "browsing" view — shows all modules and their lessons.
Layout: Two-column on desktop (sidebar: module list, main: lesson cards), single column on mobile.
Data: Import from `ALL_MODULES` in `lessons.ts`.
Props: `{ setActiveLesson: (lessonId: string, moduleId: string) => void }`
State: `activeModule: string | null` (which module is expanded in sidebar)

### Step 5: Build LessonViewer (60 minutes)
**New File:** `src/components/sections/learning/LessonViewer.tsx`
The full lesson reading experience.
Sections in order:
1. Breadcrumb: Module Name → Lesson Title
2. Header: title, difficulty badge, duration, track badge
3. Learning objectives (checklist display)
4. Explanation (markdown-style — parse `**text**` as bold, \`code\` as inline code)
5. Syntax Block (if exists — use CodeBlock)
6. Examples (code blocks with titles and descriptions)
7. Exercises (ExercisePanel components)
8. Lesson Quiz (per-lesson quiz questions)
9. "Mark Complete" button + next lesson navigation

### Step 6: Build ExercisePanel (20 minutes)
**New File:** `src/components/sections/learning/ExercisePanel.tsx`
Props: `{ exercise: Exercise }`
State: `showHint: boolean`, `showAnswer: boolean`
Display: Prompt text, "Show Hint" button → hint text, "Reveal Answer" button → answer text
All styled with GlassCard in the existing design language.

### Step 7: Build SearchSection (30 minutes)
**New File:** `src/components/sections/learning/SearchSection.tsx`
Input: Large glass-style search input with search icon
Debounce: 250ms with useEffect
Results: Cards showing module name, lesson title, difficulty, duration, tag list
Empty state: "Start typing to search lessons..." or "No results for 'X'"
Result click: Navigate to lesson (pass `setActive` and lesson/module IDs)

### Step 8: Wire Up in App.tsx (15 minutes)
**File:** `src/App.tsx`
Add state for `activeLessonId` and `activeModuleId`.
Update `renderSection()` to handle `'Learn'` and `'Search'` cases.
Pass necessary props down.

### Step 9: Add localStorage to Progress Tracker (15 minutes)
**File:** `src/components/sections/ProgressSection.tsx`
```typescript
// On mount, load saved state:
const [topics, setTopics] = useState<TrackedTopic[]>(() => {
  const saved = localStorage.getItem('excel-sql-progress');
  return saved ? JSON.parse(saved) : buildTopics();
});

// On every change, save:
useEffect(() => {
  localStorage.setItem('excel-sql-progress', JSON.stringify(topics));
}, [topics]);
```

### Step 10: Fix Interview Section Buttons (5 minutes)
**File:** `src/components/sections/InterviewSection.tsx`
The component needs `setActive` prop. Add `onClick` to "View Full Roadmap" → `setActive('Roadmap')` and "Practice More Quizzes" → `setActive('Quiz')`.

---

## 34. CRITICAL NOTES FOR GEMINI

### What You MUST NOT Change
1. **The visual design** — user explicitly said "keep the current website design exactly as it is"
2. **The color palette** — every hex color is intentional
3. **The GlassCard component** — it is the visual foundation; do not alter its styles
4. **The background gradient** — the `body` background in `index.css` is sacred
5. **The Inter font** — do not switch to another font
6. **The existing component APIs** — don't change props of existing components without reason

### What You MUST Preserve in New Code
1. **Same TypeScript patterns** — strict types, no `any`, proper interfaces
2. **Same Tailwind approach** — utility-first, minimal custom CSS
3. **Same glassmorphism formula** — `rgba(255,255,255,0.04)` + `blur(16px)` + `border-white/10`
4. **Same ambient design language** — glow effects, gradient accents, muted white opacity scale
5. **Same naming conventions** — PascalCase components, camelCase variables, SCREAMING_SNAKE for constants
6. **Same file organization** — data in `/data/`, components in `/components/`, ui primitives in `/ui/`
7. **Functional components only** — no class components
8. **Named exports** — all components use `export function X()` not `export default function X()` (except `App.tsx` which uses default export)

### Code Style Rules Observed in the Project
```typescript
// ✅ Named export (all components except App)
export function MyComponent({ prop }: Props) { ... }

// ✅ Interface for props, not type alias
interface MyProps {
  name: string;
  onClick?: () => void;
}

// ✅ Explicit type annotations
const [state, setState] = useState<string>('');

// ✅ const for type narrowing
const filtered = filter === 'All' ? data : data.filter(...);

// ✅ Tailwind utility classes first, inline style for dynamic values
className="rounded-2xl border border-white/10"
style={{ background: `${color}15` }}  // dynamic opacity

// ✅ Template literals for dynamic hex opacity
`${phase.color}15`   // "#22d3ee" + "15" = 9% opacity
`${phase.color}40`   // "#22d3ee" + "40" = 25% opacity

// ✅ Spreading in JSX
<GlassCard className="p-6 sm:p-8">

// ❌ No class components
// ❌ No useContext yet
// ❌ No external animation libraries
// ❌ No CSS modules
// ❌ No styled-components
```

### The Lesson `explanation` Field
The `explanation` field in each lesson uses informal markdown:
- `**text**` for bold
- `` `code` `` for inline code
- Lines starting with `- ` for bullet points

These are NOT parsed as markdown anywhere yet. When building `LessonViewer`, you need to either:
1. Install and use `react-markdown` (simplest)
2. Write a simple parser for `**bold**` and `` `code` `` (lightweight)

**Recommended:** Use `react-markdown` with a custom renderer to apply the site's typography styles.

```bash
npm install react-markdown
```

### The `syntaxBlock` Field
Present in most lessons. It's plain preformatted text (not markdown). Should be rendered in a `<CodeBlock>` component with dark background and monospace font.

### Phase Color Consistency
The color assigned to each phase/module is used EVERYWHERE consistently:
- Phase dot glow in roadmap
- Topic card border/background tint
- Progress ring stroke color
- Module card accent

Never reassign these colors:
| Phase | Color |
|-------|-------|
| Excel Foundation | `#22d3ee` |
| Excel Intermediate | `#a78bfa` |
| Excel Advanced | `#f472b6` |
| SQL Core | `#34d399` |
| SQL Intermediate | `#fb923c` |
| SQL Expert | `#f43f5e` |

### The `done` Field in Roadmap Data
The initial `done` values in `roadmaps.ts` are **demo values** to show the UI works (a few topics pre-checked). These should eventually be replaced with user-specific progress from localStorage/Supabase.

Currently:
- Excel Foundation: Interface (done=true), Formulas (done=true), Formatting (done=false)
- SQL Core: SELECT (done=true), Joins (done=true), Aggregation (done=false)
- All others: done=false

### Testing the Project After Changes
There is no test suite. Manual testing only. After every change:
1. `npm run dev` — check for runtime errors
2. `npx tsc --noEmit` — check for TypeScript errors
3. `npm run lint` — check for ESLint errors
4. `npm run build` — verify production build succeeds
5. Test on mobile viewport (Chrome DevTools)

### The ZIP File
When the user asks for a ZIP of the project to download, use:
```bash
cd /path/to/parent
zip -r excel-sql-career-academy.zip excel-sql-academy/ \
  --exclude "*/node_modules/*" \
  --exclude "*/.git/*" \
  --exclude "*/dist/*"
```

### Suggested Future Package Additions
If/when installing new packages, these are the vetted choices:
```bash
npm install react-syntax-highlighter       # code highlighting
npm install @types/react-syntax-highlighter -D

npm install react-markdown                 # lesson explanation rendering

npm install zustand                        # state management (when needed)

npm install @supabase/supabase-js         # auth + database

npm install framer-motion                  # animations (only if needed)

npm install react-hot-toast               # notifications/toasts

npm install jspdf html2canvas             # PDF certificate generation
```

---

## APPENDIX A: COMPLETE FILE CONTENTS SUMMARY

All files are either fully documented above or exist exactly as created in the Vite project setup. Key files to re-read if context is needed:

| File | Lines | Action if Lost |
|------|-------|---------------|
| `src/data/lessons.ts` | 1,368 | Most critical — regenerate from the lesson specs in sections 22-23 of this document |
| `src/types/index.ts` | 35 | Short — recreate from section 15 |
| `src/App.tsx` | 36 | Short — recreate from section 15 |
| `src/components/NavBar.tsx` | 110 | Medium — recreate from section 15 |
| `src/components/sections/HeroSection.tsx` | 152 | Medium — recreate from section 15 |

---

## APPENDIX B: IMPORTANT PROMPTS USED DURING DEVELOPMENT

### Prompt 1 (Initial Project)
> "Create a premium modern learning website called Excel SQL Career Academy. Features: Dark theme, Glassmorphism UI, Modern hero section, Excel Learning Roadmap, SQL Learning Roadmap, Interactive Quiz Section, Progress Tracker, Interview Questions Section, Mobile Responsive Design. Use: React, TypeScript, Tailwind CSS. Generate complete project structure and homepage code."

### Prompt 2 (Full Vite Project)
> "I downloaded the JSX file. Now generate a complete Vite + React + TypeScript + Tailwind CSS project. Give me: package.json, vite.config.ts, tsconfig.json, tailwind.config.js, postcss.config.js, src/App.tsx, src/main.tsx, all required files. Provide the complete project structure and code files separately. Convert this entire project into a downloadable ZIP project ready for GitHub and Vercel deployment."

### Prompt 3 (Feature Expansion)
> "Continue working on the existing Excel SQL Career Academy project. Do NOT create a new project. Do NOT change the current UI or design. Expand the existing project by adding: 1. Complete Excel Learning section with structured lessons, explanations, examples, practice exercises and quizzes. 2. Complete SQL Learning section with structured lessons, explanations, examples, practice exercises and quizzes. 3. Search for all lessons. 4. Progress Tracker. 5. Navigation for all learning modules. Keep the current website design exactly as it is. Update the existing project files instead of creating a new one."

### Prompt 4 (This Handover)
> "I want to migrate this entire project from Claude to Google Gemini. Generate a COMPLETE PROJECT HANDOVER DOCUMENT. This is NOT a summary. This document must contain absolutely everything required so another AI can continue development with zero loss of context."

---

## APPENDIX C: QUICK REFERENCE CARD

```
Project: Excel SQL Career Academy
Stack:   React 18 + TypeScript (strict) + Tailwind 3.4 + Vite 5
Deploy:  Vercel (vercel.json configured)
Design:  Dark glassmorphism, Inter font, cosmic gradient background

Primary color:  #22d3ee (cyan)
Secondary:      #a78bfa (purple)
Background:     #080b14 (near black)

Glass formula:  rgba(255,255,255,0.04) + blur(16px) + border rgba(255,255,255,0.1)
Gradient:       linear-gradient(135deg, #22d3ee, #a78bfa)

Run:       npm run dev
Build:     npm run build
TypeCheck: npx tsc --noEmit
Deploy:    vercel --prod

Current sections: Home, Roadmap, Quiz, Progress, Interview
Missing UI:       Learn, Search (data ready in lessons.ts)
Critical bug:     Progress tracker not persisted (no localStorage)

Next task: Build LearningSection + LessonViewer + SearchSection UI
```

---

*End of Handover Document. Version 1.0. Generated June 2025.*
*This document was authored by Claude (Anthropic) for handover to Google Gemini.*
*All source code belongs to the user who commissioned this project.*

---

---

# ═══════════════════════════════════════════════════════════
# APPENDIX D — COMPLETE SOURCE CODE (EVERY FILE, VERBATIM)
# ═══════════════════════════════════════════════════════════

> **FOR GEMINI:** This appendix contains the full, verbatim source code of every file in the project.
> Copy each block exactly into the correct path shown in the heading.
> The project tree below maps every file to its location.

---

## COMPLETE PROJECT FILE TREE

```
excel-sql-academy/                          ← project root
│
├── .eslintrc.cjs                           ← ESLint config
├── .gitignore                              ← Git ignore rules
├── index.html                              ← HTML entry point (loads React, Google Fonts)
├── package.json                            ← npm dependencies & scripts
├── postcss.config.js                       ← PostCSS plugins (Tailwind + Autoprefixer)
├── tailwind.config.js                      ← Tailwind theme (colors, fonts, custom tokens)
├── tsconfig.json                           ← TypeScript compiler options (strict mode)
├── tsconfig.node.json                      ← TypeScript config for Vite build tool only
├── vercel.json                             ← Vercel SPA rewrites + asset cache headers
├── vite.config.ts                          ← Vite build config + React plugin
│
├── public/
│   └── favicon.svg                         ← Gradient XS logo (SVG, inline)
│
└── src/
    ├── App.tsx                             ← ROOT: owns nav state, renders active section
    ├── main.tsx                            ← ReactDOM.createRoot entry point
    ├── index.css                           ← Tailwind directives + global body/scrollbar styles
    │
    ├── types/
    │   └── index.ts                        ← ALL shared TypeScript interfaces and NavSection type
    │
    ├── data/
    │   ├── roadmaps.ts                     ← EXCEL_ROADMAP + SQL_ROADMAP (3 phases × 3 topics each)
    │   ├── quiz.ts                         ← 8 global quiz questions (QuizQuestion[])
    │   ├── interview.ts                    ← 8 interview Q&As (InterviewQuestion[])
    │   └── lessons.ts                      ← 1,368 lines: ALL lesson content for Learn section
    │                                          Exports: EXCEL_MODULES, SQL_MODULES, ALL_MODULES,
    │                                          searchLessons(), plus 4 TypeScript interfaces
    │
    └── components/
        ├── NavBar.tsx                      ← Fixed top nav, scroll blur, mobile hamburger
        ├── Footer.tsx                      ← Logo + copyright footer
        │
        ├── ui/
        │   ├── GlassCard.tsx               ← CORE PRIMITIVE: glassmorphism card wrapper
        │   └── Badge.tsx                   ← Excel (cyan) / SQL (emerald) category pill
        │
        └── sections/
            ├── HeroSection.tsx             ← Full-screen landing: orbs, counters, CTAs
            ├── RoadmapSection.tsx          ← Tabbed Excel/SQL phase roadmap
            ├── QuizSection.tsx             ← 8-question global quiz + results screen
            ├── ProgressSection.tsx         ← SVG rings + clickable topic checklist
            ├── InterviewSection.tsx        ← Accordion interview Q&A
            └── learning/                   ← ⚠️ EMPTY DIRECTORY — UI TO BE BUILT
                                               (data is ready in lessons.ts)
```

---

---

## FILE 1 — `package.json`

```json
{
  "name": "excel-sql-career-academy",
  "private": true,
  "version": "1.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "tsc && vite build",
    "preview": "vite preview",
    "lint": "eslint . --ext ts,tsx --report-unused-disable-directives --max-warnings 0"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "@types/react": "^18.2.66",
    "@types/react-dom": "^18.2.22",
    "@typescript-eslint/eslint-plugin": "^7.2.0",
    "@typescript-eslint/parser": "^7.2.0",
    "@vitejs/plugin-react": "^4.2.1",
    "autoprefixer": "^10.4.19",
    "eslint": "^8.57.0",
    "eslint-plugin-react-hooks": "^4.6.0",
    "eslint-plugin-react-refresh": "^0.4.6",
    "postcss": "^8.4.38",
    "tailwindcss": "^3.4.3",
    "typescript": "^5.2.2",
    "vite": "^5.2.0"
  }
}
```

---

## FILE 2 — `vite.config.ts`

```typescript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  build: {
    outDir: 'dist',
    sourcemap: false,
    rollupOptions: {
      output: {
        manualChunks: {
          vendor: ['react', 'react-dom'],
        },
      },
    },
  },
})
```

---

## FILE 3 — `tsconfig.json`

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
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true,
    "jsx": "react-jsx",
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noFallthroughCasesInSwitch": true
  },
  "include": ["src"],
  "references": [{ "path": "./tsconfig.node.json" }]
}
```

---

## FILE 4 — `tsconfig.node.json`

```json
{
  "compilerOptions": {
    "composite": true,
    "skipLibCheck": true,
    "module": "ESNext",
    "moduleResolution": "bundler",
    "allowSyntheticDefaultImports": true
  },
  "include": ["vite.config.ts"]
}
```

---

## FILE 5 — `tailwind.config.js`

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {
      fontFamily: {
        sans: ['Inter', 'system-ui', 'sans-serif'],
      },
      colors: {
        brand: {
          cyan: '#22d3ee',
          purple: '#a78bfa',
          pink: '#f472b6',
          emerald: '#34d399',
          orange: '#fb923c',
          rose: '#f43f5e',
        },
      },
      animation: {
        'pulse-slow': 'pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite',
      },
      backdropBlur: {
        xs: '2px',
      },
    },
  },
  plugins: [],
}
```

---

## FILE 6 — `postcss.config.js`

```javascript
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
```

---

## FILE 7 — `vercel.json`

```json
{
  "rewrites": [
    {
      "source": "/(.*)",
      "destination": "/index.html"
    }
  ],
  "headers": [
    {
      "source": "/assets/(.*)",
      "headers": [
        {
          "key": "Cache-Control",
          "value": "public, max-age=31536000, immutable"
        }
      ]
    }
  ]
}
```

---

## FILE 8 — `.eslintrc.cjs`

```javascript
module.exports = {
  root: true,
  env: { browser: true, es2020: true },
  extends: [
    'eslint:recommended',
    'plugin:@typescript-eslint/recommended',
    'plugin:react-hooks/recommended',
  ],
  ignorePatterns: ['dist', '.eslintrc.cjs'],
  parser: '@typescript-eslint/parser',
  plugins: ['react-refresh'],
  rules: {
    'react-refresh/only-export-components': [
      'warn',
      { allowConstantExport: true },
    ],
  },
}
```

---

## FILE 9 — `.gitignore`

```
node_modules
.pnp
.pnp.js
dist
dist-ssr
.env
.env.local
.env.development.local
.env.test.local
.env.production.local
npm-debug.log*
yarn-debug.log*
yarn-error.log*
pnpm-debug.log*
lerna-debug.log*
.vscode/
.idea/
*.suo
*.ntvs*
*.njsproj
*.sln
*.sw?
.DS_Store
Thumbs.db
```

---

## FILE 10 — `index.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/favicon.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="description" content="Excel SQL Career Academy — Master Excel & SQL from zero to hired. Structured roadmaps, interactive quizzes, and real interview prep." />
    <meta name="theme-color" content="#080b14" />
    <meta property="og:title" content="Excel SQL Career Academy" />
    <meta property="og:description" content="Master Excel & SQL from zero to hired. Structured roadmaps, quizzes, and interview prep." />
    <meta property="og:type" content="website" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet" />
    <title>Excel SQL Career Academy</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.tsx"></script>
  </body>
</html>
```

---

## FILE 11 — `public/favicon.svg`

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32">
  <defs>
    <linearGradient id="g" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#22d3ee"/>
      <stop offset="100%" stop-color="#a78bfa"/>
    </linearGradient>
  </defs>
  <rect width="32" height="32" rx="8" fill="url(#g)"/>
  <text x="50%" y="50%" dominant-baseline="central" text-anchor="middle" font-family="Inter,sans-serif" font-size="14" font-weight="900" fill="white">XS</text>
</svg>
```

---

## FILE 12 — `src/main.tsx`

```tsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.tsx'
import './index.css'

ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
)
```

---

## FILE 13 — `src/index.css`

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  * {
    box-sizing: border-box;
  }

  html {
    scroll-behavior: smooth;
  }

  body {
    margin: 0;
    padding: 0;
    font-family: 'Inter', system-ui, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    background: radial-gradient(ellipse at 20% 0%, #0f1729 0%, #080b14 40%, #050710 100%);
    min-height: 100vh;
    color: white;
  }

  #root {
    min-height: 100vh;
  }
}

@layer utilities {
  .glass {
    background: rgba(255, 255, 255, 0.04);
    backdrop-filter: blur(16px);
    -webkit-backdrop-filter: blur(16px);
    border: 1px solid rgba(255, 255, 255, 0.1);
    box-shadow: 0 4px 32px rgba(0, 0, 0, 0.3), inset 0 1px 0 rgba(255, 255, 255, 0.08);
  }

  .gradient-text {
    background: linear-gradient(90deg, #22d3ee, #a78bfa);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .gradient-btn {
    background: linear-gradient(135deg, #22d3ee, #a78bfa);
    box-shadow: 0 4px 32px rgba(34, 211, 238, 0.35);
  }
}

/* Scrollbar */
::-webkit-scrollbar { width: 6px; }
::-webkit-scrollbar-track { background: transparent; }
::-webkit-scrollbar-thumb { background: rgba(255, 255, 255, 0.1); border-radius: 3px; }
::-webkit-scrollbar-thumb:hover { background: rgba(255, 255, 255, 0.2); }

/* Selection */
::selection { background: rgba(34, 211, 238, 0.3); color: white; }
```

---

## FILE 14 — `src/types/index.ts`

```typescript
export interface Topic {
  title: string;
  done: boolean;
  desc: string;
}

export interface Phase {
  phase: string;
  color: string;
  topics: Topic[];
}

export interface QuizQuestion {
  id: number;
  category: string;
  question: string;
  options: string[];
  answer: number;
  explanation: string;
}

export interface InterviewQuestion {
  cat: string;
  q: string;
  a: string;
  icon: string;
}

export interface TrackedTopic extends Topic {
  phase: string;
  track: string;
  color: string;
}

export type NavSection = 'Home' | 'Roadmap' | 'Quiz' | 'Progress' | 'Interview';
// ⚠️ ADD 'Learn' | 'Search' to this union when building the learning UI
```

---

## FILE 15 — `src/App.tsx`

```tsx
import { useState, useEffect } from 'react';
import { NavBar } from './components/NavBar';
import { Footer } from './components/Footer';
import { HeroSection } from './components/sections/HeroSection';
import { RoadmapSection } from './components/sections/RoadmapSection';
import { QuizSection } from './components/sections/QuizSection';
import { ProgressSection } from './components/sections/ProgressSection';
import { InterviewSection } from './components/sections/InterviewSection';
import { NavSection } from './types';

export default function App() {
  const [active, setActive] = useState<NavSection>('Home');

  useEffect(() => {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }, [active]);

  const renderSection = () => {
    switch (active) {
      case 'Home':      return <HeroSection setActive={setActive} />;
      case 'Roadmap':   return <RoadmapSection />;
      case 'Quiz':      return <QuizSection />;
      case 'Progress':  return <ProgressSection />;
      case 'Interview': return <InterviewSection />;
      default:          return <HeroSection setActive={setActive} />;
    }
  };

  return (
    <div className="min-h-screen text-white font-sans">
      <NavBar active={active} setActive={setActive} />
      <main>{renderSection()}</main>
      <Footer />
    </div>
  );
}
```

---

## FILE 16 — `src/components/NavBar.tsx`

```tsx
import { useState, useEffect } from 'react';
import { NavSection } from '../types';

interface NavBarProps {
  active: NavSection;
  setActive: (s: NavSection) => void;
}

const SECTIONS: NavSection[] = ['Home', 'Roadmap', 'Quiz', 'Progress', 'Interview'];
// ⚠️ Add 'Learn' between 'Roadmap' and 'Quiz' when building the learning section

export function NavBar({ active, setActive }: NavBarProps) {
  const [scrolled, setScrolled] = useState(false);
  const [menuOpen, setMenuOpen] = useState(false);

  useEffect(() => {
    const handler = () => setScrolled(window.scrollY > 30);
    window.addEventListener('scroll', handler);
    return () => window.removeEventListener('scroll', handler);
  }, []);

  return (
    <nav
      className="fixed top-0 left-0 right-0 z-50 transition-all duration-300"
      style={{
        background: scrolled ? 'rgba(10,10,20,0.85)' : 'transparent',
        backdropFilter: scrolled ? 'blur(20px)' : 'none',
        WebkitBackdropFilter: scrolled ? 'blur(20px)' : 'none',
        borderBottom: scrolled ? '1px solid rgba(255,255,255,0.06)' : 'none',
      }}
    >
      <div className="max-w-7xl mx-auto px-4 sm:px-6 flex items-center justify-between h-16">
        {/* Logo */}
        <button
          className="flex items-center gap-2.5"
          onClick={() => setActive('Home')}
        >
          <div
            className="w-8 h-8 rounded-lg flex items-center justify-center"
            style={{ background: 'linear-gradient(135deg, #22d3ee, #a78bfa)' }}
          >
            <span className="text-sm font-black text-white">XS</span>
          </div>
          <span className="font-bold text-white text-sm hidden sm:block leading-tight">
            Excel SQL<br />
            <span className="text-[10px] font-normal tracking-widest text-white/40 uppercase">Career Academy</span>
          </span>
        </button>

        {/* Desktop nav */}
        <div className="hidden md:flex items-center gap-1">
          {SECTIONS.map((s) => (
            <button
              key={s}
              onClick={() => setActive(s)}
              className={`px-4 py-2 rounded-xl text-sm font-medium transition-all duration-200 ${
                active === s
                  ? 'text-white bg-white/10'
                  : 'text-white/50 hover:text-white/80 hover:bg-white/5'
              }`}
            >
              {s}
            </button>
          ))}
        </div>

        {/* CTA */}
        <div className="hidden md:flex items-center">
          <button
            className="px-4 py-2 rounded-xl text-sm font-semibold text-white transition-all duration-200 hover:opacity-80"
            style={{ background: 'linear-gradient(135deg, #22d3ee, #a78bfa)' }}
            onClick={() => setActive('Quiz')}
          >
            Take Quiz →
          </button>
        </div>

        {/* Mobile hamburger */}
        <button
          className="md:hidden text-white/70 hover:text-white p-2"
          onClick={() => setMenuOpen(!menuOpen)}
          aria-label="Toggle menu"
        >
          <div className="space-y-1.5">
            <span className={`block w-6 h-0.5 bg-current transition-all duration-200 ${menuOpen ? 'rotate-45 translate-y-2' : ''}`} />
            <span className={`block w-6 h-0.5 bg-current transition-all duration-200 ${menuOpen ? 'opacity-0' : ''}`} />
            <span className={`block w-6 h-0.5 bg-current transition-all duration-200 ${menuOpen ? '-rotate-45 -translate-y-2' : ''}`} />
          </div>
        </button>
      </div>

      {/* Mobile menu */}
      {menuOpen && (
        <div
          className="md:hidden px-4 pb-4 space-y-1"
          style={{ background: 'rgba(10,10,20,0.95)' }}
        >
          {SECTIONS.map((s) => (
            <button
              key={s}
              onClick={() => { setActive(s); setMenuOpen(false); }}
              className="w-full text-left px-4 py-3 rounded-xl text-sm font-medium text-white/70 hover:text-white hover:bg-white/5 transition-all"
            >
              {s}
            </button>
          ))}
        </div>
      )}
    </nav>
  );
}
```

---

## FILE 17 — `src/components/Footer.tsx`

```tsx
export function Footer() {
  return (
    <footer className="border-t border-white/6 mt-10 px-4 py-12">
      <div className="max-w-7xl mx-auto flex flex-col sm:flex-row items-center justify-between gap-4">
        <div className="flex items-center gap-2.5">
          <div
            className="w-8 h-8 rounded-lg flex items-center justify-center"
            style={{ background: 'linear-gradient(135deg, #22d3ee, #a78bfa)' }}
          >
            <span className="text-sm font-black text-white">XS</span>
          </div>
          <div>
            <p className="font-bold text-white text-sm">Excel SQL Career Academy</p>
            <p className="text-white/30 text-xs">From zero to data analyst.</p>
          </div>
        </div>
        <div className="flex flex-col sm:flex-row items-center gap-4 text-white/25 text-xs">
          <span>© 2025 Excel SQL Career Academy</span>
          <span className="hidden sm:inline">·</span>
          <span>All rights reserved</span>
        </div>
      </div>
    </footer>
  );
}
```

---

## FILE 18 — `src/components/ui/GlassCard.tsx`
### ⚠️ CRITICAL: This is the core visual primitive. Do not alter its styles.

```tsx
import React from 'react';

interface GlassCardProps {
  children: React.ReactNode;
  className?: string;
  onClick?: () => void;
}

export function GlassCard({ children, className = '', onClick }: GlassCardProps) {
  return (
    <div
      className={`rounded-2xl border border-white/10 ${className}`}
      style={{
        background: 'rgba(255,255,255,0.04)',
        backdropFilter: 'blur(16px)',
        WebkitBackdropFilter: 'blur(16px)',
        boxShadow: '0 4px 32px rgba(0,0,0,0.3), inset 0 1px 0 rgba(255,255,255,0.08)',
      }}
      onClick={onClick}
    >
      {children}
    </div>
  );
}
```

---

## FILE 19 — `src/components/ui/Badge.tsx`

```tsx
import React from 'react';

interface BadgeProps {
  children: React.ReactNode;
  color?: 'excel' | 'sql' | 'default';
}

const colorMap: Record<string, string> = {
  excel: 'bg-cyan-500/20 text-cyan-300 border-cyan-500/30',
  sql: 'bg-emerald-500/20 text-emerald-300 border-emerald-500/30',
  default: 'bg-white/10 text-white/70 border-white/20',
};

export function Badge({ children, color = 'default' }: BadgeProps) {
  return (
    <span className={`inline-flex px-2.5 py-0.5 rounded-full text-xs font-semibold border ${colorMap[color]}`}>
      {children}
    </span>
  );
}
```

---

## FILE 20 — `src/components/sections/HeroSection.tsx`

```tsx
import { useState, useEffect } from 'react';
import { GlassCard } from '../ui/GlassCard';
import { NavSection } from '../../types';

interface HeroSectionProps {
  setActive: (s: NavSection) => void;
}

const TECH_STACK = ['Microsoft Excel', 'Google Sheets', 'SQL Server', 'PostgreSQL', 'MySQL', 'Power BI'];

export function HeroSection({ setActive }: HeroSectionProps) {
  const [counter, setCounter] = useState({ students: 0, lessons: 0, companies: 0 });

  useEffect(() => {
    const targets = { students: 12400, lessons: 340, companies: 280 };
    const duration = 1800;
    const steps = 60;
    let step = 0;
    const timer = setInterval(() => {
      step++;
      const p = step / steps;
      const ease = 1 - Math.pow(1 - p, 3);
      setCounter({
        students: Math.floor(targets.students * ease),
        lessons: Math.floor(targets.lessons * ease),
        companies: Math.floor(targets.companies * ease),
      });
      if (step >= steps) clearInterval(timer);
    }, duration / steps);
    return () => clearInterval(timer);
  }, []);

  const stats = [
    { label: 'Students enrolled', value: counter.students.toLocaleString() + '+' },
    { label: 'Lessons & exercises', value: counter.lessons + '+' },
    { label: 'Hiring companies', value: counter.companies + '+' },
  ];

  return (
    <section className="relative min-h-screen flex flex-col items-center justify-center px-4 pt-16 overflow-hidden">
      {/* Ambient orbs */}
      <div className="absolute inset-0 pointer-events-none">
        <div
          className="absolute w-[600px] h-[600px] rounded-full opacity-20"
          style={{
            background: 'radial-gradient(circle, #22d3ee 0%, transparent 70%)',
            top: '-10%', left: '-10%',
            filter: 'blur(80px)',
          }}
        />
        <div
          className="absolute w-[500px] h-[500px] rounded-full opacity-15"
          style={{
            background: 'radial-gradient(circle, #a78bfa 0%, transparent 70%)',
            bottom: '5%', right: '-5%',
            filter: 'blur(80px)',
          }}
        />
        <div
          className="absolute w-[300px] h-[300px] rounded-full opacity-10"
          style={{
            background: 'radial-gradient(circle, #f472b6 0%, transparent 70%)',
            top: '40%', left: '50%',
            filter: 'blur(60px)',
          }}
        />
        {/* Grid overlay */}
        <div
          className="absolute inset-0 opacity-[0.03]"
          style={{
            backgroundImage: 'linear-gradient(rgba(255,255,255,0.5) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,0.5) 1px, transparent 1px)',
            backgroundSize: '60px 60px',
          }}
        />
      </div>

      <div className="relative z-10 max-w-5xl mx-auto text-center">
        {/* Eyebrow */}
        <div className="inline-flex items-center gap-2 px-4 py-2 rounded-full border border-cyan-500/30 bg-cyan-500/10 text-cyan-300 text-sm font-medium mb-8">
          <span className="w-2 h-2 rounded-full bg-cyan-400 animate-pulse" />
          Learn Excel & SQL · Land Your Dream Data Job
        </div>

        {/* Headline */}
        <h1 className="text-5xl sm:text-6xl md:text-7xl font-black text-white leading-[0.95] tracking-tight mb-6">
          Master{' '}
          <span
            style={{
              background: 'linear-gradient(90deg, #22d3ee, #a78bfa)',
              WebkitBackgroundClip: 'text',
              WebkitTextFillColor: 'transparent',
              backgroundClip: 'text',
            }}
          >
            Excel & SQL
          </span>
          <br />
          <span className="text-white/60 text-4xl sm:text-5xl md:text-6xl font-light">
            from zero to hired.
          </span>
        </h1>

        <p className="text-white/50 text-lg sm:text-xl max-w-2xl mx-auto mb-10 leading-relaxed">
          Structured roadmaps, real interview prep, and adaptive quizzes — everything you need to go from spreadsheet novice to data analyst.
        </p>

        {/* CTAs */}
        <div className="flex flex-col sm:flex-row items-center justify-center gap-4 mb-16">
          <button
            onClick={() => setActive('Roadmap')}
            className="px-8 py-4 rounded-2xl font-bold text-white text-base transition-all duration-200 hover:scale-105 hover:shadow-xl"
            style={{
              background: 'linear-gradient(135deg, #22d3ee, #a78bfa)',
              boxShadow: '0 4px 32px rgba(34,211,238,0.35)',
            }}
          >
            Start Learning →
          </button>
          <button
            onClick={() => setActive('Quiz')}
            className="px-8 py-4 rounded-2xl font-bold text-white/80 text-base border border-white/15 hover:border-white/30 hover:text-white hover:bg-white/5 transition-all duration-200"
          >
            Take Free Quiz
          </button>
        </div>

        {/* Stats */}
        <div className="grid grid-cols-3 gap-4 sm:gap-8 max-w-2xl mx-auto">
          {stats.map((stat) => (
            <GlassCard key={stat.label} className="p-4 sm:p-6">
              <div className="text-2xl sm:text-3xl font-black text-white mb-1">{stat.value}</div>
              <div className="text-white/40 text-xs sm:text-sm">{stat.label}</div>
            </GlassCard>
          ))}
        </div>

        {/* Tech pills */}
        <div className="mt-12 flex flex-wrap justify-center gap-2">
          {TECH_STACK.map((t) => (
            <span
              key={t}
              className="px-3 py-1.5 rounded-lg text-xs text-white/40 border border-white/8"
              style={{ background: 'rgba(255,255,255,0.03)' }}
            >
              {t}
            </span>
          ))}
        </div>
      </div>
    </section>
  );
}
```

---

## FILE 21 — `src/components/sections/RoadmapSection.tsx`

```tsx
import { useState } from 'react';
import { GlassCard } from '../ui/GlassCard';
import { EXCEL_ROADMAP, SQL_ROADMAP } from '../../data/roadmaps';

export function RoadmapSection() {
  const [tab, setTab] = useState<'excel' | 'sql'>('excel');
  const data = tab === 'excel' ? EXCEL_ROADMAP : SQL_ROADMAP;

  return (
    <section className="px-4 py-20 max-w-7xl mx-auto">
      <div className="text-center mb-12">
        <p className="text-white/40 text-sm uppercase tracking-widest font-semibold mb-3">Structured Learning</p>
        <h2 className="text-4xl sm:text-5xl font-black text-white mb-4">Your Learning Roadmap</h2>
        <p className="text-white/50 text-lg max-w-xl mx-auto">
          Follow a proven path from foundations to expert-level skills, one milestone at a time.
        </p>
      </div>

      {/* Tab toggle */}
      <div className="flex justify-center mb-10">
        <div
          className="flex rounded-2xl p-1 border border-white/10"
          style={{ background: 'rgba(255,255,255,0.04)' }}
        >
          {(['excel', 'sql'] as const).map((t) => (
            <button
              key={t}
              onClick={() => setTab(t)}
              className={`px-8 py-2.5 rounded-xl font-bold text-sm transition-all duration-200 ${
                tab === t ? 'text-white' : 'text-white/40 hover:text-white/60'
              }`}
              style={
                tab === t
                  ? { background: 'rgba(255,255,255,0.1)', border: '1px solid rgba(255,255,255,0.15)' }
                  : {}
              }
            >
              {t === 'excel' ? '📊 Excel' : '🗄️ SQL'}
            </button>
          ))}
        </div>
      </div>

      <div className="space-y-6">
        {data.map((phase, pi) => (
          <GlassCard key={phase.phase} className="p-6 sm:p-8">
            <div className="flex items-center gap-3 mb-6">
              <div
                className="w-3 h-3 rounded-full"
                style={{ background: phase.color, boxShadow: `0 0 12px ${phase.color}` }}
              />
              <h3 className="text-lg font-bold text-white">{phase.phase}</h3>
              <div className="flex-1 h-px bg-white/8" />
              <span className="text-xs text-white/30 font-medium">Phase {pi + 1}</span>
            </div>
            <div className="grid sm:grid-cols-3 gap-4">
              {phase.topics.map((topic) => (
                <div
                  key={topic.title}
                  className="rounded-xl p-4 border transition-all duration-200 hover:border-white/20 cursor-pointer group"
                  style={{
                    background: topic.done ? `${phase.color}15` : 'rgba(255,255,255,0.03)',
                    borderColor: topic.done ? `${phase.color}40` : 'rgba(255,255,255,0.08)',
                  }}
                >
                  <div className="flex items-start justify-between mb-2">
                    <h4 className="font-semibold text-white text-sm group-hover:text-white/90">{topic.title}</h4>
                    {topic.done ? (
                      <span
                        className="ml-2 mt-0.5 w-5 h-5 rounded-full flex items-center justify-center flex-shrink-0"
                        style={{ background: phase.color }}
                      >
                        <svg width="10" height="8" viewBox="0 0 10 8" fill="none">
                          <path d="M1 4l2.5 2.5L9 1" stroke="#000" strokeWidth="1.8" strokeLinecap="round" />
                        </svg>
                      </span>
                    ) : (
                      <span className="ml-2 mt-0.5 w-5 h-5 rounded-full border border-white/20 flex-shrink-0" />
                    )}
                  </div>
                  <p className="text-white/40 text-xs leading-relaxed">{topic.desc}</p>
                </div>
              ))}
            </div>
          </GlassCard>
        ))}
      </div>
    </section>
  );
}
```

---

## FILE 22 — `src/components/sections/QuizSection.tsx`

```tsx
import { useState } from 'react';
import { GlassCard } from '../ui/GlassCard';
import { Badge } from '../ui/Badge';
import { QUIZ_QUESTIONS } from '../../data/quiz';

interface AnswerRecord {
  correct: boolean;
  chosen: number;
  answer: number;
}

export function QuizSection() {
  const [qi, setQi] = useState(0);
  const [selected, setSelected] = useState<number | null>(null);
  const [score, setScore] = useState(0);
  const [done, setDone] = useState(false);
  const [answers, setAnswers] = useState<AnswerRecord[]>([]);

  const q = QUIZ_QUESTIONS[qi];
  const total = QUIZ_QUESTIONS.length;

  const choose = (idx: number) => {
    if (selected !== null) return;
    setSelected(idx);
    const correct = idx === q.answer;
    if (correct) setScore((s) => s + 1);
    setAnswers((a) => [...a, { correct, chosen: idx, answer: q.answer }]);
  };

  const next = () => {
    if (qi + 1 >= total) {
      setDone(true);
    } else {
      setQi((i) => i + 1);
      setSelected(null);
    }
  };

  const restart = () => {
    setQi(0);
    setSelected(null);
    setScore(0);
    setDone(false);
    setAnswers([]);
  };

  const pct = Math.round((score / total) * 100);

  if (done) {
    return (
      <section className="px-4 py-20 max-w-3xl mx-auto">
        <div className="text-center mb-12">
          <p className="text-white/40 text-sm uppercase tracking-widest font-semibold mb-3">Results</p>
          <h2 className="text-4xl sm:text-5xl font-black text-white mb-4">Quiz Complete!</h2>
        </div>
        <GlassCard className="p-8 sm:p-12 text-center">
          <div
            className="w-36 h-36 rounded-full mx-auto mb-6 flex items-center justify-center text-4xl font-black text-white relative"
            style={{
              background: `conic-gradient(${pct > 70 ? '#22d3ee' : pct > 40 ? '#fb923c' : '#f43f5e'} ${pct * 3.6}deg, rgba(255,255,255,0.08) 0)`,
            }}
          >
            <div className="w-24 h-24 rounded-full flex items-center justify-center" style={{ background: '#080b14' }}>
              <span>{pct}%</span>
            </div>
          </div>
          <h3 className="text-2xl font-bold text-white mb-2">{score} / {total} correct</h3>
          <p className="text-white/50 mb-8">
            {pct >= 80 ? '🎉 Outstanding! You\'re ready to interview.'
              : pct >= 50 ? '👍 Good effort! Review the topics and try again.'
              : '💪 Keep practicing — you\'ve got this.'}
          </p>
          <div className="flex gap-2 justify-center mb-8">
            {answers.map((a, i) => (
              <div key={i} className="h-2 w-8 rounded-full" style={{ background: a.correct ? '#22d3ee' : '#f43f5e' }} />
            ))}
          </div>
          <button
            onClick={restart}
            className="px-8 py-3.5 rounded-2xl font-bold text-white transition-all hover:scale-105"
            style={{ background: 'linear-gradient(135deg, #22d3ee, #a78bfa)' }}
          >
            Retake Quiz
          </button>
        </GlassCard>
      </section>
    );
  }

  return (
    <section className="px-4 py-20 max-w-3xl mx-auto">
      <div className="text-center mb-12">
        <p className="text-white/40 text-sm uppercase tracking-widest font-semibold mb-3">Test Your Knowledge</p>
        <h2 className="text-4xl sm:text-5xl font-black text-white mb-4">Interactive Quiz</h2>
        <p className="text-white/50 text-lg">{total} questions across Excel & SQL. No time limit.</p>
      </div>

      <GlassCard className="p-6 sm:p-10">
        <div className="flex items-center justify-between mb-6">
          <div className="flex gap-1.5">
            {QUIZ_QUESTIONS.map((_, i) => (
              <div
                key={i}
                className="h-1.5 w-8 rounded-full transition-all duration-300"
                style={{
                  background: i < qi ? '#22d3ee' : i === qi ? '#a78bfa' : 'rgba(255,255,255,0.1)',
                }}
              />
            ))}
          </div>
          <div className="flex items-center gap-2">
            <Badge color={q.category.toLowerCase() === 'excel' ? 'excel' : 'sql'}>{q.category}</Badge>
            <span className="text-white/30 text-sm">{qi + 1}/{total}</span>
          </div>
        </div>

        <h3 className="text-xl sm:text-2xl font-bold text-white mb-8 leading-relaxed">{q.question}</h3>

        <div className="space-y-3 mb-6">
          {q.options.map((opt, i) => {
            let classes = 'border-white/10 bg-white/3 text-white/70 hover:border-white/25 hover:text-white';
            if (selected !== null) {
              if (i === q.answer) classes = 'border-cyan-400/60 bg-cyan-400/10 text-cyan-300';
              else if (i === selected && selected !== q.answer) classes = 'border-red-400/60 bg-red-400/10 text-red-300';
              else classes = 'border-white/6 bg-white/2 text-white/30';
            }
            return (
              <button
                key={i}
                onClick={() => choose(i)}
                className={`w-full text-left px-5 py-4 rounded-xl border font-medium text-sm transition-all duration-200 ${classes}`}
              >
                <span className="mr-3 text-white/30">{String.fromCharCode(65 + i)}.</span>
                {opt}
              </button>
            );
          })}
        </div>

        {selected !== null && (
          <div className="rounded-xl p-4 mb-6 border border-white/10 bg-white/3">
            <p className="text-white/60 text-sm leading-relaxed">
              <span className="text-white font-semibold">Explanation: </span>
              {q.explanation}
            </p>
          </div>
        )}

        <div className="flex justify-between items-center">
          <span className="text-white/30 text-sm">Score: {score}/{qi}</span>
          <button
            onClick={next}
            disabled={selected === null}
            className="px-6 py-2.5 rounded-xl font-bold text-sm text-white transition-all duration-200 disabled:opacity-30 disabled:cursor-not-allowed hover:scale-105"
            style={{ background: 'linear-gradient(135deg, #22d3ee, #a78bfa)' }}
          >
            {qi + 1 === total ? 'See Results' : 'Next →'}
          </button>
        </div>
      </GlassCard>
    </section>
  );
}
```

---

## FILE 23 — `src/components/sections/ProgressSection.tsx`

```tsx
import { useState } from 'react';
import { GlassCard } from '../ui/GlassCard';
import { Badge } from '../ui/Badge';
import { EXCEL_ROADMAP, SQL_ROADMAP } from '../../data/roadmaps';
import { TrackedTopic } from '../../types';

function buildTopics(): TrackedTopic[] {
  return [
    ...EXCEL_ROADMAP.flatMap((p) =>
      p.topics.map((t) => ({ ...t, phase: p.phase, track: 'Excel', color: p.color }))
    ),
    ...SQL_ROADMAP.flatMap((p) =>
      p.topics.map((t) => ({ ...t, phase: p.phase, track: 'SQL', color: p.color }))
    ),
  ];
}

interface CircleProgressProps {
  val: number;
  max: number;
  color: string;
  label: string;
}

function CircleProgress({ val, max, color, label }: CircleProgressProps) {
  const pct = max ? (val / max) * 100 : 0;
  const r = 38;
  const circ = 2 * Math.PI * r;
  const dash = (pct / 100) * circ;

  return (
    <div className="flex flex-col items-center gap-2">
      <svg width="100" height="100" viewBox="0 0 100 100">
        <circle cx="50" cy="50" r={r} fill="none" stroke="rgba(255,255,255,0.07)" strokeWidth="8" />
        <circle
          cx="50" cy="50" r={r} fill="none" stroke={color} strokeWidth="8"
          strokeDasharray={`${dash} ${circ}`}
          strokeLinecap="round"
          transform="rotate(-90 50 50)"
          style={{ filter: `drop-shadow(0 0 6px ${color})`, transition: 'stroke-dasharray 0.8s ease' }}
        />
        <text x="50" y="50" textAnchor="middle" dy="0.35em" fill="white" fontSize="18" fontWeight="800">
          {val}
        </text>
      </svg>
      <span className="text-white/50 text-xs text-center">{label}</span>
    </div>
  );
}

export function ProgressSection() {
  // ⚠️ Known issue: state not persisted — add localStorage here (see handover section 29)
  const [topics, setTopics] = useState<TrackedTopic[]>(buildTopics);
  const [filter, setFilter] = useState<'All' | 'Excel' | 'SQL'>('All');

  const toggle = (title: string) => {
    setTopics((prev) => prev.map((t) => (t.title === title ? { ...t, done: !t.done } : t)));
  };

  const excelTopics = topics.filter((t) => t.track === 'Excel');
  const sqlTopics = topics.filter((t) => t.track === 'SQL');
  const excelDone = excelTopics.filter((t) => t.done).length;
  const sqlDone = sqlTopics.filter((t) => t.done).length;
  const totalDone = topics.filter((t) => t.done).length;
  const filtered = filter === 'All' ? topics : topics.filter((t) => t.track === filter);

  return (
    <section className="px-4 py-20 max-w-7xl mx-auto">
      <div className="text-center mb-12">
        <p className="text-white/40 text-sm uppercase tracking-widest font-semibold mb-3">Track Your Journey</p>
        <h2 className="text-4xl sm:text-5xl font-black text-white mb-4">Progress Tracker</h2>
        <p className="text-white/50 text-lg max-w-xl mx-auto">Mark topics as complete and watch your skills grow.</p>
      </div>

      {/* Overview cards */}
      <div className="grid grid-cols-1 sm:grid-cols-3 gap-4 mb-10">
        <GlassCard className="p-6 flex items-center gap-6">
          <CircleProgress val={excelDone} max={excelTopics.length} color="#22d3ee" label="Excel complete" />
          <div>
            <p className="text-white/40 text-xs mb-1 uppercase tracking-wider">Excel</p>
            <p className="text-2xl font-black text-white">{excelDone}/{excelTopics.length}</p>
            <p className="text-white/40 text-sm">topics done</p>
          </div>
        </GlassCard>

        <GlassCard className="p-6 flex items-center gap-6">
          <CircleProgress val={sqlDone} max={sqlTopics.length} color="#34d399" label="SQL complete" />
          <div>
            <p className="text-white/40 text-xs mb-1 uppercase tracking-wider">SQL</p>
            <p className="text-2xl font-black text-white">{sqlDone}/{sqlTopics.length}</p>
            <p className="text-white/40 text-sm">topics done</p>
          </div>
        </GlassCard>

        <GlassCard className="p-6 flex flex-col justify-center gap-2">
          <p className="text-white/40 text-xs uppercase tracking-wider">Overall Progress</p>
          <p className="text-3xl font-black text-white">{totalDone}/{topics.length}</p>
          <div className="w-full h-2 rounded-full overflow-hidden" style={{ background: 'rgba(255,255,255,0.08)' }}>
            <div
              className="h-full rounded-full transition-all duration-700"
              style={{ width: `${(totalDone / topics.length) * 100}%`, background: 'linear-gradient(90deg, #22d3ee, #a78bfa)' }}
            />
          </div>
          <p className="text-white/40 text-sm">{Math.round((totalDone / topics.length) * 100)}% complete</p>
        </GlassCard>
      </div>

      {/* Filter */}
      <div className="flex gap-2 mb-6">
        {(['All', 'Excel', 'SQL'] as const).map((f) => (
          <button
            key={f}
            onClick={() => setFilter(f)}
            className={`px-4 py-2 rounded-xl text-sm font-medium border transition-all ${
              filter === f ? 'text-white border-white/20 bg-white/10' : 'text-white/40 border-white/8 hover:text-white/60'
            }`}
          >
            {f}
          </button>
        ))}
      </div>

      {/* Checklist */}
      <div className="grid sm:grid-cols-2 gap-3">
        {filtered.map((topic) => (
          <button
            key={topic.title}
            onClick={() => toggle(topic.title)}
            className="flex items-start gap-4 p-4 rounded-xl border text-left transition-all duration-200 hover:border-white/20"
            style={{
              background: topic.done ? `${topic.color}10` : 'rgba(255,255,255,0.03)',
              borderColor: topic.done ? `${topic.color}35` : 'rgba(255,255,255,0.08)',
            }}
          >
            <div
              className="w-6 h-6 rounded-md flex items-center justify-center flex-shrink-0 mt-0.5 transition-all"
              style={{
                background: topic.done ? topic.color : 'rgba(255,255,255,0.08)',
                border: topic.done ? 'none' : '1px solid rgba(255,255,255,0.15)',
              }}
            >
              {topic.done && (
                <svg width="12" height="10" viewBox="0 0 12 10" fill="none">
                  <path d="M1 5l3 3L11 1" stroke="#000" strokeWidth="2" strokeLinecap="round" />
                </svg>
              )}
            </div>
            <div className="flex-1 min-w-0">
              <div className="flex items-center gap-2 mb-0.5">
                <span className="font-semibold text-white text-sm truncate">{topic.title}</span>
                <Badge color={topic.track.toLowerCase() as 'excel' | 'sql'}>{topic.track}</Badge>
              </div>
              <p className="text-white/35 text-xs">{topic.phase} · {topic.desc}</p>
            </div>
          </button>
        ))}
      </div>
    </section>
  );
}
```

---

## FILE 24 — `src/components/sections/InterviewSection.tsx`

```tsx
import { useState } from 'react';
import { GlassCard } from '../ui/GlassCard';
import { Badge } from '../ui/Badge';
import { INTERVIEW_QS } from '../../data/interview';

export function InterviewSection() {
  const [open, setOpen] = useState<number | null>(null);
  const [filter, setFilter] = useState<'All' | 'Excel' | 'SQL'>('All');

  const filtered = filter === 'All' ? INTERVIEW_QS : INTERVIEW_QS.filter((q) => q.cat === filter);

  return (
    <section className="px-4 py-20 max-w-4xl mx-auto">
      <div className="text-center mb-12">
        <p className="text-white/40 text-sm uppercase tracking-widest font-semibold mb-3">Ace the Interview</p>
        <h2 className="text-4xl sm:text-5xl font-black text-white mb-4">Interview Questions</h2>
        <p className="text-white/50 text-lg max-w-xl mx-auto">
          Real questions asked by top companies. Click to reveal model answers.
        </p>
      </div>

      {/* Filter */}
      <div className="flex gap-2 mb-8 justify-center">
        {(['All', 'Excel', 'SQL'] as const).map((f) => (
          <button
            key={f}
            onClick={() => setFilter(f)}
            className={`px-5 py-2 rounded-xl text-sm font-medium border transition-all ${
              filter === f ? 'text-white border-white/20 bg-white/10' : 'text-white/40 border-white/8 hover:text-white/60'
            }`}
          >
            {f}
          </button>
        ))}
      </div>

      {/* Accordion */}
      <div className="space-y-3">
        {filtered.map((item, i) => (
          <GlassCard key={item.q} className="overflow-hidden">
            <button
              onClick={() => setOpen(open === i ? null : i)}
              className="w-full flex items-center gap-4 p-5 text-left hover:bg-white/3 transition-all"
            >
              <span className="text-2xl">{item.icon}</span>
              <div className="flex-1 min-w-0">
                <div className="flex items-center gap-2 mb-1">
                  <Badge color={item.cat.toLowerCase() as 'excel' | 'sql'}>{item.cat}</Badge>
                </div>
                <p className="font-semibold text-white text-sm sm:text-base">{item.q}</p>
              </div>
              <span
                className="text-white/40 flex-shrink-0 w-6 h-6 rounded-full border border-white/15 flex items-center justify-center text-xs transition-transform duration-200"
                style={{ transform: open === i ? 'rotate(180deg)' : 'none' }}
              >
                ↓
              </span>
            </button>
            {open === i && (
              <div className="px-5 pb-5 pt-1">
                <div className="rounded-xl p-4 border border-white/8 bg-white/3">
                  <p className="text-white/70 text-sm leading-relaxed">{item.a}</p>
                </div>
              </div>
            )}
          </GlassCard>
        ))}
      </div>

      {/* Bottom CTA — ⚠️ Known issue: buttons have no onClick handlers yet */}
      <div className="mt-12">
        <GlassCard className="p-8 sm:p-12 text-center">
          <h3 className="text-2xl sm:text-3xl font-black text-white mb-3">Ready to get hired?</h3>
          <p className="text-white/50 mb-6">Complete your roadmap, ace the quiz, and walk into interviews with confidence.</p>
          <div className="flex flex-col sm:flex-row gap-3 justify-center">
            <button
              className="px-7 py-3.5 rounded-2xl font-bold text-white text-sm transition-all hover:scale-105"
              style={{ background: 'linear-gradient(135deg, #22d3ee, #a78bfa)', boxShadow: '0 4px 20px rgba(34,211,238,0.25)' }}
            >
              View Full Roadmap
            </button>
            <button className="px-7 py-3.5 rounded-2xl font-bold text-white/70 text-sm border border-white/15 hover:text-white hover:bg-white/5 transition-all">
              Practice More Quizzes
            </button>
          </div>
        </GlassCard>
      </div>
    </section>
  );
}
```

---

## FILE 25 — `src/data/roadmaps.ts`

```typescript
import { Phase } from '../types';

export const EXCEL_ROADMAP: Phase[] = [
  {
    phase: 'Foundation',
    color: '#22d3ee',
    topics: [
      { title: 'Interface & Navigation', done: true, desc: 'Ribbons, cells, rows, columns, named ranges' },
      { title: 'Formulas & Functions', done: true, desc: 'SUM, AVERAGE, IF, COUNTIF, VLOOKUP' },
      { title: 'Data Formatting', done: false, desc: 'Number formats, conditional formatting, styles' },
    ],
  },
  {
    phase: 'Intermediate',
    color: '#a78bfa',
    topics: [
      { title: 'PivotTables', done: false, desc: 'Aggregation, slicers, calculated fields' },
      { title: 'Charts & Dashboards', done: false, desc: 'Dynamic charts, sparklines, KPI cards' },
      { title: 'Advanced Formulas', done: false, desc: 'INDEX/MATCH, XLOOKUP, array formulas' },
    ],
  },
  {
    phase: 'Advanced',
    color: '#f472b6',
    topics: [
      { title: 'Power Query', done: false, desc: 'ETL, M language, data transformations' },
      { title: 'Power Pivot & DAX', done: false, desc: 'Data models, measures, KPIs' },
      { title: 'VBA & Macros', done: false, desc: 'Automation, custom functions, event triggers' },
    ],
  },
];

export const SQL_ROADMAP: Phase[] = [
  {
    phase: 'Core SQL',
    color: '#34d399',
    topics: [
      { title: 'SELECT & Filtering', done: true, desc: 'WHERE, LIKE, IN, BETWEEN, NULL handling' },
      { title: 'Joins', done: true, desc: 'INNER, LEFT, RIGHT, FULL OUTER, CROSS joins' },
      { title: 'Aggregation', done: false, desc: 'GROUP BY, HAVING, aggregate functions' },
    ],
  },
  {
    phase: 'Intermediate SQL',
    color: '#fb923c',
    topics: [
      { title: 'Subqueries & CTEs', done: false, desc: 'Correlated subqueries, WITH clause, recursion' },
      { title: 'Window Functions', done: false, desc: 'ROW_NUMBER, RANK, LAG, LEAD, PARTITION BY' },
      { title: 'Data Manipulation', done: false, desc: 'INSERT, UPDATE, DELETE, UPSERT patterns' },
    ],
  },
  {
    phase: 'Expert SQL',
    color: '#f43f5e',
    topics: [
      { title: 'Query Optimization', done: false, desc: 'Indexes, execution plans, query hints' },
      { title: 'Stored Procedures', done: false, desc: 'Variables, control flow, error handling' },
      { title: 'Database Design', done: false, desc: 'Normalization, ERD, constraints, transactions' },
    ],
  },
];
```

---

## FILE 26 — `src/data/quiz.ts`

```typescript
import { QuizQuestion } from '../types';

export const QUIZ_QUESTIONS: QuizQuestion[] = [
  {
    id: 1,
    category: 'Excel',
    question: 'Which Excel function returns the position of a value in a range?',
    options: ['VLOOKUP', 'MATCH', 'INDEX', 'OFFSET'],
    answer: 1,
    explanation: 'MATCH returns the relative position of a lookup value in a one-dimensional range.',
  },
  {
    id: 2,
    category: 'SQL',
    question: 'Which clause filters results AFTER aggregation?',
    options: ['WHERE', 'FILTER', 'HAVING', 'GROUP BY'],
    answer: 2,
    explanation: 'HAVING filters grouped rows, while WHERE filters individual rows before grouping.',
  },
  {
    id: 3,
    category: 'Excel',
    question: 'What does the $ symbol do in a cell reference like $A$1?',
    options: ['Formats as currency', 'Creates absolute reference', 'Names the cell', 'Links to another sheet'],
    answer: 1,
    explanation: '$A$1 is an absolute reference — it won\'t shift when the formula is copied.',
  },
  {
    id: 4,
    category: 'SQL',
    question: 'Which window function assigns a unique sequential integer to rows?',
    options: ['RANK()', 'DENSE_RANK()', 'ROW_NUMBER()', 'NTILE()'],
    answer: 2,
    explanation: 'ROW_NUMBER() always assigns unique integers, even to tied values.',
  },
  {
    id: 5,
    category: 'Excel',
    question: 'Power Query is used primarily for what purpose?',
    options: ['Creating charts', 'Running macros', 'ETL and data transformation', 'Formatting cells'],
    answer: 2,
    explanation: 'Power Query is Excel\'s ETL tool — Extract, Transform, Load — for shaping data.',
  },
  {
    id: 6,
    category: 'SQL',
    question: 'What is the correct order of SQL clauses in a SELECT statement?',
    options: [
      'SELECT → WHERE → FROM → GROUP BY → HAVING',
      'FROM → WHERE → SELECT → GROUP BY → HAVING',
      'SELECT → FROM → WHERE → GROUP BY → HAVING',
      'FROM → SELECT → WHERE → HAVING → GROUP BY',
    ],
    answer: 2,
    explanation: 'The logical order is SELECT → FROM → WHERE → GROUP BY → HAVING → ORDER BY.',
  },
  {
    id: 7,
    category: 'Excel',
    question: 'Which function combines the functionality of VLOOKUP and HLOOKUP?',
    options: ['INDEX', 'XLOOKUP', 'INDIRECT', 'CHOOSE'],
    answer: 1,
    explanation: 'XLOOKUP (Excel 365+) can search both rows and columns, returning arrays — it replaces both VLOOKUP and HLOOKUP.',
  },
  {
    id: 8,
    category: 'SQL',
    question: 'What does a LEFT JOIN return?',
    options: [
      'Only matching rows from both tables',
      'All rows from the right table plus matches',
      'All rows from the left table plus matching rows from the right',
      'All rows from both tables regardless of matches',
    ],
    answer: 2,
    explanation: 'LEFT JOIN returns every row from the left table; unmatched right-side columns are NULL.',
  },
];
```

---

## FILE 27 — `src/data/interview.ts`

```typescript
import { InterviewQuestion } from '../types';

export const INTERVIEW_QS: InterviewQuestion[] = [
  {
    cat: 'Excel',
    q: 'Explain the difference between VLOOKUP and INDEX/MATCH.',
    a: 'VLOOKUP only looks right and requires column numbers that break when columns are inserted. INDEX/MATCH is more flexible — it can look left, handles column insertions gracefully, and is generally faster on large datasets because INDEX/MATCH only searches one column.',
    icon: '📊',
  },
  {
    cat: 'SQL',
    q: 'What is the difference between DELETE, TRUNCATE, and DROP?',
    a: 'DELETE removes specific rows with a WHERE clause and can be rolled back (it\'s DML). TRUNCATE removes all rows faster without logging individual deletions, resets identity columns, but cannot be filtered. DROP removes the entire table structure and all its data permanently (DDL).',
    icon: '🗄️',
  },
  {
    cat: 'Excel',
    q: 'How would you build a dynamic dashboard in Excel?',
    a: 'Use PivotTables as data sources with structured table references, connect slicers across multiple pivots using Report Connections, use named ranges or OFFSET/COUNTA for dynamic chart ranges, and add form controls or dropdown validation to drive parameters. Power Query handles data refresh automation.',
    icon: '📈',
  },
  {
    cat: 'SQL',
    q: 'When would you use a CTE over a subquery?',
    a: 'CTEs improve readability and maintainability for complex multi-step logic, enable recursive queries (like hierarchy traversal), and can be referenced multiple times in a single statement without re-execution in some engines. Subqueries are fine for simple, one-off filtering but become hard to read when nested.',
    icon: '🔍',
  },
  {
    cat: 'SQL',
    q: 'Explain how indexes affect query performance.',
    a: 'Indexes speed up SELECT queries by allowing the engine to locate rows via a B-tree structure without full table scans. However, they slow INSERT/UPDATE/DELETE because the index must be maintained on every write. Use indexes on frequently filtered or joined columns, but avoid over-indexing write-heavy tables.',
    icon: '⚡',
  },
  {
    cat: 'Excel',
    q: 'What is DAX and when would you use it over regular Excel formulas?',
    a: 'DAX (Data Analysis Expressions) is used in Power Pivot and Power BI to create measures and calculated columns over relational data models. Use DAX when your dataset exceeds Excel\'s row limit, when you need relationships between multiple tables, or when you require time intelligence functions like TOTALYTD or SAMEPERIODLASTYEAR.',
    icon: '🧮',
  },
  {
    cat: 'SQL',
    q: 'What are window functions and when do you use them?',
    a: 'Window functions (OVER clause) perform calculations across a set of rows related to the current row without collapsing them into groups. Use them for running totals, moving averages, rankings within categories (RANK, DENSE_RANK), and row-over-row comparisons (LAG/LEAD) — scenarios where GROUP BY would lose row-level detail.',
    icon: '🪟',
  },
  {
    cat: 'Excel',
    q: 'How do you handle large datasets in Excel efficiently?',
    a: 'Use structured Tables (Ctrl+T) instead of plain ranges for dynamic references, load data via Power Query to avoid holding millions of rows in the grid, use Power Pivot\'s columnar store for aggregations, avoid volatile functions like OFFSET and INDIRECT in large models, and turn off automatic calculation during bulk operations.',
    icon: '🚀',
  },
];
```

---

## FILE 28 — `src/data/lessons.ts`
### ⚠️ LARGEST FILE (1,368 lines) — Contains ALL lesson content for the Learn section

```typescript
export interface Exercise {
  prompt: string;
  hint: string;
  answer: string;
}

export interface LessonQuiz {
  question: string;
  options: string[];
  answer: number;
  explanation: string;
}

export interface Lesson {
  id: string;
  title: string;
  duration: string;
  difficulty: 'Beginner' | 'Intermediate' | 'Advanced';
  summary: string;
  objectives: string[];
  explanation: string;
  syntaxBlock?: string;
  examples: { title: string; code: string; description: string }[];
  exercises: Exercise[];
  quiz: LessonQuiz[];
  tags: string[];
}

export interface LessonModule {
  id: string;
  title: string;
  icon: string;
  color: string;
  track: 'Excel' | 'SQL';
  phase: string;
  lessons: Lesson[];
}

// ─── EXCEL MODULES ───────────────────────────────────────────────────────────
export const EXCEL_MODULES: LessonModule[] = [
  {
    id: 'excel-foundation',
    title: 'Excel Foundation',
    icon: '📊',
    color: '#22d3ee',
    track: 'Excel',
    phase: 'Phase 1',
    lessons: [
      {
        id: 'excel-interface',
        title: 'Interface & Navigation',
        duration: '15 min',
        difficulty: 'Beginner',
        summary: 'Learn the Excel interface, ribbon, and how to navigate efficiently.',
        objectives: [
          'Identify key parts of the Excel interface',
          'Navigate cells using keyboard shortcuts',
          'Understand workbooks, worksheets, and cells',
          'Use the Name Box and Formula Bar',
        ],
        explanation: `Excel's interface is built around the concept of a grid — rows (numbered) and columns (lettered) that intersect to form cells. Every cell has a unique address, like A1 or C5.

The **Ribbon** sits at the top and contains tabs (Home, Insert, Formulas, Data, etc.). Each tab groups related commands into sections.

The **Name Box** (left of the formula bar) shows the active cell address. You can type any address there and press Enter to jump directly to that cell.

The **Formula Bar** shows the raw content of the selected cell — useful to see formulas vs displayed values.

**Worksheets** are tabs at the bottom. A workbook can contain many sheets. Right-click a tab to rename, move, copy, or color-code it.

Key navigation shortcuts that professionals use daily:
- **Ctrl + End** — jump to the last used cell
- **Ctrl + Home** — jump to A1
- **Ctrl + Arrow** — jump to end of data in that direction
- **Ctrl + Shift + Arrow** — select to end of data
- **F2** — enter edit mode on current cell`,
        examples: [
          {
            title: 'Cell Reference Styles',
            code: 'A1        → Column A, Row 1 (relative)\n$A$1      → Absolute reference (locked)\n$A1       → Column locked, row relative\nA$1       → Row locked, column relative\nSheet2!A1 → Reference to another sheet',
            description: 'Excel supports four reference types. Absolute references ($) do not shift when a formula is copied.',
          },
          {
            title: 'Navigating with the Name Box',
            code: '1. Click the Name Box (shows current cell like "A1")\n2. Type: C100\n3. Press Enter → jumps to cell C100\n\nTo select a range:\n1. Click the Name Box\n2. Type: A1:D50\n3. Press Enter → selects that entire range',
            description: 'The Name Box is the fastest way to navigate large spreadsheets without scrolling.',
          },
        ],
        exercises: [
          {
            prompt: 'What keyboard shortcut jumps to the last used cell in a worksheet?',
            hint: 'Hold Ctrl and press the End key.',
            answer: 'Ctrl + End',
          },
          {
            prompt: 'Write a cell reference that locks column B but leaves the row flexible.',
            hint: 'Put the $ only before the column letter.',
            answer: '$B1',
          },
          {
            prompt: 'How do you reference cell A1 on a sheet named "Sales"?',
            hint: 'Use the sheet name followed by an exclamation mark.',
            answer: "Sales!A1",
          },
        ],
        quiz: [
          {
            question: 'Which part of the Excel interface shows the raw formula of the selected cell?',
            options: ['The Name Box', 'The Formula Bar', 'The Ribbon', 'The Status Bar'],
            answer: 1,
            explanation: 'The Formula Bar shows the exact content — formula or value — of the active cell.',
          },
          {
            question: 'What does pressing Ctrl + Arrow do?',
            options: [
              'Selects the entire column',
              'Opens a new workbook',
              'Jumps to the last non-empty cell in that direction',
              'Copies the cell',
            ],
            answer: 2,
            explanation: 'Ctrl + Arrow jumps to the boundary of a data region — extremely useful for navigating large datasets.',
          },
          {
            question: 'The reference $C$5 is an example of which type?',
            options: ['Relative reference', 'Mixed reference', 'Absolute reference', 'External reference'],
            answer: 2,
            explanation: 'Both column and row are locked with $, making it absolute — it will not change when copied.',
          },
        ],
        tags: ['interface', 'navigation', 'cells', 'shortcuts', 'ribbon'],
      },
      {
        id: 'excel-formulas',
        title: 'Formulas & Core Functions',
        duration: '25 min',
        difficulty: 'Beginner',
        summary: 'Master essential Excel functions: SUM, AVERAGE, IF, COUNTIF, and VLOOKUP.',
        objectives: [
          'Write formulas using arithmetic operators',
          'Use SUM, AVERAGE, MIN, MAX, COUNT',
          'Apply IF for conditional logic',
          'Use COUNTIF and SUMIF for conditional counting/summing',
          'Build a basic VLOOKUP',
        ],
        explanation: `Every Excel formula starts with an **=** sign. Without it, Excel treats your entry as plain text.

**Arithmetic operators:** + - * / ^ (power) — Excel follows standard order of operations. Use parentheses to control evaluation order.

**SUM** adds all values in a range. It ignores text and empty cells automatically.

**AVERAGE** divides the sum by the count of numeric values. Empty cells and text are excluded.

**IF** is the backbone of conditional logic. It tests a condition: if TRUE, return one value; if FALSE, return another. IFs can be nested (though SWITCH or IFS is cleaner for many conditions).

**COUNTIF** counts cells that match one criterion. **SUMIF** sums cells where a related column meets a criterion.

**VLOOKUP** (Vertical Lookup) searches the first column of a table for a value, then returns a value from a column to the right. The fourth argument (range_lookup) should almost always be FALSE for exact matches.`,
        syntaxBlock: `=SUM(range)
=AVERAGE(range)
=IF(condition, value_if_true, value_if_false)
=COUNTIF(range, criteria)
=SUMIF(range, criteria, sum_range)
=VLOOKUP(lookup_value, table_array, col_index_num, [range_lookup])`,
        examples: [
          {
            title: 'SUM, AVERAGE, MIN, MAX',
            code: '=SUM(B2:B10)          → adds all values in B2 to B10\n=AVERAGE(B2:B10)      → average of the range\n=MIN(B2:B10)          → smallest value\n=MAX(B2:B10)          → largest value\n=COUNT(B2:B10)        → count of numeric cells\n=COUNTA(B2:B10)       → count of non-empty cells',
            description: 'These statistical functions form the foundation of any Excel analysis.',
          },
          {
            title: 'IF with nested logic',
            code: '=IF(A2>=90, "A", IF(A2>=80, "B", IF(A2>=70, "C", "F")))\n\n→ Returns grade letter based on score in A2\n\nAlternative using IFS (Excel 2019+):\n=IFS(A2>=90,"A", A2>=80,"B", A2>=70,"C", TRUE,"F")',
            description: 'Nested IFs handle multiple conditions. IFS() is cleaner for 3+ conditions.',
          },
          {
            title: 'VLOOKUP Example',
            code: 'Table in A1:C10:\n  A: EmployeeID | B: Name | C: Salary\n\n=VLOOKUP(E2, A1:C10, 2, FALSE)  → returns Name\n=VLOOKUP(E2, A1:C10, 3, FALSE)  → returns Salary\n\nAlways use FALSE (exact match) unless doing\napproximate range lookups (like tax brackets).',
            description: 'VLOOKUP searches the leftmost column and returns a value from a column to its right.',
          },
        ],
        exercises: [
          {
            prompt: 'Write a formula to sum values in D2:D100 but only where column C equals "West".',
            hint: 'Use SUMIF with three arguments: range, criteria, sum_range.',
            answer: '=SUMIF(C2:C100,"West",D2:D100)',
          },
          {
            prompt: 'Write an IF formula: if B5 > 1000, return "High", otherwise return "Low".',
            hint: 'IF(condition, true_result, false_result)',
            answer: '=IF(B5>1000,"High","Low")',
          },
          {
            prompt: 'Using VLOOKUP, look up the value in A2 within table H1:J50 and return column 3. Use exact match.',
            hint: 'Fourth argument FALSE means exact match.',
            answer: '=VLOOKUP(A2,H1:J50,3,FALSE)',
          },
        ],
        quiz: [
          {
            question: 'What does COUNTIF(A1:A100, ">500") return?',
            options: [
              'The sum of all values over 500',
              'The count of cells with a value greater than 500',
              'The average of values over 500',
              'An error',
            ],
            answer: 1,
            explanation: 'COUNTIF counts cells meeting a criterion. ">500" is a text-format criterion that counts values greater than 500.',
          },
          {
            question: 'In VLOOKUP, what does the 4th argument FALSE specify?',
            options: [
              'Return FALSE if not found',
              'Exact match lookup',
              'Search from bottom to top',
              'Approximate match',
            ],
            answer: 1,
            explanation: 'FALSE means exact match. Without it (or with TRUE), Excel does an approximate match on sorted data — almost never what you want for IDs or names.',
          },
          {
            question: 'Which formula correctly averages only values greater than 0 in B1:B20?',
            options: [
              '=AVERAGE(IF(B1:B20>0))',
              '=AVERAGEIF(B1:B20,">0")',
              '=AVERAGE(B1:B20,">0")',
              '=SUMIF(B1:B20)/COUNT(B1:B20)',
            ],
            answer: 1,
            explanation: 'AVERAGEIF(range, criteria) averages only cells that meet the condition.',
          },
        ],
        tags: ['SUM', 'AVERAGE', 'IF', 'COUNTIF', 'VLOOKUP', 'formulas', 'functions'],
      },
      {
        id: 'excel-formatting',
        title: 'Data Formatting & Conditional Formatting',
        duration: '20 min',
        difficulty: 'Beginner',
        summary: 'Format cells professionally and highlight data patterns automatically.',
        objectives: [
          'Apply number, currency, date, and percentage formats',
          'Use custom number formats',
          'Apply conditional formatting rules',
          'Create data bars and color scales',
        ],
        explanation: `Formatting controls how values **appear** without changing the underlying data. A cell showing "£1,234.56" might store the number 1234.56 — the format is cosmetic.

**Number formats** available via Ctrl+1 (Format Cells):
- **General** — default, no specific format
- **Number** — decimal places, thousands separator
- **Currency/Accounting** — adds currency symbol
- **Date** — many display options
- **Percentage** — multiplies by 100 and adds %
- **Custom** — write your own format code

**Custom format syntax:** \`[color][condition]format\`
For example: \`0.0"x"\` displays 2.5 as "2.5x"
Or: \`[Green]▲0%;[Red]▼0%\` shows positive in green with up arrow.

**Conditional Formatting** applies formats automatically based on rules — highlights, data bars, color scales, or icon sets. Rules are evaluated in priority order; the first matching rule wins.`,
        syntaxBlock: `Custom Number Formats:
#,##0.00        → 1,234.56
0%              → 75%
"$"#,##0        → $1,235
dd/mm/yyyy      → 25/12/2024
[>100][Green]0;[Red]0   → green if >100, red otherwise`,
        examples: [
          {
            title: 'Common Custom Number Formats',
            code: '0.00         → always 2 decimal places (1.5 → 1.50)\n#,##0        → thousands separator, no decimals\n0.0%         → percentage with 1 decimal\n"Q"0         → Q1, Q2, Q3...\n[h]:mm       → elapsed hours over 24\n+0;-0;0      → explicit + for positives',
            description: 'Custom formats give you precise control over display without changing underlying values.',
          },
          {
            title: 'Conditional Formatting: Highlight Rules',
            code: 'Steps:\n1. Select range B2:B100\n2. Home → Conditional Formatting → Highlight Cell Rules\n3. "Greater Than" → enter 1000 → pick fill color\n\nOr via formula rule:\n1. New Rule → "Use a formula"\n2. Formula: =B2>AVERAGE($B$2:$B$100)\n3. This highlights cells above the average',
            description: 'Formula-based rules give maximum flexibility — reference entire ranges using absolute references.',
          },
        ],
        exercises: [
          {
            prompt: 'Write a custom format that shows positive numbers in green and negative numbers in red.',
            hint: 'Use [Color] codes with a semicolon to separate positive;negative formats.',
            answer: '[Green]0.00;[Red]-0.00',
          },
          {
            prompt: 'What format code displays the number 0.75 as "75.0%"?',
            hint: 'Percentage format multiplies by 100 automatically.',
            answer: '0.0%',
          },
        ],
        quiz: [
          {
            question: 'Applying a currency format to a cell changes the underlying stored value.',
            options: ['True', 'False'],
            answer: 1,
            explanation: 'False. Formatting is purely cosmetic — the underlying numeric value is unchanged. =A1+1 will still use the raw number.',
          },
          {
            question: 'When multiple Conditional Formatting rules apply to the same cell, which one takes priority?',
            options: [
              'The rule that was created first',
              'The rule with the highest numeric value',
              'The rule highest in the rule list',
              'All rules apply simultaneously',
            ],
            answer: 2,
            explanation: 'Rules are evaluated from top to bottom in the Conditional Formatting Rules Manager. The first matching rule wins (unless "Stop if True" is unchecked).',
          },
        ],
        tags: ['formatting', 'conditional formatting', 'number format', 'color scale', 'data bars'],
      },
    ],
  },
  {
    id: 'excel-intermediate',
    title: 'Excel Intermediate',
    icon: '📈',
    color: '#a78bfa',
    track: 'Excel',
    phase: 'Phase 2',
    lessons: [
      {
        id: 'excel-pivottables',
        title: 'PivotTables',
        duration: '30 min',
        difficulty: 'Intermediate',
        summary: 'Summarise and analyse thousands of rows with drag-and-drop PivotTables.',
        objectives: [
          'Create a PivotTable from a data table',
          'Arrange rows, columns, values, and filters',
          'Apply value field settings (Sum, Count, Average, %)',
          'Add slicers for interactive filtering',
          'Create calculated fields',
        ],
        explanation: `A PivotTable is Excel's most powerful analysis tool. It lets you instantly summarise, group, and cross-tabulate large datasets without writing a single formula.

**Data requirements:** Your source data should be in a flat table — one row per record, column headers in row 1, no merged cells, no blank rows.

**Four zones:**
- **Rows** — groups data vertically (e.g., by Region)
- **Columns** — groups data horizontally (e.g., by Quarter)
- **Values** — the numbers being aggregated (Sum, Count, Average, etc.)
- **Filters** — a dropdown that filters the entire PivotTable

**Value Field Settings** control how the value is aggregated and displayed. Right-click a value → "Value Field Settings". Use "Show Values As" for percentages, running totals, rank, etc.

**Slicers** (Insert → Slicer) are visual filter buttons that connect to one or more PivotTables. Use Report Connections to link slicers to multiple pivots on the same dashboard.

**Refresh:** PivotTables do not auto-update. Right-click → Refresh, or use Data → Refresh All.`,
        syntaxBlock: `Calculated Field formula example:
= Revenue - Cost
= [Sales] * [Margin %]
(Reference field names in square brackets)`,
        examples: [
          {
            title: 'Building a PivotTable Step by Step',
            code: 'Source data columns: Date, Region, Product, Revenue, Units\n\n1. Click anywhere in data → Insert → PivotTable\n2. Drag "Region"  → Rows area\n3. Drag "Product" → Columns area\n4. Drag "Revenue" → Values area (auto-sums)\n5. Drag "Date"    → Filters area\n\nResult: Revenue cross-tabulated by Region vs Product\nwith a date filter dropdown at top.',
            description: 'A PivotTable built in under a minute that would take hours to replicate with formulas.',
          },
          {
            title: 'Show Values As: % of Grand Total',
            code: '1. Right-click any value cell in the PivotTable\n2. "Show Values As" → "% of Grand Total"\n\nEach cell now shows its share of the total.\nOther useful options:\n- "% of Row Total"   → share within each row\n- "Difference From"  → variance vs a base item\n- "Running Total In" → cumulative sum\n- "Rank Smallest to Largest"',
            description: 'Show Values As transforms raw numbers into insights without adding a single formula.',
          },
        ],
        exercises: [
          {
            prompt: 'You have sales data with columns: Date, Salesperson, Product, Amount. Describe how to build a PivotTable showing total Amount by Salesperson.',
            hint: 'Salesperson goes in Rows, Amount goes in Values.',
            answer: 'Insert PivotTable → drag Salesperson to Rows → drag Amount to Values (Sum). This gives a total per salesperson.',
          },
          {
            prompt: 'Your PivotTable shows old data after the source was updated. What do you do?',
            hint: 'PivotTables do not refresh automatically.',
            answer: 'Right-click inside the PivotTable → Refresh (or Data → Refresh All).',
          },
        ],
        quiz: [
          {
            question: 'What is the maximum recommended way to keep source data clean for PivotTables?',
            options: [
              'Use merged cells for headers',
              'Format source data as an Excel Table (Ctrl+T)',
              'Leave blank rows between sections',
              'Put totals in the source data',
            ],
            answer: 1,
            explanation: 'Excel Tables auto-expand when new data is added, so your PivotTable source automatically includes new rows after a refresh.',
          },
          {
            question: 'Which PivotTable area would you use to create a column for each product category?',
            options: ['Rows', 'Columns', 'Values', 'Filters'],
            answer: 1,
            explanation: 'Fields in the Columns area create separate columns for each unique value — perfect for cross-tabulation by category.',
          },
        ],
        tags: ['PivotTable', 'pivot', 'summarise', 'slicer', 'calculated field', 'aggregate'],
      },
      {
        id: 'excel-advanced-formulas',
        title: 'Advanced Formulas: INDEX/MATCH & XLOOKUP',
        duration: '35 min',
        difficulty: 'Intermediate',
        summary: 'Replace VLOOKUP with the more powerful INDEX/MATCH and XLOOKUP combinations.',
        objectives: [
          'Understand why INDEX/MATCH beats VLOOKUP',
          'Write INDEX/MATCH for flexible lookups',
          'Use XLOOKUP for modern lookups',
          'Perform two-way lookups',
          'Handle errors with IFERROR and IFNA',
        ],
        explanation: `**VLOOKUP's limitations:**
1. Can only look to the right — the lookup column must be leftmost
2. Column index number breaks when you insert/delete columns
3. Requires the entire table array to be included
4. Marginally slower on huge datasets

**INDEX/MATCH solves all of these:**
- INDEX returns the value at a specific row/column position in an array
- MATCH finds the position (row number) of a lookup value in a range
- Combined: MATCH finds the row, INDEX returns the value from any column

**XLOOKUP** (Excel 365/2021) is the modern replacement for both. It can look left, return multiple columns at once, has a built-in not-found argument, and supports wildcard matching.

**IFERROR / IFNA** wrap any formula to catch errors and return a custom message or blank instead of #N/A or #VALUE!.`,
        syntaxBlock: `=INDEX(return_array, MATCH(lookup_value, lookup_array, 0))

=XLOOKUP(lookup_value, lookup_array, return_array, [if_not_found], [match_mode], [search_mode])

=IFERROR(formula, value_if_error)
=IFNA(formula, value_if_na)`,
        examples: [
          {
            title: 'INDEX/MATCH vs VLOOKUP',
            code: 'Data: A=ID, B=Name, C=Dept, D=Salary\nLookup ID from F2\n\nVLOOKUP (can only go right, fragile):\n=VLOOKUP(F2, A:D, 4, FALSE)   → Salary\n\nINDEX/MATCH (flexible, robust):\n=INDEX(D:D, MATCH(F2, A:A, 0))  → Salary\n=INDEX(B:B, MATCH(F2, A:A, 0))  → Name\n=INDEX(C:C, MATCH(F2, A:A, 0))  → Dept\n\nNotice: INDEX/MATCH can return any column,\nnot just columns to the right of the lookup.',
            description: 'INDEX/MATCH decouples the lookup column from the return column, making formulas robust to table changes.',
          },
          {
            title: 'XLOOKUP with fallback',
            code: '=XLOOKUP(F2, A:A, D:D, "Not Found")\n→ Returns Salary; shows "Not Found" if no match\n\nReturn multiple columns:\n=XLOOKUP(F2, A:A, B:D)\n→ Returns Name, Dept, and Salary together\n\nLook up the last match:\n=XLOOKUP(F2, A:A, D:D, ,-1, -1)\n→ Searches from bottom to top (last occurrence)',
            description: 'XLOOKUP is cleaner than INDEX/MATCH and has powerful built-in options for edge cases.',
          },
          {
            title: 'Two-Way Lookup',
            code: 'Find the value where Row = Region (F2) AND Column = Month (F3)\n\n=INDEX(B2:M10,\n  MATCH(F2, A2:A10, 0),\n  MATCH(F3, B1:M1, 0)\n)\n\nFirst MATCH → finds the row number\nSecond MATCH → finds the column number\nINDEX → returns the value at that intersection',
            description: 'Two-way (matrix) lookup uses two MATCH functions inside INDEX to look up rows and columns simultaneously.',
          },
        ],
        exercises: [
          {
            prompt: 'Rewrite VLOOKUP(G2, A:E, 3, FALSE) using INDEX/MATCH to return column C.',
            hint: 'INDEX returns from column C:C; MATCH finds the row in column A:A.',
            answer: '=INDEX(C:C, MATCH(G2, A:A, 0))',
          },
          {
            prompt: 'Write an XLOOKUP that looks up B2 in range F:F, returns values from G:G, and shows "Missing" if not found.',
            hint: 'The 4th argument of XLOOKUP is the not-found value.',
            answer: '=XLOOKUP(B2, F:F, G:G, "Missing")',
          },
        ],
        quiz: [
          {
            question: 'What does the third argument of MATCH (match_type = 0) specify?',
            options: [
              'Sort the array ascending',
              'Return the position of an exact match',
              'Return an approximate match',
              'Return 0 if not found',
            ],
            answer: 1,
            explanation: '0 means exact match. 1 means less-than (sorted ascending). -1 means greater-than (sorted descending). Always use 0 for lookup tables.',
          },
          {
            question: 'You need to look up a value that is in column E and return a result from column B (to the LEFT). Which formula works?',
            options: [
              'VLOOKUP(val, B:E, -3, FALSE)',
              'INDEX(B:B, MATCH(val, E:E, 0))',
              'VLOOKUP(val, E:B, 1, FALSE)',
              'LOOKUP(val, E:E)',
            ],
            answer: 1,
            explanation: 'INDEX/MATCH handles left lookups naturally. VLOOKUP cannot look left because it always returns from columns to the right of the lookup column.',
          },
        ],
        tags: ['INDEX', 'MATCH', 'XLOOKUP', 'VLOOKUP', 'lookup', 'IFERROR', 'two-way lookup'],
      },
    ],
  },
  {
    id: 'excel-advanced',
    title: 'Excel Advanced',
    icon: '🚀',
    color: '#f472b6',
    track: 'Excel',
    phase: 'Phase 3',
    lessons: [
      {
        id: 'excel-power-query',
        title: 'Power Query: ETL for Excel',
        duration: '40 min',
        difficulty: 'Advanced',
        summary: 'Import, clean, and transform data from any source without formulas.',
        objectives: [
          'Connect to CSV, Excel, and web data sources',
          'Clean data: remove duplicates, rename columns, change types',
          'Transform: pivot/unpivot, merge queries, group by',
          'Understand the M formula language basics',
          'Load data to worksheet or Data Model',
        ],
        explanation: `Power Query (Get & Transform in Excel 2016+) is Excel's ETL engine. ETL stands for **Extract, Transform, Load** — the same process data engineers perform at enterprise scale.

**Why Power Query vs manual cleaning:**
- All steps are recorded and **repeatable** — run again with one click when new data arrives
- Works with millions of rows without slowing Excel's grid
- Handles sources that change shape: new columns, different date formats, etc.

**The Query Editor:** Opens when you click Data → Get Data. Shows a preview of your data and a **Steps pane** on the right that records every transformation.

**M Language:** Every step generates M code behind the scenes. You can view it via View → Advanced Editor. You don't need to write M manually, but understanding it helps troubleshoot complex transforms.

**Load options:**
- To worksheet — materialises into the grid
- To Data Model — keeps it in memory for Power Pivot (handles 100M+ rows)
- Connection Only — for queries that feed other queries`,
        syntaxBlock: `Sample M code generated by Power Query:
let
  Source = Csv.Document(File.Contents("sales.csv")),
  PromotedHeaders = Table.PromoteHeaders(Source),
  ChangedTypes = Table.TransformColumnTypes(
    PromotedHeaders,
    {{"Date", type date}, {"Amount", type number}}
  ),
  FilteredRows = Table.SelectRows(
    ChangedTypes, each [Amount] > 0
  )
in
  FilteredRows`,
        examples: [
          {
            title: 'Cleaning a CSV Import',
            code: 'Steps in the Query Editor:\n1. Data → Get Data → From File → From CSV\n2. Preview loads → Transform Data\n3. Home → Use First Row as Headers\n4. Select "Date" column → right-click → Change Type → Date\n5. Select "Amount" → Change Type → Decimal Number\n6. Home → Remove Rows → Remove Blank Rows\n7. Home → Remove Duplicates\n8. Close & Load → To Worksheet',
            description: 'Every step is recorded. Next month, paste new data into the file and click Refresh — all steps rerun automatically.',
          },
          {
            title: 'Unpivot: Wide to Tall',
            code: 'Before (wide format):\n  Name  | Jan | Feb | Mar\n  Alice |  10 |  15 |  20\n\nAfter unpivot (tall/tidy format):\n  Name  | Month | Value\n  Alice | Jan   | 10\n  Alice | Feb   | 15\n  Alice | Mar   | 20\n\nSteps:\n1. Select Name column → right-click → Unpivot Other Columns\n2. Rename "Attribute" → "Month", "Value" → "Sales"',
            description: 'Unpivoting converts wide data into the tall format that PivotTables and charts require.',
          },
        ],
        exercises: [
          {
            prompt: 'You have 12 monthly CSV files with identical structure. How would you combine them in Power Query?',
            hint: 'Power Query can combine all files in a folder automatically.',
            answer: 'Data → Get Data → From File → From Folder. Select the folder. Power Query presents a Combine & Transform option that stacks all files with a source file column added.',
          },
          {
            prompt: 'What is the main advantage of loading a large query "To Data Model" instead of to a worksheet?',
            hint: 'Think about Excel grid row limits vs in-memory columnar storage.',
            answer: 'The Data Model (Power Pivot) has no row limit and uses in-memory columnar compression, handling 100M+ rows efficiently. The worksheet is limited to ~1M rows.',
          },
        ],
        quiz: [
          {
            question: 'Power Query steps recorded in the Steps pane are written in which language?',
            options: ['VBA', 'DAX', 'M (Power Query Formula Language)', 'Python'],
            answer: 2,
            explanation: 'Each transformation in Power Query generates M code. You can view and edit it directly in the Advanced Editor (View menu).',
          },
          {
            question: 'What does "Unpivot Columns" do to a table?',
            options: [
              'Sorts columns alphabetically',
              'Converts column headers into row values (wide to tall)',
              'Removes duplicate columns',
              'Transposes rows and columns',
            ],
            answer: 1,
            explanation: 'Unpivot converts wide format (one column per category) into tall/tidy format (one row per data point) — the format required for most analysis tools.',
          },
        ],
        tags: ['Power Query', 'ETL', 'M language', 'unpivot', 'merge', 'transform', 'data cleaning'],
      },
      {
        id: 'excel-vba',
        title: 'VBA & Macros',
        duration: '45 min',
        difficulty: 'Advanced',
        summary: 'Automate repetitive tasks and build custom tools with Excel VBA.',
        objectives: [
          'Record and run a macro',
          'Understand VBA syntax: Sub, variables, loops',
          'Reference cells and ranges in VBA',
          'Use If/Else and For loops',
          'Create a simple custom function (UDF)',
        ],
        explanation: `VBA (Visual Basic for Applications) is Excel's built-in programming language. It lets you automate anything you can do manually in Excel — and much more.

**The VBA Editor (Alt+F11):** Opens the IDE where you write and manage code. Code lives in Modules (for general subs/functions), ThisWorkbook, or Sheet objects.

**Macros vs Procedures vs Functions:**
- A **Sub** does something (no return value) — run from the Ribbon or a button
- A **Function** returns a value — can be used as a worksheet formula (UDF)

**Object model:** Excel VBA uses a hierarchy — Application → Workbook → Worksheet → Range → Cell. You navigate it with dots: \`Worksheets("Sheet1").Range("A1").Value\`

**Recording macros** is the fastest way to learn — record an action, then look at the generated code in the VBA editor to understand the syntax.

**Key rule:** Always declare variables with \`Dim\`, and add \`Option Explicit\` at the top of every module to catch typos.`,
        syntaxBlock: `Sub HelloWorld()
  MsgBox "Hello, Excel!"
End Sub

Sub FormatReport()
  Dim ws As Worksheet
  Dim lastRow As Long
  Set ws = Worksheets("Sales")
  lastRow = ws.Cells(ws.Rows.Count, "A").End(xlUp).Row

  Dim i As Long
  For i = 2 To lastRow
    If ws.Cells(i, "C").Value > 10000 Then
      ws.Cells(i, "C").Interior.Color = RGB(0, 200, 100)
    End If
  Next i
End Sub

Function DoubleIt(x As Double) As Double
  DoubleIt = x * 2
End Function`,
        examples: [
          {
            title: 'Find Last Row (Essential Pattern)',
            code: "' Find last used row in column A:\nlastRow = Cells(Rows.Count, \"A\").End(xlUp).Row\n\n' Find last used column in row 1:\nlastCol = Cells(1, Columns.Count).End(xlToLeft).Column\n\n' Loop through all data rows:\nFor i = 2 To lastRow\n  ' Do something with row i\n  Cells(i, \"B\").Value = Cells(i, \"A\").Value * 1.1\nNext i",
            description: 'Finding the last row dynamically is the most important VBA pattern — it makes your code work regardless of dataset size.',
          },
          {
            title: 'Error Handling with On Error',
            code: "Sub SafeImport()\n  On Error GoTo ErrorHandler\n\n  ' Your main code here\n  Workbooks.Open \"C:\\data\\sales.xlsx\"\n  MsgBox \"File opened successfully!\"\n  Exit Sub\n\nErrorHandler:\n  MsgBox \"Error \" & Err.Number & \": \" & Err.Description\nEnd Sub",
            description: 'Always add error handling to production macros — files may be missing, sheets renamed, or data in unexpected formats.',
          },
        ],
        exercises: [
          {
            prompt: 'Write a VBA Sub called "ClearFormatting" that removes all cell formatting in the range A1:Z100 of the active sheet.',
            hint: 'Use .ClearFormats on a Range object.',
            answer: "Sub ClearFormatting()\n  ActiveSheet.Range(\"A1:Z100\").ClearFormats\nEnd Sub",
          },
          {
            prompt: 'Write a UDF called "TaxAmount" that takes a price and rate and returns price * rate.',
            hint: 'Use Function instead of Sub, and assign the result to the function name.',
            answer: 'Function TaxAmount(price As Double, rate As Double) As Double\n  TaxAmount = price * rate\nEnd Function',
          },
        ],
        quiz: [
          {
            question: 'What is the difference between a VBA Sub and a Function?',
            options: [
              'Sub is faster; Function is slower',
              'Sub performs actions with no return value; Function returns a value',
              'Sub can only be recorded; Function must be typed',
              'There is no difference',
            ],
            answer: 1,
            explanation: 'A Sub performs actions (formatting, opening files, loops). A Function returns a value and can be used as a worksheet formula (UDF).',
          },
          {
            question: 'What does `Cells(Rows.Count, "A").End(xlUp).Row` find?',
            options: [
              'The first row in column A',
              'The total number of rows in Excel',
              'The last row containing data in column A',
              'The last row in the selection',
            ],
            answer: 2,
            explanation: 'This pattern starts at the absolute last row of Excel, then jumps up (xlUp) to find the last non-empty cell — giving the last data row in column A.',
          },
        ],
        tags: ['VBA', 'macros', 'automation', 'Sub', 'Function', 'loop', 'UDF'],
      },
    ],
  },
];

// ─── SQL MODULES ─────────────────────────────────────────────────────────────
// ─── SQL MODULES ──────────────────────────────────────────────────────────────

export const SQL_MODULES: LessonModule[] = [
  {
    id: 'sql-core',
    title: 'Core SQL',
    icon: '🗄️',
    color: '#34d399',
    track: 'SQL',
    phase: 'Phase 1',
    lessons: [
      {
        id: 'sql-select',
        title: 'SELECT, WHERE & Filtering',
        duration: '20 min',
        difficulty: 'Beginner',
        summary: 'Query data with SELECT and filter precisely using WHERE conditions.',
        objectives: [
          'Write a basic SELECT statement',
          'Filter rows with WHERE and comparison operators',
          'Use BETWEEN, IN, LIKE, and IS NULL',
          'Sort results with ORDER BY',
          'Limit output with LIMIT / TOP',
        ],
        explanation: `SQL (Structured Query Language) is the universal language for querying relational databases. Every SQL query starts with the **SELECT** statement.

**Clause execution order** (logical, not written order):
1. FROM — identify the table
2. WHERE — filter rows
3. GROUP BY — group filtered rows
4. HAVING — filter groups
5. SELECT — choose columns
6. ORDER BY — sort output
7. LIMIT — restrict row count

**Comparison operators:** = <> (not equal) < > <= >=

**BETWEEN** is inclusive on both ends: \`BETWEEN 10 AND 20\` includes 10 and 20.

**IN** is a shorthand for multiple OR conditions.

**LIKE** enables pattern matching: % matches any sequence of characters, _ matches exactly one character.

**IS NULL / IS NOT NULL** — never use = NULL or <> NULL for null checks; NULL comparisons always return NULL (unknown), not TRUE or FALSE.`,
        syntaxBlock: `SELECT column1, column2 FROM table_name
WHERE condition
ORDER BY column1 ASC|DESC
LIMIT n;

-- Filtering operators:
WHERE age BETWEEN 18 AND 65
WHERE country IN ('UK', 'USA', 'Canada')
WHERE name LIKE 'A%'        -- starts with A
WHERE name LIKE '%son'      -- ends with son
WHERE email IS NULL
WHERE email IS NOT NULL`,
        examples: [
          {
            title: 'Basic SELECT with WHERE',
            code: "-- Get all employees in the Sales department earning over 50000\nSELECT employee_id, first_name, last_name, salary\nFROM employees\nWHERE department = 'Sales'\n  AND salary > 50000\nORDER BY salary DESC;",
            description: 'Chain multiple conditions with AND / OR. Use parentheses to control evaluation order.',
          },
          {
            title: 'IN, BETWEEN, LIKE, IS NULL',
            code: "-- IN: shorthand for multiple OR conditions\nSELECT * FROM products\nWHERE category IN ('Electronics', 'Clothing', 'Books');\n\n-- BETWEEN: inclusive range\nSELECT * FROM orders\nWHERE order_date BETWEEN '2024-01-01' AND '2024-03-31';\n\n-- LIKE: pattern matching\nSELECT * FROM customers\nWHERE email LIKE '%@gmail.com';\n\n-- IS NULL: find missing data\nSELECT * FROM customers\nWHERE phone IS NULL;",
            description: 'These operators are essential for real-world data filtering — most production queries use at least one of them.',
          },
        ],
        exercises: [
          {
            prompt: 'Write a query to find all customers from either "London" or "Manchester", ordered by last_name ascending.',
            hint: 'Use IN() for the city filter.',
            answer: "SELECT * FROM customers\nWHERE city IN ('London', 'Manchester')\nORDER BY last_name ASC;",
          },
          {
            prompt: 'Find all products where the product_name starts with "Pro" and the price is between 100 and 500.',
            hint: 'Use LIKE with % wildcard and BETWEEN.',
            answer: "SELECT * FROM products\nWHERE product_name LIKE 'Pro%'\n  AND price BETWEEN 100 AND 500;",
          },
          {
            prompt: 'Write a query to find all employees with no manager assigned (manager_id is missing).',
            hint: 'Never use = NULL — use IS NULL instead.',
            answer: 'SELECT * FROM employees\nWHERE manager_id IS NULL;',
          },
        ],
        quiz: [
          {
            question: 'Which operator correctly checks for a NULL value in SQL?',
            options: ['= NULL', 'IS NULL', '== NULL', 'EQUALS NULL'],
            answer: 1,
            explanation: 'IS NULL is the correct syntax. NULL represents "unknown" — any comparison using = returns NULL (not TRUE), so = NULL never matches.',
          },
          {
            question: 'The condition WHERE price BETWEEN 10 AND 20 includes prices of exactly 10 and 20.',
            options: ['True', 'False'],
            answer: 0,
            explanation: 'BETWEEN is inclusive on both ends. It is equivalent to WHERE price >= 10 AND price <= 20.',
          },
          {
            question: 'Which LIKE pattern matches "car", "cat", and "can" but NOT "cart"?',
            options: ["'ca%'", "'ca_'", "'c_r'", "'%at'"],
            answer: 1,
            explanation: "ca_ matches exactly 4 characters: c, a, and exactly one more. 'cart' has 4 characters so ca_ would also match it. 'ca%' would match all of them.",
          },
        ],
        tags: ['SELECT', 'WHERE', 'LIKE', 'IN', 'BETWEEN', 'IS NULL', 'ORDER BY', 'filtering'],
      },
      {
        id: 'sql-joins',
        title: 'JOINs: Combining Tables',
        duration: '30 min',
        difficulty: 'Beginner',
        summary: 'Combine data from multiple tables using INNER, LEFT, RIGHT, and FULL OUTER JOINs.',
        objectives: [
          'Understand relational database keys',
          'Write INNER JOIN queries',
          'Use LEFT JOIN to include unmatched rows',
          'Understand RIGHT and FULL OUTER JOIN',
          'Join more than two tables',
          'Spot and avoid duplicate rows from joins',
        ],
        explanation: `Relational databases store related data in separate tables to avoid redundancy. **JOINs** reunite this data for analysis.

**Primary Key (PK):** A column (or combination) that uniquely identifies each row in a table. Values must be unique and non-null.

**Foreign Key (FK):** A column in one table that references the PK of another — establishing the relationship.

**JOIN types:**
- **INNER JOIN:** Returns only rows where the join condition is TRUE in BOTH tables. Rows with no match are excluded.
- **LEFT JOIN:** Returns ALL rows from the left table, plus matching rows from the right. Non-matching right columns are NULL.
- **RIGHT JOIN:** The reverse — all rows from right table.
- **FULL OUTER JOIN:** All rows from both tables; NULLs fill where there's no match.
- **CROSS JOIN:** Every row from left × every row from right (Cartesian product). Use with care.

**Aliases:** Use table aliases (e.g., \`e\` for employees) to keep queries readable, especially when joining multiple tables.`,
        syntaxBlock: `SELECT t1.col, t2.col
FROM table1 t1
INNER JOIN table2 t2 ON t1.id = t2.foreign_id;

LEFT JOIN  → all from left + matches from right
RIGHT JOIN → all from right + matches from left
FULL OUTER JOIN → all from both tables`,
        examples: [
          {
            title: 'INNER JOIN: Customers with Orders',
            code: "SELECT c.customer_id, c.name, o.order_id, o.total\nFROM customers c\nINNER JOIN orders o ON c.customer_id = o.customer_id\nORDER BY c.name;\n\n-- Only customers who HAVE placed an order appear.\n-- Customers with no orders are excluded.",
            description: 'INNER JOIN is the most common join — it returns only the intersection of both tables.',
          },
          {
            title: 'LEFT JOIN: Find customers with NO orders',
            code: "SELECT c.customer_id, c.name, o.order_id\nFROM customers c\nLEFT JOIN orders o ON c.customer_id = o.customer_id\nWHERE o.order_id IS NULL;\n\n-- The LEFT JOIN keeps all customers.\n-- WHERE o.order_id IS NULL filters to only those\n-- who have no matching order row.",
            description: 'This pattern — LEFT JOIN + WHERE right side IS NULL — is a classic anti-join for finding unmatched records.',
          },
          {
            title: 'Three-table JOIN',
            code: "SELECT e.first_name, e.last_name,\n       d.department_name,\n       l.city\nFROM employees e\nINNER JOIN departments d ON e.department_id = d.department_id\nINNER JOIN locations l ON d.location_id = l.location_id\nORDER BY e.last_name;",
            description: 'Chain multiple JOINs to traverse a database schema. Each JOIN adds a new table to the result set.',
          },
        ],
        exercises: [
          {
            prompt: 'Write a query joining "employees" (e) to "departments" (d) on department_id, returning employee name and department name.',
            hint: 'Use INNER JOIN with ON clause matching the shared key.',
            answer: 'SELECT e.first_name, e.last_name, d.department_name\nFROM employees e\nINNER JOIN departments d ON e.department_id = d.department_id;',
          },
          {
            prompt: 'List all products that have NEVER been ordered. Products table has product_id; order_items has product_id.',
            hint: 'LEFT JOIN order_items onto products, then filter where order_items.product_id IS NULL.',
            answer: 'SELECT p.product_id, p.product_name\nFROM products p\nLEFT JOIN order_items oi ON p.product_id = oi.product_id\nWHERE oi.product_id IS NULL;',
          },
        ],
        quiz: [
          {
            question: 'An INNER JOIN between tables A (100 rows) and B (80 rows) with 60 matching rows returns how many rows?',
            options: ['100', '80', '60', '180'],
            answer: 2,
            explanation: 'INNER JOIN returns only matching rows — the intersection. 60 rows from A have a match in B, so 60 rows are returned.',
          },
          {
            question: 'You LEFT JOIN customers to orders. A customer with no orders appears in the result. What value is in the order_id column for that row?',
            options: ['0', 'Empty string', 'NULL', 'An error is thrown'],
            answer: 2,
            explanation: 'Unmatched rows from the right table (orders) are filled with NULLs in all right-side columns.',
          },
        ],
        tags: ['JOIN', 'INNER JOIN', 'LEFT JOIN', 'RIGHT JOIN', 'FULL OUTER JOIN', 'foreign key', 'primary key'],
      },
      {
        id: 'sql-aggregation',
        title: 'Aggregation & GROUP BY',
        duration: '25 min',
        difficulty: 'Beginner',
        summary: 'Summarise data with COUNT, SUM, AVG, MIN, MAX and GROUP BY.',
        objectives: [
          'Use aggregate functions: COUNT, SUM, AVG, MIN, MAX',
          'Group results with GROUP BY',
          'Filter groups with HAVING',
          'Understand the difference between WHERE and HAVING',
          'Use COUNT(*) vs COUNT(column)',
        ],
        explanation: `Aggregate functions collapse many rows into a single result. They are the SQL equivalent of Excel's SUM, AVERAGE, and COUNTIF.

**Key aggregate functions:**
- **COUNT(*)** — counts all rows including NULLs
- **COUNT(column)** — counts non-NULL values in that column
- **SUM(column)** — total of numeric values
- **AVG(column)** — arithmetic mean (ignores NULLs)
- **MIN / MAX** — smallest / largest value

**GROUP BY** splits rows into groups and applies the aggregate to each group separately. Any column in SELECT that is NOT inside an aggregate function MUST appear in GROUP BY.

**WHERE vs HAVING:**
- WHERE filters INDIVIDUAL ROWS before grouping
- HAVING filters GROUPS after aggregation
- You cannot use aggregate functions in WHERE
- You can use column names (or aliases) in HAVING

**NULL in aggregates:** Most aggregate functions ignore NULLs. COUNT(*) is the exception — it counts every row regardless.`,
        syntaxBlock: `SELECT column, AGG_FUNCTION(col2)
FROM table
WHERE row_filter          -- filters rows BEFORE grouping
GROUP BY column
HAVING group_filter       -- filters groups AFTER aggregating
ORDER BY AGG_FUNCTION(col2) DESC;`,
        examples: [
          {
            title: 'GROUP BY with multiple aggregates',
            code: "SELECT\n  department,\n  COUNT(*) AS employee_count,\n  AVG(salary) AS avg_salary,\n  MAX(salary) AS highest_salary,\n  MIN(salary) AS lowest_salary\nFROM employees\nGROUP BY department\nORDER BY avg_salary DESC;",
            description: 'One row per department summarising all employees within it — equivalent to a PivotTable.',
          },
          {
            title: 'HAVING: filter groups',
            code: "-- Find departments with more than 5 employees\n-- earning an average salary over 60000\nSELECT department, COUNT(*) AS headcount, AVG(salary) AS avg_sal\nFROM employees\nGROUP BY department\nHAVING COUNT(*) > 5\n   AND AVG(salary) > 60000\nORDER BY headcount DESC;\n\n-- Note: can't use WHERE COUNT(*) > 5\n-- COUNT(*) doesn't exist until after GROUP BY",
            description: 'HAVING is WHERE for groups. It runs after aggregation, so you can use aggregate functions in the condition.',
          },
        ],
        exercises: [
          {
            prompt: 'Count the number of orders per customer, but only show customers with more than 3 orders.',
            hint: 'GROUP BY customer_id, then use HAVING COUNT(*) > 3.',
            answer: 'SELECT customer_id, COUNT(*) AS order_count\nFROM orders\nGROUP BY customer_id\nHAVING COUNT(*) > 3;',
          },
          {
            prompt: 'Find the total revenue per product category for orders placed in 2024.',
            hint: 'Filter the year in WHERE, then GROUP BY category.',
            answer: "SELECT category, SUM(revenue) AS total_revenue\nFROM orders\nWHERE YEAR(order_date) = 2024\nGROUP BY category\nORDER BY total_revenue DESC;",
          },
        ],
        quiz: [
          {
            question: 'What is wrong with this query?\nSELECT department, COUNT(*)\nFROM employees\nWHERE COUNT(*) > 5\nGROUP BY department;',
            options: [
              'Nothing, it is valid SQL',
              'WHERE cannot use aggregate functions — use HAVING instead',
              'GROUP BY must come before WHERE',
              'COUNT(*) requires a column name',
            ],
            answer: 1,
            explanation: 'WHERE runs before GROUP BY, so aggregate functions like COUNT(*) do not exist yet at that point. Use HAVING after GROUP BY to filter on aggregated values.',
          },
          {
            question: 'What is the difference between COUNT(*) and COUNT(email)?',
            options: [
              'There is no difference',
              'COUNT(*) counts all rows; COUNT(email) counts only non-NULL email values',
              'COUNT(email) is faster',
              'COUNT(*) only counts distinct values',
            ],
            answer: 1,
            explanation: 'COUNT(*) includes every row (even NULLs). COUNT(column) excludes rows where that column is NULL — useful for counting how many records actually have that value.',
          },
        ],
        tags: ['GROUP BY', 'HAVING', 'COUNT', 'SUM', 'AVG', 'MIN', 'MAX', 'aggregation'],
      },
    ],
  },
  {
    id: 'sql-intermediate',
    title: 'Intermediate SQL',
    icon: '⚡',
    color: '#fb923c',
    track: 'SQL',
    phase: 'Phase 2',
    lessons: [
      {
        id: 'sql-ctes',
        title: 'CTEs & Subqueries',
        duration: '30 min',
        difficulty: 'Intermediate',
        summary: 'Write readable, modular SQL using Common Table Expressions and subqueries.',
        objectives: [
          'Write correlated and non-correlated subqueries',
          'Use subqueries in SELECT, FROM, and WHERE',
          'Write CTEs with the WITH clause',
          'Chain multiple CTEs',
          'Write a basic recursive CTE',
        ],
        explanation: `**Subqueries** are queries nested inside another query. They can appear in three places:
- **In SELECT** — scalar subquery returning one value per row
- **In FROM** — derived table (the subquery result acts as a table)
- **In WHERE** — filter based on a sub-result (with IN, EXISTS, comparison)

**Correlated vs Non-correlated:**
- **Non-correlated** — the subquery runs once independently, then its result is used by the outer query
- **Correlated** — the subquery references the outer query and runs once per outer row (can be slow on large data)

**CTEs (Common Table Expressions)** use the WITH clause to name a subquery and reference it like a table. Benefits over subqueries:
- Readable left-to-right (define before use)
- Can be referenced multiple times in the same query
- Enable recursive queries
- Easier to debug (comment out individual CTEs)

**Recursive CTEs** are used for hierarchical data — org charts, bill-of-materials, category trees. They consist of an anchor member (base case) UNION ALL'd with the recursive member.`,
        syntaxBlock: `-- Basic CTE:
WITH cte_name AS (
  SELECT ...
  FROM ...
  WHERE ...
)
SELECT * FROM cte_name;

-- Multiple CTEs:
WITH cte1 AS (...),
     cte2 AS (SELECT ... FROM cte1 ...)
SELECT * FROM cte2;`,
        examples: [
          {
            title: 'Subquery vs CTE',
            code: "-- Subquery approach (harder to read):\nSELECT *\nFROM (SELECT department, AVG(salary) AS avg_sal\n      FROM employees GROUP BY department) sub\nWHERE sub.avg_sal > 70000;\n\n-- CTE approach (cleaner):\nWITH dept_averages AS (\n  SELECT department, AVG(salary) AS avg_sal\n  FROM employees\n  GROUP BY department\n)\nSELECT *\nFROM dept_averages\nWHERE avg_sal > 70000;",
            description: 'CTEs read like a story — define first, then use. Much easier to understand and maintain than nested subqueries.',
          },
          {
            title: 'Recursive CTE: Employee Hierarchy',
            code: "WITH RECURSIVE org_chart AS (\n  -- Anchor: top-level employees (no manager)\n  SELECT employee_id, name, manager_id, 1 AS level\n  FROM employees\n  WHERE manager_id IS NULL\n\n  UNION ALL\n\n  -- Recursive: add direct reports\n  SELECT e.employee_id, e.name, e.manager_id, oc.level + 1\n  FROM employees e\n  INNER JOIN org_chart oc ON e.manager_id = oc.employee_id\n)\nSELECT * FROM org_chart\nORDER BY level, name;",
            description: 'Recursive CTEs traverse tree structures. The anchor is the root; the recursive part joins back to the CTE to add the next level.',
          },
        ],
        exercises: [
          {
            prompt: 'Rewrite this subquery as a CTE:\nSELECT * FROM (SELECT product_id, SUM(qty) AS total FROM sales GROUP BY product_id) s WHERE total > 100;',
            hint: 'Name the inner query in a WITH clause, then SELECT from it.',
            answer: "WITH product_sales AS (\n  SELECT product_id, SUM(qty) AS total\n  FROM sales\n  GROUP BY product_id\n)\nSELECT * FROM product_sales WHERE total > 100;",
          },
          {
            prompt: 'Write a query using a subquery in WHERE to find employees who earn more than the company-wide average salary.',
            hint: 'The inner query returns one value: AVG(salary). The outer query compares each row to it.',
            answer: 'SELECT * FROM employees\nWHERE salary > (SELECT AVG(salary) FROM employees);',
          },
        ],
        quiz: [
          {
            question: 'A correlated subquery differs from a non-correlated subquery because:',
            options: [
              'It uses the WITH clause',
              'It references a column from the outer query and re-runs for each outer row',
              'It can only appear in the FROM clause',
              'It always returns exactly one row',
            ],
            answer: 1,
            explanation: 'A correlated subquery references the outer query (e.g., WHERE e.dept = outer.dept) and executes once per row of the outer query, which can be slow on large tables.',
          },
          {
            question: 'Can you reference a CTE multiple times within the same query?',
            options: ['No, each CTE can only be referenced once', 'Yes, a CTE can be joined, filtered, or selected from multiple times in the same query'],
            answer: 1,
            explanation: 'This is one of the key advantages of CTEs over subqueries — you define the logic once and reuse it, avoiding code duplication.',
          },
        ],
        tags: ['CTE', 'WITH', 'subquery', 'correlated', 'derived table', 'recursive', 'modular SQL'],
      },
      {
        id: 'sql-window-functions',
        title: 'Window Functions',
        duration: '35 min',
        difficulty: 'Intermediate',
        summary: 'Calculate running totals, rankings, and row comparisons without collapsing data.',
        objectives: [
          'Understand the OVER() clause',
          'Use PARTITION BY to scope calculations',
          'Apply ORDER BY inside window frames',
          'Use ROW_NUMBER, RANK, and DENSE_RANK',
          'Apply LAG and LEAD for row comparisons',
          'Calculate running totals and moving averages',
        ],
        explanation: `Window functions perform calculations across a set of rows related to the current row — **without** collapsing those rows into groups like GROUP BY does. Every row in the result retains its identity.

**The OVER() clause** defines the "window" — the set of rows the function sees. Empty OVER() means the entire result set.

**PARTITION BY** divides rows into independent windows (like GROUP BY, but without collapsing). Each partition is calculated separately.

**ORDER BY inside OVER()** defines the order within the window. Required for ranking functions and running totals. For frame functions (SUM, AVG), it defines which rows are included.

**Ranking functions:**
- **ROW_NUMBER()** — unique integer per row, no ties
- **RANK()** — tied rows get the same rank, next rank is skipped (1,1,3)
- **DENSE_RANK()** — tied rows get the same rank, no gaps (1,1,2)
- **NTILE(n)** — divides rows into n roughly equal buckets

**Offset functions:**
- **LAG(col, n)** — value from n rows before the current row
- **LEAD(col, n)** — value from n rows after the current row

These are perfect for period-over-period comparisons (this month vs last month).`,
        syntaxBlock: `SELECT col,
  FUNCTION() OVER (
    [PARTITION BY partition_col]
    [ORDER BY order_col ASC|DESC]
    [ROWS BETWEEN ... AND ...]
  ) AS alias
FROM table;

-- Common frame clauses:
ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW  -- running total
ROWS BETWEEN 2 PRECEDING AND CURRENT ROW          -- 3-row moving avg`,
        examples: [
          {
            title: 'ROW_NUMBER, RANK, DENSE_RANK',
            code: "SELECT\n  name, department, salary,\n  ROW_NUMBER() OVER (PARTITION BY department ORDER BY salary DESC) AS row_num,\n  RANK()       OVER (PARTITION BY department ORDER BY salary DESC) AS rnk,\n  DENSE_RANK() OVER (PARTITION BY department ORDER BY salary DESC) AS dense_rnk\nFROM employees;\n\n-- If two people in Sales tie for 1st:\n-- ROW_NUMBER: 1, 2, 3   (arbitrary tiebreak)\n-- RANK:       1, 1, 3   (skips 2)\n-- DENSE_RANK: 1, 1, 2   (no skip)",
            description: 'Run this to clearly see the difference between the three ranking functions when ties exist.',
          },
          {
            title: 'LAG for Month-over-Month Change',
            code: "SELECT\n  month,\n  revenue,\n  LAG(revenue, 1) OVER (ORDER BY month) AS prev_month_revenue,\n  revenue - LAG(revenue, 1) OVER (ORDER BY month) AS mom_change,\n  ROUND(\n    (revenue - LAG(revenue, 1) OVER (ORDER BY month))\n    / LAG(revenue, 1) OVER (ORDER BY month) * 100, 1\n  ) AS mom_pct_change\nFROM monthly_sales;",
            description: 'LAG is the go-to for period-over-period analysis in dashboards and finance queries.',
          },
          {
            title: 'Running Total',
            code: "SELECT\n  order_date,\n  daily_revenue,\n  SUM(daily_revenue) OVER (\n    ORDER BY order_date\n    ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW\n  ) AS running_total\nFROM daily_sales;",
            description: 'ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW is the standard frame for a running total.',
          },
        ],
        exercises: [
          {
            prompt: 'Rank employees within each department by salary (highest = rank 1) using DENSE_RANK.',
            hint: 'PARTITION BY department, ORDER BY salary DESC inside OVER().',
            answer: 'SELECT name, department, salary,\n  DENSE_RANK() OVER (PARTITION BY department ORDER BY salary DESC) AS dept_rank\nFROM employees;',
          },
          {
            prompt: 'Write a query showing each sale amount and the previous row\'s amount using LAG.',
            hint: 'LAG(column, 1) with ORDER BY the date column.',
            answer: 'SELECT sale_date, amount,\n  LAG(amount, 1) OVER (ORDER BY sale_date) AS previous_amount\nFROM sales;',
          },
        ],
        quiz: [
          {
            question: 'PARTITION BY inside OVER() is most similar to which SQL clause?',
            options: ['WHERE', 'HAVING', 'GROUP BY', 'ORDER BY'],
            answer: 2,
            explanation: 'PARTITION BY divides rows into independent subsets — just like GROUP BY. The key difference is that PARTITION BY does not collapse rows; every original row is still in the output.',
          },
          {
            question: 'You use RANK() and two rows tie for rank 2. What is the next rank assigned?',
            options: ['3', '4', '2', 'NULL'],
            answer: 1,
            explanation: 'RANK() skips ranks after ties. Two rows at rank 2 means the next distinct rank is 4. Use DENSE_RANK() if you want 3 instead.',
          },
        ],
        tags: ['window function', 'OVER', 'PARTITION BY', 'ROW_NUMBER', 'RANK', 'LAG', 'LEAD', 'running total'],
      },
    ],
  },
  {
    id: 'sql-advanced',
    title: 'Expert SQL',
    icon: '🏆',
    color: '#f43f5e',
    track: 'SQL',
    phase: 'Phase 3',
    lessons: [
      {
        id: 'sql-optimization',
        title: 'Query Optimization & Indexes',
        duration: '40 min',
        difficulty: 'Advanced',
        summary: 'Write high-performance queries and understand how indexes work under the hood.',
        objectives: [
          'Read and interpret an execution plan',
          'Understand B-tree indexes and when to use them',
          'Know which query patterns hurt performance',
          'Apply covering indexes',
          'Use query hints appropriately',
        ],
        explanation: `Query optimization is the difference between a query that runs in 50ms and one that takes 50 seconds on the same data.

**How the query optimizer works:** The database parses your SQL, generates multiple execution plans, estimates their cost, and picks the cheapest one. Understanding this helps you write queries the optimizer can handle well.

**Execution plans** show how the DB executes your query — use EXPLAIN (PostgreSQL/MySQL) or Execution Plan in SSMS (SQL Server). Key nodes to understand:
- **Seq Scan / Table Scan** — reads every row. Fine on small tables, terrible on large ones.
- **Index Scan / Index Seek** — uses an index to find rows quickly.
- **Hash Join / Merge Join / Nested Loop** — different join algorithms with different cost profiles.

**Indexes** are sorted data structures (usually B-trees) that allow the DB to find rows without scanning the entire table. They work like a book's index — jump to the right page instead of reading every page.

**When indexes help:** Columns in WHERE, JOIN ON, and ORDER BY clauses.
**When they hurt:** Heavy INSERT/UPDATE/DELETE workloads (indexes must be maintained on every write).

**Key anti-patterns that break indexes:**
- Wrapping a column in a function: \`WHERE YEAR(date) = 2024\` → use \`WHERE date >= '2024-01-01' AND date < '2025-01-01'\`
- Leading wildcard: \`WHERE name LIKE '%Smith'\` → can't use index
- Implicit type conversion: comparing varchar to int
- SELECT * — fetches all columns, bypassing covering index benefit`,
        syntaxBlock: `-- View execution plan:
EXPLAIN ANALYZE SELECT ... (PostgreSQL)
EXPLAIN SELECT ...          (MySQL)

-- Create an index:
CREATE INDEX idx_employees_dept ON employees(department_id);
CREATE UNIQUE INDEX idx_email ON customers(email);

-- Covering index (includes all needed columns):
CREATE INDEX idx_cover ON orders(customer_id, order_date)
  INCLUDE (total_amount);`,
        examples: [
          {
            title: 'Index-Breaking vs Index-Friendly Patterns',
            code: "-- BAD: function wrapping breaks the index on order_date\nSELECT * FROM orders WHERE YEAR(order_date) = 2024;\n\n-- GOOD: range condition uses the index\nSELECT * FROM orders\nWHERE order_date >= '2024-01-01' AND order_date < '2025-01-01';\n\n-- BAD: leading wildcard can't use B-tree index\nSELECT * FROM customers WHERE email LIKE '%@gmail.com';\n\n-- GOOD: no leading wildcard\nSELECT * FROM customers WHERE email LIKE 'john%';\n\n-- BAD: implicit cast on varchar id\nSELECT * FROM users WHERE user_id = 12345;  -- user_id is VARCHAR\n-- GOOD: match types\nSELECT * FROM users WHERE user_id = '12345';",
            description: 'These patterns are responsible for the majority of slow query issues in production systems.',
          },
          {
            title: 'Reading an Execution Plan (PostgreSQL)',
            code: "EXPLAIN ANALYZE\nSELECT c.name, SUM(o.total)\nFROM customers c\nINNER JOIN orders o ON c.customer_id = o.customer_id\nWHERE o.order_date >= '2024-01-01'\nGROUP BY c.name;\n\n-- Sample output:\n-- HashAggregate (cost=1250.00..1275.00 rows=500)\n--   -> Hash Join (cost=350.00..1150.00)\n--        -> Seq Scan on customers (cost=0..120.00)\n--        -> Index Scan on orders (cost=0..800.00)\n--             Index Cond: (order_date >= '2024-01-01')\n\n-- 'Seq Scan' on a large table = potential problem\n-- 'Index Scan' on the filtered column = good",
            description: 'Execution plans read bottom-up, inside-out. High cost nodes on large Seq Scans are your optimization targets.',
          },
        ],
        exercises: [
          {
            prompt: "Rewrite this index-breaking query to use the index on sale_date:\nSELECT * FROM sales WHERE MONTH(sale_date) = 6 AND YEAR(sale_date) = 2024;",
            hint: 'Replace the function calls with a date range comparison.',
            answer: "SELECT * FROM sales\nWHERE sale_date >= '2024-06-01' AND sale_date < '2024-07-01';",
          },
          {
            prompt: 'What index would most benefit a query that frequently filters on customer_id and orders by order_date?',
            hint: 'The filter column comes first in a composite index.',
            answer: 'CREATE INDEX idx_orders_cust_date ON orders(customer_id, order_date);',
          },
        ],
        quiz: [
          {
            question: 'Which scan type in an execution plan indicates the database is reading every row in a table?',
            options: ['Index Scan', 'Index Seek', 'Sequential Scan / Table Scan', 'Bitmap Scan'],
            answer: 2,
            explanation: 'Sequential Scan (PostgreSQL) or Table Scan (SQL Server) reads every row. This is acceptable for small tables or when selecting most of the table, but should be avoided for large, frequently queried tables.',
          },
          {
            question: 'Why does WHERE UPPER(email) = \'TEST@EXAMPLE.COM\' prevent index usage?',
            options: [
              'UPPER() is not a valid SQL function',
              'Functions wrapping an indexed column prevent the optimizer from using that index',
              'The email column must be lowercase',
              'This syntax requires a full-text index',
            ],
            answer: 1,
            explanation: 'Wrapping a column in a function means the optimizer cannot use a standard B-tree index on that column — it must evaluate the function for every row. Store data consistently or use a function-based index instead.',
          },
        ],
        tags: ['optimization', 'index', 'execution plan', 'B-tree', 'query performance', 'EXPLAIN', 'slow query'],
      },
      {
        id: 'sql-stored-procedures',
        title: 'Stored Procedures & Transactions',
        duration: '35 min',
        difficulty: 'Advanced',
        summary: 'Encapsulate business logic in stored procedures and ensure data integrity with transactions.',
        objectives: [
          'Create and execute stored procedures',
          'Use input and output parameters',
          'Write control flow: IF, WHILE, CASE',
          'Understand ACID transactions',
          'Use BEGIN, COMMIT, and ROLLBACK',
          'Handle errors with TRY/CATCH',
        ],
        explanation: `**Stored Procedures** are named, compiled SQL programs stored in the database. Benefits:
- **Performance:** Pre-compiled execution plan
- **Security:** Grant EXECUTE permission without granting table access
- **Reusability:** Call the same logic from multiple applications
- **Reduced network traffic:** Send one CALL instead of many statements

**Variables** are declared with DECLARE and assigned with SET or SELECT.

**Control flow:** IF/ELSE, WHILE loops, and CASE expressions give stored procedures programming capabilities.

**Transactions** are the cornerstone of data integrity. They group statements into an atomic unit — either ALL succeed (COMMIT) or ALL are undone (ROLLBACK).

**ACID properties:**
- **Atomicity** — all or nothing
- **Consistency** — data is always in a valid state
- **Isolation** — concurrent transactions don't interfere
- **Durability** — committed data survives crashes

**TRY/CATCH (SQL Server) / EXCEPTION (PostgreSQL)** catches runtime errors and allows graceful rollback and logging.`,
        syntaxBlock: `-- SQL Server syntax:
CREATE PROCEDURE proc_name
  @param1 INT,
  @param2 VARCHAR(100)
AS
BEGIN
  SET NOCOUNT ON;
  -- procedure body
END;

BEGIN TRANSACTION;
  -- statements
  IF @@ERROR <> 0 ROLLBACK;
  ELSE COMMIT;`,
        examples: [
          {
            title: 'Stored Procedure with Error Handling (SQL Server)',
            code: "CREATE PROCEDURE TransferFunds\n  @FromAccount INT,\n  @ToAccount   INT,\n  @Amount      DECIMAL(18,2)\nAS\nBEGIN\n  SET NOCOUNT ON;\n  BEGIN TRY\n    BEGIN TRANSACTION;\n      UPDATE accounts\n        SET balance = balance - @Amount\n        WHERE account_id = @FromAccount;\n\n      UPDATE accounts\n        SET balance = balance + @Amount\n        WHERE account_id = @ToAccount;\n    COMMIT TRANSACTION;\n  END TRY\n  BEGIN CATCH\n    ROLLBACK TRANSACTION;\n    THROW;  -- re-raise the error to the caller\n  END CATCH;\nEND;",
            description: 'A classic bank transfer — the debit and credit must both succeed or both fail. TRY/CATCH ensures a rollback on any error.',
          },
          {
            title: 'Control Flow in SQL',
            code: "-- IF/ELSE:\nIF @score >= 90 SET @grade = 'A'\nELSE IF @score >= 80 SET @grade = 'B'\nELSE SET @grade = 'C';\n\n-- WHILE loop:\nDECLARE @i INT = 1;\nWHILE @i <= 10\nBEGIN\n  INSERT INTO numbers(n) VALUES(@i);\n  SET @i = @i + 1;\nEND;\n\n-- CASE in SELECT:\nSELECT order_id,\n  CASE status\n    WHEN 1 THEN 'Pending'\n    WHEN 2 THEN 'Shipped'\n    WHEN 3 THEN 'Delivered'\n    ELSE 'Unknown'\n  END AS status_label\nFROM orders;",
            description: 'SQL control flow enables complex business logic to live in the database layer where it can be shared across all applications.',
          },
        ],
        exercises: [
          {
            prompt: 'Write a stored procedure GetEmployeesByDept that accepts @DeptId INT and returns all employees in that department.',
            hint: 'CREATE PROCEDURE with one parameter, then a simple SELECT with WHERE.',
            answer: 'CREATE PROCEDURE GetEmployeesByDept\n  @DeptId INT\nAS\nBEGIN\n  SELECT * FROM employees\n  WHERE department_id = @DeptId;\nEND;',
          },
          {
            prompt: 'Wrap these two INSERTs in a transaction that rolls back if either fails:\nINSERT INTO orders ...\nINSERT INTO order_items ...',
            hint: 'Use BEGIN TRANSACTION, then check for errors before COMMIT.',
            answer: 'BEGIN TRANSACTION;\n  INSERT INTO orders ...;\n  INSERT INTO order_items ...;\n  IF @@ERROR <> 0\n    ROLLBACK TRANSACTION;\n  ELSE\n    COMMIT TRANSACTION;',
          },
        ],
        quiz: [
          {
            question: 'Which ACID property ensures that if a transaction is committed, the data survives a system crash?',
            options: ['Atomicity', 'Consistency', 'Isolation', 'Durability'],
            answer: 3,
            explanation: 'Durability guarantees that committed transactions are permanently saved — typically via write-ahead logging — and survive crashes, power failures, or restarts.',
          },
          {
            question: 'What is the main security benefit of stored procedures?',
            options: [
              'They encrypt the data',
              'You can grant EXECUTE permission without granting direct table access',
              'They prevent SQL injection automatically',
              'They compress query results',
            ],
            answer: 1,
            explanation: 'You can grant a user EXECUTE on a procedure without giving them SELECT/INSERT/UPDATE/DELETE on the underlying tables — enforcing controlled, audited data access.',
          },
        ],
        tags: ['stored procedure', 'transaction', 'ACID', 'COMMIT', 'ROLLBACK', 'TRY CATCH', 'control flow'],
      },
    ],
  },
];

// ─── Combined search index ────────────────────────────────────────────────────

export const ALL_MODULES: LessonModule[] = [...EXCEL_MODULES, ...SQL_MODULES];

export function searchLessons(query: string): { lesson: Lesson; module: LessonModule }[] {
  if (!query.trim()) return [];
  const q = query.toLowerCase();
  const results: { lesson: Lesson; module: LessonModule }[] = [];

  ALL_MODULES.forEach((mod) => {
    mod.lessons.forEach((lesson) => {
      const searchText = [
        lesson.title,
        lesson.summary,
        lesson.explanation,
        ...lesson.tags,
        ...lesson.objectives,
      ]
        .join(' ')
        .toLowerCase();

      if (searchText.includes(q)) {
        results.push({ lesson, module: mod });
      }
    });
  });

  return results;
}
```


---

## FILE 29 — `src/components/sections/learning/` (EMPTY DIRECTORY)

This directory exists but contains **no files**. It is where the following components need to be built:

| File to create | Purpose |
|----------------|---------|
| `LearningSection.tsx` | Main browse view: module list + lesson cards, sidebar navigation |
| `LessonViewer.tsx` | Full lesson display: explanation, examples, exercises, per-lesson quiz |
| `SearchSection.tsx` | Search input + debounced results using `searchLessons()` from lessons.ts |
| `ModuleCard.tsx` | Card for each module (icon, title, color, lesson count, phase) |
| `LessonCard.tsx` | Card for individual lesson (title, duration, difficulty badge) |
| `ExercisePanel.tsx` | Exercise component with hint reveal and answer reveal |
| `CodeBlock.tsx` | Styled preformatted code display (install react-syntax-highlighter) |

See Section 33 of the handover document for exact step-by-step build instructions.

---

## SUMMARY: ALL 29 FILES

| # | File | Type | Status |
|---|------|------|--------|
| 1 | `package.json` | Config | ✅ Complete |
| 2 | `vite.config.ts` | Config | ✅ Complete |
| 3 | `tsconfig.json` | Config | ✅ Complete |
| 4 | `tsconfig.node.json` | Config | ✅ Complete |
| 5 | `tailwind.config.js` | Config | ✅ Complete |
| 6 | `postcss.config.js` | Config | ✅ Complete |
| 7 | `vercel.json` | Config | ✅ Complete |
| 8 | `.eslintrc.cjs` | Config | ✅ Complete |
| 9 | `.gitignore` | Config | ✅ Complete |
| 10 | `index.html` | HTML | ✅ Complete |
| 11 | `public/favicon.svg` | SVG | ✅ Complete |
| 12 | `src/main.tsx` | React | ✅ Complete |
| 13 | `src/index.css` | CSS | ✅ Complete |
| 14 | `src/types/index.ts` | TypeScript | ✅ Complete |
| 15 | `src/App.tsx` | React | ✅ Complete |
| 16 | `src/components/NavBar.tsx` | React | ✅ Complete |
| 17 | `src/components/Footer.tsx` | React | ✅ Complete |
| 18 | `src/components/ui/GlassCard.tsx` | React | ✅ Complete |
| 19 | `src/components/ui/Badge.tsx` | React | ✅ Complete |
| 20 | `src/components/sections/HeroSection.tsx` | React | ✅ Complete |
| 21 | `src/components/sections/RoadmapSection.tsx` | React | ✅ Complete |
| 22 | `src/components/sections/QuizSection.tsx` | React | ✅ Complete |
| 23 | `src/components/sections/ProgressSection.tsx` | React | ✅ Complete |
| 24 | `src/components/sections/InterviewSection.tsx` | React | ✅ Complete |
| 25 | `src/data/roadmaps.ts` | Data | ✅ Complete |
| 26 | `src/data/quiz.ts` | Data | ✅ Complete |
| 27 | `src/data/interview.ts` | Data | ✅ Complete |
| 28 | `src/data/lessons.ts` | Data | ✅ Complete (1,368 lines) |
| 29 | `src/components/sections/learning/*` | React | ⚠️ TO BE BUILT |

---

*End of Appendix D — Complete Source Code*
*Total document: Original handover (1,941 lines) + this appendix (all source files verbatim)*
*Generated June 2025 by Claude (Anthropic) for handover to Google Gemini*
