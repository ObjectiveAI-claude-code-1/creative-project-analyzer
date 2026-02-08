# Creative Project Analyzer - Task Definitions

This document defines the individual evaluation tasks that comprise the Creative Project Analyzer. Each task represents a distinct dimension of creative assessment, designed to be evaluated independently and contribute to a rich, multidimensional profile of the creative work.

Per the SPEC requirements:
- **4 tasks are always evaluated** (unconditional)
- **4 tasks are conditionally evaluated** based on optional input fields
- Each task is **distinctly different** from the others

---

## Always-Evaluated Tasks

These four tasks run on every creative project, requiring only the creative work itself.

### Task 1: Conceptual Originality Scorer

**Purpose**: Evaluate the novelty and freshness of the core idea behind the creative work.

**What it assesses**:
- Does the work bring something genuinely new to its field or medium?
- Does it approach familiar territory from an unexpected angle or perspective?
- Does it synthesize disparate elements, influences, or concepts into something that feels new?
- Does it reveal hidden connections or make us see something familiar in a new light?

**Evaluation approach**: Binary HIGH/LOW assessments across four sub-dimensions (idea freshness, perspective novelty, combinatorial creativity, revelatory quality), aggregated into a single originality score.

**Input**: The creative work (text description, image, video, or audio)

**Output**: Score from 0 (completely derivative) to 1 (strikingly original)

---

### Task 2: Technical Execution Scorer

**Purpose**: Evaluate the craft, skill, and mastery demonstrated in realizing the work.

**What it assesses**:
- Does the work demonstrate mastery of its chosen medium and techniques?
- Is the execution refined, polished, and intentional in its details?
- Does it attempt technically ambitious or difficult feats?
- Does it demonstrate creative solutions to technical challenges?

**Evaluation approach**: Multi-level assessments (None/Low/Medium/High/Exceptional) across four sub-dimensions (skill demonstration, finish and polish, technical ambition, problem-solving), weighted and aggregated.

**Input**: The creative work (text description, image, video, or audio)

**Output**: Score from 0 (poor execution) to 1 (masterful execution)

---

### Task 3: Emotional Resonance Scorer

**Purpose**: Evaluate the work's capacity to evoke feeling, mood, and emotional response.

**What it assesses**:
- Does the work evoke precise, identifiable feelings rather than vague impressions?
- Are the evoked feelings complex and layered rather than simplistic?
- Does the emotional content feel authentic rather than manipulative or forced?
- Do the feelings linger after experiencing the work, creating lasting impact?

**Evaluation approach**: Binary assessments (WEAK/STRONG) across four emotional dimensions (specificity, depth, authenticity, lasting impression), combined to produce an overall resonance score.

**Input**: The creative work (text description, image, video, or audio)

**Output**: Score from 0 (emotionally flat) to 1 (profoundly moving)

---

### Task 4: Aesthetic Cohesion Scorer

**Purpose**: Evaluate the unity, harmony, and internal consistency of the work's aesthetic choices.

**What it assesses**:
- Do the sensory elements (visual, auditory, tactile) work together harmoniously?
- Does the work maintain a consistent voice, tone, and mood throughout?
- When elements contrast or clash, is this purposeful and meaningful?
- Does the whole exceed the sum of its parts, creating a unified gestalt?

**Evaluation approach**: Multi-level assessments across four cohesion dimensions (sensory harmony, tonal consistency, intentional contrast, gestalt quality), aggregated into an overall cohesion score.

**Input**: The creative work (text description, image, video, or audio)

**Output**: Score from 0 (disjointed/incoherent) to 1 (perfectly unified)

---

## Conditionally-Evaluated Tasks

These four tasks only run when specific optional inputs are provided, enabling deeper contextual analysis.

### Task 5: Intentional Coherence Scorer

**Condition**: Only evaluated when `creator_statement` optional input is provided.

**Purpose**: Evaluate the alignment between what the creator intended and what the work achieves.

**What it assesses**:
- Does the work accomplish its stated objectives and goals?
- Are the creative choices appropriate and effective for achieving the stated goals?
- Does the creator demonstrate accurate self-awareness about their own work?
- Do the stated intentions feel authentic rather than post-hoc rationalization?

**Evaluation approach**: Compare the work against the creator's stated intent using binary assessments (MISALIGNED/ALIGNED) across four coherence dimensions, aggregated into an overall intentional coherence score.

**Input**: 
- The creative work (text description, image, video, or audio)
- The creator's statement describing their intent, goals, and vision

**Output**: Score from 0 (fails to achieve stated intent) to 1 (perfectly realizes stated vision)

**Skip condition**: When `creator_statement` is not provided, this task is skipped and produces no output.

---

### Task 6: Audience Resonance Scorer

**Condition**: Only evaluated when `target_audience` optional input is provided.

**Purpose**: Evaluate how effectively the work connects with its intended audience.

**What it assesses**:
- Is the work accessible and approachable for its target audience?
- Does it address matters, themes, or concerns that audience cares about?
- Is the tone, complexity, and register appropriate for the audience?
- Does it speak the audience's aesthetic and cultural language fluently?

**Evaluation approach**: Evaluate the work in context of the specified target audience using multi-level assessments (Poor/Fair/Good/Excellent) across four audience-fit dimensions, aggregated into an overall audience resonance score.

**Input**:
- The creative work (text description, image, video, or audio)
- Description of the target audience (demographics, expertise level, cultural context, expectations)

**Output**: Score from 0 (completely misses the audience) to 1 (perfectly speaks to the audience)

**Skip condition**: When `target_audience` is not provided, this task is skipped and produces no output.

---

### Task 7: Constraint Navigation Scorer

**Condition**: Only evaluated when `project_constraints` optional input is provided.

**Purpose**: Evaluate how creatively and effectively the work operates within its limitations.

**What it assesses**:
- Does the work achieve remarkable results despite limited resources or restrictions?
- Are limitations transformed into creative opportunities rather than mere obstacles?
- Is the scope and ambition appropriately calibrated to the constraints?
- Where trade-offs were necessary, are they handled elegantly and intelligently?

**Evaluation approach**: Evaluate the work's achievements relative to its documented constraints using binary assessments (STRUGGLED/THRIVED) across four constraint-navigation dimensions, aggregated into an overall score.

**Input**:
- The creative work (text description, image, video, or audio)
- Description of project constraints (budget, timeline, materials, client requirements, technical limitations)

**Output**: Score from 0 (constrained by limitations) to 1 (transcended limitations brilliantly)

**Skip condition**: When `project_constraints` is not provided, this task is skipped and produces no output.

---

### Task 8: Contextual Positioning Scorer

**Condition**: Only evaluated when `references` optional input is provided.

**Purpose**: Evaluate how the work relates to its influences and positions itself within creative traditions.

**What it assesses**:
- Are influences absorbed and transformed rather than merely copied or referenced?
- Does the work demonstrate understanding of and respect for its creative lineage?
- Where it diverges from influences, is this departure generative and meaningful?
- What does the work add to the conversation its references began?

**Evaluation approach**: Evaluate the work's relationship to its stated references and influences using multi-level assessments across four positioning dimensions (influence integration, tradition awareness, productive departure, contribution clarity), aggregated into an overall contextual positioning score.

**Input**:
- The creative work (text description, image, video, or audio)
- List or description of reference works, influences, and inspirations

**Output**: Score from 0 (derivative imitation) to 1 (meaningful evolution of influences)

**Skip condition**: When `references` is not provided, this task is skipped and produces no output.

---

## Task Distinctiveness Summary

Each task evaluates a fundamentally different aspect of creative work:

| Task | Focus | Key Question |
|------|-------|--------------|
| Conceptual Originality | Ideas & novelty | Is it new? |
| Technical Execution | Craft & skill | Is it well-made? |
| Emotional Resonance | Feeling & affect | Does it move us? |
| Aesthetic Cohesion | Unity & harmony | Does it hold together? |
| Intentional Coherence | Intent & achievement | Did it do what it meant to? |
| Audience Resonance | Communication & fit | Does it reach its audience? |
| Constraint Navigation | Resourcefulness & ingenuity | Did it thrive within limits? |
| Contextual Positioning | Tradition & evolution | Where does it stand in history? |

These eight dimensions are orthogonal—a work can score high on technical execution but low on emotional resonance, or high on originality but low on audience fit. This independence ensures the vector output provides genuine multidimensional insight rather than redundant measurements of the same underlying quality.

---

## Output Structure

The Creative Project Analyzer produces a vector of scores. When all optional inputs are provided, the output contains eight scores. When optional inputs are omitted, the corresponding conditional tasks are skipped, and the output vector is shorter.

**Minimum output** (no optional inputs): 4 scores
- conceptual_originality
- technical_execution  
- emotional_resonance
- aesthetic_cohesion

**Maximum output** (all optional inputs provided): 8 scores
- conceptual_originality
- technical_execution
- emotional_resonance
- aesthetic_cohesion
- intentional_coherence
- audience_resonance
- constraint_navigation
- contextual_positioning

This flexible output structure allows users to receive exactly the analysis they need based on the context they can provide.
