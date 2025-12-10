Here is a condensed **AI Coding Prompt Grammar Cheatsheet**. You can keep this accessible to quickly structure your requests for maximum accuracy.

---

# 📜 AI Coding Prompt Cheatsheet

### 1. The Syntax Structure: `C.R.C.O.`
Every prompt should follow this sentence structure for best results.

| Component | Definition | Example Keywords |
| :--- | :--- | :--- |
| **C**ontext | Who is the AI? What is the current state? | *"Act as a Senior Architect...", "I am using Next.js 14..."* |
| **R**equest | What specific action do you want? | *"Refactor...", "Scaffold...", "Debug...", "Write unit tests..."* |
| **C**onstraints | What rules must be followed? | *"Use Tailwind only...", "No external libraries...", "Must be TypeScript..."* |
| **O**utput | How should the answer look? | *"Return code only...", "Explain the logic first...", "JSON format..."* |

---

### 2. The "Action Verb" Dictionary
Don't use weak verbs like "make" or "fix." Use precise technical commands.

* **Scaffold:** Create the file structure and folder hierarchy (no logic yet).
* **Refactor:** Change the code structure without changing its behavior (clean up).
* **Annotate:** Add comments and documentation strings to existing code.
* **Decouple:** Separate a complex function into smaller, independent pieces.
* **Mock:** Create fake data or a fake API response for testing.
* **Hydrate:** Connect static HTML to dynamic JavaScript logic.
* **Optimize:** Improve time complexity (Big O) or memory usage.

---

### 3. The Adjective Bank (Style Modifiers)
Add these adjectives to your prompt to enforce code quality.

* **"Idiomatic":** Write code the way a native expert of that language would (e.g., "Pythonic").
* **"Atomic":** Keep components/functions small and focused on one single task.
* **"Defensive":** Include error handling and type checking for edge cases.
* **"Dry (Don't Repeat Yourself)":** Ensure no logic is duplicated; use helper functions.
* **"Strict":** (For TypeScript) Do not use `any` types; strictly define interfaces.

---

### 4. Copy-Paste Templates

#### The "New Feature" Template
> "Act as a **[Language]** expert. I need to build a **[Feature Name]**.
> **Context:** My current stack is **[Stack Details]**.
> **Task:** Scaffold the necessary files and write the logic for **[Functionality]**.
> **Constraints:** Use **[Library X]** for styling. Ensure the code is modular.
> **Output:** Provide the file paths and the code blocks for each file."

#### The "Debugger" Template
> "I am getting the following error: **[Error Message]**.
> **Context:** This happens when I **[User Action]**.
> **Task:** Analyze the code below and find the root cause.
> **Constraints:** Do not rewrite the whole file, only fix the broken function. Explain *why* it broke.
> **Output:** Fix the bug and add a comment explaining the fix."

#### The "Refactoring" Template
> "Review the following code block.
> **Task:** Refactor this to be more readable and performant.
> **Constraints:** Reduce the nesting level (avoid 'arrow code'). Add proper error handling.
> **Output:** Return the optimized code only."

---

### 5. "Magic Phrases" for Better Logic
Use these specific sentences to stop the AI from hallucinating or being lazy.

* **"Think step-by-step."** (Forces the AI to use logic before writing code).
* **"Do not skip any code for brevity."** (Prevents the AI from writing `// ... existing code ...`).
* **"Cite your sources."** (If asking for a library recommendation).
* **"Critique your own solution."** (Asks the AI to look for flaws in the code it just wrote).

---
