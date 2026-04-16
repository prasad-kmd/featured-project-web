# Agent Operational Protocol: Engineering Workspace

This manual provides authoritative instructions for AI agents and developers tasked with extending, maintaining, or refactoring the Engineering Workspace platform.

## 1. Environment & Context
Engineering Workspace is a precision-built technical workspace. Maintain the "Engineering Excellence" standard in all operations.

## 2. Core Directory Workflows

### 2.1 Managing Content (`content/`)
The `content/` directory is the repository's database.
- **Hierarchy:** Always place new files in the correct subdirectory (`blog`, `articles`, `projects`, `wiki`, `authors`).
- **File Format:** Prefer `.md` for text-heavy content and `.html` for custom layout pages.
- **Frontmatter Standard:** Every file MUST contain valid YAML frontmatter.
  ```yaml
  title: "Example Title"
  slug: "example-slug" # Must match filename
  date: "YYYY-MM-DD"
  status: "Published"
  author: "author-slug" # Reference content/authors/author-slug.md
  ```

### 2.2 Extending the Pipeline (`lib/content.ts`)
The content pipeline transforms files into components.
- **Refactoring:** When modifying logic, ensure support for both `.md` and `.html` variants.
- **New Features:** If adding a new Markdown shortcode (like quizzes), update the `marked` tokenizer and the `ContentRenderer` hydration logic.

### 2.3 UI Components (`components/`)
- **Atomic Components:** Keep primitives in `components/ui/`.
- **Feature Components:** Group logic-heavy components in the root `components/` directory.
- **Client Directives:** Only use `"use client"` when necessary for hooks or event listeners.

## 3. Technical Pitfalls & Constraints

### 3.1 Type Safety
- **Avoid `any`:** This is a zero-tolerance policy for new code. Use specific library types or `unknown`.
- **Zod:** Use Zod for any new configuration or environment variable definitions.

### 3.2 Performance
- **Client Hydration:** Be mindful of the `ContentRenderer`. Do not add heavy client-side processing that blocks the main thread.
- **Imports:** Always use named imports from `lucide-react` to enable tree-shaking.

### 3.3 Animations
- **Syncing:** Ensure Framer Motion and GSAP animations do not conflict. Prefer Framer Motion for layout-level transitions.

## 4. Operational Tasks

### 4.1 Adding a New Content Type
1. Create a directory in `content/`.
2. Update the `type` union in `lib/content.ts`.
3. Create `app/{type}/page.tsx` (Listing) and `app/{type}/[slug]/page.tsx` (Detail).
4. Register the new type in the `Navigation` component.

### 4.2 Updating Branding
1. Modify `lib/config.ts` for site metadata.
2. Update global CSS variables in `app/globals.css` for primary theme shifts.

## 5. Pre-Submission Checklist
- [ ] Run `pnpm lint` and resolve all warnings.
- [ ] Verify content rendering for Blogs, Projects, and Wiki.
- [ ] Test the "Command + K" search functionality.
- [ ] Validate responsive behavior in both Light and Dark modes.
- [ ] Ensure all external links correctly use the security bridge.
