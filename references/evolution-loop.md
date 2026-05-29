# Evolution Loop

Use this reference when the user wants the review system to keep improving across modules, subjects, and exam seasons.

## Course-Level Evolution

After each module or practice round, update:

- `review-plan.md`: current phase, current module, completed/pending task states, and next action.
- Review weights: adjust `S+` through `X` labels when teacher questions, mistakes, vocabulary problems, new materials, completion rate, or remaining time change the expected exam value.
- `mistake-log.md`: wrong question, wrong answer, correct answer, tested point, why wrong, memory hook, and similar trap.
- `vocab-log.md`: classified professional terms, ordinary words, and exam-stem phrases with the right explanation depth.
- `weak-points.md`: weak concept, evidence, repair action, and retest date.
- `teacher-style.md`: recurring stem wording, distractor design, repeated knowledge areas, and difficulty.
- `evolution-notes.md`: what should change in the next module's notes or practice questions.

Do not rebuild the whole review plan after every practice round. Update only the status fields and next action unless the user's deadline, scope, teacher hints, or available materials changed.

## Weight Adjustment Rules

Increase a section's weight when:
- Teacher review questions repeatedly test it.
- The user makes repeated mistakes or marks low confidence.
- It connects multiple later topics.
- It contains high-yield diagrams, code-output patterns, mechanisms, formulas, or comparison traps.
- It has many professional terms that block question comprehension.
- It becomes more valuable because the exam is close and it has high time return.

Decrease a section's weight when:
- Teacher explicitly marks it as not important or detail-only.
- It is mostly background and rarely appears in review questions.
- The user already answers it reliably and time is short.
- It has many slides but few testable concepts.
- It is lower yield than remaining unfinished `S+`, `S`, or `A` topics.

When weights change, adjust output volume immediately:
- `S+` or `S`: expand notes and practice unless already mastered.
- `A` or `B+`: keep useful coverage, but compress if behind schedule.
- `B` or `C`: compress when time is limited.
- `D`: mention only.
- `X`: skip or defer.

## Environment And Schedule Rebalancing

Recalculate workload whenever the user resumes, finishes a module, sends answers, adds teacher review questions, or changes the deadline.

Check:
- Days and hours remaining.
- Completed modules and generated PDFs.
- Remaining modules and their tier distribution.
- Mistake repair still pending.
- Vocabulary load, especially professional terms.
- Whether the current phase is knowledge building, module practice, teacher-question practice, weak-point repair, simulation, or final review.

If the user is ahead of schedule:
- Keep explanatory depth for `S+`, `S`, and `A`.
- Add deeper examples or challenge questions for persistent weak points.

If the user is on track:
- Follow the normal tier workload table.
- Keep the next action narrow and concrete.

If the user is behind schedule:
- Compress `B+/B/C`.
- Drop most `D/X`.
- Move quickly from notes to practice for `S+`, `S`, and urgent `A`.
- Prioritize teacher-style questions and mistake repair over broad rereading.

If the user is in final emergency mode:
- Stop expanding new low-tier notes.
- Build a compressed pack from `S+`, `S`, wrong questions, professional terms, English stem traps, and teacher review-question patterns.

When changing a time plan, explicitly state what workload was reduced or expanded and why.

## Review Adjustment Rules

If mistakes are mostly vocabulary:
- Separate professional terminology from ordinary vocabulary before adding drills.
- For professional terms, add detailed Chinese explanation, related concepts, exam wording, common traps, and memory hooks.
- For ordinary words, keep short common meanings and quick recognition cues.
- Put English terms closer to Chinese explanations in module notes.
- Use question stems that repeat the same term or phrase in different wording.

If mistakes are mostly professional terminology:
- Rebuild the module's keyword table around the tested concept, not just the English word.
- Add comparison rows for similar professional terms.
- Generate MCQs that test definition, function, location, mechanism, and application of the term.

If mistakes are mostly ordinary vocabulary:
- Add a compact ordinary-word list for the current module.
- Avoid long concept explanations unless the word is actually functioning as a professional term.
- Generate quick stem-reading drills using the words in context.

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
