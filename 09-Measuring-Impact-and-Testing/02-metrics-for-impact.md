
 
This file tackles the profound problem: "What should we measure?" Vanity metrics (page views, total sign-ups) stroke the ego but provide zero psychological insight. This file defines the psychometrically-valid outcome measures that tell us if we're successfully changing behavior.

**1. The Hierarchy of Metrics: From Output to Outcome**
We must redefine our KPIs based on the behavioral outcomes defined in Folder 03.
- **Level 1 - The Output Metric (The Psuedo-Insight):** A user completed a sign-up form. This is a system state, not a behavioral outcome. It's easy to measure, but it tells you nothing about the user's mental state.
- **Level 2 - The Action Metric (The Mechanical Behavior):** A user performed a specific action. "Saved a document." "Invited a user." This is better, but still lacks context.
- **Level 3 - The True Behavioral Outcome KPI (The Emotional & Functional Job):** The user's job is not just "invite a user." The job of a manager persona is to "effectively coordinate my team to feel less stressed." The outcome KPI might be "A project with 3+ active collaborators logging into the project 5 days in a row." This KPI signals that the *target outcome* of collaborative coordination has been achieved. The user has successfully automated their "invite user" routine into a functioning team habit.
- *Dev's Core KPI Architecture:* Your analytics data warehouse must model these as distinct entities. An event payload for a user action is not just `{event: 'click', label: 'invite_button'}`. It must be a semantically rich event: `{event: 'TargetOutcomeAttempted', targetOutcomeId: 'team_collaboation_milestone', state: {currentTeamSize: 2, targetTeamSize: 3}}`. This shifts the fundamental analytics question from "How many clicks?" to "At what rate are users progressing through our pre-defined behavioral outcome milestones?"

**2. The "Guardian" Metrics: The Psychological Health Check**
For every North Star behavioral outcome KPI, we must have a paired counter-metric that detects if we are hitting our goal at the cost of the user's psychological well-being.
- **North Star Metric:** Daily Active Users (DAU). **Guardian Metric:** "Compulsive Use Score." A ratio of (unsolicited, late-night, rapid-scrolling sessions with low content creation) to total sessions. If DAU is up but the compulsive score is significantly up, you are not manufacturing healthy habits; you are manufacturing clinical-grade anxiety loops. This is a system health alarm.
- **North Star Metric:** Average Revenue Per User (ARPU). **Guardian Metric:** "Seller's Remorse Churn." A cohort of high-spending users who completely churn out within 60 days. High ARPU from this segment is a psychological cancer. The `GuardianMetricService` does not optimize product features; it triggers an alert to the executive team and the ethics council. It's a safety valve built directly into the core business intelligence pipeline.

**3. The Single Metric That Matters: The Behavioral Value Exchange Index (BVEI)**
This is the ultimate, synthesizing metric. It measures the perceived fairness of the exchange: `(Perceived Value Gained) / (Perceived Cost)`. A score > 1.0 means the user is getting a fair deal; the business is sustainable. A score < 1.0 means the user is being psychologically exploited; churn is inevitable.
- *How to Proxy this KPI:* It's a composite score from different data sources.
    - **Perceived Value Gained:** Measured by depth of feature adoption for core JTBD features, qualitative NPS scores segmented by persona, and rate of unsolicited, positive social sharing.
    - **Perceived Cost:** Measured by subscription price (objective), a user-friction survey (subjective "time and effort" cost), and analysis of "cognitive strain" episodes—e.g., how often a user hits a dead end, triggers an error state, or exhibits "pogo-sticking" (rapid back-and-forth navigation).
- *Dev's Ultimate Dashboard:* The CEO's dashboard should be this single number, the BVEI, trended over time. It doesn't tell you what to do, but it tells you the absolute, unvarnished health of the human-product relationship. Building this aggregation pipeline is the final, capstone task of a UX Psychology Developer, integrating behavioral, financial, and experiential data into a single index of truth.

---

