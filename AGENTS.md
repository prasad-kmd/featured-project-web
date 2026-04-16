# Agent Manual: Operating on Engineering Workspace

This manual provides detailed workflows and standards for AI agents and developers to effectively contribute to and maintain the Engineering Workspace codebase.

## 🤖 Mission Context
Engineering Workspace is a specialized Next.js 16 platform. All operations should prioritize performance, technical aesthetics, and type safety.

## 📂 Repository Navigation

### Core Logic
- `lib/content.ts`: The CMS engine. Modify this to change how Markdown/HTML is processed.
- `lib/animations.ts`: Standardized Framer Motion variants. Use these for UI consistency.
- `lib/config.ts`: Global site metadata and social links.

### Content Hierarchy
- `content/blog/`: News and updates.
- `content/articles/`: Detailed documentation.
- `content/projects/`: Portfolio items.
- `content/wiki/`: Permanent knowledge base.
- `content/authors/`: contributor profiles.

### UI Components
- `components/ui/`: Atomic Radix-based components.
- `components/unique-cards.tsx`: Specialized card designs for different content types.
- `components/content-renderer.tsx`: The client-side bridge for CMS content.

## 🛠 Standard Workflows

### 1. Adding a New Post
1. Identify the target collection (e.g., `projects`).
2. Create `content/projects/slug-name.md`.
3. Fill mandatory frontmatter:
   ```yaml
   ---
   title: "Project Alpha"
   slug: "project-alpha"
   date: "2025-01-01"
   description: "Summary of the project."
   author: "your-author-slug"
   tags: ["Engineering", "Robotics"]
   ---
   ```
4. Verify the new page at `/projects/slug-name`.

### 2. Extending the Content Pipeline
To add a new Markdown syntax (e.g., a custom diagram shortcode):
1. **Parser Level:** Update `marked` extensions in `lib/content.ts`.
2. **HTML Level:** Ensure the extension returns a specific class or data attribute.
3. **Hydration Level:** If interactivity is needed, add a processor to the `useEffect` in `components/content-renderer.tsx`.

### 3. Adding a UI Component
1. Place atomic components in `components/ui/`.
2. Use `cn()` utility for class merging.
3. Ensure the component supports the current theme system (`dark:` classes).
4. Export through a named export for better tree-shaking.

## 📜 Coding Guidelines

### TypeScript
- **No `any`:** Use interfaces or generics. If a type is unknown, use `unknown`.
- **Zod:** Use Zod for any data validation, especially from external sources or environment variables.

### React
- **Composition:** Prefer component composition over deep prop drilling.
- **Hooks:** Extract reusable logic into hooks in the `hooks/` directory.

### Styling
- **Utility First:** Use Tailwind utility classes.
- **Theming:** Use CSS variables for colors (e.g., `text-primary`, `bg-background`).
- **Variants:** Use `class-variance-authority` (CVA) for components with multiple states.

## 🔍 Verification Protocol
Before submitting any code change:
- [ ] **Linting:** Run `pnpm lint`.
- [ ] **Accessibility:** Check that new interactive elements have appropriate ARIA attributes.
- [ ] **Responsiveness:** Verify the change on mobile and desktop viewports.
- [ ] **Themes:** Check both Light and Dark mode appearance.
- [ ] **Content Pipeline:** If `lib/content.ts` was modified, verify all existing post types still render correctly.
