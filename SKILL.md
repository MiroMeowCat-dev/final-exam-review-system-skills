---
name: final-exam-review-system
description: Build a reusable final-exam review system from course materials. Use when Codex needs to read PPT/PDF/DOCX/images/handouts/exercises/code screenshots for a course, create a module-by-module review plan, analyze review-part weights from knowledge count/importance/exam likelihood/user weakness, generate appropriately sized bilingual Chinese-English study notes, produce exam-style MCQs, grade answers, maintain mistake and vocabulary logs, analyze teacher review-question style, and iteratively optimize review materials for different subjects including Python/programming courses.
---

# Final Exam Review System

## Core Intent

Turn raw course materials into a closed-loop exam-review system:

1. Read all source materials first, including text, images, diagrams, arrows, tables, learning objectives, summaries, exercises, and teacher markings.
2. Build a course-level map and module-by-module review plan.
3. Generate bilingual, high-density, reconstructed review notes.
4. Generate concise exam-style practice questions.
5. Grade the user's answers, update mistake and vocabulary logs, then target weak points.
6. Use teacher review questions and accumulated mistakes to evolve the next round of materials.

Default to supporting a Chinese-speaking student preparing for an English multiple-choice final exam unless the user specifies another exam format.
When a course includes Python or programming teaching content, treat it as a likely high-priority area until the actual materials and teacher hints prove otherwise.

## Session Start State Check

Before doing intake or planning, determine the current review state from the user's course folder and prior artifacts:

1. No usable `review-plan.md`: start from intake, read the source inventory, then create the first detailed review plan.
2. Existing `review-plan.md` with pending items: read the plan, module notes, mistake log, vocabulary log, weak-point file, and teacher-style file if present; continue the next unfinished task instead of rebuilding the plan.
3. Existing plan plus new materials or changed deadline: update the plan minimally, record what changed, then continue from the revised next action.
4. Existing plan but unclear progress: infer progress from completed module files, PDFs, logs, and timestamps; ask at most one concise clarification only if the next step cannot be safely inferred.

State the mode before acting: `starting new plan`, `continuing existing plan`, or `updating existing plan`. Treat `review-plan.md` as the source of truth once it exists unless the user explicitly asks to restart.

## Intake

Start by locating all available materials and making a source inventory:

- PPT/PDF slides, handouts, lecture notes, assignments, practice questions, screenshots, images, tables, code screenshots, and teacher review questions.
- Exam information: format, language, number of questions, allowed scope, teacher hints, deadlines, and the user's available days.
- Course traits: life science, programming, quantitative, humanities/social science, language-heavy, or mixed.
- Programming traits when present: Python topics, code-output patterns, data structures, graph/chart selection, common errors, and whether code appears as text or screenshots.

Do not summarize from filenames, prior memory, or old notes alone. If visual content is present, inspect it or ask for renderable pages/screenshots when inspection is blocked.

## Reading Rules

Read each module before writing its notes. Capture:

- Text content, slide titles, definitions, examples, summary slides, and learning objectives.
- Diagrams, pathways, flow arrows, comparison charts, maps, curves, microscopic images, UI/code screenshots, and table relationships.
- Teacher labels such as `important`, `not important`, `do not try to learn`, `details not important`, starred slides, circled content, and repeated emphasis.
- Hidden exam value from visuals: sequence, direction, cause-effect, structure-function, receptor/pathway mechanisms, code behavior, formula constraints, or comparison boundaries.

Images are evidence, not decoration. Keep only a few genuinely useful images in final materials; usually reconstruct visuals into mechanism chains, comparison tables, logic maps, keyword tables, traps, and memory hooks.

## Planning Workflow

Create a review plan only when the state check shows there is no usable plan, or when the existing plan must be revised because the scope, deadline, or available materials changed. After the first full pass, create or update the plan before generating detailed materials:

1. Course map: modules, major concepts, dependency order, exam-likely areas, and low-priority areas.
2. Pacing: divide available days into knowledge-building, module practice, teacher-question practice, weak-point repair, and final simulation.
3. Module plan: for each module, list source files, expected outputs, difficulty, and what must be practiced.
4. Subject priority: for Python/programming modules, explicitly plan concept understanding, code-output practice, easy-error repair, and data-structure/chart-selection questions.
5. Adaptive review weighting: estimate each module/section/subtopic's value and workload before deciding output volume.
6. Compression rule: make early modules more explanatory when the user's logic is not established; make later review increasingly focused on teacher style, mistakes, and high-yield traps.
7. Continuation rule: mark completed, in-progress, and pending tasks so future sessions can resume without re-planning.

Read `references/course-adaptation-and-templates.md` when adapting the workflow to a specific subject or when the user asks for concrete output templates.

## Adaptive Review Weighting And Workload Allocation

Before generating detailed notes or questions, evaluate each review part at the module, session, and subtopic level. Use the result to decide explanation depth, table/detail density, visual reconstruction, examples, question count, and PDF space. Do not give every part the same length by default.

Use four scoring groups:

1. Content value: knowledge-point count, concept complexity, mechanism/sequence length, comparison density, professional-term load, visual/data/code density, and dependency on later topics.
2. Exam value: teacher emphasis, learning objectives, summary slides, teacher review-question frequency, fit with English MCQs, likely stem types, distractor potential, and match with observed teacher style.
3. Personal risk: wrong answers, circled uncertainty, unknown professional terms, ordinary vocabulary blocking comprehension, slow response, repeated confusion, and low confidence.
4. Environment and schedule: days remaining, available study time, completion rate, remaining weighted workload, current phase, deadline pressure, and whether the user is ahead of or behind the plan.

Add subject-specific dimensions after the base groups. Examples:

- Python/programming: code-output risk, mutation vs reassignment, final variable state, index/slice/boundary risk, data structure choice, chart choice, and error prediction.
- Life science/medicine/psychology: pathway order, receptor/region/function matching, arrow direction, hormone/ion/signal flow, anatomy map risk, and mechanism-vs-location traps.
- Statistics/data/quantitative courses: formula conditions, assumption checks, unit/variable meaning, graph interpretation, correlation vs causation, and calculation trap density.
- Humanities/business/social science: concept boundary, theory/framework comparison, case matching, chronology, named model use, and scenario-application risk.
- Language-heavy courses: term recognition, false friends, stem phrase recognition, definition boundary, and ordinary-vs-professional word ambiguity.

Use fine-grained tiers instead of only high/medium/low:

- `S+` absolute core: must be detailed, frequently tested, fragile, or repeatedly wrong.
- `S` high-frequency core: detailed notes, multiple examples, and many MCQs.
- `A` high value: solid explanation, key traps, and required practice.
- `B+` medium-high value: focused explanation with representative traps.
- `B` standard value: normal coverage and a small question set.
- `C` low value: compact explanation, essential keywords only.
- `D` skim: one or two sentences, usually no questions.
- `X` skip/defer: omit unless needed for context or the user asks.

Use schedule-aware workload allocation:

- If time is sufficient and progress is on track, cover `S+`, `S`, and `A` fully, keep `B+/B` standard, compress `C`, and skim `D`.
- If time is sufficient but mistakes are concentrated, increase personal-risk weight and expand weak `A/B+` topics.
- If time is tight or the plan is behind, expand only `S+`, `S`, and urgent `A`; compress `B+/B`; skip most `C/D`.
- If teacher review questions are available, raise exam-value weight and prioritize topics matching teacher style.
- If knowledge review is mostly complete, reduce long explanations and shift workload toward practice, mistakes, vocabulary, and simulation.
- If the user is in final review mode, prioritize `S+`, `S`, teacher-style traps, wrong-question clusters, professional terms, and English stem phrases.

When mentioning or revising time arrangements, compare completed work against remaining weighted workload. Adjust the next workload, not just the calendar. For example, if 40% of time remains but 70% of weighted work remains, compress lower tiers and move immediately to high-yield notes, teacher-style questions, and mistake repair.

Never let slide count alone decide weight. A short section with teacher emphasis, high trap density, strong dependency, or repeated mistakes can be `S+`; a long section marked `details not important` can be `C`, `D`, or `X`.

## Module Output

For each module, produce a source Markdown file first, then export/render a PDF if requested or expected. Each module should usually include:

- Module logic map: the story of the module, not a slide-by-slide list.
- Weight rationale: why each major part is `S+` through `X`, and how that affects generated material, question count, and time allocation.
- Core concepts: Chinese explanations with retained English definitions or keywords.
- English keyword table: English term, Chinese meaning, exam reaction, and common trap.
- Mechanism/sequence chain: `stimulus -> transduction -> pathway -> processing -> output`, or the course-specific equivalent.
- Comparison tables for easy-confusion pairs.
- Visual reconstruction: summarize key figures as flow, relation, direction, contrast, or code/output behavior.
- Examples: include worked examples when the module depends on application, especially Python code output, concept boundaries, and easy-mistake usage.
- MCQ trap list: `NOT/except`, definition vs function, location, mechanism, sequence, comparison, cause-effect, code output, list/dict/array behavior, data-structure choice, chart choice, units, or graph interpretation.
- Practice questions: mostly English single-choice MCQs when the exam is English; format the question sheet and answer key as separate sections.

## Practice Question Formatting

Default practice sets should match the user's preferred two-part layout:

1. Question sheet first:
   - Title as `Practice Questions: <difficulty/focus>`, for example `Practice Questions: 稍难但高频`.
   - Add a short method box in Chinese before the questions, usually: `做题方法：先自己选答案，再看答案解析。遇到代码输出题，请不要凭感觉，逐行写出变量变化。`
   - Put each question in its own lightly separated block with enough whitespace for handwritten answers.
   - Use English question stems and vertical A-D options.
   - Do not show the correct answer or explanation inside the question block.
2. Answer key second:
   - Put answers after all questions, ideally after a page break in PDF outputs.
   - Title as `Answer Key and Explanations`.
   - Use a compact table with exactly these core columns: `Q`, `Ans`, `Why`.
   - Keep `Why` concise and rule-focused; for difficult or professional terms, add brief Chinese clarification only when needed.

When the user sends handwritten/circled answers, preserve the original question numbers so answer checking and mistake logging can map back cleanly.

Avoid these failure modes:

- Only reading text and missing figures.
- Dumping many screenshots into the PDF.
- Deleting all figures and losing pathway/diagram information.
- Writing all-English notes when the user needs Chinese explanation.
- Making only lookup tables without explanation.
- Mechanically summarizing by slide page order.
- Giving equal space to low-weight and high-weight sections.
- Making notes too short to preserve exam logic.
- Mixing answers into the practice question blocks before the user has attempted them.
- Giving answers without logging mistakes and vocabulary.

## Practice And Feedback Loop

After each module:

1. Give a small, high-quality MCQ set that covers the main exam points.
2. Ask the user to send answers, circled wrong questions, screenshots, or uncertain words.
3. Grade answers with concise reasoning.
4. Append mistakes to the mistake log with categories.
5. Append unknown or high-value words to the vocabulary log with professional-vs-ordinary classification.
6. Identify weak points and generate targeted repair notes, same-type variant questions, or follow-up questions.

Use teacher review questions only after the knowledge base is established unless the user asks otherwise. When teacher questions are available, analyze style, repeated concepts, wording patterns, difficulty, and distractor design before generating simulations.

## Mistake And Vocabulary Classification

Classify every logged wrong question by the main reason it happened:

- Concept/definition.
- Mechanism/sequence.
- Comparison/confusion pair.
- Visual, graph, table, pathway, or code screenshot interpretation.
- Code output, data structure, chart choice, or programming behavior.
- English stem wording such as `NOT`, `except`, `most likely`, `best describes`, or `which statement is true`.
- Professional terminology.
- Ordinary vocabulary.
- Careless reading, time pressure, or answer strategy.

Classify every unknown word or term before explaining it:

- Professional term: course-specific concept, process, structure, method, function, receptor, pathway, data structure, statistical term, programming concept, theory, or named framework. Record it separately with detailed Chinese explanation, related concepts, exam wording, common traps, and memory hook.
- Ordinary word: general English word that only affects reading comprehension. Record a short common meaning, the meaning in this question, and a quick recognition cue; do not over-explain it like a course concept.
- Exam-stem phrase: recurring test instruction or wording pattern. Record how to react in MCQs, especially for negative wording and comparison prompts.

If a word can be both ordinary and professional, classify it by its role in the course and the question. For example, `function` is ordinary in general English but professional in programming or physiology when it is tested as a concept.

## Persistent Course Artifacts

Maintain course-specific files in the user's chosen course folder when doing real review work:

- `review-plan.md`: source inventory, current status, timeline, module order, task states, and next action.
- `teacher-style.md`: teacher review-question patterns, wording, repeated traps, and priority areas.
- `modules/<module-name>.md`: module notes and practice set.
- `mistake-log.md`: categorized wrong questions and why they happened.
- `vocab-log.md`: categorized professional terms, ordinary words, and exam-stem phrases.
- `weak-points.md`: current weak modules and next repair actions.
- `evolution-notes.md`: lessons learned that should improve future modules or future courses.
- `pdf/`: rendered module notes, mistake-log PDFs, vocabulary PDFs, and final review PDFs when requested.

Read `references/evolution-loop.md` when updating logs, using mistakes to revise materials, or improving the skill itself.

## PDF Quality

When producing PDFs:

- Keep the Markdown source.
- Ensure Chinese, English, tables, question numbering, and answer sections render correctly.
- Use clear headings, compact tables, and readable spacing.
- Do not let large images dominate pages.
- Keep practice questions and answer keys visually separate; preserve readable spacing for handwritten answers when printed.
- Render-check the PDF when tools are available; fix garbled text, clipped tables, broken layout, or content that is too sparse.
- Keep mistake logs separately exportable as PDFs so they can grow across modules and support final review.

## Completion Criteria

A review cycle is complete only when it has:

- A module/course plan grounded in the actual materials.
- Reconstructed bilingual notes rather than raw slide translation.
- Practice questions with answers and explanations.
- Updated mistake and vocabulary records after the user practices.
- A next-step recommendation based on weak points, teacher question style, and remaining time.
