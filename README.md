# Engineering Workspace

A modern, high-performance technical documentation and engineering portfolio platform built with **Next.js 16**, **Tailwind CSS 4**, and **TypeScript**. Optimized for mechatronics research, digital architecture, and high-fidelity documentation.

---

[![Framework: Next.js 16](https://img.shields.io/badge/Next.js-16-000000?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![Language: TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org/)
[![Style: Tailwind CSS 4](https://img.shields.io/badge/Tailwind_CSS-4-38B2AC?style=for-the-badge&logo=tailwind-css)](https://tailwindcss.com/)
[![Runtime: React 19](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react)](https://react.dev/)
[![Animation: Framer Motion](https://img.shields.io/badge/Framer_Motion-12-ff69b4?style=for-the-badge&logo=framer)](https://www.framer.com/motion/)
[![Deployment: Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://vercel.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

---

## ✨ Features

### 🚀 Performance-First Architecture
- **Next.js 16 App Router:** Lightning-fast server-side rendering and minimal client-side hydration.
- **Zero-Database CMS:** Manage your entire site via Markdown (`.md`) and HTML (`.html`) files. No complex database management or migrations required.
- **Static Generation:** Optimized for speed with full support for `generateStaticParams` and aggressive caching.

### 🎨 Unique Design Identity ("Engineering Excellence")
- **Redesigned Hero (v7):** A technical dashboard aesthetic featuring a timed carousel of latest works, geometric grid systems, and code-focused visual accents.
- **Magic Bento Grid:** A dynamic, interactive layout system for showcasing key highlights and skills.
- **Specialized Content Cards:** Distinct visual identities for Blog, Articles, and Projects to help users distinguish between different content types.
- **Technical Wiki:** A structured digital garden designed for persistent knowledge and extensive documentation.

### 🛠️ Advanced Technical Pipeline
- **Premium Syntax Highlighting:** Powered by Shiki with VS Code-accurate themes (One Dark Pro) and a custom Mac-style terminal UI.
- **LaTeX Math Support:** Full math notation rendering via KaTeX ($...$ and $$...$$).
- **Interactive Quizzes:** Inject dynamic, JSON-encoded quiz components directly into your Markdown content.
- **GitHub-style Alerts:** Native support for `[!NOTE]`, `[!TIP]`, `[!WARNING]`, and `[!CAUTION]` blockquotes.

### 🛡️ Enterprise-Grade Utilities
- **Spam Protection:** Integrated temp-mail domain blocker for the contact form via `public/data/tempmail.json`.
- **Smart Table of Contents:** Automatically generated TOC with active-state scroll tracking for long-form articles.
- **Search & Command Palette:** Global `Cmd+K` search modal for instant navigation across the entire platform.
- **Secure Link Bridge:** Protects users with a transition page for all external links.

### ✍️ Authors System
- **Contributor Dossiers:** Comprehensive directory of contributors with high-fidelity profile pages, social integration, and contribution metrics.

---

## 🚀 Getting Started

### 1. Prerequisites
- **Node.js**: v20.x or higher
- **Package Manager**: `pnpm` (recommended)

### 2. Installation & Setup
```bash
# Clone the repository
git clone https://github.com/prasad-kmd/featured-project-web.git

# Navigate to the project directory
cd featured-project-web

# Install dependencies
pnpm install

# Create local data directory if missing
mkdir -p public/data
```

### 3. Identity Configuration
Customize the workspace by editing `lib/config.ts`:
```typescript
export const siteConfig = {
  title: "Your Workspace Name",
  author: "Your Name",
  githubUsername: "your-handle",
  url: "https://your-domain.com",
  // social links, toolbox, contact info, etc.
};
```

### 4. Development & Production
```bash
# Start development server
pnpm dev

# Build for production
pnpm build
pnpm start
```
The site will be available at `http://localhost:3000`.

---

## 📝 Content Management

To add new content, create a file in the appropriate directory within `content/`.

### Frontmatter Example
All files require YAML frontmatter to populate metadata:
```markdown
---
title: "Computational Kinematics in Robotics"
slug: "computational-kinematics"
date: "2025-05-15"
status: "Published"
description: "In-depth analysis of mechatronic system efficiency."
author: "your-author-slug"
tags: ["Engineering", "Research"]
category: "Mechatronics"
---
```

### Interactive Shortcodes
- **Math:** `$E=mc^2$`
- **Quizzes:**
  ```text
  [quiz]
  {
    "question": "What is the primary law of robotics?",
    "options": ["Don't harm humans", "Obey orders", "Self-protection"],
    "answer": 0
  }
  [/quiz]
  ```

---

## 📂 Project Structure

```text
├── app/              # Next.js App Router (Routes & API)
├── components/       # Reusable UI library and features
├── content/          # Your "Database" (Markdown/HTML files)
├── lib/              # CMS Pipeline, utilities, and config
├── hooks/            # Custom React hooks for global state
├── public/           # Static assets (Fonts, Images, JSON data)
└── types/            # Shared TypeScript definitions
```

## 🛠 Tech Stack
- **Framework:** Next.js 16 (App Router)
- **Styling:** Tailwind CSS 4
- **Syntax Highlighting:** Shiki
- **Math:** KaTeX
- **Animations:** Framer Motion & GSAP
- **Icons:** Lucide React
- **Theme:** next-themes

---

Built with ❤️ for the Engineering Community.
