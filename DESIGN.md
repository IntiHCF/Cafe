# Design System Specification: The Urban Editorial

## 1. Overview & Creative North Star
### Creative North Star: "The Brutalist Zine"
This design system moves away from the "polished corporate" aesthetic to embrace the raw, unrefined energy of Dublin’s alternative street culture. It is an "Urban Editorial" experience—where the sophistication of high-end coffee meets the grit of a wheatpasted alleyway. 

The layout breaks the traditional digital grid through **Intentional Asymmetry**. Elements should feel "stapled" or "taped" onto the screen. We achieve a premium feel not through softness, but through extreme intentionality: high-contrast typography scales, overlapping containers, and a rejection of standard UI tropes like rounded corners and subtle shadows. This is a digital manifestation of a high-end, self-published arts culture.

---

## 2. Colors & Tonal Depth
Our palette is rooted in the industrial materials of the city—charcoal, concrete, and high-visibility accents.

### The Palette (Material Design Mapping)
*   **Surface/Background (`#131313`):** The "Charcoal Black" base. Everything builds from this darkness.
*   **Primary (`#ffefc5` / `#fad02c`):** The "Caution Tape" yellow. Used for high-impact CTAs and critical brand moments.
*   **Secondary (`#c1c7d0`):** The "Raw Concrete" gray. Used for structural elements and secondary information.
*   **Tertiary (`#f0f0f0`):** The "Off-White" paper stock. Used for high-contrast readability against dark backgrounds.

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning. To separate content, you must use **Background Color Shifts**. 
*   Place a `surface-container-low` section against a `surface` background to define a change in content.
*   Use the **Overlap Principle**: Instead of a border, allow a `tertiary` (off-white) container to partially overlap a `primary` (yellow) element to create a hard-edged boundary.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers:
*   **Base Layer:** `surface` (#131313)
*   **Intermediate Layer:** `surface-container-low` (#1c1b1b) for subtle grouping.
*   **High-Impact Layer:** `surface-bright` (#393939) for cards that need to "pop" against the charcoal.

---

## 3. Typography
The typography is the voice of the brand. It must feel industrial, functional, and occasionally human.

*   **Display & Headlines (Space Grotesque):** Used at massive scales (`display-lg` at 3.5rem). This font should feel heavy and architectural. Use tight letter-spacing (-2%) for headlines to increase the "industrial" feel.
*   **Body (Inter):** While the prompt suggested monospace, we utilize Inter for body text to ensure high-end readability, but we style it with increased line-height (1.6) to mimic the layout of a modern art catalog. 
*   **Annotations (The "Scrawled" Layer):** For artisanal notes (e.g., "Roasted in Dublin 8" or "Limited Batch"), use a handwritten-style font (fallback to a clean monospace like `label-md` at 0.75rem if handwriting assets are unavailable) to break the rigid industrial grid.

---

## 4. Elevation & Depth
In a brutalist system, we reject soft drop shadows. Depth is achieved through **Tonal Layering** and **Hard Offsets**.

*   **The Layering Principle:** Stacking `surface-container-highest` on top of `surface-dim` creates a "flat depth" that feels architectural rather than digital.
*   **Brutalist Shadows:** If depth is required for a floating button or card, do not use a blur. Use a **Hard Offset**: A 4px by 4px solid block of `outline-variant` (#4d4633) behind the element to mimic a physical shadow cast by a slab.
*   **Glassmorphism (The "Varnish" Effect):** For navigation bars or floating tooltips, use `surface` at 80% opacity with a heavy `backdrop-filter: blur(20px)`. This mimics the look of frosted glass against a dark Dublin street.
*   **The Ghost Border:** For input fields, use the `outline-variant` at 20% opacity. It should be barely there—a suggestion of a boundary, not a cage.

---

## 5. Components

### Buttons
*   **Primary:** `primary-container` (Yellow) background, `on-primary-container` text. **0px border-radius**. High-contrast, all-caps text.
*   **Secondary:** `surface` background with a `primary` 2px solid stroke. 
*   **Tertiary:** Underlined text only, using the `label-md` scale.

### Cards & Lists
*   **Forbid Dividers:** Do not use horizontal rules. Use **Vertical White Space** (Step 12 or 16 in the spacing scale) to separate list items.
*   **Image Treatment:** Images should have a `0.5` or `1` step spacing "frame" in `secondary-fixed` (Concrete Gray) to look like printed photos pasted into a zine.

### Input Fields
*   **Style:** Sharp 0px corners. Background should be `surface-container-highest`.
*   **Focus State:** A bold 2px border of `primary` (Yellow). No "glow" or soft transitions.

### Signature Component: The "Wheatpaste" Badge
A custom component for promotions or coffee origins. A `tertiary` (off-white) box rotated by -1 or -2 degrees, overlapping the edge of a container, featuring `label-sm` monospace text. It should feel like a sticker slapped onto a wall.

---

## 6. Do’s and Don’ts

### Do:
*   **Embrace Asymmetry:** Align some text to the left and some "metadata" (like prices or dates) to the far right.
*   **Use High Contrast:** Stick to `on-background` (off-white) text on `background` (charcoal). Avoid mid-gray text that reduces the "edgy" impact.
*   **Bleed Images:** Allow hero images to touch the very edge of the viewport (0px margin) to emphasize the raw, brutalist layout.

### Don’t:
*   **No Rounded Corners:** Any radius above 2px is a violation of the system. We prioritize "sharp and rebellious" over "friendly and approachable."
*   **No Standard Shadows:** Never use the default browser `box-shadow`. If it isn't a hard-edged offset or a tonal shift, it doesn't belong.
*   **No Centering Everything:** Centered layouts feel like templates. Keep the majority of the content left-aligned to maintain the editorial "zine" feel.