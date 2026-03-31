# Design System: The Cooling Oasis

## 1. Overview & Creative North Star
The "Cooling Oasis" is not merely a color palette; it is a sensory experience designed to evoke the relief of a shaded pool on a scorching day. The Creative North Star for this system is **"Refractive Fluidity."** 

To move beyond the "template" look, we reject the rigid, boxy constraints of traditional web design. Instead, we embrace a layout style inspired by high-end editorial magazines—utilizing generous whitespace (the "cooling" element) and intentional asymmetry. Components should feel as though they are floating in clear water, using overlapping layers and shifts in tonal depth to create a sense of immersion. By prioritizing "breathing room" over structural lines, we ensure the interface feels energetic yet calm.

## 2. Colors: Tonal Immersion
Our palette balances the crystalline energy of `primary` (#006386 / #00BFFF) with the radiant warmth of `secondary` (#6C5A00 / #FFD700).

### The "No-Line" Rule
**Borders are prohibited for sectioning.** To separate content, you must use background color shifts. For example, a `surface-container-low` section should sit against a `surface` background. This creates a sophisticated, seamless transition that mimics natural light and shadow rather than a wireframe.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
- **Base Layer:** `surface` (#F3F7F8) – The foundation of the oasis.
- **Content Blocks:** `surface-container-low` or `surface-container-lowest` (White) to create soft "islands" of information.
- **Interactive Layers:** Use `surface-container-highest` for elements that need to feel closest to the user.

### The "Glass & Gradient" Rule
To capture the "Oasis" concept, use **Glassmorphism** for floating headers, navigation bars, or modal overlays. 
- **Specs:** Use a semi-transparent `surface` color with a `backdrop-blur` of 20px–40px. 
- **Signature Textures:** For primary CTAs and Hero sections, utilize a subtle linear gradient from `primary` (#006386) to `primary-container` (#00BDFD) at a 135-degree angle. This adds "visual soul" and prevents the vibrant blue from feeling flat or clinical.

## 3. Typography: Editorial Authority
We use **Inter** not as a functional default, but as a precise architectural tool. 

- **Display & Headlines:** Use `display-lg` (3.5rem) and `headline-lg` (2rem) with tight letter-spacing (-0.02em) to create an authoritative, editorial feel. These should be treated as "hero" elements that break the grid.
- **Body & Labels:** `body-md` (0.875rem) provides high legibility against the cool gray backgrounds. 
- **Hierarchy through Contrast:** Create drama by pairing a massive `display-sm` title with a significantly smaller `label-md` uppercase tag. This high-contrast scale is the hallmark of premium design.

## 4. Elevation & Depth
In this design system, depth is earned through color, not just shadows.

### The Layering Principle
Achieve hierarchy by stacking tiers. Place a `surface-container-lowest` card (Pure White) on top of a `surface-container-low` section (#EDF2F3). The contrast is enough to define the boundary without a single pixel of stroke.

### Ambient Shadows
When an element must "float" (like a FAB or a dropdown):
- **Shadow Color:** Use a tinted version of the `on-surface` color (e.g., #2B2F31 at 5% opacity).
- **Blur:** Large, diffused values (e.g., `offset: 0 12px, blur: 32px`). Avoid dark, muddy grays.

### The "Ghost Border" Fallback
If a border is required for accessibility, it must be a **Ghost Border**: use `outline-variant` at 15% opacity. It should be felt, not seen.

## 5. Components

### Buttons
- **Primary:** Gradient fill (`primary` to `primary-container`), white text, 12px (`md`) radius.
- **Secondary:** `secondary-container` fill with `on-secondary-container` text. High energy, used for "Sunshine" moments.
- **Tertiary:** No fill, `primary` text. Use for low-emphasis actions.

### Cards & Lists
**Forbid dividers.** To separate list items, use increased vertical padding from our spacing scale (e.g., `spacing-4` or `1.4rem`) or alternating `surface-container` subtle shifts. Cards should use the `lg` (1rem) or `xl` (1.5rem) roundness to feel soft and approachable.

### Input Fields
Soft `surface-container-high` backgrounds with a `md` (0.75rem) corner radius. On focus, transition the background to `surface-container-lowest` and add a subtle `primary` ghost border.

### Signature Component: The "Oasis Blur"
A decorative background element consisting of large, organic blobs of `primary_container` and `tertiary_container` with a 100px blur, placed behind content to break the "white wall" of the background.

## 6. Do's and Don'ts

### Do:
- **Do** use `spacing-16` (5.5rem) and `spacing-20` (7rem) for section margins. Space is your most valuable asset.
- **Do** overlap elements. A headline can slightly overlap an image or a card to create a sense of depth and fluidity.
- **Do** use `secondary` (Gold) sparingly as an "accent light"—it should feel like a glint of sun on water.

### Don't:
- **Don't** use 1px solid borders to define boxes. It breaks the "Oasis" immersion.
- **Don't** use pure black (#000000) for text. Use `on-surface` (#2B2F31) for a softer, premium contrast.
- **Don't** crowd the interface. If a screen feels "busy," increase the background whitespace using the top end of the spacing scale.