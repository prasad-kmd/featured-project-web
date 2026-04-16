# Engineering Workspace

A high-performance, technically-inspired documentation and engineering portfolio platform. Optimized for mechatronics research, digital architecture, and high-fidelity project showcasing.

---

[![Framework: Next.js 16](https://img.shields.io/badge/Next.js-16-000000?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![Language: TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org/)
[![Style: Tailwind CSS 4](https://img.shields.io/badge/Tailwind_CSS-4-38B2AC?style=for-the-badge&logo=tailwind-css)](https://tailwindcss.com/)
[![Runtime: React 19](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react)](https://react.dev/)
[![Animation: Framer Motion](https://img.shields.io/badge/Framer_Motion-12-ff69b4?style=for-the-badge&logo=framer)](https://www.framer.com/motion/)
[![Deployment: Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://vercel.com/)

---

## 🚀 Vision: Engineering Excellence
Engineering Workspace isn't just a portfolio; it's a technical dashboard designed to communicate complex engineering concepts with precision and style.

### ✨ Core Features
- **📂 File-Based CMS:** Zero-database architecture. Manage everything via Markdown (`.md`) and HTML (`.html`).
- **🎨 Technical UI Identity:** A custom design language featuring geometric grid systems, terminal-style code blocks, and dynamic bento grids.
- **🛠️ Advanced pipeline:**
  - **Premium Highlighting:** VS Code-accurate Shiki highlighting with Mac-style window UI.
  - **LaTeX Mastery:** First-class support for complex mathematical notation.
  - **Interactive Knowledge:** Injectable quiz components for educational content.
- **✍️ Multi-Author System:** Detailed contributor "Dossiers" with social links and contribution metrics.
- **🛡️ Enterprise Grade:** Spam-protected contact forms, temporary mail domain blocking, and secure link bridging.

## 🏁 Getting Started

### 1. Installation & Local Setup
```bash
# Clone the repository
git clone https://github.com/prasad-kmd/featured-project-web.git

# Navigate to project
cd featured-project-web

# Install dependencies
pnpm install
```

### 2. Branding & Configuration
Modify `lib/config.ts` to define your identity:
```typescript
export const siteConfig = {
  title: "Your Engineering Space",
  author: "Engineer Name",
  githubUsername: "your-handle",
  // social links, toolbox, etc.
};
```

### 3. Launch Development Server
```bash
pnpm dev
```
Explore the workspace at `http://localhost:3000`.

## 📝 Content Management
Adding content requires no coding. Simply create a file in the appropriate directory within `/content`.

### Frontmatter Standard
All content files must include YAML frontmatter:
```markdown
---
title: "Computational Fluid Dynamics in Robotics"
slug: "cfd-robotics"
date: "2025-08-15"
status: "Published"
author: "your-author-slug"
tags: ["CFD", "Robotics", "Research"]
---
```

### Interactive Components
Use shortcodes directly in your Markdown:
- **Math:** `$E=mc^2$` or `$$\text{Full Equation}$$`
- **Quizzes:** `[quiz] { ...json data... } [/quiz]`
- **Alerts:** `> [!NOTE] This is a GitHub-style alert.`

## 📂 Project Navigation
```text
├── app/              # Next.js Routes & API (Logic)
├── components/       # UI Library & Feature Components
├── content/          # The "Database" (Markdown/HTML files)
├── lib/              # CMS Pipeline & Shared Utilities
├── public/           # Static Assets (Images, Fonts, Data)
├── hooks/            # Custom React Hooks
└── types/            # Shared TypeScript Interfaces
```

## 🛠 Tech Stack & Tools
- **Framework:** Next.js 16 (App Router)
- **Content:** Marked, Shiki, KaTeX, Gray-matter
- **Animations:** Framer Motion, GSAP
- **Icons:** Lucide React
- **Theme:** next-themes

---
Built with precision for the Engineering Community.
