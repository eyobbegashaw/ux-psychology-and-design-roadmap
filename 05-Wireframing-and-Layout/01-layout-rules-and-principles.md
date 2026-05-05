
This file is a developer's manual for applying Gestalt psychology and foundational layout principles directly to the structural code of a user interface. These aren't abstract art rules; they are the primitive functions of visual cognition that our brain executes before conscious thought.

**1. The Principle of Proximity (Grouping Related Elements)**
Objects that are placed close together are perceived as a group. This is the single most powerful tool for eliminating cognitive load.
- *Cognitive Logic:* If related elements are near each other, System 1 doesn't have to work. It effortlessly chunks them. If an icon is 50px from its label, System 2 has to engage to ask, "Does this icon belong to this label, or the one below it?"
- *Dev Implementation (The Spacing System is a Cognitive System):* Your CSS spacing tokens (e.g., `--spacing-xs: 4px; --spacing-sm: 8px; --spacing-md: 16px;`) must enforce a strict proximity hierarchy. The distance between a label and its own input field (`--spacing-sm`) must be dramatically smaller than the distance between two separate form groups (`--spacing-xl`). This isn't a stylistic choice; it's an API for the brain. A `FormGroup` component in your design system should programmatically enforce these spacing relationships, making it impossible to visually mis-group elements.

**2. The Principle of Similarity (Visual Grammar for Function)**
Elements that look similar (in color, shape, size, or typography) are perceived as having the same function. This creates a visual grammar.
- *Dev Implementation:* The `Button` component hierarchy is a perfect example. A `variant="primary"` button should be used for one and only one type of core action (e.g., "Submit," "Save"). A `variant="secondary"` (outlined) button should be used for all non-primary, but still important, actions (e.g., "Cancel," "Back"). A `variant="tertiary"` (text-only) button should be for subordinate actions. If a designer uses a primary-style button for a non-primary action, it's a cognitive lie. Your component's prop-type definitions and documentation must explicitly call out the *single psychological purpose* of each variant, preventing their misuse and keeping the visual grammar clear and predictable.

**3. The Principle of Common Region and the "Weber's Law of Just Noticeable Difference"**
- **Common Region:** Elements within a bounded area (a card, a bordered panel) are perceived as a group, even if they are far apart. A card UI is the strongest implementation of this. You can have a title, an image, a snippet of text, and a button spread across 200px, but the card's background and border tell the brain "this is one object."
- **Weber's Law in Layout:** We perceive differences on a relative, not absolute, scale. A 5px margin increase around a tiny icon is huge; a 5px increase around a full-width hero image is invisible. The practical dev rule is that your spacing scale must be non-linear, typically based on a geometric progression (e.g., 4, 8, 16, 32, 64px). Your CSS custom properties must enforce this progression. A developer cannot just put `margin-bottom: 23px`; the system must force them to choose the nearest correct cognitive token, like `var(--spacing-lg)`. This ensures that all spatial relationships across the product are legible to the brain's pattern-matching systems.

**4. Figure-Ground and Visual Hierarchy (F and Z Patterns)**
The brain instantly separates a page into "figure" (what's important) and "ground" (the background).
- *The Z-Pattern Layout:* For pages with minimal text, like a landing page, the eye naturally scans in a Z-pattern: top-left to top-right, then diagonally down to bottom-left, then to bottom-right. The key elements (Logo, Login/Call-to-Action) must be placed at the anchor points of the Z. A visual dead spot is the bottom-left corner, which is often missed. Placing a critical trust signal there is a design failure.
- *Dev Note:* The layout grid is a cognitive delivery mechanism. A 12-column CSS Grid system is not arbitrary. It allows us to mathematically place elements on the high-attention Z-path. The hero image and headline dominate the top row (start of the Z). The CTA is placed appropriately at the end of the Z. The grid code is a direct implementation of a pre-attentive visual scan path.

---
