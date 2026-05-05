 
This file is the linchpin. If User Personas define the "who," this file defines the critical "what." We must define the Target Outcome with the precision of a developer writing a function signature. The input is a user's current behavioral state. The output is the desired, measurable behavioral state.

**1. Distinguishing Dream Outcomes from Target Outcomes**
A Dream Outcome is "be fit." A Target Outcome is "run 5k three times a week for a month." We can't design for a dream. We must decompose it into a sequence of concrete, achievable Target Outcomes using the Behavior Grid from Folder 02.
- **The Decomposition (The Green Dot Path):**
    - First Target Outcome (Green Dot, One-Time): Complete a single 1-mile walk this week.
    - Second Target Outcome (Blue Span, Duration): Complete three 1-mile walks in a week, for two weeks.
    - Third Target Outcome (Purple Path, Permanent-ish): Run 5k three times a week for a month.
- **Dev Note:** This decomposition IS the product roadmap. A win for the Minimum Viable Product (MVP) is not "get users fit." It's "get the user to complete a Green Dot action." Our analytics instrumentation is built to track these specific behavioral outcomes as the primary North Star Metric, not a vague proxy like "engagement minutes."

**2. Defining the Core Action for Each Outcome**
For each target outcome, there is one critical, non-negotiable action the user must take.
- *The Action Must Be a Verb:* It's not "signed up." That's a system state. It's "completed their first purchase," "invited a team member," "ran their first report."
- **Backcasting from the Action:** If the Core Action for the first week is "User publishes their first post," we backcast:
    - What must be true immediately before? They have a draft.
    - Before that? They've started writing in the editor.
    - Before that? They've clicked "New Post."
    - Before that? They've arrived on the dashboard.
- **The Funnel as a Behavioral Chain:** This backcasting IS the activation funnel. Every step in that chain is a micro-behavioral outcome. The UI state machine for this flow is now a behavioral machine. If a user fails at the "start writing in the editor" step, the psychological intervention is not a generic pop-up; it's a specific Facilitator prompt, like a friendly placeholder text: "Don't worry about perfection. First drafts are supposed to be messy. What's on your mind?"

**3. Outcome-Based Metrics: The Living System**
The final output of this file is the specification for our analytics event schema. We're not tracking random clicks. We're tracking a finite set of `CoreActionAttempted`, `CoreActionCompleted`, and `TargetOutcomeAchieved` domain events. Every event carries the persona type and current psychological state vector of the user. This allows us to segment our conversion funnels not just by traffic source, but by *Need for Cognition* or *Uncertainty Avoidance*, providing profoundly deeper insight into why a behavior change is or isn't happening.

---
