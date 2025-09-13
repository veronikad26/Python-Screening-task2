# Python Screening Task 2 — Debugging Prompt

**Purpose:** This repository holds the materials for *Task 2: Write a Prompt for an AI Debugging Assistant*.  
Below is a concise explanation of the design choices behind the prompt, how it prevents revealing solutions, how it encourages student-friendly feedback, and direct answers to the required reasoning questions (tone, balance, and adaptations).

**Submitted By:** Veronika Dhingra

---


## Design choice

---

## 🔄 Workflow Flowchart

```mermaid
flowchart LR
    A[Empathy & Restatement] --> B[Diagnosis: Likely Causes]
    B --> C[Debugging Steps / Experiments]
    C --> D[Hints: Concept → Localize → Targeted Experiment]
    D --> E[No Solution Given]

1. **Socratic + scaffolded workflow**  
   - The prompt forces the assistant to follow a predictable sequence: empathy/restatement → check for missing info → short diagnoses → small experiments → three escalating hints → resources & next step.  
   - **Why:** Scaffolding teaches debugging skills and prevents the assistant from jumping straight to the fix. It avoids spoon-feeding the entire solution directly to the user which promotes logic building and         learning.  

2. **Suggestions before solutions**  
   - The assistant is instructed to suggest small experiments (prints, assertions, minimal test commands) rather than code replacements.  
   - **Why:** Students learn by observing program state and interpreting results. The prompt intentionally pushes the AI to teach debugging skills rather than handing over the answer to the student
   

3. **Conciseness and friendliness**  
   - Responses are short (≤300 words) and use beginner-friendly language by default.  
   - **Why:** Clear, supportive replies are easier to act on and reduce student frustration.

5. **Explicit hard rules**  
   - The prompt contains unambiguous prohibitions (no corrected code, no direct fixes but only abstract pseudocode if asked for high-level guidance).  
   - **Why:** Clear constraints keep the assistant from leaking full solutions.

---

## Avoids giving the direct solution

- **Explicit prohibitions**: Never provides corrected code, implementation diffs, or exact one-line fixes. If asked directly, the assistant must politely refuse and offer a final hint instead.  
- **Controlled outputs**: Tiny snippets allowed only for *observation* not to alter logic.  
- **Template enforcement**: The reply structure (diagnosis → experiments → hints → next step) channels the assistant into guiding discovery, not patching the bug.  
- **Pseudocode policy**: High-level pseudocode may be given but no clear syntax. 

---

## Student-friendly feedback

- **Empathy + restatement** to show understanding and reduce frustration.  
- **Prioritized likely causes** (2–4 bullets) give students realistic directions without overload.  
- **Actionable, small experiments** (3–6 steps) help them gather evidence quickly.  
- **Escalating hints** scaffold discovery: concept → location → experiment.  
- **Next-step & resources** ensure students always know what to try next.  
- **Supportive tone** maintains motivation and focus.

---

## Reasoning 

### 1) What tone and style should the AI use when responding?  
Friendly, encouraging, and Socratic. Use jargon-light language by default, shifting to more technical phrasing if the student is and advanced learner. Responses should be concise (≤300 words) and avoid condescension.

### 2) How should the AI balance between identifying bugs and guiding the student?  
Begin with a short prioritized diagnosis (2–4 possible root causes), then suggest targeted, minimal experiments the student can run to collect evidence. The assistant should *guide discovery* (ask and suggest) rather than *prescribe fixes*. More specific hints should only appear once earlier steps have been tried and attempted. This creates a learning enviornment between the AI and the learner. 

### 3) How would you adapt this prompt for beginner vs. advanced learners?  
- **Beginners:** Use simple, clear language, define technical terms, recommend step-by-step 'print()' checks, small inputs and basic test commands. Provide more guidance and beginner-friendly resources which enhance the learning for the student.  
- **Advanced learners:** Offer abstract, higher-level guidance and debugging techniques including invariants, profiling, fuzz testing and architecture issues. Suggest advanced tools (linters, profilers, property-based testing) without detailed instructions.



