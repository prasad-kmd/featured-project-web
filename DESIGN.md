# Architecture & Design: Engineering Workspace

## 1. Vision & Identity
Engineering Workspace is a specialized platform for technical documentation. Its design identity, "Engineering Excellence," is characterized by structured layouts, geometric precision, and a code-first aesthetic.

## 2. Technical Stack
- **Framework:** Next.js 16 (App Router)
- **Runtime:** React 19
- **Styling:** Tailwind CSS 4
- **Animation:** Framer Motion (Orchestration), GSAP (Complex interactions)
- **State Management:** React Context API + Custom Hooks
- **Content Pipeline:** Unified (Remark/Rehype), Shiki, KaTeX

## 3. Core Architecture

### 3.1 File-Based CMS Pipeline
The CMS is the heart of the platform. It operates on a transformation pipeline that converts static files into rich interactive experiences.

#### Transformation Lifecycle:
1. **Ingestion:** `lib/content.ts` reads files from the `content/` directory based on the requested route.
2. **Metadata Extraction:** `gray-matter` parses the YAML frontmatter to populate the `ContentItem` interface.
3. **Markdown Processing:**
   - **Parsing:** `marked` converts Markdown to HTML.
   - **Highlighting:** `shiki` identifies code blocks and applies `one-dark-pro` theming. It also wraps blocks in a custom "Mac-style" UI.
   - **Math Protection:** Display math (`$$...$$`) is wrapped in protected `<div>` tags to prevent Markdown parser interference.
4. **Enrichment (Static):**
   - **Heading IDs:** Regex-based injection of IDs into headers for Table of Contents (TOC) generation.
   - **Alerts:** Transformation of blockquotes into GitHub-style alerts (`[!NOTE]`).
5. **Sanitization:** Removal of `<script>` tags to ensure security.
6. **Client-Side Hydration:**
   - **Quiz Injection:** The `ContentRenderer` identifies quiz placeholders and hydrates them with the `Quiz` React component.
   - **Math Rendering:** `katex` auto-render scans the hydrated DOM for math expressions.
   - **Link Processing:** External links are modified to route through the `/external-link` bridge.

### 3.2 State & Logic Management
The platform uses a decentralized state approach, leveraging React Context for cross-cutting concerns.

- **`BookmarksContext`:** Manages user-saved content in `localStorage`.
- **`SidebarContext`:** Orchestrates the navigation state and collapsible behaviors.
- **`ThemeContext`:** Handles dark/light mode switching via `next-themes`.

### 3.3 Custom Hook System
- **`useAccentColor`:** Manages the dynamic primary color system.
- **`usePersistentState`:** A wrapper around `useState` that syncs with `localStorage`.
- **`useDebounce`:** Optimizes search and filtering operations.

## 4. UI/UX Systems

### 4.1 "Engineering Excellence" Design System
The visual language is defined by:
- **Local Fonts:** Precise typography using `JetBrains Mono` and `Inter`.
- **Geometric Grid Systems:** Used as background patterns to reinforce the engineering theme.
- **Interactive Feedback:** `ClickSpark` for tactile input feedback and `Framer Motion` for layout transitions.

### 4.2 Component Categories
- **Layout Primitives:** `Container`, `Section`, `Grid`.
- **Technical UI:** `ContentRenderer`, `TOC`, `ArticleSidebar`.
- **Interactive Widgets:** `Quiz`, `MagicBento`, `SkillMatrix`.
- **Utility Components:** `BookmarkButton`, `AIContentIndicator`.

## 5. Performance Strategy
- **Static Generation:** Extensive use of `generateStaticParams` for content routes.
- **Aggressive Caching:** Use of React `cache` for filesystem-heavy operations.
- **Dynamic Imports:** Non-critical libraries (like KaTeX auto-render) are loaded on-demand.
- **Optimized Assets:** Local fonts are configured with `display: swap` to minimize FOIT.

## 6. Security Model
- **Input Sanitization:** HTML is sanitized during the build process.
- **Domain Whitelisting:** Contact forms use a temp-mail blacklist.
- **Bridge Redirects:** External navigation is intercepted to provide user warnings.
