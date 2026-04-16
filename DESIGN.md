# Design Document: Engineering Workspace

## Overview
Engineering Workspace is a high-fidelity technical documentation platform and engineering portfolio template. It is designed to bridge the gap between complex technical data and professional, accessible web presentation.

## Core Technologies
- **Framework:** Next.js 16 (App Router)
- **Language:** TypeScript
- **Styling:** Tailwind CSS 4
- **Animations:** Framer Motion & GSAP
- **Content Processing:** Marked (Markdown), Shiki (Syntax Highlighting), KaTeX (Math rendering)
- **CMS:** File-based (Zero-database)

## Architecture

### 1. File-Based CMS Pipeline
The platform uses a custom pipeline to transform raw Markdown and HTML files into rich, interactive pages.

**Flow:**
1. **Source:** Files are stored in `content/{type}/{slug}.md` or `.html`.
2. **Parsing:** `gray-matter` extracts frontmatter metadata and raw content.
3. **Markdown Transformation:** `marked` converts Markdown to HTML.
4. **Enrichment:**
   - **Shiki:** Enhances `<pre><code>` blocks with VS Code-accurate highlighting and a custom "Mac-style" UI wrapper.
   - **Custom Extensions:** Quizzes (`[quiz]...[/quiz]`) and Alerts (`[!NOTE]`) are identified and prepared for hydration.
   - **Heading IDs:** IDs are injected into `<h2>-<h4>` tags for the Table of Contents.
5. **Sanitization:** Script tags are removed to prevent accidental execution.
6. **Hydration (Client-side):** `ContentRenderer` handles:
   - Dynamic Quiz injection via React components.
   - External link modification (redirecting through a bridge page).
   - Math rendering via `katex/contrib/auto-render`.
   - Code copy buttons.

### 2. Data Models

#### ContentItem
Represents a blog post, article, project, or wiki entry.
```typescript
interface ContentItem {
  slug: string;
  title: string;
  date?: string;
  description?: string;
  content: string; // Processed HTML
  rawContent: string;
  final?: boolean;
  firstImage?: string;
  readingTime?: number;
  technical?: string;
  category?: string;
  tags?: string[];
  aiAssisted?: boolean;
  author?: string;
  type?: "blog" | "articles" | "projects" | "tutorials" | "wiki" | "quizzes";
}
```

#### Author
Represents a contributor.
```typescript
interface Author {
  name: string;
  slug: string;
  role: string;
  bio: string;
  avatar: string;
  twitter?: string;
  github?: string;
  linkedin?: string;
  bodyContent?: string;
}
```

### 3. Component Architecture
- **UI Components (`components/ui/`):** Atomic components (Buttons, Inputs, Dialogs) based on Radix UI.
- **Feature Components (`components/`):** High-level components like `FeaturedHero`, `MagicBento`, `ContentRenderer`, and `Quiz`.
- **Layouts:** Use of the App Router's nested layouts for persistent sidebars and navigation.

## UI/UX Philosophy

### Engineering Excellence Aesthetic
The design focuses on a "Technical Dashboard" feel. Key elements include:
- **Geometric Grid Systems:** Used in backgrounds and headers to convey structure.
- **Code-Focused Aesthetics:** Mono fonts, syntax-highlighted accents, and terminal-like wrappers.
- **High-Fidelity Feedback:** Use of Framer Motion for subtle transitions and `ClickSpark` for interactive feedback.

### Accessibility & Performance
- **Theme Support:** Robust dark/light mode via `next-themes`.
- **Responsive Design:** Mobile-first approach with a collapsible sidebar for tablet/desktop.
- **Fast Hydration:** Critical content is rendered on the server, with interactive elements (Quizzes, Math) hydrated progressively on the client.

## Routing Strategy
- **Static Content:** Pages in `/blog`, `/projects`, etc., are statically generated via `generateStaticParams` for optimal performance.
- **Dynamic Utilities:** `/api/og` for dynamic OpenGraph images and `/api/search` for full-text search capability.
