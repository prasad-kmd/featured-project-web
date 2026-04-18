# Enhancement Roadmap: Implementation Tasks

This task list outlines the steps to transform the current repository into the **Perfect Enhanced Combination**.

## Phase 1: Core Foundation & API Integration
- [ ] **Port External API Clients:**
    - [ ] Add `lib/notion.ts` for Notion CMS integration.
    - [ ] Add `lib/github.ts` for repository activity fetching.
    - [ ] Add `lib/arxiv.ts` (if needed) or Blogger RSS logic.
- [ ] **Enhance Content Engine:**
    - [ ] Modify `lib/content.ts` to support hybrid loading (Local Files + Notion).
    - [ ] Implement robust error handling/fallback for CMS failures.
- [ ] **Type Definitions:**
    - [ ] Merge `types/` from all repos to ensure consistency (especially for Notion Blocks and External Feeds).

## Phase 2: Engineering Toolbox (/tools)
- [ ] **Infrastructure:**
    - [ ] Create `app/tools/page.tsx` (Tools Directory).
    - [ ] Set up layout for self-contained tool components.
- [ ] **Component Porting (Electronics):**
    - [ ] Resistor Color Code & Voltage Divider.
    - [ ] 555 Timer & LED Resistor calculators.
- [ ] **Component Porting (Mechanical):**
    - [ ] Moment of Inertia & Beam Deflection.
    - [ ] ISO Fits & Tolerances.
- [ ] **Component Porting (Software/Math):**
    - [ ] Matrix Calculator & Curve Fitter.
    - [ ] LaTeX/MathML Converter.

## Phase 3: UI/UX & Interactivity
- [ ] **Advanced Interactions:**
    - [ ] Integrate `CustomCursor.tsx` with link-aware state.
    - [ ] Integrate `CustomContextMenu.tsx`.
    - [ ] Refine `ClickSpark.tsx` settings for Tailwind 4.
- [ ] **PWA & Performance:**
    - [ ] Port `public/sw.js` and `manifest.json`.
    - [ ] Configure `next-pwa` (or standard Service Worker registration).
    - [ ] Implement View Transitions for route changes.
- [ ] **Command Palette:**
    - [ ] Enhance the search modal to include Tools and External results.

## Phase 4: Page Expansion & Knowledge Base
- [ ] **Knowledge Ecosystem:**
    - [ ] Implement `/glossary` with search and filtering.
    - [ ] Port the specialized Wiki templates.
- [ ] **Community & Social:**
    - [ ] Port `/team` and `/sponsorship` pages.
    - [ ] Implement the `/status` page for real-time updates.
- [ ] **External Discovery:**
    - [ ] Create `/feeds` page aggregating arXiv, Open Library, etc.

## Phase 5: Final Refinement & Polish
- [ ] **Aesthetic Standardization:**
    - [ ] Ensure all ported components use the Tailwind 4 `@theme` variables.
    - [ ] Synchronize accent colors across tools and CMS pages.
- [ ] **Animation Orchestration:**
    - [ ] Use GSAP to create complex entry animations for the new tools.
- [ ] **Documentation:**
    - [ ] Update `README.md` with the new combined features.
    - [ ] Update `AGENTS.md` with instructions for managing the hybrid CMS.
