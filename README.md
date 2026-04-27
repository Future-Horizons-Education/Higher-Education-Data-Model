# Future Horizons Education — Design System

A design system for building accessible, professional academic management interfaces and process visualisations for the UK Higher Education sector.

> **Organisation**: Future Horizons Education
> **Web**: https://www.futurehorizonseducation.com
> **Flagship product**: SJMS — Student Journey Management System

## About Future Horizons Education

Future Horizons Education designs **Academic Management Systems** and **University Systems** grounded in efficient, effective workflow-design principles. The starting point is always the people who deliver and use academic systems: registry staff, programme leaders, academics, professional services, and — centrally — the student.

The design system covers:
- Data design & modelling
- Systems architecture & infrastructure
- Academic management processes
- The student journey & academic pathways to success
- Systems management, administrative processes, and effective university process design

The goal is to **visualise these processes** as crucial tools for academic delivery, and to take those visualised workflows into the design of the **academic systems of the future**.

## Sources

This design system was built from the following attached sources:

| Source | Path / URL | Notes |
|---|---|---|
| Company site | https://www.futurehorizonseducation.com | Brand voice, positioning |
| Flagship codebase | `sjms 2.5 New Build/` (local mount) | React/Tailwind/TS SJMS 2.5. Source of truth for visuals. |
| Reference repo | `RJK134/SJMS-2.5` (GitHub) | Same codebase, version-controlled. |
| Related projects | `Projects/` (local mount) | Equismile, Finance Information App, herm-platform, Inbound to Workflow Hub, kanban, sjms-v4-integrated, UKRI Security App, VetApp, etc. |

The reader is not assumed to have access — sources are listed for traceability.

## Products represented

1. **SJMS 2.5 — Student Journey Management System** (primary product)
   - Four role-based portals: **Staff (Admin)**, **Academic**, **Student**, **Applicant**.
   - Modules: Admissions, Enrolment, Academic Records, Assessment, Student Finance, Timetabling, Attendance, Placements, Student Support, Reporting, Documents, Compliance (UKVI), EC & Appeals, Governance, Accommodation.
   - Tech: React 18 + TypeScript + Tailwind + shadcn/ui on the client; Express/Prisma/PostgreSQL on the server; Keycloak for IAM; n8n for workflow automation.
2. **Process-map visualisations** (e.g. `FHE End-to-End Admissions & Enrolment Process Map.html`, `FHE_Curriculum_Management_Process_Map.html`) — static HTML documentation used to communicate process design.
3. **Global HE Data Atlas** (`global/`) — a reference data model of Higher Education across 16 regional contexts. Each region is a self-contained JSON model of the entities, attributes, reference data, regulators, and interop standards that define that system. A single React viewer (`global/index.html`) renders all 16 models from a common schema.

### Global HE Atlas — regional coverage

| Region | Model | Entities | Anchored on |
|---|---|---|---|
| HERM (reference) | `global/models/herm.json` | 79 | Higher Education Reference Model (CAUDIT/HERM v2) |
| United Kingdom | `global/models/uk.json` | 197 | HESA/OfS, UCAS, SLC, UKVI, QAA |
| United States | `global/models/usa.json` | 67 | IPEDS, Common App, FAFSA/Title IV, regional accreditors |
| Canada | `global/models/canada.json` | 45 | StatCan PSIS, provincial application centres (OUAC, ApplyAlberta) |
| European Union / EHEA | `global/models/eu.json` | 42 | Bologna (ECTS, Diploma Supplement), ESG, Europass/EDC, Erasmus+ |
| Switzerland | `global/models/switzerland.json` | 32 | swissuniversities, SHIS-studex, swissuniversities Admission |
| Australia | `global/models/australia.json` | 44 | TEQSA, TCSI, CHESSN/USI, HELP/FEE-HELP |
| New Zealand | `global/models/new-zealand.json` | 29 | NZQA, TEC, StudyLink, NSN |
| Asia (regional overview) | `global/models/asia.json` | 15 | Cross-cutting standards for East/SE Asia |
| China | `global/models/china.json` | 22 | Gaokao, MoE, CHSI, CSC |
| India | `global/models/india.json` | 29 | UGC, NAAC, NBA, ABC, NEP 2020, CUET |
| Africa | `global/models/africa.json` | 14 | AU/HAQAA, regional QA bodies |
| South America | `global/models/south-america.json` | 21 | CAPES/SISU (BR), SIES (CL), CONEAU (AR) |
| MENA | `global/models/mena.json` | 13 | GCC accreditation bodies, regional ministries |
| Israel | `global/models/israel.json` | 20 | CHE/PBC, psychometric entrance test |
| Russia | `global/models/russia.json` | 19 | Rosobrnadzor, EGE, Federal Register |

**Total: 688 entities** across 16 models, all queryable through one viewer with a region switcher. Each model uses the same node shape (`{id, name, attributes[], relationships[], referenceData[]}`) so they can be compared, diffed, or federated.



## Index

| File / folder | What's inside |
|---|---|
| `README.md` | This file — context, content fundamentals, visual foundations, iconography. |
| `SKILL.md` | Skill manifest for Claude Code / Agent Skills. |
| `colors_and_type.css` | Brand CSS variables — colors, typography, spacing, radii, shadows. |
| `assets/` | Logos, favicons, generic brand imagery. |
| `fonts/` | Self-hosted web fonts (or Google Fonts fallback documented here). |
| `preview/` | Small HTML cards for the Design System tab (swatches, type specimens, components). |
| `ui_kits/sjms/` | High-fidelity recreation of the SJMS 2.5 portals — components + index.html click-through. |
| `data-model/` | HERM-based UK Higher Education data model — ER diagrams, entity definitions, reference data. |
| `global/` | **Global HE Data Atlas** — 16 regional data models (HERM, UK, USA, Canada, EU/EHEA, Switzerland, Australia, NZ, Asia, China, India, Africa, South America, MENA, Israel, Russia) with a unified interactive viewer. Open `global/index.html`. |
| `SJMS Data Model Map.html` | Interactive ER diagram viewer for the SJMS 2.5 schema. |

---

## Content Fundamentals

The brand voice is **professional, considered, and sector-literate** — written for Higher Education leaders, academic staff, and technologists. It is never chatty.

### Tone
- **Authoritative but accessible.** Avoids marketing superlatives. Favours precision.
- **Systems-thinking vocabulary.** "Bounded contexts", "canonical data", "golden journeys", "target operating model", "reference-data governance".
- **Sector-specific.** UCAS, SLC, HESA/OfS, HECoS, SITS, CAS, UKVI, Keycloak — used without apology, because the audience knows them.
- **Student-centred when describing outcomes.** "The student journey", "academic pathways to success".
- **Quietly British.** UK English spellings (colour, centre, realise, programme, enrolment). Dates as DD Mmm YYYY or DD/MM/YYYY.

### Voice & person
- **Third person / institutional "we"** in marketing copy. "We design", "We start with the people who deliver and use…".
- **Second person "you"** only in portal UI, when addressing the end user ("Welcome back, {firstName}", "Your application", "Your modules").
- **No "I"** — this is an organisation, not a personality.

### Casing
- **Sentence case** for UI labels, buttons, page titles, nav items: "New student", "Marks entry", "My programme".
- **Title Case** for product names and formal document titles: "Student Journey Management System", "Admissions & Enrolment Process Map".
- **ALL CAPS** reserved for status codes in data (`ENROLLED`, `SUBMITTED`, `CONDITIONAL_OFFER`) — these are code, not copy; the UI renders them as "Enrolled", "Submitted", "Conditional offer" via a lookup.

### Emoji & decoration
- **No emoji.** None in the product UI, none in docs, none in marketing copy. The brand is sober.
- **No exclamation marks** in UI copy. An empty state says "No recent notifications", not "No notifications yet!".

### Example copy (from the codebase)
- Portal tile subtitles — terse, functional: "Registry, Finance, Admissions, QA & Compliance" / "Programme Leaders, Module Leaders, Tutors & Examiners".
- Dashboard greeting: "Welcome back, {firstName}" / "Here's an overview of your Student Journey Management System".
- Empty states: "No records found", "No recent notifications", "No upcoming events", "—" (em dash) as the null-placeholder in tables.
- Error states are apologetic but precise: "Unable to load dashboard statistics" (accompanied by an AlertCircle icon).
- Footer: "© 2026 Future Horizons Education. All rights reserved."

### Do / Don't

| Do | Don't |
|---|---|
| "Unable to load dashboard statistics" | "Oops! Something went wrong 😬" |
| "No upcoming events" | "Nothing scheduled — enjoy the quiet!" |
| "Sign in" | "Log in now!" |
| "Student number" | "Student ID" (inconsistent with UK HE vocabulary) |
| "Programme" | "Program" |
| "Enrolment", "Centre", "Colour" | "Enrollment", "Center", "Color" |

---

## Visual Foundations

### Palette
The palette is **deep navy + slate + amber**. It reads as institutional, trustworthy, and calm — with a single warm accent to direct attention.

- **Primary — Navy** `#1e3a5f` (scale 50–950). Used for the sidebar background, primary CTAs, page titles (`text-primary-900`), and focus rings. The login screen uses a three-stop navy gradient (`primary-800 → primary-700 → primary-900`).
- **Secondary — Slate** `#334155` (scale 50–950). Body text, muted surfaces, neutral chrome. Effectively the Tailwind `slate` ramp.
- **Accent — Cyan** `#3bb3d9` (scale 50–950). The brand's striated-globe colour. Used sparingly: notification dot, unread indicators, key accent icons, student-portal tile, secondary accent buttons. Never used as a primary CTA — navy is the primary action colour. (The SJMS 2.5 codebase currently ships amber as accent; the **real brand colour is cyan** per the official logo and should be used going forward. Flag with dev team to update `tailwind.config.ts` accent tokens.)
- **Semantic**: `success` `#22c55e`, `warning` `#f59e0b`, `destructive` `#ef4444`, `muted` `#f1f5f9`, `border` `#e2e8f0`.
- **Surface**: `background` `#f8fafc`, `card` `#ffffff`, `foreground` `#0f172a`.

Dark mode exists in the codebase (`.dark` class) but is not currently used in production — keep it supported but design to the light theme.

### Typography
- **Sans (UI body + headings)**: **Inter**, system fallback `system-ui, -apple-system, sans-serif`. (Yes, Inter is on the discouraged-overused list, but it is what the codebase ships. Flag with the client if a bespoke typeface is desired — see *Font substitutions*.)
- **Mono**: **JetBrains Mono**, `Fira Code`, `monospace`. Used for student numbers, IDs, code blocks, and tabular data where column alignment matters.

**Type scale** (matches Tailwind defaults used in-product):

| Token | Size | Weight | Use |
|---|---|---|---|
| `h1` | 1.5rem (24px) / `text-2xl` | 700 | Page titles. On login and hero: 1.875rem (`text-3xl`). |
| `h2` | 1.25rem (20px) / `text-xl` | 600 | Section headers. |
| `h3` | 1.125rem (18px) / `text-lg` | 600 | Card titles inside a page. |
| `body` | 0.875rem (14px) / `text-sm` | 400 | Default UI body. |
| `body-lg` | 1rem (16px) / `text-base` | 400 | Descriptions on login screen. |
| `caption` | 0.75rem (12px) / `text-xs` | 500 | Badges, meta, breadcrumbs. |
| `stat` | 1.5rem (24px) / `text-2xl` | 700 | KPI values in StatCards. |

Line-height is Tailwind defaults. Tracking is Tailwind defaults (no `tracking-tight` except where shadcn Card titles apply it).

### Spacing & layout
- Tailwind 4px base unit. Cards use `p-6` (24px). Stacks use `space-y-6` (24px) between major sections, `space-y-3` (12px) inside cards.
- **Sidebar**: fixed 64 units wide (`w-64` = 256px), full height, navy background.
- **Top bar**: 64px tall (`h-16`), white, bottom-border `#e2e8f0`.
- **Grid**: KPI rows use `grid-cols-1 sm:grid-cols-2 lg:grid-cols-4` with `gap-4`. Two-column sections use `lg:grid-cols-2 gap-6`.
- **Page padding**: `p-4 lg:p-6` on main content.
- **Max read-width** is not enforced — this is a data-dense admin tool.

### Corners & elevation
- **Radius**: `--radius: 0.5rem` (8px). Cards, buttons, inputs, badges (pill `rounded-full`), sidebar tiles `rounded-lg`.
- **Shadows**: minimal. Cards use Tailwind `shadow-sm`. Hover on clickable cards bumps to `shadow-lg` and translates `-translate-y-1`. Profile dropdown uses `shadow-lg`. No heavy drop shadows anywhere.
- **Borders**: 1px `#e2e8f0` for most dividers, inputs, tables. Sidebar dividers use `border-primary-600`.

### Backgrounds
- **Page background**: flat `#f8fafc` (`background`). No repeating patterns, no hand-drawn illustrations, no grain.
- **Hero / marketing surfaces**: navy gradient (`from-primary-800 via-primary-700 to-primary-900`). The FHE website appears to use full-width navy hero sections with inline graphics.
- **Process maps**: full-bleed white with navy/amber accents, treated like printable technical diagrams.

### Animation & interaction
- **Duration**: 150–200ms. Tailwind `transition-colors` / `transition-all`.
- **Easing**: Tailwind default (`ease-in-out`). No bouncy springs.
- **Hover**: interactive cards lift (`hover:-translate-y-1 hover:shadow-lg`). Buttons darken one step (`hover:bg-primary-600`). Nav items get `bg-primary-600/50`.
- **Press**: no scale transforms; default browser active state.
- **Spinners**: Lucide `Loader2` with `animate-spin`. Used for loading tables, KPI skeletons, form submits.
- **Reduced-motion**: the DataTable infinite-scroll path respects `prefers-reduced-motion` and falls back to a manual "Load more" button.
- **No fades, no parallax, no scroll-triggered animation** in product surfaces.

### Transparency, blur, capsules
- **Transparency** is used sparingly: `hover:bg-primary-600/50`, `bg-muted/50` for zebra rows, `bg-black/50` for the mobile sidebar overlay.
- **Backdrop-blur** is not used in-product (no frosted glass).
- **Capsules**: badges are `rounded-full` pills. Avatars are `rounded-full`.
- **Protection gradients** (e.g. over imagery) are not used — the brand doesn't overlay text on photography.

### Imagery tone
When imagery is used (mostly on marketing / process-map covers), it's **cool-toned, desaturated, documentary**. No warm stock-photo students-smiling-in-a-library clichés. Prefer diagrams, workflow illustrations, and schematic visuals.

### Fixed elements
- Sidebar is sticky / full-height on desktop, drawer on mobile.
- Top bar is sticky.
- No floating action buttons.

---

## Iconography

**Primary icon library: [Lucide](https://lucide.dev) / `lucide-react`.** Every icon in the SJMS 2.5 codebase comes from Lucide — `Users`, `GraduationCap`, `BookOpen`, `ClipboardCheck`, `Calendar`, `Bell`, `Search`, `Shield`, `Wallet`, `Hotel`, `FolderOpen`, `Building`, `Building2`, `ChevronDown`, `ChevronRight`, `ChevronUp`, `ChevronsUpDown`, `AlertCircle`, `AlertTriangle`, `Loader2`, `Menu`, `X`, `LogOut`, `LayoutDashboard`, `UserCheck`, `UserPlus`, `TrendingUp`, `TrendingDown`, `FileText`, `FileEdit`, `Download`.

- **Style**: Lucide is a 24×24 line-icon set, 2px stroke, rounded caps and joins, no fill. It is the Feather fork — same visual DNA.
- **Sizing in-product**: `h-4 w-4` for inline / button icons, `h-5 w-5` for nav and standard UI, `h-6 w-6` for mobile menu toggle, `h-3 w-3` for sort chevrons and micro-trend indicators.
- **Colour**: icons inherit `currentColor`. Nav icons are white on navy. Accent icons use `text-accent` or `text-primary`. Muted / decorative icons use `text-muted-foreground`.
- **Delivery**: imported as React components (`import { Users } from 'lucide-react'`). For static HTML artefacts (slides, process maps, design previews), use the Lucide CDN: `https://unpkg.com/lucide@latest` or inline SVGs copied from lucide.dev.

**No icon font**, no custom SVG sprite sheet, no PNG icons. The codebase has not committed its own icon assets.

**No emoji.** Do not use emoji as UI glyphs. Do not use unicode symbols as icons (the one exception: `—` em-dash as a null placeholder in tables).

**Logos**: the FHE brand mark is a **striated globe** — horizontal cyan (`#3bb3d9`) and navy (`#1e3a5f`) bands forming a spherical form, paired with a sans-serif "Future Horizons Education" wordmark. Real raster assets live in `assets/`:
- `fhe-logo-mark.png` — transparent globe mark, works on any background.
- `fhe-logo-onDark.jpg` — full lockup (mark + wordmark in white) on black.
- `fhe-logo-onLight.jpg` — small full-colour lockup on white.

Use `fhe-logo-mark.png` as the sidebar / favicon mark in product UI. Use the full lockup on marketing surfaces where there's room for the wordmark. The "FH" amber tile that appears in older SJMS 2.5 screenshots is a placeholder and should be replaced with the real mark. The favicon is in `assets/favicon.svg`.

**Process-map diagrams** (not in this system but referenced): use boxes with light navy borders, thin amber connectors, Lucide icons inside nodes, and labels in Inter. Treat process maps as the brand's signature visual artefact.

---

## Font substitutions

Inter and JetBrains Mono are loaded via Google Fonts in this design system (self-hostable; see `fonts/`). **No substitutions were required** — both are already on Google Fonts and match the codebase exactly.

> **Action for the client**: if Future Horizons Education has commissioned a bespoke typeface for brand communications, please send the `.woff2` / `.ttf` files and licence terms so we can replace Inter in marketing/process-map surfaces (keep Inter for product UI unless otherwise directed).

---

## Caveats

See end-of-build summary in chat for known gaps and iteration questions.
