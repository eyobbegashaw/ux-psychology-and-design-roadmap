This file operationalizes Fogg's Behavior Wizard, which is a framework for selecting the correct psychological strategy based on the type of behavior change we're targeting. As a developer, this helps you scope features correctly. You can't build a feature for a "Blue Dot" behavior the same way you would for a "Purple Path" behavior. The grid uses two axes: Type of Change and Time Period.

**1. The Five Types of Behavior Change (The "What")**
- **Do a New Behavior (Green Dot):** Unfamiliar to the user.
    - *Strategy:* Increase Ability to the absolute maximum. "Try it once." The design must be a Facilitator prompt. A one-click demo, a pre-filled template, an interactive wizard. *Example: A person who has never invested buys their first stock.*
- **Do a Familiar Behavior (Blue Dot):** User knows it, just needs to do it.
    - *Strategy:* Increase Motivation with a Spark prompt. A reminder, a limited-time offer, a social prompt. *Example: A person who has invested before buys another stock.*
- **Increase Behavior Intensity or Duration (Purple Path):** Do more of a behavior.
    - *Strategy:* Here, you can ask for more Ability (more effort) because the user has a high, demonstrated Motivation. Gamification, streaks, and increasing levels of challenge apply here. *Example: A casual runner trains for a marathon.*
- **Decrease Behavior Intensity or Duration (Gray Path):** Do less of a behavior.
    - *Strategy:* This is the hardest one. You must use cognitive strain and friction. Make the behavior harder to do (decrease Ability). A mandatory cooling-off period for an online purchase, or a "Do you really need to buy this?" pop-up linked to a spending tracker. *Example: A person buys fewer sugary snacks.*
- **Stop a Behavior Altogether (Black Path):** Cease a behavior.
    - *Strategy:* The ultimate goal. This often requires a replacement behavior or a powerful, permanent friction. An app that blocks gambling sites is the facilitator that makes the behavior impossible, thereby reducing Ability to zero. *Example: A person stops smoking.*

**2. The Three Time Periods (The "When")**
- **Dot (One-Time):** A single occurrence.
- **Span (Duration):** A behavior with an end. "Learn to code in 3 months."
- **Path (Permanent Change):** A change from now on. "Exercise for life."

**3. The Grid as a Product Backlog Organizer**
This is a powerful tool for prioritizing epics. The psychological difficulty of implementing a "Black Path" feature (permanent cessation) is vastly higher than a "Green Dot" feature (one-time novel action). Your product's complexity, timeline, and required psychological engineering grow exponentially as you move from a Green Dot to a Black Path. This grid lets you have a data-informed conversation with product managers: "You've asked for a feature to stop user churn, which is a Black Path-Span behavior. That requires a fundamentally different, more intrusive, and more friction-heavy architecture than acquiring new users, which is a Green Dot-Dot behavior."

---
