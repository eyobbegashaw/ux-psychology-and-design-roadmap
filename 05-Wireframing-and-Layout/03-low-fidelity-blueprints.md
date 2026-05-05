
 
This file positions the low-fidelity blueprint as a formal specification, as critical as an API contract or a database schema. It's the structural psychology document of record for a page or feature.

**1. The Blueprint as a Cognitive Information Architecture (IA) Document**
This isn't a drawing; it's a diagram of a cognitive space. It answers these questions in a pixel-agnostic way:
- **Visual Weight Distribution:** What is the heaviest element on the page? (This will capture attention first). What is the second? This creates a visual hierarchy of content, which directly translates to an HTML source order, which is critical for both screen readers and for the browser's rendering engine.
- **The "Invisible Path" (Eye-Tracking Prediction):** A good blueprint has arrows drawn on it showing the predicted Z-pattern or F-pattern eye scan. Each stop on the scan path is a numbered "cognitive beat" that corresponds to a user's internal monologue: (1) "What is this?" -> Answer: Hero Headline. (2) "Why should I care?" -> Answer: Sub-headline and key benefit bullets. (3) "What do I do next?" -> Answer: CTA button.
- *Dev Translation:* This sequence of cognitive beats is the exact specification for the order of components in your JSX or HTML template. If the "What do I do next?" beat (the CTA) is placed before the "Why should I care?" beat in the code, no amount of visual styling can fix the structural cognitive failure.

**2. The Blueprint's Patterns: From "Page Types" to "Cognitive Templates"**
We start to see patterns. A "landing page" isn't just a page; it's a specific high-level cognitive template: *Emotionally Hook -> Logically Justify -> Call to Action -> Fortify with Trust.*
- *The 10,000-Foot View:* We can blueprint this at the product level. Our app might have only five core cognitive templates:
    1.  **The Hook-and-Action Template:** For marketing pages.
    2.  **The Discovery Feed Template:** For browsing content (low-effort action, variable reward).
    3.  **The Immersive Editor Template:** For creation (full-screen, minimalist UI, flow state).
    4.  **The Analytical Dashboard Template:** For High-NFC users (dense, customizable, System 2 playground).
    5.  **The Settings/Management Template:** For utility tasks (predictable, form-based, low-anxiety).
- *Developer Architecture:* This insight is profound. Instead of building 50 unique pages, we build 5 templated, data-driven layouts. The `SHELL` of the "Analytical Dashboard" template is a set of backend-configured widgets. The user's psychographic profile determines which template they are served by default. A High-NFC user's homepage might be the Analytical Dashboard, while a Low-NFC user's is the Discovery Feed. The low-fidelity blueprint is the spec for these core system components. It's the clearest definition before any high-fidelity design work begins, saving months of wasted effort.