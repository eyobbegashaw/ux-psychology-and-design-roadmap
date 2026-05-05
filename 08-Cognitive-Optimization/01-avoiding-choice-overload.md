
This file is a direct technical response to Barry Schwartz's "Paradox of Choice" and the Hick-Hyman Law. The core premise: increasing the number of choices does not increase freedom. It increases decision paralysis, anxiety, and post-choice regret. Our job is to be choice architects, not choice hoarders.

**1. Hick-Hyman Law as a UI Performance Budget**
The Hick-Hyman Law states that the time it takes to make a decision increases logarithmically with the number of choices. This is not just a psychological theory; it's a mathematical formula for cognitive latency: `RT = a + b log2(n)`.
- *Dev Translation:* A navigation menu with 15 items is a cognitive function call with `n=15`. The user's brain takes measurably longer to resolve it than a menu with `n=5`. This "decision time" is an invisible tax on every interaction.
- *The Performance Budget for Cognition:* We set a performance budget for page load time (e.g., under 2 seconds). We must also set a cognitive performance budget for decision nodes. A core principle is the "Magic Number 7 ± 2" (Miller's Law) for working memory, but for simple visual choice, the optimal number is often even lower: a 3- or 4-option cluster.
- **The Solution: Progressive Disclosure.** This is the master pattern. Don't show all 15 options at once. Show 5 high-level categories. On hover or click, disclose the sub-options. This transforms one complex choice (n=15) into two simpler choices (n=5, then n=3). The cognitive burden is now divided into manageable System 1 chunks. The developer's `NavigationMenu` component must have a `progressiveDisclosure: boolean` prop, architecturally enabling this cognitive load-shedding.

**2. The Paradox of Choice in UI Patterns**
We actively reduce the visible choice set to increase conversion, a concept known as the "Jam Study" effect (fewer jams on display led to 10x more sales).
- **The E-Commerce Category Page:** Presenting 500 dresses isn't a feature; it's a panic attack. The UI must lead with curation: "The 5 Best Dresses For a Summer Wedding." These curated lists act as cognitive safe havens. The backend `ProductRecommendation` engine isn't just predicting what the user wants to buy; it's actively reducing their choice set from a paralyzing 500 to an empowering 5.
- **The SaaS Pricing Page (The Classic Error):** We saw the power of the decoy in folder 01. But a page with 6 different plans (Starter, Growth, Business, Enterprise, with add-on modules) is a choice-overload nightmare. The MVP pricing page should have two, maybe three plans. The "compare plans" feature, if present, should default to a high-level comparison of the recommended 2 plans, with a clear, secondary "View a full feature matrix" link for the High-NFC, System 2-comparison users who explicitly seek out the complexity.

**3. The "Single-Option" Aversion Paradox**
Here is a profound psychological nuance: presenting a single option can also be paralyzing. The user has no frame of reference. "Is this $50 shirt good value? I have no idea."
- *The Solution: The Cognitive Anchor of One Plus a Decoy.* Always provide a comparative context, even if you only really want to sell one thing. The single option must be presented alongside a clearly less-attractive alternative. The classic "buy one for $49, or buy the 6-month supply for $37/month" is a choice of two, where the single purchase merely serves as a value anchor for the "best" option. The user's decision is now "Which of these two?" not "Should I buy at all?"—a decisive psychological reframing.

---
