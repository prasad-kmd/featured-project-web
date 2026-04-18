# System Design Architecture: Engineering Workspace

## 1. Overview
The **Engineering Workspace** is a high-performance, modular platform designed for technical documentation, engineering calculations, and professional portfolio management. It utilizes a hybrid architecture that combines static speed with dynamic content management.

---

## 2. Technology Stack
- **Framework:** Next.js 16 (App Router)
- **Language:** TypeScript 5+ (Strict Type Safety)
- **Styling:** Tailwind CSS 4 (Theme-first architecture)
- **Animations:** GSAP 3 (Complex Interactions) & Framer Motion (Layouts)
- **Content:** Hybrid (Local Markdown/HTML + Notion Headless CMS)
- **Icons:** Lucide React

---

## 3. Core Architectural Modules

### A. Hybrid Content Management System (HCMS)
The HCMS is the heart of the platform. It abstracts content source from content rendering.
1.  **Content Loaders (`lib/content.ts` & `lib/notion.ts`):** Parallel pipelines that fetch data from the local file system (`content/` directory) and the Notion API.
2.  **Normalization Layer:** Transforms raw Markdown, HTML, or Notion Blocks into a standardized `ContentItem` interface.
3.  **Content Renderer (`components/content-renderer.tsx`):** A universal component that processes standardized content, injecting interactive elements like KaTeX math, Shiki code blocks, and Quiz components.

### B. Engineering Toolbox
A suite of self-contained React components located in `app/tools/`.
- **Atomic Design:** Each tool is a standalone module with its own state logic and UI.
- **Shared Math Lib:** Utilizes a common utility layer for complex calculations (e.g., Matrix operations, unit conversions).
- **Export Engine:** Uses `html2canvas` and `jsPDF` to allow users to export technical results.

### C. UI/UX Layer
- **Global State:** Managed via React Context API (Theme, Sidebar, Bookmarks, Accent Colors).
- **Navigation:** A dual-mode system featuring a persistent `Navigation` sidebar and a context-aware `FloatingNavbar`.
- **Command Palette (`search.tsx`):** A site-wide indexer that provides instant access to content, tools, and external feeds.

---

## 4. Component Hierarchy
```text
RootLayout
├── ThemeProvider
│   ├── AccentColorInitializer
│   ├── SidebarProvider
│   │   ├── BookmarksProvider
│   │   │   ├── ViewTransitions
│   │   │   │   ├── CustomContextMenu
│   │   │   │   ├── FloatingNavbar
│   │   │   │   ├── Navigation (Sidebar)
│   │   │   │   ├── Main Content Area
│   │   │   │   │   ├── {Page Content}
│   │   │   │   │   └── Footer
│   │   │   │   └── Toaster
```

---

## 5. Data Flow
1.  **Request:** User navigates to a route (e.g., `/blog/[slug]`).
2.  **Server Action:** `getContentItem` is called. It checks the local cache, then the file system, then Notion.
3.  **Processing:** Content is parsed for frontmatter, Shiki code highlighting is applied server-side.
4.  **Hydration:** Client-side components (KaTeX, Quizzes, GSAP) hydrate and animate the static content.
5.  **Interaction:** User actions (bookmarks, accent changes) are persisted to `localStorage` via custom hooks.

---

## 6. Performance Strategies
- **Server-Side Rendering (SSR):** Used for all content pages to ensure SEO and fast initial paint.
- **Static Site Generation (SSG) / ISR:** Used for stable routes like tools and landing pages.
- **Dynamic Imports:** Engineering tools are code-split to reduce initial bundle size.
- **Asset Optimization:** Next.js Image component and local font hosting for minimal layout shift.
