# Design System Strategy: The Golden Harvest

## 1. Overview & Creative North Star
**Creative North Star: "The Heritage Editorial"**

This design system rejects the sterile, flat aesthetic of modern SaaS in favor of a "Heritage Editorial" approach. We are moving away from rigid, boxy grids toward a layout that feels like a high-end lifestyle magazine—tactile, warm, and deeply intentional. 

By leveraging "The Golden Harvest" concept, we evoke nostalgia through rich tonal depth and "organic asymmetry." We break the "template" look by using exaggerated typographic scales and overlapping elements that suggest layers of physical parchment and linen. The goal is a digital experience that feels "cozy" yet "authoritative," using soft transitions rather than hard lines to guide the user’s eye.

---

## 2. Colors & Tonal Depth
Our palette is rooted in the earth. It uses the heavy saturation of `#974400` (Primary) and the glow of `#795900` (Secondary) to create a sense of sun-drenched warmth.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. We achieve separation through "Tonal Carving." 
- To define a new section, shift the background from `surface` (`#fbfbe2`) to `surface-container-low` (`#f5f5dc`). 
- For internal content blocks, use `surface-container` (`#efefd7`) to create a subtle "well" effect.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked, fine-milled papers. 
- **Base Level:** `surface`
- **Floating Cards:** `surface-container-lowest` (`#ffffff`) to create maximum "pop" against the cream backgrounds.
- **Inset Elements:** `surface-dim` (`#dbdcc3`) for footer areas or utility bars to grounded the layout.

### The "Glass & Grain" Rule
To elevate the "Golden Harvest" feel, use Glassmorphism for floating navigation or overlays. Utilize `surface` at 80% opacity with a `24px` backdrop blur. This allows the "harvest" colors to bleed through the interface, softening the digital edge.

### Signature Textures
Avoid flat buttons. Main CTAs should utilize a subtle linear gradient from `primary` (`#974400`) to `primary_container` (`#bb5808`) at a 135-degree angle. This adds "soul" and a sense of physical weight to the interaction.

---

## 3. Typography
We use **Inter** not as a standard UI face, but as a modern grotesque that provides a clean counterpoint to our rustic color palette.

- **Display (Large/Medium):** Used for "Editorial Moments." These should be set with tight letter-spacing (-0.02em) to feel like a masthead.
- **Headlines:** Used to break the flow. Pair a `headline-lg` with a `body-md` in an asymmetrical layout (e.g., left-aligned headline with a wide right margin) to mimic premium print.
- **Body:** `body-lg` is your workhorse. Use a generous line-height (1.6) to ensure the "cozy" readability required by the brand.
- **Labels:** Always in `label-md` using `on_surface_variant` (`#564338`) to maintain a soft, low-contrast sophistication.

---

## 4. Elevation & Depth
Depth in this system is organic, mimicking ambient light in a physical space.

- **The Layering Principle:** Avoid shadows where a color shift will suffice. A `surface-container-high` (`#eaead1`) element sitting on `surface` provides enough "lift" for most functional needs.
- **Ambient Shadows:** For high-elevation elements (modals/dropdowns), use a multi-layered shadow: `0px 12px 32px rgba(48, 50, 33, 0.06)`. Note the use of `inverse_surface` as the shadow tint rather than pure black; this keeps the shadow "warm."
- **The Ghost Border:** If a border is required for accessibility, use `outline_variant` (`#ddc1b3`) at **15% opacity**. It should be felt, not seen.
- **Soft Corners:** Adhere strictly to the **8px (DEFAULT)** roundness for standard components, but use **16px (xl)** for large hero imagery to emphasize the "organic" nature of the harvest.

---

## 5. Components

### Buttons
- **Primary:** Gradient fill (`primary` to `primary_container`), `on_primary` text, 8px radius. No border.
- **Secondary:** `surface-container-highest` fill with `primary` text. This creates a "tonal" button that feels part of the background.
- **Tertiary:** Text-only using `primary` color, with a subtle `surface-hover` state.

### Input Fields
- **Container:** Use `surface-container-low`.
- **Active State:** Change background to `surface-container-lowest` and add a 1px "Ghost Border" using `primary`.
- **Labels:** Always floating above the field in `label-sm` to maintain a clean horizontal rhythm.

### Cards & Lists
- **Prohibition:** Divider lines are forbidden. 
- **Separation:** Use a `2.75rem` (8) or `3.5rem` (10) vertical gap from the spacing scale to separate list items. Use a slight background shift on hover (`surface-container-high`) to define the hit area.

### Featured "Harvest" Component: The Inset Hero
For blog or product features, use an "Inset Hero" card: A `surface-container-lowest` container with `1.5rem` padding, housing an image with an `xl` (16px) radius, creating a "frame-within-a-frame" editorial look.

---

## 6. Do’s and Don’ts

### Do:
- **Do** use asymmetrical margins. If a container is centered, try offsetting the text inside to the left to create visual tension.
- **Do** use `tertiary` (`#006290`) sparingly for functional links or "Success" states to provide a cool contrast to the sea of warm oranges.
- **Do** prioritize white space. The "Golden Harvest" needs room to breathe to avoid feeling cluttered or "cheap."

### Don’t:
- **Don't** use pure black `#000000` for text. Always use `on_surface` (`#1b1d0e`).
- **Don't** use 100% opaque borders. They break the "editorial" flow and make the UI look like a wireframe.
- **Don't** use standard "drop shadows." If it doesn't look like ambient light hitting paper, it doesn't belong in this system.