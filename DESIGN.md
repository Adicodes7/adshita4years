# Design System Document: The Ethereal Archive

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Curator"**

This design system rejects the rigid, boxy constraints of traditional web layouts in favor of an editorial, scrapbook-inspired experience. It is designed to feel like a high-end, bespoke photo essay—intentional, romantic, and deeply personal. 

We achieve this through **Intentional Asymmetry**. Rather than perfectly centered grids, we utilize overlapping elements and varied spacing to mimic the tactile feel of physical mementos laid out on a clean surface. By leveraging high-contrast typography scales and a "Blue-on-Blue" tonal depth, the interface breathes with a sophisticated, calm energy. This is not a template; it is a curated memory.

---

## 2. Colors: Tonal Depth & Soul
The palette moves away from "flat UI" by using the full spectrum of blues to create atmospheric perspective.

*   **Primary (`#00193c`):** Our "Midnight Navy." Reserved for the most critical editorial anchors and high-contrast text.
*   **Secondary (`#0c6780`):** "Oceanic Teal." Used for interactive elements that require a softer, more romantic touch than the deep primary.
*   **Surface Tiers:** Use `surface_container_lowest` (#ffffff) for the "paper" of our scrapbook and `surface` (#f7f9fe) for the ambient environment.

**The "No-Line" Rule**
Under no circumstances should 1px solid borders be used to define sections. Boundaries must be felt, not seen. Define transitions using background shifts—e.g., a `surface_container_low` section transitioning into a `surface_bright` hero area.

**The Glass & Gradient Rule**
To add "soul," use subtle linear gradients for large interactive surfaces, transitioning from `primary` to `primary_container`. For floating navigation or over-image labels, use **Glassmorphism**: apply `surface_container_lowest` at 60% opacity with a `20px` backdrop-blur to allow the soft blues of the background to bleed through.

---

## 3. Typography: The Editorial Voice
We pair the authoritative elegance of Noto Serif with the modern, approachable clarity of Manrope.

*   **Display & Headlines (Noto Serif):** These are your "Hero" moments. Use `display-lg` (3.5rem) for anniversary dates or names. The Serif conveys heritage and romance. Ensure tight letter-spacing (-0.02em) for a high-end fashion magazine feel.
*   **Body & Labels (Manrope):** Use `body-lg` for storytelling. Manrope’s geometric nature balances the serif's curves, ensuring the "clean" aspect of the prompt is maintained even amidst romantic imagery.
*   **Hierarchy as Identity:** Use `label-md` in all-caps with increased letter-spacing (0.1em) using the `secondary` color to denote "Chapters" or "Timeline" markers.

---

## 4. Elevation & Depth: The Layering Principle
We do not use shadows to lift objects; we use them to ground them.

*   **Tonal Layering:** Depth is achieved by stacking. Place a `surface_container_lowest` card (Pure White) onto a `surface_container_low` background (Pale Blue). This creates a "soft lift" that feels like a heavy cardstock invitation sitting on a silk tablecloth.
*   **Ambient Shadows:** For "floating" photos or scrapbook elements, use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(0, 27, 63, 0.06);`. The shadow color is a tint of `on_primary_fixed`, making it look like natural light filtered through water, rather than a dirty grey smudge.
*   **The "Ghost Border" Fallback:** If a container sits on a background of the same color, use a 1px border of `outline_variant` at **15% opacity**. It should be barely perceptible.
*   **Roundedness:** Apply `xl` (1.5rem) to all primary photography and `md` (0.75rem) to interactive components like buttons. This "mismatch" ensures photos feel soft and organic while the UI feels functional.

---

## 5. Components: Functional Elegance

### Buttons
*   **Primary:** Background `primary_container`, text `on_primary_fixed`. Use a subtle 0.5s transition on hover to `primary`. Shape: `full` (pill-shaped) to contrast with the `xl` rounded photos.
*   **Tertiary:** No background. Use `title-sm` typography in `secondary` with a custom underline that sits 4px below the baseline.

### Cards & Scrapbook Elements
*   **The Photo Frame:** Photos should never be bare. Give them an `xl` corner radius and place them inside a `surface_container_lowest` container with generous `8` (2.75rem) padding to mimic a polaroid or framed print.
*   **Forbid Dividers:** Do not use horizontal rules (`<hr>`). Use the Spacing Scale—specifically `16` (5.5rem) or `20` (7rem)—to create "islands" of content.

### Inputs & Fields
*   **Text Inputs:** Use `surface_container_highest` for the background with a `none` border. On focus, transition the background to `surface_container_lowest` with a `2px` `outline` in `primary`.

### Additional Component: The "Memory Scroll"
A horizontal-scrolling list of images where each image is slightly offset vertically from the last (Asymmetry). Use `spacing-5` between items.

---

## 6. Do’s and Don’ts

### Do:
*   **Embrace Negative Space:** If a section feels crowded, double the padding using the `24` (8.5rem) spacing token.
*   **Overlap Elements:** Allow a `headline-lg` to slightly overlap the edge of a `rounded-xl` photo. This breaks the "web template" feel and creates the scrapbook aesthetic.
*   **Use Subtle Motion:** Elements should fade in and move up by `1rem` on scroll to mimic the feeling of opening a physical album.

### Don’t:
*   **Don't use Pure Black:** Never use `#000000`. Use `primary` or `on_surface` (#181c20) to keep the "Blue" atmosphere intact.
*   **Don't use Sharp Corners:** Avoid `none` or `sm` rounding for anything other than the most utilitarian labels. It breaks the "Romantic" mood.
*   **Don't Grid-Lock:** Avoid perfectly symmetrical two-column layouts. Try a 40/60 split or a single centered column with wide margins.

### Accessibility Note:
While we use soft blues, ensure all body text (`body-lg`) maintains a contrast ratio of at least 4.5:1 against the background. Use the `on_surface` and `primary` tokens specifically for this purpose.