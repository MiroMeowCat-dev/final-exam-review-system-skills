# Evolution Loop

Use this reference when the user wants the review system to keep improving across modules, subjects, and exam seasons.

## Course-Level Evolution

After each module or practice round, update:

- `review-plan.md`: current phase, current module, completed/pending task states, and next action.
- `mistake-log.md`: wrong question, wrong answer, correct answer, tested point, why wrong, memory hook, and similar trap.
- `vocab-log.md`: unfamiliar English term, Chinese meaning, exam reaction, context, and memory hook.
- `weak-points.md`: weak concept, evidence, repair action, and retest date.
- `teacher-style.md`: recurring stem wording, distractor design, repeated knowledge areas, and difficulty.
- `evolution-notes.md`: what should change in the next module's notes or practice questions.

Do not rebuild the whole review plan after every practice round. Update only the status fields and next action unless the user's deadline, scope, teacher hints, or available materials changed.

## Review Adjustment Rules

If mistakes are mostly vocabulary:
- Add recognition drills and bilingual keyword tables.
- Put English terms closer to Chinese explanations.
- Use question stems that repeat the same term in different wording.

If mistakes are mostly mechanism/sequence:
- Rewrite the module logic as a chain.
- Add arrow diagrams or numbered steps.
- Ask sequence and cause-effect MCQs.

If mistakes are mostly comparison:
- Build tighter A vs B tables.
- Add "which statement is true/false" questions.
- Include near-miss distractors.

If mistakes are mostly code output:
- Add short executable-looking examples.
- Ask output, error, and final variable state questions.
- Explain mutation, indexing, slicing, loop boundary, truthiness, operator precedence, and type behavior.
- Add one same-type variant question after the explanation.

If mistakes are mostly data-structure or chart-choice questions:
- Rebuild the comparison table around use case, strengths, limits, and exam keywords.
- Add scenario-based MCQs that ask for the most appropriate list/dict/array/chart.
- Explain why the wrong options are tempting but unsuitable.

If mistakes come from `NOT`, `except`, or wording:
- Add stem-recognition drills.
- Mark negative wording clearly in explanations.
- Include distractor diagnosis.

If the user is running out of time:
- Compress new notes.
- Prioritize teacher style, mistakes, high-yield traps, and simulation.
- Reduce long explanations except for repeated weak points.

## Skill-Level Evolution

When a lesson is useful beyond one course, update the skill itself:

1. Decide whether the change belongs in `SKILL.md` or a reference file.
2. Put core workflow changes in `SKILL.md`.
3. Put subject-specific or template-heavy details in `references/course-adaptation-and-templates.md`.
4. Put feedback-loop rules in `references/evolution-loop.md`.
5. Keep the skill concise; do not add course-specific lecture content to the skill.
6. Validate after edits with the skill validator.

Examples of reusable lessons:

- A new subject type needs a different practice-question pattern.
- A repeated PDF rendering problem needs a stronger quality check.
- The user consistently struggles with English stems, so the default module template should include more stem-recognition practice.
- Teacher review questions reveal a recurring distractor style that should influence simulation generation.
- Python modules reveal repeated code-output misses, so future programming modules should include more examples before the practice set.

## Retest Pattern

After repairing weak points, generate a small retest:

```markdown
# Retest

- Scope:
- Weak points targeted:
- Question count:
- Difficulty:
- Success threshold:
```

If the user passes the retest, move the weak point to monitoring. If not, rewrite the explanation using a different representation and test again.
