Design choices — why I worded it this way

- Socratic + tiered hints: The prompt enforces a three-level hint system (conceptual → targeted → near-solution). That nudges students toward self-repair and learning, instead of passively receiving an answer.
- Structured, repeatable reply format: The ordered sections make it easy to evaluate whether the assistant is helpful and whether it withheld the solution.
- Explicit “no full solution” rule + reveal condition: To avoid accidentally giving away the answer, the assistant is forbidden from posting a full corrected implementation until the student demonstrates effort. This protects learning outcomes.
- Short actionable debugging steps: Practical commands and tiny test suggestions help students make progress quickly without the assistant doing the work for them.
- Encouraging tone: Keeps novices engaged and reduces frustration.

Required reasoning (answers)

1) What tone and style should the AI use when responding?
Friendly, encouraging, and patient. Use a Socratic method: ask guiding questions, give small clues, and avoid lecturing. Use plain language and short paragraphs for beginners; use concise, technical phrasing for advanced users. Always end with clear next steps.

2) How should the AI balance between identifying bugs and guiding the student?
First, identify the most likely root causes (ranked, concise). Then guide the student to confirm them via small, specific experiments (prints, asserts, minimal test inputs). Give increasingly specific hints only if the student is stuck. The assistant should identify clearly but stop short of performing the final code change — the student should apply the fix and learn from it.

3) How would you adapt this prompt for beginner vs. advanced learners?
- Beginners: Use simpler language, add more explicit debugging steps (exact `print()` locations and exact example inputs), longer conceptual explanations, and offer small examples illustrating the concept. Provide reassurance and suggest beginner-friendly tools (`print`, `assert`, `pdb.set_trace()`).
- Advanced learners: Be concise, point to likely pitfalls (mutability, concurrency, floating-point precision, algorithmic complexity), offer references to relevant standard library docs or specific functions, and propose advanced diagnostics (profiling, `pytest` parametrized tests, type checking with `mypy`).
