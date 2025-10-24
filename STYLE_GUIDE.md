# qepi. Packing Planner - Design System

**Quick Reference Guide for Consistent Styling**

---

## 🎯 Golden Rule

**Always use CSS variables. Never hardcode values.**

When you need spacing, colors, shadows, etc. → check this guide → use the variable.

---

## Design Tokens Reference

### Spacing (Based on 4px Grid)

```css
--spacing-xs: 4px;      /* Micro spacing, tight gaps */
--spacing-sm: 8px;      /* Small gaps between related items */
--spacing-md: 12px;     /* Default spacing, most common */
--spacing-lg: 16px;     /* Medium spacing */
--spacing-xl: 20px;     /* Large spacing */
--spacing-2xl: 24px;    /* Section spacing */
--spacing-3xl: 32px;    /* Major section spacing */
--spacing-4xl: 40px;    /* Page-level spacing */
--spacing-5xl: 48px;    /* Extra large spacing */
--spacing-6xl: 60px;    /* Modal/card padding */
```

**Usage Examples:**
```css
✅ padding: var(--spacing-md) var(--spacing-lg);
✅ gap: var(--spacing-sm);
✅ margin-bottom: var(--spacing-2xl);

❌ padding: 12px 16px;
❌ gap: 8px;
❌ margin-bottom: 24px;
```

---

### Border Radius (Shape Scale)

```css
--radius-xs: 4px;       /* Minimal rounding */
--radius-sm: 8px;       /* Small elements, inputs */
--radius-md: 10px;      /* Small buttons, small cards */
--radius-lg: 12px;      /* Standard buttons, cards */
--radius-xl: 16px;      /* Primary buttons, large cards */
--radius-2xl: 20px;     /* Modals, dialogs */
--radius-3xl: 24px;     /* Extra large modals */
--radius-full: 50%;     /* Circles */
--radius-round: 9999px; /* Fully rounded pills/badges/tags */
```

#### Border Radius Usage Rules

**Buttons**: Use `--radius-xl` (16px) for a balanced, modern look
```css
.btn, .new-trip-cta-btn {
    border-radius: var(--radius-xl);
}
```

**Pills/Badges/Tags**: Use `--radius-round` (9999px) for fully rounded appearance
```css
.trip-duration-badge,
.trip-countdown-badge,
.trip-socket-inline,
.badge-new {
    border-radius: var(--radius-round);
}
```

**Usage Examples:**
```css
✅ border-radius: var(--radius-xl);     /* Buttons */
✅ border-radius: var(--radius-round);  /* Pills/badges */
✅ border-radius: var(--radius-2xl);    /* Cards/modals */

❌ border-radius: 12px;
❌ border-radius: 50%;
❌ border-radius: 9999px;  /* Use var(--radius-round) instead */
```

---

### Elevation (Box Shadows)

```css
--shadow-none: none;
--shadow-xs: 0 1px 2px 0 rgba(0, 0, 0, 0.05);       /* Subtle hint */
--shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.06);         /* Slight elevation */
--shadow-md: 0 2px 8px rgba(0, 0, 0, 0.08);         /* Cards, raised elements */
--shadow-lg: 0 4px 15px rgba(0, 0, 0, 0.1);         /* Modals, popovers */
--shadow-xl: 0 10px 40px rgba(0, 0, 0, 0.15);       /* Large modals */
--shadow-sidebar: 2px 0 10px rgba(0, 0, 0, 0.05);   /* Sidebar specific */
```

**Accent Shadows:**
```css
--shadow-accent-sm: 0 3px 12px var(--accent-shadow);
--shadow-accent-md: 0 4px 16px var(--accent-shadow);
```

**Usage Examples:**
```css
✅ box-shadow: var(--shadow-md);
✅ box-shadow: var(--shadow-accent-sm);

❌ box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
```

---

### Typography

#### Font Family

**Primary Font**: Nunito (600, 700, 800 weights)
**Logo Font**: Sugo Pro Display (900 weight, bold geometric display font)

```css
body {
    font-family: 'Nunito', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
}

.sidebar-logo {
    font-family: 'Sugo Pro Display', sans-serif;
    font-size: 40px;
    font-weight: 900;
    letter-spacing: -3px;
}
```

#### Typography Scale

**Fluid/Responsive Scale (Preferred)**
```css
--text-xs: clamp(0.625rem, 0.6rem + 0.15vw, 0.6875rem);   /* 10-11px */
--text-sm: clamp(0.75rem, 0.72rem + 0.2vw, 0.8125rem);    /* 12-13px */
--text-base: clamp(0.8125rem, 0.78rem + 0.2vw, 0.875rem); /* 13-14px */
--text-lg: clamp(0.9375rem, 0.9rem + 0.25vw, 1.0625rem);  /* 15-17px */
--text-xl: clamp(1.125rem, 1.05rem + 0.35vw, 1.375rem);   /* 18-22px */
--text-2xl: clamp(1.5rem, 1.35rem + 0.75vw, 2rem);        /* 24-32px */
--text-3xl: clamp(2rem, 1.75rem + 1.25vw, 2.75rem);       /* 32-44px */
```

**Fixed Typography (Use sparingly)**
```css
--text-fixed-9: 9px;
--text-fixed-10: 10px;
--text-fixed-11: 11px;
--text-fixed-12: 12px;
--text-fixed-13: 13px;
--text-fixed-14: 14px;
--text-fixed-16: 16px;
--text-fixed-18: 18px;
--text-fixed-20: 20px;
--text-fixed-24: 24px;
--text-fixed-32: 36px;
```

**Font Weight Guidelines:**
- `font-weight: 600` - Semibold (buttons, labels, navigation)
- `font-weight: 700` - Bold (headings, emphasis)
- `font-weight: 800` - Extra bold (logo, hero text)

**Usage Examples:**
```css
✅ font-size: var(--text-base);
✅ font-size: var(--text-sm);
✅ font-family: 'Nunito', sans-serif;
✅ font-weight: 600;

❌ font-size: 14px;
❌ font-size: 24px;
❌ font-weight: 500;
```

---

### Motion & Transitions

```css
--duration-fast: 0.15s;     /* Quick hover effects */
--duration-normal: 0.2s;    /* Standard transitions */
--duration-slow: 0.3s;      /* Smooth state changes */

--easing-standard: ease;
--easing-smooth: cubic-bezier(0.2, 0, 0, 1);
```

**Usage Examples:**
```css
✅ transition: all var(--duration-normal) var(--easing-standard);
✅ transition: transform var(--duration-fast);

❌ transition: all 0.3s;
❌ transition: all 0.2s ease;
```

---

### Color Palette

#### Brand Colors

**Primary Accent - Pear**
```css
--accent-primary: #CCE51D;
--accent-hover: #B8CC1A;
--accent-light: #F5FADB;
--accent-shadow: rgba(204, 229, 29, 0.3);
```
**Usage**: Primary buttons, active states, highlights, main CTAs

**Secondary Accent - Bice Blue**
```css
--accent-secondary: #0E6BA8;
--accent-secondary-hover: #0C5A8E;
--accent-secondary-light: #E6F1F8;
--accent-secondary-shadow: rgba(14, 107, 168, 0.3);
```
**Usage**: Secondary buttons, info messages, links, alternative CTAs

**Tertiary Accent - Imperial Red**
```css
--accent-tertiary: #FB4B4E;
--accent-tertiary-hover: #E03D40;
--accent-tertiary-light: #FEECED;
--accent-tertiary-shadow: rgba(251, 75, 78, 0.3);
```
**Usage**: Delete actions, errors, warnings, destructive actions

**Quaternary Accent - Lavender Blush**
```css
--accent-quaternary: #EEE5E9;
--accent-quaternary-hover: #DDD0D5;
--accent-quaternary-text: #8B6B7A;
--accent-quaternary-shadow: rgba(238, 229, 233, 0.4);
```
**Usage**: Countdown badges, "days away" pills, subtle highlights

#### Neutral Colors

**Backgrounds**
```css
--color-white: #FFFFFF;         /* Main backgrounds */
--color-gray-50: #f8f9fa;       /* Alternative backgrounds */
--color-gray-100: #f5f7fa;      /* Subtle backgrounds, cards */
--color-gray-200: #f0f0f0;      /* Borders */
```

**Text Colors**
```css
--color-gray-800: #1a1a1a;      /* Primary text */
--color-gray-700: #666;         /* Secondary text */
--color-gray-600: #999;         /* Tertiary text */
--color-black: #000000;         /* Specific UI elements */
```

#### Semantic Colors

```css
--color-error: #FB4B4E;         /* Imperial red */
--color-success: #CCE51D;       /* Pear */
--color-info: #0E6BA8;          /* Bice blue */
--color-warning: #FB4B4E;       /* Imperial red */
```

#### Color Usage Rules

1. **No colors outside this palette** except white and the defined grays
2. Use Pear for all primary actions and active states
3. Use Bice blue for secondary/informational elements
4. Use Imperial red for errors, warnings, and delete actions
5. Use Lavender blush for countdown badges and subtle accent highlights
6. Maintain proper contrast ratios for accessibility
7. **NO GRADIENTS** - Always use solid colors

**Usage Examples:**
```css
✅ background: var(--accent-primary);
✅ color: var(--accent-secondary);
✅ border-color: var(--color-gray-200);

❌ background: #CCE51D;
❌ color: #0E6BA8;
❌ border-color: #f0f0f0;
❌ background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);  /* NO GRADIENTS! */
```

### 🚫 NO GRADIENTS ALLOWED

**CRITICAL RULE**: This design system uses **solid colors only**. No gradients, no matter how subtle.

**Why?**
- Modern, clean aesthetic
- Better consistency across the app
- Gradients often clash with Material Design 3 principles
- Easier to maintain and update

**Wrong:**
```css
❌ background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
❌ background: linear-gradient(135deg, var(--color-info) 0%, #764ba2 100%);
❌ background: radial-gradient(circle, #fff 0%, #f0f0f0 100%);
```

**Correct:**
```css
✅ background: var(--accent-quaternary);
✅ background: var(--accent-secondary);
✅ background: var(--color-gray-50);
```

**If you need visual depth:**
- Use `box-shadow` with shadow variables
- Use subtle borders
- Use hover states with slightly darker colors
- Layer elements with different background colors

---

## Common Patterns

### Buttons vs Pills/Badges - Design Consistency

**CRITICAL**: Maintain clear visual distinction between interactive buttons and informational badges.

#### Buttons (Interactive CTAs)
- **Border Radius**: `var(--radius-xl)` (16px) - moderately rounded
- **Purpose**: Actions, CTAs, interactive elements
- **Examples**: "New Trip", "Create Trip", "Save", "Delete"

```css
.btn,
.new-trip-cta-btn,
.create-trip-btn {
    border-radius: var(--radius-xl);      /* 16px - squared, modern */
    padding: var(--spacing-12) var(--spacing-24);
    font-weight: 700;
}
```

#### Pills/Badges/Tags (Informational)
- **Border Radius**: `var(--radius-round)` (9999px) - fully rounded
- **Purpose**: Display data, status, counts
- **Examples**: "8 days", "In 3 days", "Type C", socket info

```css
.trip-duration-badge,
.trip-countdown-badge,
.trip-socket-inline,
.badge-new {
    border-radius: var(--radius-round);   /* 9999px - fully rounded pill */
    padding: var(--spacing-3) var(--spacing-10);
    font-weight: 600;
}
```

### Cards
```css
.card {
    padding: var(--spacing-24);
    border-radius: var(--radius-2xl);
    box-shadow: var(--shadow-md);
}
```

### Input Fields
```css
.input {
    padding: var(--spacing-12) var(--spacing-16);
    border-radius: var(--radius-sm);
    font-size: var(--text-base);
    border: 1px solid var(--color-gray-400);
}
```

---

## Quick Checklist When Coding

Before adding new styles, ask:
- [ ] Am I using spacing variables? (not `12px`)
- [ ] Am I using radius variables? (not `10px`)
- [ ] Am I using shadow variables? (not `0 2px 8px...`)
- [ ] Am I using text variables? (not `14px`)
- [ ] Am I using duration variables? (not `0.3s`)
- [ ] Am I using solid colors? (NO gradients!)
- [ ] Is this a button? Use `--radius-xl` (16px)
- [ ] Is this a badge/pill/tag? Use `--radius-round` (9999px)
- [ ] Am I using consistent font-weight? (600 for UI, 700 for buttons, 800 for logo)

---

## Why This Matters

**Before:**
Need to update all card padding? Search & replace 50 instances of `padding: 15px 20px`

**After:**
Need to update all card padding? Change `--spacing-lg: 16px` to `--spacing-lg: 18px` in ONE place. Done! ✨

---

## ⚠️ Important Exception: Socket Images

**DO NOT modify socket image styles!**

The socket/plug icon SVG styles in the `getSocketSVG()` function (around line 4,213) use inline styles and should remain untouched:

```javascript
// This is correct - DO NOT change!
const svgStyle = 'display: inline-block; vertical-align: middle; margin-right: 6px;';
```

**Why?**
- These are dynamically generated SVG icons for electrical socket types
- Inline styles are necessary for the SVG rendering to work correctly
- They're generated in JavaScript, not in CSS

**Socket-related CSS classes that DO use variables (these are fine):**
```css
.trip-card-socket      /* Uses var(--color-gray-700), var(--text-xs) */
.trip-socket-inline    /* Uses var(--color-gray-*), var(--spacing-*) */
.city-card-socket      /* Uses var(--text-fixed-12) */
```

---

## Reference

Based on Material Design 3 principles:
- 4px spacing grid for visual rhythm
- Consistent elevation system
- Predictable motion timing

Keep this file open when styling. When in doubt, check here first!

