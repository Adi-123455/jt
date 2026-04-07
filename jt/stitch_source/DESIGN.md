# Design System Strategy: The New York Kinetic

## 1. Overview & Creative North Star
**Creative North Star: "The Editorial Revival"**

This design system rejects the "actor portfolio" tropes of 1990s Hollywood (faded gold gradients and heavy serif fonts) in favor of 1994 Manhattan: crisp, high-contrast, and kinetic. It captures the energy of a classic sitcom set—vibrant, multi-layered, and intentionally framed—while maintaining the sophisticated minimalism of mid-90s editorial design.

We move beyond the template look by utilizing **intentional asymmetry**. Layouts should feel like a high-end magazine spread: images should break the container bounds, and typography should overlap "Polaroid" frames. This system is designed to feel professional enough for a high-stakes casting director, yet playful enough to capture the "Tribbiani" charm.

## 2. Colors & Surface Architecture

The palette is anchored in a clinical `surface` white, punctuated by "Electric Teal" (`primary`) and "Studio Blue" (`secondary`).

*   **The "No-Line" Rule:** Visual separation is never achieved through 1px borders. Instead, use background shifts. A "Skills" section should transition from `surface` to `surface-container-low` to define its boundary. 
*   **Surface Hierarchy & Nesting:** Treat the UI as physical layers. 
    *   **Level 0 (Base):** `surface` (#f9f9fe)
    *   **Level 1 (Sections):** `surface-container-low` (#f2f3f9)
    *   **Level 2 (Cards/Modules):** `surface-container-lowest` (#ffffff)
*   **The "Glass & Gradient" Rule:** To evoke 94’s optimism, floating navigation or "Quick Info" badges must use Glassmorphism: `surface-container-low` at 80% opacity with a 12px backdrop-blur. 
*   **Signature Textures:** Use subtle linear gradients for CTAs, transitioning from `primary` (#006a6b) at the top-left to `primary-container` (#6ef0f1) at the bottom-right. This adds a "lithographic" depth that flat colors lack.

## 3. Typography: The "Manhattan Bold" Scale

The typography system pairs the utilitarian precision of **Manrope** with the geometric, wide-set personality of **Space Grotesk**.

*   **Display & Headline (Space Grotesk):** These are your "NYC" fonts. They should be used with tight letter-spacing (-2%) to feel modern and impactful. `display-lg` is reserved for name branding; `headline-md` is for section titles.
*   **Body & Labels (Manrope):** This provides the "Professional" balance. Use `body-lg` for monologues or bios to ensure high readability.
*   **The Signature Pairing:** Always pair a `headline-lg` in `primary` color with a `label-md` in `tertiary` (#bd0055) for small captions (e.g., "REEL 1994") to create that high-energy, editorial rhythm.

## 4. Elevation & Depth

We avoid the "web app" look by using tonal stacking and ambient light physics.

*   **The Layering Principle:** Depth is "built," not "shadowed." Place a `surface-container-highest` element behind a `surface-container-lowest` "Polaroid" card to create a physical stack effect.
*   **Ambient Shadows:** For floating elements like a "Contact Joey" FAB, use a shadow with a 32px blur, 0px spread, and 6% opacity. Use a tinted shadow: `#2e3339` (on-surface) mixed with a hint of `secondary` (#0059cb) to prevent a "dirty" grey look.
*   **The "Ghost Border" Fallback:** If a container needs more definition (like an input field), use `outline-variant` (#aeb2ba) at **15% opacity**.
*   **Polaroid Frames:** Images should always sit within a `surface-container-lowest` container with a generous bottom padding (the "Polaroid" chin) and a `sm` (0.125rem) corner radius.

## 5. Components

### Buttons
*   **Primary:** Gradient of `primary` to `primary-container`. `md` roundedness. No border. Text in `on_primary`.
*   **Secondary:** `surface-container-highest` background with `primary` text. No border.
*   **State Change:** On hover, use `primary_fixed_dim` for a subtle "glow" effect rather than a color darken.

### Polaroid Image Cards
*   **Structure:** A `surface-container-lowest` background with an inner image. 
*   **Detail:** Use a `tertiary` (#bd0055) "Status Chip" in the top corner (e.g., "NEW REEL") to break the clean lines.

### Input Fields
*   **Style:** Minimalist. No bottom line or full box. Use `surface-container-low` as the fill. 
*   **Focus:** Transition background to `surface-container-high` and add a `primary` label.

### Chips (Action/Filter)
*   **Style:** Use `secondary-container` with `on_secondary_container` text. Use `full` roundedness for a "pill" look that contrasts with the geometric layout.

### Lists & Credits
*   **Execution:** Forbid dividers. Use `surface-container-low` alternating backgrounds or simply 24px of vertical whitespace between roles/credits.

## 6. Do's and Don'ts

### Do
*   **Do** overlap elements. Let a text block in `display-sm` partially cover the corner of a photo.
*   **Do** use `tertiary` (#bd0055) sparingly as a "high-energy" accent for highlights or notification dots.
*   **Do** embrace the whitespace. 1994 minimalism is about the "breath" between the content.

### Don't
*   **Don't** use 100% black. Use `on_surface` (#2e3339) for all text to keep the "ink on paper" editorial feel.
*   **Don't** use "Drop Shadows" on text. If you need emphasis, use a `secondary-container` background highlight behind the text.
*   **Don't** use sharp 0px corners. Even the most "brutalist" 90s look needs the `DEFAULT` (0.25rem) radius to feel premium and touchable.