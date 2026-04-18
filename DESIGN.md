# Design System Documentation

## Overview

This document defines the design system for the Engineering Workspace platform. It covers visual identity, component library, interaction patterns, and accessibility standards.

---

## Table of Contents

1. [Design Principles](#design-principles)
2. [Color System](#color-system)
3. [Typography](#typography)
4. [Spacing & Layout](#spacing--layout)
5. [Components](#components)
6. [Animations](#animations)
7. [Icons](#icons)
8. [Accessibility](#accessibility)
9. [Responsive Design](#responsive-design)
10. [Dark Mode](#dark-mode)

---

## Design Principles

### 1. Technical Excellence

- **Precision:** Clean lines, geometric shapes, engineering aesthetics
- **Clarity:** Information hierarchy, readable typography, clear navigation
- **Functionality:** Every element serves a purpose, no decorative fluff

### 2. Performance-First

- **Fast Loading:** Optimized assets, minimal JavaScript, efficient CSS
- **Smooth Interactions:** 60fps animations, instant feedback
- **Progressive Enhancement:** Core functionality without JavaScript

### 3. Accessibility

- **Inclusive:** WCAG 2.1 AA compliance minimum
- **Flexible:** Multiple input methods (keyboard, touch, mouse)
- **Readable:** High contrast, scalable text, clear focus states

### 4. Consistency

- **Unified Language:** Same patterns across all pages
- **Predictable:** Elements behave as expected
- **Documented:** All components have usage guidelines

---

## Color System

### Primary Palette

```css
/* Brand Colors */
--primary: #2563eb;           /* Engineering Blue */
--primary-hover: #1d4ed8;
--primary-light: #3b82f6;
--primary-dark: #1e40af;

/* Accent Colors (Customizable) */
--accent: #ef4444;            /* Default: Red */
--accent-hover: #dc2626;
--accent-light: #f87171;
```

### Neutral Palette

```css
/* Light Mode */
--background: #ffffff;
--foreground: #0f172a;
--muted: #64748b;
--muted-foreground: #64748b;
--border: #e2e8f0;
--card: #ffffff;
--card-foreground: #0f172a;

/* Dark Mode */
--background: #0f172a;
--foreground: #f8fafc;
--muted: #475569;
--muted-foreground: #94a3b8;
--border: #1e293b;
--card: #1e293b;
--card-foreground: #f8fafc;
```

### Semantic Colors

```css
/* Status Colors */
--success: #22c55e;
--warning: #f59e0b;
--error: #ef4444;
--info: #3b82f6;

/* Functional Colors */
--link: #2563eb;
--link-hover: #1d4ed8;
--code-background: #1e293b;
--code-foreground: #e2e8f0;
```

### Gradient System

```css
/* Background Gradients */
--gradient-primary: linear-gradient(135deg, var(--primary), var(--accent));
--gradient-subtle: linear-gradient(180deg, rgba(var(--primary-rgb), 0.1), transparent);
--gradient-glass: linear-gradient(135deg, rgba(255,255,255,0.1), rgba(255,255,255,0.05));

/* Text Gradients */
--gradient-text: linear-gradient(90deg, var(--primary), var(--accent));
```

### Color Contrast Ratios

| Combination | Ratio | WCAG Level |
|-------------|-------|------------|
| Foreground/Background | 16.1:1 | AAA |
| Muted/Background | 4.5:1 | AA |
| Primary/White | 4.5:1 | AA |
| Success/White | 4.5:1 | AA |

---

## Typography

### Font Families

```css
/* Primary Font - Headings */
--font-heading: 'Amoria Regular', sans-serif;

/* Secondary Font - Body */
--font-body: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;

/* Monospace - Code */
--font-mono: 'JetBrains Mono', 'Fira Code', monospace;

/* Display - Special */
--font-display: 'Mozilla Headline', sans-serif;
```

### Type Scale

```css
/* Heading Sizes */
--text-xs: 0.75rem;      /* 12px */
--text-sm: 0.875rem;     /* 14px */
--text-base: 1rem;       /* 16px */
--text-lg: 1.125rem;     /* 18px */
--text-xl: 1.25rem;      /* 20px */
--text-2xl: 1.5rem;      /* 24px */
--text-3xl: 1.875rem;    /* 30px */
--text-4xl: 2.25rem;     /* 36px */
--text-5xl: 3rem;        /* 48px */
--text-6xl: 3.75rem;     /* 60px */

/* Line Heights */
--leading-none: 1;
--leading-tight: 1.25;
--leading-snug: 1.375;
--leading-normal: 1.5;
--leading-relaxed: 1.625;
--leading-loose: 2;

/* Font Weights */
--font-thin: 100;
--font-light: 300;
--font-normal: 400;
--font-medium: 500;
--font-semibold: 600;
--font-bold: 700;
--font-extrabold: 800;
--font-black: 900;
```

### Heading Styles

```tsx
// H1 - Page Titles
<h1 className="text-4xl md:text-5xl font-black amoriaregular tracking-tight">
  {title}
</h1>

// H2 - Section Headers
<h2 className="text-2xl md:text-3xl font-bold google-sans tracking-tight">
  {section}
</h2>

// H3 - Subsections
<h3 className="text-xl md:text-2xl font-semibold google-sans">
  {subsection}
</h3>

// H4 - Card Titles
<h4 className="text-lg font-semibold google-sans">
  {cardTitle}
</h4>
```

### Body Text Styles

```tsx
// Standard Paragraph
<p className="text-base leading-relaxed text-foreground/90">
  {content}
</p>

// Small Text (Captions, Metadata)
<span className="text-sm text-muted-foreground">
  {metadata}
</span>

// Large Text (Lead paragraphs)
<p className="text-lg leading-relaxed text-foreground/80">
  {lead}
</p>
```

### Code Typography

```tsx
// Inline Code
<code className="px-1.5 py-0.5 rounded-md bg-muted text-sm font-mono">
  {code}
</code>

// Code Blocks
<pre className="p-4 rounded-lg bg-code-background overflow-x-auto">
  <code className="text-sm font-mono text-code-foreground">
    {codeBlock}
  </code>
</pre>
```

---

## Spacing & Layout

### Spacing Scale

```css
/* Base Unit: 4px */
--space-0: 0;
--space-1: 0.25rem;   /* 4px */
--space-2: 0.5rem;    /* 8px */
--space-3: 0.75rem;   /* 12px */
--space-4: 1rem;      /* 16px */
--space-5: 1.25rem;   /* 20px */
--space-6: 1.5rem;    /* 24px */
--space-8: 2rem;      /* 32px */
--space-10: 2.5rem;   /* 40px */
--space-12: 3rem;     /* 48px */
--space-16: 4rem;     /* 64px */
--space-20: 5rem;     /* 80px */
--space-24: 6rem;     /* 96px */
```

### Layout Containers

```css
/* Container Widths */
--container-sm: 640px;
--container-md: 768px;
--container-lg: 1024px;
--container-xl: 1280px;
--container-2xl: 1536px;

/* Container Padding */
--container-padding-x: 1rem;
--container-padding-y: 2rem;
```

### Grid System

```tsx
// Standard Grid
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
  {items}
</div>

// Bento Grid (Featured Content)
<div className="grid grid-cols-1 md:grid-cols-4 grid-rows-4 gap-4 h-[600px]">
  {/* Large featured item */}
  <div className="md:col-span-2 md:row-span-2">{featured}</div>

  {/* Medium items */}
  <div className="md:col-span-2">{medium1}</div>
  <div className="md:col-span-1">{small1}</div>
  <div className="md:col-span-1">{small2}</div>
</div>
```

### Section Spacing

```tsx
// Standard Section
<section className="py-16 md:py-24">
  <Container>{content}</Container>
</section>

// Compact Section
<section className="py-8 md:py-12">
  <Container>{content}</Container>
</section>

// Hero Section
<section className="py-24 md:py-32">
  <Container>{hero}</Container>
</section>
```

---

## Components

### Button Variants

```tsx
// Primary Button
<Button variant="primary">
  Primary Action
</Button>

// Secondary Button
<Button variant="secondary">
  Secondary Action
</Button>

// Outline Button
<Button variant="outline">
  Outline Action
</Button>

// Ghost Button
<Button variant="ghost">
  Ghost Action
</Button>

// sizes: sm, md, lg
// disabled state supported
```

### Card Styles

```tsx
// Standard Card
<Card className="rounded-2xl border border-border/50 bg-card p-6 hover:border-primary/30 transition-all">
  <CardHeader>{title}</CardHeader>
  <CardContent>{content}</CardContent>
  <CardFooter>{actions}</CardFooter>
</Card>

// Glassmorphic Card
<Card className="rounded-[1.5rem] border border-border/40 bg-gradient-to-br from-card/80 to-background/50 backdrop-blur-sm">
  {content}
</Card>

// Interactive Card
<Card className="group cursor-pointer">
  <div className="transition-transform group-hover:scale-[1.02]">
    {content}
  </div>
</Card>
```

### Input Fields

```tsx
// Text Input
<Input
  label="Email"
  placeholder="Enter your email"
  error={errors.email}
  helperText="We'll never share your email"
/>

// Select Dropdown
<Select
  label="Category"
  options={categories}
  placeholder="Select a category"
/>

// Search Input
<SearchInput
  placeholder="Search..."
  onSearch={handleSearch}
  loading={isSearching}
/>
```

### Navigation Components

```tsx
// Floating Navbar
<FloatingNavbar
  links={navLinks}
  logo={logo}
  actions={userActions}
/>

// Sidebar Navigation
<SidebarNav
  items={sidebarItems}
  collapsible
  defaultOpen
/>

// Breadcrumb
<Breadcrumb
  items={[
    { label: 'Home', href: '/' },
    { label: 'Blog', href: '/blog' },
    { label: 'Article Title', href: '/blog/article' }
  ]}
/>
```

### Content Components

```tsx
// Table of Contents
<TableOfContents
  headings={headings}
  activeHeading={activeHeading}
  onHeadingClick={scrollToHeading}
/>

// Code Block with Shiki
<CodeBlock
  code={codeString}
  language="typescript"
  theme="one-dark-pro"
  showLineNumbers
  copyButton
/>

// Callout/Alert
<Callout type="info" icon>
  This is an informational message
</Callout>

<Callout type="warning">
  This is a warning message
</Callout>

<Callout type="tip">
  This is a helpful tip
</Callout>
```

### Interactive Components

```tsx
// Quiz Component
<Quiz
  questions={quizData.questions}
  onComplete={handleComplete}
  showExplanation
/>

// Bookmark Button
<BookmarkButton
  itemId={post.id}
  variant="icon" // or "button"
  showCount
/>

// Search Modal (Cmd+K)
<SearchModal
  isOpen={isOpen}
  onClose={setIsOpen}
  searchResults={results}
/>
```

---

## Animations

### Animation Principles

1. **Purposeful:** Every animation serves a functional purpose
2. **Subtle:** Prefer understated over flashy
3. **Performant:** Use CSS transforms and opacity
4. **Accessible:** Respect `prefers-reduced-motion`

### Duration Scale

```css
--duration-instant: 0ms;
--duration-fast: 150ms;
--duration-normal: 300ms;
--duration-slow: 500ms;
--duration-slower: 1000ms;
```

### Easing Functions

```css
--ease-linear: linear;
--ease-in: cubic-bezier(0.4, 0, 1, 1);
--ease-out: cubic-bezier(0, 0, 0.2, 1);
--ease-in-out: cubic-bezier(0.4, 0, 0.2, 1);
--ease-bounce: cubic-bezier(0.68, -0.55, 0.265, 1.55);
```

### Common Animations

```tsx
// Fade In
<motion.div
  initial={{ opacity: 0 }}
  animate={{ opacity: 1 }}
  transition={{ duration: 0.3 }}
>
  {content}
</motion.div>

// Slide Up
<motion.div
  initial={{ opacity: 0, y: 20 }}
  animate={{ opacity: 1, y: 0 }}
  transition={{ duration: 0.4, ease: 'easeOut' }}
>
  {content}
</motion.div>

// Scale (Hover)
<motion.div
  whileHover={{ scale: 1.02 }}
  transition={{ duration: 0.2 }}
>
  {content}
</motion.div>

// Stagger Children
<motion.div
  variants={{
    container: {
      transition: {
        staggerChildren: 0.1
      }
    }
  }}
>
  {children}
</motion.div>
```

### View Transitions

```tsx
// Page Transition (Scale Effect)
<ViewTransitions effect="scale">
  {children}
</ViewTransitions>

// Custom Transition Config
{
  scale: {
    enter: { scale: 0.95, opacity: 0 },
    enterActive: { scale: 1, opacity: 1 },
    exit: { scale: 1.05, opacity: 0 },
    exitActive: { scale: 1, opacity: 0 }
  }
}
```

### Micro-interactions

```tsx
// Button Press
<button
  className="active:scale-95 transition-transform"
>
  Click Me
</button>

// Link Hover
<a
  className="group inline-flex items-center gap-1"
>
  Learn More
  <ArrowIcon className="group-hover:translate-x-1 transition-transform" />
</a>

// Loading Spinner
<Spinner className="animate-spin" />
```

---

## Icons

### Icon Library

**Primary:** Lucide React
```tsx
import { ArrowRight, Search, Menu } from 'lucide-react';

<ArrowRight className="w-5 h-5" />
```

### Icon Sizes

```css
--icon-xs: 0.75rem;   /* 12px */
--icon-sm: 1rem;      /* 16px */
--icon-md: 1.25rem;   /* 20px */
--icon-lg: 1.5rem;    /* 24px */
--icon-xl: 2rem;      /* 32px */
--icon-2xl: 3rem;     /* 48px */
```

### Icon Usage Guidelines

1. **Consistency:** Use same icon for same action throughout
2. **Clarity:** Choose recognizable, intuitive icons
3. **Accessibility:** Always include aria-labels
4. **Sizing:** Match icon size to context

```tsx
// Good
<button aria-label="Search">
  <Search className="w-5 h-5" />
</button>

// Bad - Missing label
<button>
  <Search className="w-5 h-5" />
</button>
```

---

## Accessibility

### WCAG 2.1 AA Requirements

#### Color Contrast
- Normal text: 4.5:1 minimum
- Large text (18px+): 3:1 minimum
- UI components: 3:1 minimum

#### Keyboard Navigation
- All interactive elements focusable
- Logical tab order
- Visible focus indicators
- No keyboard traps

#### Screen Reader Support
- Semantic HTML structure
- ARIA labels where needed
- Alt text for images
- Live regions for dynamic content

### Focus Styles

```css
/* Default Focus Ring */
.focus-visible {
  outline: 2px solid var(--primary);
  outline-offset: 2px;
}

/* Custom Focus Ring */
.focus-ring-primary {
  @apply focus-visible:ring-2 focus-visible:ring-primary focus-visible:ring-offset-2;
}
```

### Skip Links

```tsx
<SkipLink href="#main-content">
  Skip to main content
</SkipLink>

<main id="main-content">
  {content}
</main>
```

### Form Accessibility

```tsx
<FormField>
  <Label htmlFor="email">Email Address</Label>
  <Input
    id="email"
    type="email"
    aria-describedby="email-error"
    aria-invalid={!!errors.email}
  />
  {errors.email && (
    <ErrorMessage id="email-error">
      {errors.email}
    </ErrorMessage>
  )}
</FormField>
```

---

## Responsive Design

### Breakpoints

```css
--breakpoint-sm: 640px;   /* Small devices */
--breakpoint-md: 768px;   /* Tablets */
--breakpoint-lg: 1024px;  /* Desktops */
--breakpoint-xl: 1280px;  /* Large desktops */
--breakpoint-2xl: 1536px; /* Extra large */
```

### Mobile-First Approach

```tsx
// Start with mobile styles, add breakpoints for larger screens
<div className="
  grid grid-cols-1          /* Mobile: 1 column */
  md:grid-cols-2            /* Tablet: 2 columns */
  lg:grid-cols-3            /* Desktop: 3 columns */
  gap-4
">
  {items}
</div>
```

### Touch Targets

```css
/* Minimum touch target size: 44x44px */
.touch-target {
  min-width: 44px;
  min-height: 44px;
}
```

### Responsive Typography

```tsx
// Fluid typography
<h1 className="text-3xl md:text-4xl lg:text-5xl">
  Responsive Heading
</h1>

// Using clamp()
<style>{`
  .fluid-text {
    font-size: clamp(1.5rem, 4vw, 3rem);
  }
`}</style>
```

---

## Dark Mode

### Implementation

```tsx
// Theme Provider Setup
<ThemeProvider
  attribute="class"
  defaultTheme="system"
  enableSystem
  disableTransitionOnChange
>
  {children}
</ThemeProvider>
```

### Dark Mode Styles

```css
/* Light mode (default) */
:root {
  --background: #ffffff;
  --foreground: #0f172a;
}

/* Dark mode */
.dark {
  --background: #0f172a;
  --foreground: #f8fafc;
}
```

### Dark Mode Images

```tsx
<Image
  src="/img/example.webp"
  alt="Example"
  className="dark:invert dark:brightness-90"
/>
```

### Theme Toggle

```tsx
<ThemeToggle
  variants={['light', 'dark', 'system']}
  showTooltip
/>
```

---

## Component Examples

### Featured Hero Component

```tsx
<FeaturedHero
  title="Engineering Excellence"
  subtitle="Building the future, one project at a time"
  carousel={{
    items: latestProjects,
    interval: 5000,
    showIndicators: true
  }}
  cta={{
    primary: { label: 'View Projects', href: '/projects' },
    secondary: { label: 'Read Blog', href: '/blog' }
  }}
/>
```

### Magic Bento Grid

```tsx
<MagicBento
  items={[
    { type: 'featured', content: featuredProject, span: 'col-span-2 row-span-2' },
    { type: 'standard', content: project1, span: 'col-span-1' },
    { type: 'standard', content: project2, span: 'col-span-1' },
    { type: 'wide', content: article1, span: 'col-span-2' }
  ]}
  layout="bento"
  animated
/>
```

---

## Design Resources

### Figma Files
- [Component Library](#) (internal link)
- [Page Templates](#) (internal link)
- [Icon Set](#) (internal link)

### Code Repositories
- [Component Source](/components)
- [Style Definitions](/app/globals.css)
- [Tailwind Config](/tailwind.config.js)

### Inspiration
- Vercel Design System
- Radix UI Primitives
- shadcn/ui Components

---

**Document Version:** 1.0
**Last Updated:** 2026
**Maintained By:** Design Team