# Improvement Suggestions: Engineering Workspace

This document identifies technical debt, optimization opportunities, and strategic enhancements for the platform.

## 1. Technical Debt & Maintenance
- [ ] **ESLint Dependency Fix:** The flat config currently fails due to a missing `@eslint/eslintrc` dependency. This should be added to `devDependencies`.
- [ ] **Test Coverage:** Currently, the repository has no test suite. Implementing **Vitest** for math utilities and **Playwright** for tool UI verification is high priority.
- [ ] **Type Refinement:** Replace remaining `any` types in `lib/content.ts` (especially in Shiki and Marked extensions) with precise interfaces.
- [ ] **Build Optimization:** Implement `sharp` for image optimization if deployment environment supports it.

## 2. Feature Enhancements
- [ ] **AI Technical Assistant:** Integrate a RAG-based LLM (using the local content as a knowledge base) to answer engineering questions.
- [ ] **Interactive 3D Viewers:** Add support for `.stl` or `.obj` file rendering within projects using **Three.js** or **React Three Fiber**.
- [ ] **Live Collaboration:** Implement **Yjs** or **Ably** for real-time collaboration on engineering tools (e.g., shared whiteboard or calculation sheet).
- [ ] **Advanced Data Viz:** Integrate **D3.js** for more complex engineering data visualizations that exceed the capabilities of Chart.js.

## 3. UI/UX Improvements
- [ ] **Advanced Command Palette:** Add "Action Commands" (e.g., `> Create New Blog`, `> Toggle Theme`) to the search modal.
- [ ] **Personalization:** Allow users to save tool presets and calculation history to a "Local Dashboard".
- [ ] **Accessibility (A11y):** Conduct a full ARIA audit, especially for the complex interactive calculators.

## 4. Performance Optimizations
- [ ] **Edge Runtime:** Explore moving certain API routes (like OG image generation and external feed fetching) to the Edge Runtime for lower latency.
- [ ] **Streaming SSR:** Implement React 19 streaming to show content shells while heavy Shiki highlighting or external data is being processed.
- [ ] **WASM for Heavy Math:** For complex simulations (like PID tuning or 3D rendering), port heavy calculation logic to **Rust/WASM**.
