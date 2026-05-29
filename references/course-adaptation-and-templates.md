# Course Adaptation And Templates

Use this reference when tailoring the final-exam review workflow to a specific course or when concrete output templates are useful.

## Course Profile

Create or update a short course profile before module writing:

```markdown
# Course Profile

- Course:
- Exam format:
- Exam language:
- Time remaining:
- Materials:
- Teacher hints:
- Student strengths:
- Student weak points:
- Output language style:
- PDF required:
```

If the user does not specify exam format, default to English single-choice MCQ because that is the base use case.

## Subject Adaptation

Life science / medicine / psychology:
- Prioritize pathways, receptor mechanisms, anatomical locations, direction of flow, cause-effect, and high-confusion comparisons.
- Convert figures into mechanism chains and comparison tables.
- Common traps: hyperpolarization vs depolarization, receptor type, region/function mismatch, first relay, pathway order.

Programming / data / Python:
- Treat Python teaching content as high priority unless the actual teacher hints say otherwise.
- Prioritize code output, data type behavior, expressions, operators, conditionals, loops, list/dict/array behavior, control flow, function scope, and choosing appropriate data structures or charts.
- Build the logic map in a learning order such as `data types -> expressions -> operators -> conditionals -> loops -> lists/dicts/arrays -> functions -> charts/data structures`.
- Include short code examples and ask what the output/error/final variable state is.
- Use more examples than purely conceptual modules because programming mistakes often come from application details.
- Common traps: mutation vs reassignment, indexing, slicing, truthiness, type conversion, loop boundaries, indentation, key lookup, aliasing, and array/list behavior differences.

Quantitative / engineering / statistics:
- Prioritize formulas, units, assumptions, graph interpretation, variable meaning, boundary conditions, and common calculation traps.
- Include worked examples and wrong-option diagnosis.
- Common traps: unit mismatch, sign/direction, correlation vs causation, formula condition not met.

Humanities / social science / business:
- Prioritize definitions, theorist/framework comparison, cause-effect, chronology, case application, and concept boundaries.
- Include concept maps and scenario-based MCQs.
- Common traps: similar theory names, overbroad definitions, exception wording, mismatched example.

Language-heavy courses:
- Prioritize bilingual term mapping, phrase recognition, false friends, and test-stem patterns.
- Maintain a larger vocab log and include rapid recognition drills.

## Review Plan Template

```markdown
# Review Plan

## Current Status
- Mode: starting new plan / continuing existing plan / updating existing plan
- Last updated:
- Current phase:
- Current module:
- Days remaining:
- Available study time:
- Completion rate:
- Remaining weighted workload:
- Schedule status: ahead / on_track / behind / urgent
- Completed:
- In progress:
- Next action:
- Reason for plan update:

## Source Inventory
| Source | Modules | Visual-heavy? | Teacher hints | Notes |
|---|---:|---|---|---|

## Course Logic Map
1. 
2. 
3. 

## Module Schedule
| Day | Module | Status | Goal | Output | Practice | Checkpoint |
|---|---|---|---|---|---|---|

## Priority
- High:
- Medium:
- Low / skim:

## Adaptive Review Weight Matrix
| Part | Content value | Exam value | Personal risk | Environment pressure | Subject-specific factors | Tier | Output volume | Question load | Time action |
|---|---:|---:|---:|---:|---|---|---|---|---|

Scoring: use 0-5 for each numeric group. Add subject-specific notes instead of forcing every course into the same dimensions. Set `Tier` to `S+`, `S`, `A`, `B+`, `B`, `C`, `D`, or `X`.

## Workload Allocation
| Tier | Notes depth | Examples/visuals | Question load | Time rule |
|---|---|---|---|---|
| S+ | maximum | required | 8-12 | protect even when time is short |
| S | detailed | strongly recommended | 6-10 | protect unless already mastered |
| A | solid | key examples/visuals | 4-6 | keep in normal and tight plans |
| B+ | focused | representative | 3-5 | compress if behind |
| B | standard | optional | 2-4 | keep only if time allows |
| C | compact | usually no | 0-2 | compress heavily |
| D | skim | no | 0 | one or two sentences |
| X | omit/defer | no | 0 | skip unless needed for context |

## Next Action
```

Use `planned`, `in_progress`, `done`, `needs_retest`, or `blocked` for status. When resuming, read `Current Status` first, then inspect logs and module files only as needed to confirm the next action.

## Module Notes Template

```markdown
# Module X - Title

## 1. Module Logic
Chinese explanation of the module's main story.

## 2. Weight Rationale
| Part | Tier | Main reasons | Output volume | Question load | Time decision |
|---|---|---|---|---|---|

## 3. Core Concepts
| English | 中文 | Why it matters | Exam clue |
|---|---|---|---|

## 4. Mechanism / Sequence
`Step 1 -> Step 2 -> Step 3 -> Result`

## 5. Key Comparisons
| A | B | Difference | MCQ trap |
|---|---|---|---|

## 6. Visual Reconstruction
- Figure/diagram:
- What it shows:
- Direction/relationship:
- Likely question:

## 7. Examples / Code Output
- Example:
- What changes:
- Output/result:
- Why:

## 8. MCQ Traps
- 

## 9. Practice Questions
Follow the practice-set layout below.

## 10. Answer Key and Explanations
Follow the answer-key layout below.
```

For non-programming modules, merge the examples/code-output section into core concepts or visual reconstruction. For Python/programming modules, keep it as a required section.

## Adaptive Weight Dimensions

Use the base dimensions first, then add subject-specific dimensions.

Base dimensions:
- Content value: knowledge count, concept complexity, mechanism length, comparison density, professional terms, visual/data/code density, and dependency.
- Exam value: teacher emphasis, learning objectives, summary slides, teacher review questions, MCQ fit, stem type, distractor potential, and teacher style.
- Personal risk: mistakes, uncertainty, unknown terms, vocabulary blocks, slow response, repeated confusion, and low confidence.
- Environment pressure: days remaining, available hours, completion rate, remaining weighted workload, current phase, and whether the plan is ahead/on track/behind/urgent.

Subject-specific examples:
- Python/programming: code output, mutation/final state, index/slice boundary, data structure choice, chart choice, and error prediction.
- Life science/medicine/psychology: pathway order, receptor-region-function matching, signal flow, anatomy maps, and mechanism traps.
- Statistics/data: formula assumptions, unit/variable meaning, graph interpretation, correlation vs causation, and calculation traps.
- Humanities/business/social science: concept boundary, theory comparison, case matching, chronology, framework application, and scenario traps.

## Weight-Based Output Rules

Use the tier to decide how much to generate:

- `S+`: maximum detail, all key terms, mechanism chains, comparison tables, visual/code reconstruction, memory hooks, common traps, and 8-12 targeted MCQs.
- `S`: detailed explanation, key terms, examples, important visuals, traps, and 6-10 MCQs.
- `A`: solid explanation, key examples, main traps, and 4-6 MCQs.
- `B+`: focused explanation, representative examples, and 3-5 MCQs.
- `B`: standard explanation and 2-4 MCQs.
- `C`: compact explanation, essential terms, and 0-2 MCQs.
- `D`: skim note only, usually no MCQs.
- `X`: skip or defer unless needed for context.

For Python/programming courses, `S+`, `S`, and `A` topics should include code-output or final-state reasoning when relevant. For science mechanism topics, high tiers should include mechanism chains and diagram reconstruction. For statistics/data topics, high tiers should include assumptions, formulas, units, and graph interpretation.

## Schedule-Based Workload Rules

When planning time, adjust workload using completion state:

- Time sufficient and on track: keep `S+`, `S`, `A` full; keep `B+/B` standard; compress `C/D`.
- Time sufficient but mistakes clustered: expand weak `A/B+` topics and add retests.
- Behind schedule: preserve `S+`, `S`, urgent `A`; compress `B+/B`; skip most `C/D`.
- Urgent/final review: focus on `S+`, `S`, teacher-style questions, mistakes, professional terms, and stem traps.
- Knowledge pass complete: reduce explanation length and shift time into practice, mistake repair, and simulations.

If remaining weighted workload is larger than remaining time, reduce output volume from the bottom tiers upward. Do not cut `S+` unless the user explicitly chooses an emergency skim plan.

## Programming Practice Types

Use these types for Python/data courses:

- Concept distinction: identify the best definition or behavior.
- Code output: choose printed output, returned value, final variable state, or error.
- Easy operator trap: precedence, integer/float behavior, comparison, boolean logic.
- Collection behavior: list indexing/slicing/mutation, dict key/value lookup, array behavior.
- Control flow: branch selected, loop count, break/continue effect.
- Best choice: choose the most suitable data structure, chart type, or operation.
- English wording: recognize stems such as `What is the output`, `Which statement is true`, `Which data structure is most appropriate`, and `What happens after this code runs`.

## Practice Set Layout Template

Use this layout when generating module practice questions or simulation sets:

```markdown
# Practice Questions: 稍难但高频

> 做题方法
>
> 先自己选答案，再看答案解析。遇到代码输出题，请不要凭感觉，逐行写出变量变化。

### 1. What is the value of `int(6.9)`?

A. 6

B. 7

C. 6.9

D. Error

### 2. What is the result of `2 + 3 * 4 ** 2`?

A. 50

B. 80

C. 400

D. 64
```

Formatting rules:
- Keep one question per block with clear spacing.
- Use English stems by default for English MCQ exams.
- Keep A-D options on separate lines.
- Leave answers out of the question section.
- For PDF/HTML rendering, use light blue or light gray question headers and a pale yellow method box when practical.
- For Markdown-only output, headings and spacing are enough; do not overcomplicate the source.

## Answer Key Layout Template

Put this section after all questions, preferably after a page break when exporting to PDF:

```markdown
# Answer Key and Explanations

| Q | Ans | Why |
|---|---|---|
| 1 | A | `int()` truncates the decimal part. |
| 2 | A | `**` first, then `*`, then `+`: `4**2=16`, `3*16=48`, `2+48=50`. |
| 3 | B | `==` tests equality; `=` assigns a value. |
```

Answer-key rules:
- Use exactly `Q`, `Ans`, and `Why` as the core columns.
- Keep explanations concise and directly tied to the tested rule.
- Use English explanations for short programming rules when clear; add Chinese clarification for difficult concepts, professional terms, or recurring traps.
- Preserve original question numbers so user answers, screenshots, mistake logs, and retests map cleanly.
- Do not duplicate the full question in the answer table unless the user asks for a standalone answer sheet.

## Mistake Log Template

```markdown
# Mistake Log

## Categories
- Concept/definition
- Mechanism/sequence
- Comparison/confusion pair
- Visual/graph/table/pathway/code screenshot
- Code output/programming behavior
- English stem wording
- Professional terminology
- Ordinary vocabulary
- Careless/strategy

| Date | Module | Category | Question | Your answer | Correct answer | Tested point | Why wrong | Repair action | Memory hook | Similar trap |
|---|---|---|---|---|---|---|---|---|---|---|
```

Add a same-type variant question after important mistakes when the user needs immediate retesting.

## Vocabulary Log Template

```markdown
# Vocabulary Log

## Professional Terms
Use this section for course concepts and exam-tested terminology. Explain in detail.

| Term | 中文 | Subject/category | Detailed explanation | Related concepts | Exam wording | Common trap | Memory hook |
|---|---|---|---|---|---|---|---|

## Ordinary Words
Use this section for general English words. Keep explanations short.

| Word | 常用含义 | Meaning in this question | Quick recognition cue |
|---|---|---|---|

## Exam-Stem Phrases
Use this section for recurring test wording and instructions.

| Phrase | 中文反应 | What to do in MCQs | Trap |
|---|---|---|---|
```

## Teacher Style Template

```markdown
# Teacher Style

## Repeated Topics
- 

## Question Stem Patterns
- Definition:
- Function:
- Location:
- Mechanism:
- Sequence:
- Comparison:
- NOT/except:
- Code/output:
- Data structure/chart choice:

## Distractor Patterns
- 

## Simulation Rules
- Question count:
- Difficulty:
- Modules to emphasize:
```
