 
This file is the final translation. We take the emotional journey and the behavior-infused stories and model them as concrete, deterministic logic using UML flowcharts, but with a twist: we are modeling not just the system's logic, but the user's cognitive decision tree.

**1. The Cognitive Flowchart (The User's View)**
Before we draw the system's process, we must draw the user's decision-making flowchart.
- `[Start]` -> `[See Login Screen]` -> `{Decision: Do I remember my password?}`.
- -> `[Yes]` (Confidence) -> `[Type Password]`.
- -> `[No]` (Anxiety) -> `{Decision: Is there an easier option?}` -> `[See "Use Biometrics" button]` (Relief) -> `[Scan Fingerprint]`.
- Why this first? It forces us to design the `{Decision}` nodes. The system flowchart then becomes about providing the optimal path for the "No" branch. A user in an anxiety state at `{Decision: Is there an easier option?}` needs a phenomenal "Facilitator" prompt right there. This cognitive flowchart is the direct input for the UI's information architecture and component placement.

**2. The System Process Model as a Psychological State Machine**
Now, we model the system. But each system state (`LOGGED_OUT`, `AUTHENTICATING`, `AWAITING_MFA`, `LOGGED_IN`) is directly mapped to a user's cognitive state (Curious, Neutral, Impatient, Satisfied).
- *A Mapped State Transition:*
    - **State:** `AWAITING_MFA` (System). **User Cognitive State:** "Slightly frustrated but secure." (They understand why it's happening).
    - **Allowed User Actions:** Enter code, Resend code, Use backup code.
    - **Forbidden User Actions:** Go back to login. (This would be a security hole and a cognitive dead end).
- **An "Error State" is a Psychological "Fail State":** If the system transitions to `MFA_FAILED`, it's not just a technical error. The user has simultaneously transitioned to a "Feeling Locked Out & Insecure" cognitive state. The error-handling logic in our flowchart must therefore include a recovery branch that doesn't just say "Error," but says: "That code didn't work. But don't worry, your account is still locked and safe. Here is your designated recovery manager's phone number." The flowchart explicitly connects a technical exception to a psychological intervention.

**3. Connecting Flowcharts to Backend Event-Driven Architecture**
These flowcharts become the sacred source of truth for our event storming sessions. A transition in the flowchart from `AWAITING_MFA` to `MFA_FAILED` is a domain event: `UserMfaFailedEvent`. This event is handled by three distinct services:
1.  **Security Service:** Logs the failure, checks for brute-force patterns.
2.  **Analytics Service:** Records this as a critical conversion funnel drop-off point, tagged with the `anxiety` cognitive state flag.
3.  **Trust & Recovery Service:** Triggers an immediate, out-of-band communication (if a pattern is detected): "We saw you had trouble logging in. Is everything okay? Click here to get immediate, human support."
This is the end goal: transforming abstract user psychology into a tightly-defined, event-driven, and deeply humane system architecture. The flowchart isn't a diagram; it's the central nervous system of our product.