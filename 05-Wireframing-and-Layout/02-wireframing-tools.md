 
This file isn't about the tools themselves (Figma, Sketch, pen and paper). It's about the cognitive function of the wireframing *process* and what layer of fidelity is required to test a psychological hypothesis. The tool is just an extension of our brain.

**1. The Psychology of Low Fidelity: Why "Ugly" Works**
Low-fidelity wireframes (gray boxes, no images, a default font like Arial) are a psychologist's most powerful tool. Why? Because they deliberately sabotage the Aesthetic-Usability Effect. When you show a stakeholder a polished, colorful high-fidelity mockup, their System 1 kicks in: "Ooh, that looks pretty, it must be good." They stop evaluating the structural psychology and start judging the color palette.
- *The Test:* A low-fidelity wireframe forces the viewer's System 2 to engage with the core question: "Is this the right information, in the right order, at the right time?" A discussion about a gray box is a discussion about cognitive flow. A discussion about a beautifully-rendered hero image is a discussion about emotion and branding. You must use the right tool for the right cognitive conversation.
- *Dev Handoff:* A perfect wireframe handoff is one where the developer can see only the structural constraints—the HTML elements, the semantic hierarchy (`H1`, `H2`, `button`), and the flex/grid relationships—without any visual fluff. A tool that exports this into a basic HTML/CSS skeleton is gold.

**2. The "Content-First" Wireframe: Exposing the Skeleton**
A wireframe must never be built with lorem ipsum. Lorem ipsum is a cognitive vacuum. It tells you nothing. The wireframe must use real, albeit draft, content.
- *The Hypothesis:* A headline isn't a graphical element; it's a psychological trigger. A button's label isn't a string; it's a promise. A wireframe with real copy, even if it's 12px Arial, tests the cognitive logic: "Does this sequence of micro-copy—headline, sub-headline, body text, button label—correctly move the user from State A (curious) to State B (committed)?"
- *The Developer's Role:* This means our content management architecture must be considered in the wireframe. The wireframe is a template for a content model. A "Testimonial Card" wireframe isn't just an image placeholder, a name, and a quote; it's a signal that the backend `Testimonial` data structure needs fields for `photo`, `fullName`, `shortQuote`, and `psychographicTarget` (so the right testimonial can be shown to the right persona).

**3. The Collaborative Wireframe as a "Shared Mental Model" Artifact**
The purpose of a wireframe is to externalize a mental model from a psychologist/designer's brain and implant it into a developer's and PM's brain so everyone is aligned.
- *Cognitive Synchronization:* When a developer looks at a wireframe and says, "Ah, so the user's System 1 is being guided by this big card to the 'Start Free Trial' button, and System 2 doesn't need to engage because we've hidden the complex feature list below the fold," the wireframe has succeeded. It has successfully transmitted a complex psychological strategy. The tool (Figma, Miro, a whiteboard) is just the medium for that brain-to-brain synchronization. The file's version history is a record of our evolving psychological hypotheses.

---
