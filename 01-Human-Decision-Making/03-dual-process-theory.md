This file translates the Nobel-prize-winning work of Kahneman and Thaler into a UI development playbook. Standard economics assumes a rational "Econ." Behavioral economics studies the real, biased, emotional "Human." Our users are Humans.

**1. Prospect Theory and Loss Aversion**
We feel the pain of a loss approximately twice as powerfully as the pleasure of an equivalent gain. This is not a cognitive bias; it's a fundamental feature of the human operating system.
- **The "Endowment Effect" Re-framing:** Instead of a "Free Trial," it's a "30-Day Owner's Trial." You already own these premium features. If you cancel, you *lose* them. Copy and framing are everything.
- **Risk Aversion in Decision Architecture:** When framing a choice, highlight what the user stands to lose by not acting. "Don't lose your data—backup now" is more powerful than "Backup now to save your data." We must A/B test this language rigorously, monitoring not just conversion but also long-term user satisfaction to avoid a trust-eroding, adversarial relationship.
- **Dev Implementation of a "Sunk Cost" Illusion:** A progress bar in an onboarding flow can start at 10%. The user hasn't done anything, but they've already "invested" in the process and are more likely to finish to avoid losing that initial, artificially-granted progress. This requires a carefully weighted completion algorithm.

**2. Nudge Theory: Architecting Choice**
A nudge is a change in the choice architecture that predictably alters behavior without forbidding any options or significantly changing economic incentives.
- **Defaults are Destiny:** The default choice is the single most powerful nudge. This places an immense ethical and technical responsibility on our shoulders.
    - *Tech Note:* The `defaultChecked` or `defaultValue` in a form component is a behavioral sledgehammer. A checkbox that says "Protect my privacy" and is ticked by default has a vastly different outcome than one that is unticked. We must log default selections as a core analytics event to ensure our "helpful nudge" isn't driving users into a state they don't want and didn't choose.
- **Anchoring and the Decoy Effect:** We don't judge prices in a vacuum; we judge them relative to an "anchor."
    - *The Economist's Classic Example:*
        - A: Online Subscription - $59
        - B: Print Subscription - $125
        - C: Print & Online - $125  <-- The Decoy makes option C a cognitive no-brainer.
    - *Dev Note:* When rendering pricing tables, the structure of the data model must support the "decoy" plan type. The front-end rendering logic isn't just painting pretty cards; it's algorithmically highlighting the "most popular" or "best value" option, often using visual weight, size, and color with a "Most Popular" badge to make the anchor and the decoy perform their psychological work.

**3. Mental Accounting: Value Relativity**
Users place different subjective values on the same amount of money based on its source and intended use. A tax refund is "free money," while a salary bonus is "hard-earned cash." A $200 credit in a "Marketing Budget" line item is spent differently than $200 from a personal account.
- *UX Application:* Structuring pricing. A business productivity app's pricing page shouldn't just be "Pro plan is $15/month." It should be "Automate your expense reports. The average employee saves 5 hours/month. At $50/hour salary, that's a $250 value. Your price: $15/month." This reframes the cost from an expense to an investment with a measurable ROI, tapping into a different mental account.

---
