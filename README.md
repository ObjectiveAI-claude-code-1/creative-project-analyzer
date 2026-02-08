# Creative Project Analyzer

A vector function that evaluates creative projects across 8 distinct dimensions of artistic merit, producing a probability distribution across quality tiers from "Developing" to "Masterwork."

## Overview

This analyzer provides comprehensive, multidimensional evaluation of creative works including visual art, music, performance, design, writing, and mixed media projects. It accepts work in multiple formats (text descriptions, images, video, or audio) along with optional contextual information that enables deeper analysis.

## Quality Tiers

The function outputs a probability distribution across five quality tiers:

| Tier | Description |
|------|-------------|
| **Developing** | Work that shows potential but has significant areas for growth |
| **Competent** | Solid work meeting baseline professional standards |
| **Accomplished** | Strong work demonstrating real skill and vision |
| **Exceptional** | Outstanding work pushing boundaries in its field |
| **Masterwork** | Transcendent work that advances the art form itself |

## Evaluation Dimensions

### Always Evaluated (4 dimensions)

1. **Conceptual Originality** - Novelty and freshness of the core idea
2. **Technical Execution** - Craft, skill, and mastery in realization
3. **Emotional Resonance** - Capacity to evoke feeling and mood
4. **Aesthetic Cohesion** - Unity and internal consistency of choices

### Conditionally Evaluated (4 dimensions)

5. **Intentional Coherence** - Alignment between intent and achievement (requires `creator_statement`)
6. **Audience Resonance** - Connection with intended audience (requires `target_audience`)
7. **Constraint Navigation** - Creativity within limitations (requires `project_constraints`)
8. **Contextual Positioning** - Relationship to influences and traditions (requires `references`)

## Input Schema

### Required Field

- **work** - The creative project to evaluate. Can be:
  - Text description of the work
  - Image (photograph, render, screenshot)
  - Video (for time-based or performative works)
  - Audio (for musical or sound-based projects)

### Optional Fields

- **creator_statement** - The creator's description of their intent, goals, and vision
- **target_audience** - Description of the intended audience (demographics, expertise, expectations)
- **project_constraints** - Limitations the work was created under (budget, timeline, materials, requirements)
- **references** - Reference works, influences, and inspirations that informed the project

## Example Usage

### Basic Evaluation (4 dimensions)

```json
{
  "work": "A kinetic sculpture made from recycled ocean plastic, featuring thousands of translucent fragments that respond to air currents."
}
```

### Full Evaluation (8 dimensions)

```json
{
  "work": "An interactive mobile app generating personalized ambient soundscapes based on biometric and environmental data.",
  "creator_statement": "I wanted to make invisible data audible and beautiful, helping people feel connected to their environment.",
  "target_audience": "Mindfulness practitioners and ambient music enthusiasts ages 25-45.",
  "project_constraints": "Solo developer, 6-month timeline, $5000 budget, rule-based algorithms only.",
  "references": "Brian Eno's generative music, Ryoji Ikeda's data-driven installations."
}
```

## Output

The function returns a 5-element probability vector representing the likelihood that the work belongs to each quality tier. The probabilities sum to approximately 1.

Example output: `[0.15, 0.22, 0.35, 0.20, 0.08]`

This indicates the work is most likely "Accomplished" (35%), with meaningful probability of being "Competent" (22%) or "Exceptional" (20%).
