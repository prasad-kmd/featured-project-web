# Agent Guide: Engineering Workspace

Welcome, Agent. This guide provides technical context and instructions for working within the Engineering Workspace repository.

## 🤖 System Context
Engineering Workspace is a file-based CMS platform built with Next.js 16. It prioritizes technical documentation and high-performance rendering.

## 📂 Key Directories
- `app/`: Next.js App Router routes. Logic for data fetching should primarily happen here.
- `components/`: React components. `ui/` contains Radix-based primitives.
- `content/`: The "database". Markdown (`.md`) and HTML (`.html`) files organized by type.
- `lib/`: Core logic. `content.ts` is the heart of the CMS pipeline.
- `types/`: Shared TypeScript interfaces.

## 🛠 Working with the CMS

### Adding New Content
To add a post, create a file in `content/{blog|articles|projects|wiki}/your-slug.md`.
**Frontmatter Requirements:**
```yaml
---
title: "Title"
date: "YYYY-MM-DD"
description: "Brief summary"
author: "author-slug"
status: "Published"
---
```

### Adding New Content Types
1. Update the `type` union in `lib/content.ts` (specifically in `getContentByType` and `getContentItem`).
2. Create the corresponding directory in `content/`.
3. Create a new route in `app/` (e.g., `app/your-type/page.tsx` and `app/your-type/[slug]/page.tsx`).

### Extending the Pipeline
The transformation pipeline is in `lib/content.ts`. If you need to add support for new Markdown syntax:
1. Add a regex or extension to the `marked` configuration.
2. If it requires client-side hydration, update `components/content-renderer.tsx`.

## 📜 Coding Standards

### TypeScript
- **Avoid `any`:** When encountered, attempt to replace with specific types or `unknown`.
- **Interfaces:** Prefer `interface` for object shapes that might be extended.

### Components
- **Server Components:** Use Server Components by default for better performance.
- **Client Components:** Use `"use client"` only for components requiring interactivity (hooks, event listeners).

### Styling
- **Tailwind CSS 4:** Use utility classes. Avoid arbitrary values unless absolutely necessary.
- **Theming:** Use CSS variables (e.g., `var(--primary)`) to support theme switching.

## 🔍 Verification Checklist
- [ ] Run `pnpm lint` before submitting changes.
- [ ] Ensure new content has a valid slug and frontmatter.
- [ ] Verify that external links are correctly processed by the bridge.
- [ ] Check OpenGraph image generation if adding new routes.
