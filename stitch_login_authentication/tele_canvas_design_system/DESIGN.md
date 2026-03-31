# Design System Document

## 1. Overview & Creative North Star: "The Digital Atrium"

This design system moves beyond the utility of a standard messaging clone to create **The Digital Atrium**—an expansive, airy, and high-end editorial environment for communication. While traditional chat apps rely on rigid grids and heavy borders to contain data, this system uses "Breathable Logic." 

We achieve a signature feel by prioritizing **Asymmetric Balance** and **Atmospheric Depth**. By removing 1px borders and replacing them with tonal shifts and glassmorphism, the interface feels less like a database and more like a curated workspace. It is designed to feel "expensive" through its restraint, using the signature `primary_container` (#24A1DE) only as a purposeful beacon within a sophisticated grayscale landscape.

---

## 2. Colors & Surface Architecture

### The Palette
The color strategy relies on the interaction between "Telegram Blue" and a nuanced scale of warm and cool neutrals.

*   **Primary Execution:** Use `primary` (#00658f) for interactive elements and `primary_container` (#24a1de) for high-visibility message states.
*   **Neutral Foundation:** `surface` (#f9f9f9) acts as the canvas, while the `surface_container` series provides the structure.

### The "No-Line" Rule
**Strict Mandate:** Designers are prohibited from using 1px solid borders to define sections (e.g., separating the chat list from the message window). 
*   **The Alternative:** Boundaries must be defined solely through background shifts. Place a `surface_container_low` sidebar against a `surface` main window. This creates a "soft edge" that is easier on the eyes and feels more premium.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked materials:
1.  **Level 0 (Base):** `surface` (#f9f9f9) — The main application backdrop.
2.  **Level 1 (Sub-Navigation):** `surface_container_low` (#f3f3f3) — For the chat list or settings panels.
3.  **Level 2 (Active Elements):** `surface_container_highest` (#e2e2e2) — For hovered states or active selection indicators.
4.  **Level 3 (Overlays):** `surface_container_lowest` (#ffffff) — For elevated cards and floating menus.

### The "Glass & Gradient" Rule
To elevate the "standard" look:
*   **Glassmorphism:** Use `surface_container_lowest` at 80% opacity with a `20px` backdrop-blur for top navigation bars and floating action menus.
*   **Signature Textures:** For the main "Send" button or "New Message" CTAs, apply a subtle linear gradient from `primary` (#00658f) to `primary_container` (#24a1de) at a 135-degree angle to provide depth.

---

## 3. Typography: Editorial Hierarchy

We use **Inter** to bridge the gap between technical precision and human readability.

*   **Display & Headlines:** Use `headline-sm` (1.5rem) for main chat titles. Ensure a high contrast against `on_surface_variant` sub-text.
*   **The "Message Rhythm":**
    *   **Sender Name:** `label-md` (0.75rem) in `primary` for quick scanning.
    *   **Message Body:** `body-md` (0.875rem) with a 1.5x line-height for maximum legibility in long threads.
    *   **Timestamp:** `label-sm` (0.6875rem) in `outline` to recede into the background until needed.

---

## 4. Elevation & Depth

### The Layering Principle
Depth is achieved through **Tonal Layering**. Instead of drop shadows on every card, place a `surface_container_lowest` (#ffffff) message bubble on a `surface_container_low` (#f3f3f3) chat background. The 4-point color difference creates a natural, "physical" lift.

### Ambient Shadows
When a component must "float" (e.g., a context menu or a profile popover), use an **Ambient Shadow**:
*   **Blur:** `32px`
*   **Spread:** `-4px`
*   **Color:** `on_surface` (#1a1c1c) at **4% opacity**.
*   This mimics natural light dispersion rather than a dated "drop shadow" effect.

### The "Ghost Border" Fallback
If contrast is legally required for accessibility, use the `outline_variant` token at **15% opacity**. This creates a suggestion of a container without the visual "noise" of a solid line.

---

## 5. Components

### Message Bubbles (The Core Unit)
*   **Incoming:** `surface_container_lowest` (#ffffff) with `DEFAULT` (0.5rem/8px) corners.
*   **Outgoing:** `primary_container` (#24a1de) with text in `on_primary`.
*   **Asymmetry:** Use `lg` (1rem/16px) rounding on three corners and `sm` (0.25rem/4px) on the "origin" corner to indicate directionality.

### Buttons
*   **Primary:** Background `primary`, `xl` (1.5rem) roundedness for a pill shape. 
*   **Secondary/Ghost:** No background. Use `on_surface_variant` text. On hover, transition to `surface_container_high`.
*   **Interaction:** On `:active`, scale the button to `0.98` to provide tactile feedback.

### Chat Lists
*   **Forbid Dividers:** Use `Spacing 4` (0.9rem) of vertical white space to separate chat items.
*   **Active State:** Use `surface_container_high` with a 4px vertical "pill" of `primary` color on the far left edge to denote the active conversation.

### Inputs
*   **Style:** Minimalist. No border. Use `surface_container_highest` as the background fill.
*   **Focus State:** A subtle transition to a 1px "Ghost Border" using `primary` at 30% opacity.

---

## 6. Do's and Don'ts

### Do:
*   **Do** use white space as a structural element. If a layout feels cluttered, increase the spacing scale (e.g., move from `spacing-4` to `spacing-6`) rather than adding a line.
*   **Do** use `surface_bright` for hover states on light backgrounds to create a "glow" effect.
*   **Do** lean into the `tertiary` (#855400) tokens for "Muted" or "Archived" states to differentiate from the primary blue thread.

### Don't:
*   **Don't** use pure black (#000000). Always use `on_surface` (#1a1c1c) for text to maintain the premium, editorial tone.
*   **Don't** use sharp 0px corners. Even the most "functional" elements should have at least `sm` (4px) rounding to maintain the "Digital Atrium" softness.
*   **Don't** stack more than three levels of surface containers. If you need more depth, use a Backdrop Blur.