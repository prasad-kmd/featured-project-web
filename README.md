# Engineering Workspace

A modern, high-performance technical documentation and engineering portfolio platform. Built for mechatronics research, digital architecture, and high-fidelity documentation.

---

[![Next.js](https://img.shields.io/badge/Next.js-16-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-blue?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4-38B2AC?style=for-the-badge&logo=tailwind-css)](https://tailwindcss.com/)
[![Framer Motion](https://img.shields.io/badge/Framer_Motion-12-ff69b4?style=for-the-badge&logo=framer)](https://www.framer.com/motion/)
[![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://vercel.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

---

## ✨ Key Features

- **🚀 Next-Gen Performance:** Built with **Next.js 16** and **React 19** for near-instant page loads and seamless transitions.
- **📂 Zero-Config CMS:** Fully file-based architecture. No databases, no complex setup—just Markdown and HTML.
- **🎨 Technical Excellence UI:** A unique design language inspired by engineering dashboards, featuring:
  - **Geometric Grids:** Structured layout systems.
  - **Magic Bento:** A dynamic, interactive grid for showcasing highlights.
  - **Technical Wiki:** A structured digital garden for persistent knowledge.
- **✍️ Authors System:** High-fidelity contributors directory with detailed "Dossier" profile pages.
- **🛠️ Advanced Documentation Pipeline:**
  - **Shiki Highlighting:** VS Code-accurate syntax highlighting with a premium Mac-style terminal UI.
  - **LaTeX Support:** Full math notation rendering via KaTeX.
  - **Interactive Quizzes:** Inject base64-encoded quizzes directly into your articles.
  - **GitHub-style Alerts:** Native support for `[!NOTE]`, `[!TIP]`, and more.

## 🚀 Quick Start

### 1. Installation

```bash
# Clone the repository
git clone https://github.com/prasad-kmd/featured-project-web.git

# Navigate to the project directory
cd featured-project-web

# Install dependencies
pnpm install
```

### 2. Configuration

Edit `lib/config.ts` to customize your workspace identity:

```typescript
export const siteConfig = {
  title: "Your Engineering Workspace",
  author: "Your Name",
  url: "https://your-domain.com",
  // ... more config
};
```

### 3. Development

```bash
pnpm dev
```
Open [http://localhost:3000](http://localhost:3000) to see your workspace in action.

## 📝 Content Management

Adding content is as simple as creating a file in the `content/` directory.

### Content Types
- `content/blog/`: General updates and news.
- `content/articles/`: Deep-dive technical papers.
- `content/projects/`: Showcasing specific engineering works.
- `content/wiki/`: Permanent knowledge base and documentation.
- `content/authors/`: Profiles for contributors.

### Markdown Example (`content/blog/hello-world.md`)

```markdown
---
title: "Optimizing Robotic Kinematics"
slug: "optimizing-robotic-kinematics"
date: "2025-06-01"
description: "A deep dive into computational efficiency in mechatronics."
author: "your-slug"
tags: ["Robotics", "Math"]
---

# Introduction
Your technical content goes here... Use KaTeX for math: $E=mc^2$

[quiz]
{
  "question": "What is the primary law of robotics?",
  "options": ["Don't harm humans", "Obey orders", "Self-protection"],
  "answer": 0
}
[/quiz]
```

## 🛠 Advanced Usage

### Extending the CMS
To add a new content type:
1. Create a new directory in `content/` (e.g., `content/research/`).
2. Add the type to the `type` union in `lib/content.ts`.
3. Create the corresponding routes in `app/research/`.

### Deployment
This platform is optimized for **Vercel**.
1. Push your code to GitHub.
2. Connect your repository to Vercel.
3. Configure the `NEXT_PUBLIC_GITHUB_USERNAME` and other environment variables if needed.
4. Deploy!

## 📂 Project Structure

```text
├── app/              # App Router (Pages & API)
├── components/       # React Components (UI & Features)
├── content/          # Your "Database" (Markdown/HTML files)
├── lib/              # CMS Pipeline & Configuration
├── public/           # Static Assets (Images, Fonts)
├── styles/           # Global styles & Tailwind config
└── types/            # TypeScript Definitions
```

---

Built with ❤️ for the Engineering Community.
