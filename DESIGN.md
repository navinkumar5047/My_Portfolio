# Portfolio Design System: High-End Editorial Tech

## 1. Overview & Creative North Star
**Creative North Star: The Digital Architect**
This design system moves beyond the standard "coding portfolio" by treating code as a form of high-end architecture. We are moving away from the typical "grid of boxes" toward a sophisticated, layered environment that feels deep, intentional, and premium. By utilizing a "Dark-Mode First" editorial approach, we prioritize readability and atmospheric depth. The layout should feel like a custom-coded terminal evolved into a luxury magazine, using intentional asymmetry and breathable white space to highlight the student's technical precision.

## 2. Colors & Surface Philosophy
The palette is rooted in deep midnight blues and vibrant cyans, but its success relies on how these colors interact as layers, not just as fills.

### Surface Hierarchy & Nesting
To achieve a signature look, we abandon traditional borders. Hierarchy is defined through **Tonal Layering**. 
*   **The "No-Line" Rule:** 1px solid borders are strictly prohibited for sectioning. 
*   **Layering Logic:** 
    *   **Level 0 (Base):** `surface` (#041329) – The canvas.
    *   **Level 1 (Sections):** `surface_container_low` (#0d1c32) – Subtle shifts for background sections.
    *   **Level 2 (Cards/Containers):** `surface_container` (#112036) – The primary container for projects.
    *   **Level 3 (Floating/Active):** `surface_container_highest` (#27354c) – Elements that require immediate attention.

### The Glass & Gradient Rule
*   **Glassmorphism:** Navigation bars and floating action menus must use `surface_container` with a `0.7` opacity and a `20px` backdrop-blur. This creates an "integrated" feel where the background content bleeds through softly.
*   **Signature Textures:** For Hero sections or Primary CTAs, use a subtle linear gradient from `primary_fixed_dim` (#38debb) to `primary` (#ffffff) at a 135-degree angle. This provides a metallic, high-tech sheen.

## 3. Typography
We utilize a dual-typeface system to balance technical rigor with high-end editorial flair.

*   **Display & Headlines (Space Grotesk):** This typeface provides a structural, wide-set tech feel. Use `display-lg` for hero statements with a negative letter-spacing of `-0.02em` to create a "locked-in" professional look.
*   **Body & Labels (Manrope):** Chosen for its exceptional legibility at small sizes. Manrope's geometric nature complements the display font without competing for attention.
*   **The Hierarchy:**
    *   **Display-LG (3.5rem):** Reserved for the "Big Idea" or the student's name.
    *   **Headline-MD (1.75rem):** Section titles (e.g., "Selected Works").
    *   **Body-LG (1rem):** Primary narrative text. Maintain a line-height of 1.6 for maximum readability.
    *   **Label-MD (0.75rem):** Metadata, tech stacks, and micro-copy.

## 4. Elevation & Depth
In this system, depth is "felt" rather than "seen."

*   **Ambient Shadows:** For floating elements, use a shadow color derived from `surface_container_lowest` at 40% opacity. 
    *   *Spec:* `0 20px 40px -10px rgba(1, 14, 36, 0.4)`. This mimics natural light without creating "dirty" grey smudges.
*   **The "Ghost Border" Fallback:** If a container requires definition against a similar background, use a 1px border of `outline_variant` (#3c4a45) at **15% opacity**. It should be felt as a whisper of light, not a hard stop.
*   **Tonal Lift:** When a user hovers over a card, do not just change the color; shift the surface from `surface_container` to `surface_container_high`. This subtle "lightening" simulates the object moving closer to the viewer.

## 5. Components

### Buttons
*   **Primary:** No background. Use a "Ghost" style with a `primary_fixed` (#5ffbd6) stroke and `label-md` uppercase text. On hover (0.3s), transition to a full `primary_fixed` fill with `on_primary` text.
*   **Secondary:** Text-only with a 2px underline of `surface_tint`. On hover, the underline expands to fill the background at 10% opacity.

### Cards (Project Showcase)
*   **Forbid Divider Lines.** Use `surface_container` as the card base. 
*   **Visual Interest:** Overlap the project image slightly over the card's edge (intentional asymmetry) to break the "standard container" feel.
*   **Padding:** Use a generous `2.5rem` internal padding to ensure the content feels premium.

### Chips (Tech Stack)
*   Use `surface_container_highest` for the background.
*   Corner radius: `sm` (0.125rem) for a sharper, more "engineered" look. Avoid fully rounded "pill" shapes.

### Input Fields
*   Background: `surface_container_low`. 
*   Bottom-border only (2px) using `outline_variant`. On focus, the border animates to `primary_fixed` from the center outwards.

## 6. Do's and Don'ts

### Do:
*   **Use Asymmetry:** Place a large `display-lg` headline on the left and a small `body-md` paragraph on the far right. This "white space" creates an editorial, custom feel.
*   **Respect the 0.3s Transition:** Every interactive element (links, cards, buttons) must feel fluid. Use `cubic-bezier(0.4, 0, 0.2, 1)` for a more sophisticated motion curve than a standard "linear" transition.
*   **Group by Proximity:** Use the spacing scale (multiples of 8px) to define relationships instead of lines.

### Don't:
*   **Don't use pure black (#000):** It kills the depth of the midnight blue palette. Stick to `surface` for the darkest points.
*   **Don't use standard shadows:** Never use `rgba(0,0,0,0.5)`. Always tint your shadows with the background hue.
*   **Don't stack everything centrally:** On screens >768px, avoid center-aligning everything. It looks like a template. Use a 12-column grid but purposely leave columns 1-2 or 11-12 empty.

## 7. Responsiveness (768px Breakpoint)
*   **Desktop:** Utilize horizontal shifts and overlapping elements.
*   **Mobile (<768px):** Elements must "collapse" into a vertical stack. All `surface_container` elements should expand to full-width minus `1.5rem` margin on each side. Typography scales down (e.g., `display-lg` becomes `headline-lg`) to maintain readability without excessive scrolling.