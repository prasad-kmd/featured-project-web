# AI Agent Guidelines: Engineering Workspace

## 1. Core Mission
You are an AI Software Engineer assisting in the development of the **Engineering Workspace**. Your goal is to maintain high-fidelity documentation and robust technical tools while ensuring extreme performance and type safety.

---

## 2. Coding Standards

### TypeScript
- **No `any` Types:** Use interfaces and generics. If a type is unknown, use `unknown` and type guards.
- **Strict Mode:** All new code must comply with strict TypeScript rules.
- **Enums vs. Const Objects:** Prefer `as const` objects for better tree-shaking and type inference.

### Tailwind CSS 4
- **Theme First:** Always use theme variables (e.g., `text-primary`, `bg-card`) rather than hardcoded hex values.
- **Utility Composition:** Keep classes readable; use `@apply` in CSS files for complex, repetitive patterns.

### GSAP & Animations
- **Cleanup:** Always use `gsap.context()` or clean up tweens/timelines in `useEffect` returns to prevent memory leaks.
- **Performance:** Prefer GSAP for complex timelines and Framer Motion for simple layout entry/exit animations.

---

## 3. Workflow Guidelines

### Content Modifications
- When adding new content categories, update `lib/content.ts` and ensure the corresponding `ContentItem` type is updated.
- Always check for both `.md` and `.html` support.

### Adding Engineering Tools
1.  Place components in `components/tools/[tool-name]/`.
2.  Use the `ToolLayout` wrapper for consistency.
3.  Ensure all mathematical logic is extracted into a testable utility function in `lib/math/`.

### CMS Updates
- If modifying the Notion integration, ensure the local file fallback remains functional.
- Validate JSON schema for quizzes before injection.

---

## 4. Verification Procedures
- **Linting:** Run `pnpm lint` before submitting any change.
- **Building:** Ensure `pnpm build` passes, as many content-loading errors only appear during the build phase.
- **Type Checking:** Run `tsc --noEmit` to verify type safety across the entire workspace.

---

## 5. UI/UX Consistency
- All interactive elements should respond to the current **Accent Color**.
- Maintain the "Engineering Excellence" aesthetic: high contrast, clean lines, and subtle technical grid patterns.
- Ensure all outbound links use the `SafeLink` wrapper or the `/external-link` route logic.
