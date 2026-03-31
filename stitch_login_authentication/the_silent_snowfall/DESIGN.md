# Design System Strategy: The Silent Snowfall

## 1. Overview & Creative North Star: "Atmospheric Precision"
The Creative North Star for this design system is **Atmospheric Precision**. Rather than a generic "winter" theme of snowflakes and icons, we are evoking the physical sensation of a silent, heavy snowfall at twilight. The goal is to move beyond the "boxed-in" web layout and create a digital environment that feels expansive, quiet, and pristine.

We break the "template" look by utilizing **intentional asymmetry** and **tonal depth**. Instead of centering everything, we use the spacing scale to create large "white space" (snow drifts) that allow content to breathe. Overlapping elements—such as an image partially bleeding into a text container—create a sense of layered physical reality, mimicking how snow rests upon the landscape.

## 2. Colors: The Tonal Landscape
The palette transition from `surface` (#f7f9fb) to `primary` (#1c6090) mimics the shift from a bright morning sky to the deep shadows of an icy crevasse.

*   **Primary Roles:** `primary` (#1c6090) and `primary_container` (#3c79ab) are used for moments of high importance. These should feel like "ice anchors" in the sea of white.
*   **Secondary Roles:** `secondary` (#476364) provides a muted, sophisticated counterpoint, grounding the ethereal blues.
*   **The "No-Line" Rule:** To maintain the "Silent Snowfall" purity, **1px solid borders are strictly prohibited for sectioning.** Boundaries must be defined solely through background color shifts. For example, a `surface_container_low` section sitting on a `surface` background creates a soft, natural edge like a footprint in fresh snow.
*   **Surface Hierarchy & Nesting:** Treat the UI as stacked sheets of frosted glass. An application interface should never be flat. Use the tiering below to define importance:
    *   *Base Layer:* `surface`
    *   *Content Sections:* `surface_container_low`
    *   *Interactive Cards:* `surface_container_lowest` (White #ffffff) to create a "highlighted" lift.
*   **The "Glass & Gradient" Rule:** For high-end editorial moments (Hero sections or Floating Menus), use Glassmorphism. Apply `surface_variant` with a 60% opacity and a `20px` backdrop-blur. 
*   **Signature Textures:** Main CTAs should use a subtle linear gradient from `primary` to `primary_container` at a 135-degree angle. This adds a "glacial" depth that flat hex codes cannot achieve.

## 3. Typography: Editorial Authority
We utilize **Inter** not as a standard sans-serif, but as a precision instrument. The hierarchy is designed to convey the "hush" of a winter landscape.

*   **Display Scale (`display-lg` to `display-sm`):** These are your "silent" headers. Use low tracking (-0.02em) to make them feel heavy and established.
*   **Headline & Title:** Use `headline-lg` (2rem) for primary entry points. The contrast between a massive `display-lg` header and a tiny, high-contrast `label-md` creates an editorial, boutique feel.
*   **Body & Labels:** `body-lg` is the workhorse. To maintain elegance, avoid over-bolding. Use `on_surface_variant` (#41474f) for secondary body text to reduce visual noise and maintain the "soft" atmosphere.

## 4. Elevation & Depth: Tonal Layering
In this design system, shadows are atmospheric, not structural.

*   **The Layering Principle:** Depth is achieved by "stacking." To highlight a specific module, do not reach for a shadow first; instead, place a `surface_container_lowest` card on a `surface_container` background.
*   **Ambient Shadows:** When a floating element (like a modal or dropdown) is required, use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(28, 96, 144, 0.06);`. Note the use of a tinted shadow (using the `primary` hue) instead of pure black to mimic light passing through ice.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, it must be a **Ghost Border**: Use `outline_variant` at 15% opacity. It should be felt, not seen.
*   **Glassmorphism:** Use `backdrop-filter: blur(12px)` on all floating navigation bars. This allows the "snowy" background colors to bleed through, softening the edges of the UI and making the layout feel integrated into the environment.

## 5. Components: Pristine Primitives

*   **Buttons:**
    *   *Primary:* Gradient fill (`primary` to `primary_container`), `xl` (1.5rem) roundness. No border.
    *   *Secondary:* `surface_container_highest` fill with `on_surface` text.
    *   *Tertiary:* Ghost style. No background, `primary` text, subtle `1.5` spacing underline on hover.
*   **Input Fields:** Use `surface_container_low` as the field fill. Instead of a bottom line, use the `xl` roundness (1.5rem) to create a "pill" or "pod" look. Label text should use `label-md` sitting just above the field, never inside.
*   **Cards:** Forbid divider lines. Use `spacing.8` (2.75rem) to separate internal card elements. A card should feel like a single, solid block of carved ice.
*   **Chips:** Use `secondary_container` for the background with `on_secondary_container` text. The `full` roundness token (9999px) is mandatory here to contrast against the `xl` roundness of cards.
*   **Interactive Lists:** Forbid 1px dividers. Use a hover state of `surface_bright` and a `3.5` spacing gap between items to define boundaries.

### Suggested Signature Component: The "Frost Overlay"
A specialized container used for image captions or video overlays. It uses a `surface_container_highest` background at 40% opacity with a `blur(10px)` filter, creating a sophisticated "etched glass" effect for text legibility over complex backgrounds.

## 6. Do's and Don'ts

### Do:
*   **Do** use asymmetrical margins (e.g., `spacing.16` on the left, `spacing.8` on the right) to create a high-end, non-standard layout.
*   **Do** lean into the `primary_fixed_dim` and `secondary_fixed_dim` colors for subtle hover states.
*   **Do** prioritize vertical white space. If you think there is enough space, add `spacing.4` more.

### Don't:
*   **Don't** use pure black (#000000). Use `on_surface` (#191c1e) for all "black" text to keep the palette soft.
*   **Don't** use standard `0.5rem` roundness for large containers. Stick to `xl` (1.5rem) to maintain the "soft snow" aesthetic.
*   **Don't** use high-contrast transitions. Every color shift should feel like a gradual change in light or weather.