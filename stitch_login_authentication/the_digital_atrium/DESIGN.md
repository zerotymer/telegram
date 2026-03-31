# Design System Specification: The Digital Atrium

## 1. Overview & Creative North Star
The North Star for this design system is **"The Seasonal Sanctuary."** 

Moving away from the sterile, utilitarian "grid-of-boxes" found in most messaging apps, this system treats the interface as a living space—a digital atrium where light, air, and organic transitions dictate the flow. We break the "template" look through **intentional asymmetry** (e.g., staggered message bubbles), **overlapping elevation layers**, and an **editorial typography scale** that favors white space over density. 

The goal is to make the user feel as though they are stepping into a climate-controlled environment that reflects the natural world outside. We reject the rigid 1px border; we embrace the soft transition.

---

## 2. The Seasonal Narrative (Color Themes)
Color is not a decoration in this system; it is a temporal state. Each theme uses the primary and secondary pairings to anchor the user in a specific emotional "climate."

*   **Spring (Renewal):** Uses `primary: #FFB7C5` and `secondary: #98FB98`. A palette of optimism. Cherry blossom tones handle active states, while fresh leaf green highlights success and presence indicators.
*   **Summer (Vitality):** Uses `primary: #0077BE` and `secondary: #FFD700`. High-energy and high-contrast. The ocean blue provides deep legibility for CTAs, while sunny yellow acts as a vibrant accent for notifications.
*   **Autumn (Warmth):** Uses `primary: #C04000` and `secondary: #DA9100`. An editorial, rich aesthetic. Maple red provides an authoritative brand voice, while harvest orange adds a cozy glow to interactive elements.
*   **Winter (Serenity):** Uses `primary: #A5D6F1` and `secondary: #191970`. A focus on clarity and depth. Ice blue provides a crisp background for communication, while midnight navy offers the deepest level of contrast for text.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. Boundaries must be defined through:
1.  **Background Shifts:** e.g., A `surface-container-low` message list sitting on a `surface` background.
2.  **Tonal Transitions:** Using subtle `surface-variant` shifts to distinguish the sidebar from the chat thread.

### Glass & Gradient Rule
Floating elements (Compose buttons, Modals) must utilize **Glassmorphism**. Use semi-transparent `surface` colors with a 12px-20px `backdrop-blur`. 
*   **Signature Gradients:** Main CTAs should transition from `primary` to `primary-container` at a 135° angle to add "soul" and depth.

---

## 3. Typography: The Editorial Voice
We use **Inter** not as a system font, but as a brand asset. The hierarchy is designed to feel like a high-end magazine.

*   **Display (lg/md/sm):** 3.5rem down to 2.25rem. Reserved for empty states or "New Season" announcements. 
*   **Headline (lg/md/sm):** 2rem down to 1.5rem. Used for top-level navigation (e.g., "Chats", "Settings").
*   **Title (lg/md/sm):** 1.375rem down to 1rem. Semi-bold for contact names and group titles.
*   **Body (lg/md/sm):** 1rem down to 0.75rem. The "lg" is our primary chat bubble text—generous, legible, and airy.
*   **Label (md/sm):** 0.75rem down to 0.6875rem. Used for timestamps and metadata.

**Hierarchy Note:** Use `on-surface-variant` for timestamps to ensure they recede, allowing the `on-surface` body text to lead the eye.

---

## 4. Elevation & Depth: Tonal Layering
We achieve depth through "stacking" rather than "shadowing."

*   **The Layering Principle:** 
    *   **Base:** `surface` (The furthest back).
    *   **Sections:** `surface-container-low` (e.g., the Chat List).
    *   **Active Elements:** `surface-container-lowest` (e.g., an individual Chat Card) to create a soft, natural "lift."
*   **Ambient Shadows:** For floating action buttons (FABs), use extra-diffused shadows.
    *   *Spec:* `offset: 0 8px`, `blur: 24px`, `color: on-surface` at **6% opacity**.
*   **The Ghost Border:** If a boundary is required for accessibility, use `outline-variant` at **15% opacity**. Never use a high-contrast 100% opaque border.

---

## 5. Components

### Chat Bubbles (The Core)
*   **User Bubble:** `primary_container` background with `on_primary_container` text. 
*   **Recipient Bubble:** `surface_container_highest` background with `on_surface` text.
*   **Rounding:** Apply `rounded-xl` (1.5rem) to three corners, and `rounded-sm` (0.25rem) to the tail corner to create a signature "leaf" shape.

### Buttons
*   **Primary:** Background `primary` with `on_primary` text. `rounded-md` (0.75rem).
*   **Secondary:** Background `secondary_container` with `on_secondary_container` text.
*   **Floating Action Button (FAB):** Glassmorphism style. `surface` at 80% opacity, `backdrop-blur: 16px`, with a `primary` icon.

### Cards & Lists
*   **Rule:** Forbid divider lines. 
*   **Separation:** Use `spacing-4` (1.4rem) between list items. Use a subtle background shift to `surface_container_low` on hover/active states.

### Input Fields
*   **Style:** `surface_container_lowest` background. No border. `rounded-md`.
*   **Focus State:** A 2px "Ghost Border" using `primary` at 30% opacity.

---

## 6. Do's and Don'ts

### Do:
*   **Embrace Asymmetry:** Let message bubbles vary in width based on content; do not force them into a rigid grid column.
*   **Use Spacing as a Tool:** Use `spacing-10` (3.5rem) for page margins to give the content "room to breathe."
*   **Color Transitions:** When switching seasons, animate the background color over 600ms for a "biological" feel.

### Don't:
*   **Don't use #000000:** Shadows and text should use the `on-surface` tokens, which are deeply tinted, never pure black.
*   **Don't use 1px Dividers:** If you feel the need for a line, try using a 4px gap of `surface` color instead.
*   **Don't Over-round:** Stick to the `rounded-md` (0.75rem) for most components to maintain a modern, architectural feel. Only use `full` (pill-shape) for chips.

---

## 7. Token Reference Summary

| Token Category | Value | Usage |
| :--- | :--- | :--- |
| **Spacing (Default)** | `spacing-3` (1rem) | Standard padding for cards/bubbles. |
| **Radius (Default)** | `rounded-md` (0.75rem) | Buttons, Inputs, Cards. |
| **Radius (Accent)** | `rounded-xl` (1.5rem) | Chat Bubbles, Profile Avatars. |
| **Shadow (Ambient)** | `0 8px 24px rgba(32, 26, 27, 0.06)` | Floating UI elements. |
| **Glass** | `backdrop-blur: 20px` | Navigation bars and FABs. |