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

## Next Action
```

Use `planned`, `in_progress`, `done`, `needs_retest`, or `blocked` for status. When resuming, read `Current Status` first, then inspect logs and module files only as needed to confirm the next action.

## Module Notes Template

```markdown
# Module X - Title

## 1. Module Logic
Chinese explanation of the module's main story.

## 2. Core Concepts
| English | 中文 | Why it matters | Exam clue |
|---|---|---|---|

## 3. Mechanism / Sequence
`Step 1 -> Step 2 -> Step 3 -> Result`

## 4. Key Comparisons
| A | B | Difference | MCQ trap |
|---|---|---|---|

## 5. Visual Reconstruction
- Figure/diagram:
- What it shows:
- Direction/relationship:
- Likely question:

## 6. Examples / Code Output
- Example:
- What changes:
- Output/result:
- Why:

## 7. MCQ Traps
- 

## 8. Practice Questions
1. English question stem
   A. 
   B. 
   C. 
   D. 

## 9. Answers And Chinese Explanation
1. Answer: 
   Explanation:
```

For non-programming modules, merge the examples/code-output section into core concepts or visual reconstruction. For Python/programming modules, keep it as a required section.

## Programming Practice Types

Use these types for Python/data courses:

- Concept distinction: identify the best definition or behavior.
- Code output: choose printed output, returned value, final variable state, or error.
- Easy operator trap: precedence, integer/float behavior, comparison, boolean logic.
- Collection behavior: list indexing/slicing/mutation, dict key/value lookup, array behavior.
- Control flow: branch selected, loop count, break/continue effect.
- Best choice: choose the most suitable data structure, chart type, or operation.
- English wording: recognize stems such as `What is the output`, `Which statement is true`, `Which data structure is most appropriate`, and `What happens after this code runs`.

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
