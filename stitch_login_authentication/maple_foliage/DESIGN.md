# Design System Strategy: Rustic Elegance

## 1. Overview & Creative North Star: "The Seasonal Editor"
This design system rejects the clinical coldness of modern SaaS in favor of a "Seasonal Editor" aesthetic. Our North Star is the tactile, immersive experience of a high-end autumn editorial—think thick, matte paper stock, the smell of woodsmoke, and the rich, organic layering of a forest floor.

To achieve **Rustic Elegance**, we move away from rigid, boxy grids. We embrace intentional asymmetry, allowing content to breathe through expansive whitespace (`spacing-24`) and overlapping elements. We do not "build" pages; we "curate" compositions. By treating the screen as a canvas for tonal depth rather than a container for data, we create a premium digital experience that feels bespoke, warm, and sophisticated.

---

## 2. Colors: The Harvest Palette
Our palette is a sophisticated transition from deep, grounded earth tones to vibrant, glowing highlights.

### Surface Hierarchy & Nesting
We do not use lines to define space. We use **Tonal Layering**.
*   **The "No-Line" Rule:** 1px solid borders are strictly prohibited for sectioning. Boundaries must be defined solely through background shifts.
*   **Nesting Logic:** Treat the UI as stacked sheets of fine parchment. Use `surface-container-low` for the base page, and `surface-container` or `surface-container-highest` for internal modules. This creates a natural, soft-edge transition that feels organic rather than mechanical.

### The Glass & Gradient Rule
To prevent the UI from feeling "flat" or "heavy," use **Glassmorphism** for floating elements (Navigation bars, Modals).
*   **Technique:** Apply a semi-transparent `surface-container` color with a 20px backdrop-blur. This allows the vibrant `primary` (#8f000d) and `secondary` (#9a4600) hues to bleed through, mimicking the way light filters through autumn leaves.
*   **Signature Textures:** For hero sections or primary CTAs, use a subtle radial gradient: `primary` (#8f000d) to `primary-container` (#b22222). This adds a "glow" that flat hex codes cannot achieve.

---

## 3. Typography: Editorial Authority
We utilize **Inter** not as a generic sans-serif, but as a clean, modernist anchor against our rich, rustic colors.

*   **Display Scale (`display-lg` to `display-sm`):** These are your "statements." Use them with tight letter-spacing (-0.02em) and generous leading. Headlines should often be center-aligned or dramatically offset to break the grid.
*   **Hierarchy as Brand:** High contrast between `display-lg` (3.5rem) and `body-md` (0.875rem) is essential. This creates an editorial "rhythm" that guides the eye through the "story" of the interface.
*   **Functional Clarity:** Use `label-md` in all-caps with increased letter-spacing (+0.05em) for category tags or small metadata, ensuring every piece of information feels intentionally placed.

---

## 4. Elevation & Depth: The Layering Principle
Forget drop shadows. We define depth through **Ambient Light and Material Stacking.**

*   **Tonal Lift:** Instead of a shadow, place a `surface-container-lowest` card on a `surface-container-low` background. This creates a "ghostly" lift that feels high-end and subtle.
*   **Ambient Shadows:** If a floating state is required (e.g., a dropdown), use a "Tinted Shadow." Instead of black/grey, use `on-surface` (#2c160e) at 6% opacity with a 40px blur. This mimics the soft shadow cast by an object in a warm, sunlit room.
*   **The "Ghost Border" Fallback:** If a boundary is required for accessibility, use `outline-variant` at 15% opacity. It should be felt, not seen.

---

## 5. Components: Bespoke Elements
All components adhere to `ROUND_TWELVE` (0.75rem) to maintain a soft, approachable, yet structured hand-feel.

*   **Buttons:**
    *   *Primary:* A lush gradient of `primary` to `primary-container`. No border. White text (`on-primary`).
    *   *Secondary:* `secondary-container` background with `on-secondary-container` text.
    *   *Interactive State:* On hover, increase the elevation through a subtle color shift to `primary-fixed-dim`, never a heavy shadow.
*   **Cards & Lists:** 
    *   **Prohibition:** No divider lines between list items. Use `spacing-4` as a vertical gutter or alternate background tones (`surface-container-low` vs `surface-container-lowest`).
    *   *Editorial Card:* Image-heavy with a `display-sm` headline overlapping the image edge slightly to break the "boxed-in" feel.
*   **Input Fields:** 
    *   Use a `surface-container-highest` fill with no border. Upon focus, transition the background to `surface` and apply a 1px "Ghost Border" using the `primary` color at 40% opacity.
*   **Chips:** 
    *   Rounded `full` (9999px). Use `tertiary-fixed` with `on-tertiary-fixed` text for a "Golden Hour" glow that highlights tags without competing with primary actions.

---

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical margins. If the left margin is `spacing-12`, try a right margin of `spacing-20` for editorial layouts.
*   **Do** embrace the "Earthy Brown" (`#5D4037`). Use it for body text (`on-surface`) to keep the reading experience warm and low-strain compared to pure black.
*   **Do** use large-scale imagery that features natural textures (wood, linen, leaf veins) to complement the UI colors.

### Don'ts
*   **Don't** use 100% black or pure white (#000000 or #FFFFFF). Our "whites" are `surface-container-lowest` (#ffffff) and our "blacks" are `on-background` (#2c160e).
*   **Don't** use standard "Material Design" shadows. They are too clinical for this system.
*   **Don't** cram content. If a section feels crowded, double the spacing token (e.g., move from `spacing-8` to `spacing-16`). Luxury is defined by the space you *don't* use.