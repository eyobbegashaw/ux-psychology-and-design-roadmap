
This file dismantles the standard "As a... I want... so that..." template and rebuilds it with a psychological core. A backlog isn't a to-do list; it's a prioritized sequence of behavioral interventions.

**1. The Anatomy of a Psychologically-Complete User Story**
The standard template captures a persona, an action, and a benefit. We must inject the motivational context and cognitive state.
- **Standard Story:** "As a **user**, I want to **filter search results** so that I can **find a product faster**."
- **Psychology-Infused Story:** "As a **Low-NFC (Need for Cognition), high-anxiety Purchaser** (Persona + Cognitive State) who is feeling **overwhelmed by choice** (Current Emotional State), I want to **apply a single, one-click curated filter like 'Best for Beginners'** (Minimal-Cognitive-Ability Action), so that I can feel a **calm sense of certainty and make a confident purchase** (Emotional & Functional Outcome)."
- **Dev Specification Impact:** The standard story leads to a generic faceted search UI. The psychology-infused story directly specifies the MVP: a row of prominent, magazine-style "Curated For You" buttons above the fold. The complex faceted search, which serves a different persona (High-NFC Explorer), is a separate, lower-priority story. This stops feature bloat at the requirements stage.

**2. The Backlog as a Behavioral Gradient**
We can't ask a user to climb a mountain in one step. The backlog must be ordered according to the Fogg Behavior Grid, creating a gradient of increasing commitment.
- **Epic 1: The Foothills (Green Dot - Do New, One-Time).**
    - **Stories:** View a public feed. Watch an introductory video. Read one explainer article. These require minimal ability and motivation. The outcome is passive consumption.
- **Epic 2: The Climb (Blue Dot - Do Familiar, Multiple Times; Green Span).**
    - **Stories:** Save an item to a private list. Follow a topic. Upvote a post. These require a small, low-stakes action. The outcome is building a personal "investment."
- **Epic 3: The Peak (Purple Path - Increase Behavior).**
    - **Stories:** Create your own first post. Upload a profile picture. These are high-investment, identity-creating actions.
- **Epic 4: The New Normal (Purple Path/Black Path - Permanent Change).**
    - **Stories:** Invite a team member to collaborate. Become a community moderator. The outcome is a durable identity shift.
- **Prioritization Logic:** The backlog's priority isn't "highest business value" in a vacuum. It's "which story is the next, psychologically-feasible step on the behavioral gradient that bridges the gap between the user's current, unmotivated state and our ultimate target outcome?"

**3. Acceptance Criteria as Psychological Specifications**
"Given-When-Then" becomes a tool for cognitive state-transition testing.
- Given the user is in an anxious state on the pricing page (System 2 is hyper-vigilant),
- When a service fee appears for the first time at checkout,
- Then the fee explanation must not be a hidden tooltip but a clearly visible, one-line, plain-language justification directly below the total, and the entire page must avoid any color or animation changes that trigger a System 1 threat response (like a flashing red error). The acceptance criterion is: "The user must not experience a measurable increase in cognitive load," which we can test.

---
