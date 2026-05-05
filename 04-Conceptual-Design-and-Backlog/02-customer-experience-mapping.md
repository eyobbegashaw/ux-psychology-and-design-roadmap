
 
This file is the blueprint for the user's psyche over time. It moves a Customer Journey Map from a fluffy workshop output to a developer's behavioral state machine specification. The map plots not just actions, but emotions, thoughts, and—crucially—the psychological pain points where the system must intervene.

**1. The Dual-Track Map: Actions and Emotional States**
A journey map has two parallel lanes. Lane 1 is what the user *does*. Lane 2 is what the user *thinks and feels*.
- *Example: The "Forgot Password" Journey (A Failure Journey we must design for)*
    - **Action:** Clicks "Login." -> Enters credentials. -> Gets an "Incorrect password" error.
    - **Emotion (Lane 2):** Neutral, habitual (System 1). -> Confident. -> **Jolt of anxiety/low-grade panic. Shift to System 2.** "Wait, which password did I use? Is my account locked? Oh no, I need to pay this bill!"
    - **Action:** Clicks "Forgot Password." -> Checks email. -> Finds no email. -> Checks spam folder. -> Finds email, clicks link. -> Resets password.
    - **Emotion (Lane 2):** **Frustration & self-blame.** "This happens every time." -> Impatient. -> **Escalating anger.** -> Relief, followed by **residual distrust**.
- **The Psych-Dev Translation:** This map reveals that the core product failure isn't the forgotten password, it's the spike of anxiety and the prolonged feeling of helplessness. Our technical solution isn't just a "Forgot Password" link; it's a psychologically-informed recovery state machine.

**2. Identifying "Pain Points" as System Failures and Designing Interventions**
Every dip in the emotional lane is a "pain point" that's a direct call to action for our architecture.
- **The "Jolt of Anxiety" Pain Point:** The error message "Incorrect password" is a cold, System 2 jolt. The intervention is a warm, System 1 message: "Oops! That password doesn't match our records. Need a one-click magic link sent to your phone instead?" We immediately offer a low-ability, high-certainty escape hatch.
- **The "Waiting for Email" Pain Point:** The 30-second delay for a reset email is an eternity of learned helplessness. The intervention is a real-time UI feedback loop. After the user clicks "Send Reset Link," the button greys out and becomes a live status tracker: "Email sent to j***@e***.com. Waiting for you to click... [Resend in 15s]." This turns a passive, anxious wait into an active, system-acknowledged process.
- **Dev Implementation:** This map directly informs a `RecoveryJourneyManager` service. It manages the entire state: `AWAITING_EMAIL`, `EMAIL_DELIVERED`, `EMAIL_BOUNCED`, `LINK_CLICKED`. Based on this state, the UI doesn't just show a static page; it provides a therapeutic, step-by-step feedback loop designed to minimize anxiety and maximize the user's sense of control.

**3. The "Moment of Truth" and the "Peak-End Rule"**
Kahneman's Peak-End Rule states we judge an experience based on how we felt at its most intense point (the peak) and at its end, not on the average of every moment.
- Our journey map must explicitly identify the emotional peak and the end point.
- *The End:* The very last step of the password reset journey must not be a generic "Success!" page. It must be a subtle, satisfying, and reassuring conclusion. A smooth animation bringing them directly back to the login screen with their email pre-filled, a clear visual indicator of security (like a verified checkmark), and a message "Welcome back. We've got you." This isn't just polish; it's a strategic inoculation against the residual distrust from the failure.
- *Dev Note:* The `EndOfJourneyAction` must pass the user's ID to the next screen, enabling a personalized, seamless re-entry into the "happy path," effectively rewriting the emotional memory of the entire ordeal.

---
