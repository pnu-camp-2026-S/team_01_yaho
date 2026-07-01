---
name: skill-idea-interviewer
description: Use this skill when the user has a vague idea for a new Codex skill and wants to turn it into a concise, reusable SKILL.md draft. Trigger when the user asks to create, design, define, or shape a new skill from an abstract idea, repeated workflow, or rough capability description. Do not use for improving an existing skill version.
---

# Skill Idea Interviewer

## Purpose

Turn a user's abstract idea for a new Codex skill into a concise `SKILL.md` draft.

Keep the interview short. Ask only the minimum questions needed to produce a usable skill draft. Prefer explicit assumptions over a long interview.

## Interview Rules

- Use this skill only for creating a new skill from an idea.
- If the user wants to improve an existing skill, say this skill only covers new skill creation and ask for the existing-skill improvement workflow instead.
- Ask at most 1-2 clarifying questions per step.
- If the user does not know an answer, make a reasonable assumption and label it clearly.
- Convert answers directly into skill structure.
- Do not expand into app planning, product strategy, or broad service design unless the requested skill itself requires it.
- End with a concrete `SKILL.md` draft, not just recommendations.

## Workflow

### 1. Create A One-Sentence Skill Purpose

Rewrite the user's idea as one sentence that explains what the skill helps Codex do.

Use this shape by default:

```text
This skill helps Codex ...
```

If the idea is vague, ask one or two short questions about the repeated task or intended capability. After that, proceed with an explicit assumption.

Output:

```markdown
Purpose:
...
```

### 2. Define Trigger Conditions

Decide when the skill should be used.

Identify:

- User requests that should trigger the skill
- User requests that should not trigger the skill
- Key phrases, contexts, or artifacts that indicate relevance

Output:

```markdown
Use when:
- ...

Do not use when:
- ...
```

### 3. Define Inputs And Outputs

Clarify what the user provides and what the skill should produce.

Common inputs:

- A rough idea
- Existing notes
- Source files
- A workflow description
- Examples of desired behavior

Common outputs:

- A `SKILL.md` draft
- A short workflow
- Output format requirements
- Assumptions
- Test prompts
- Recommendations for references, scripts, or assets when clearly useful

Output:

```markdown
Inputs:
- ...

Outputs:
- ...
```

### 4. Compress The Skill Workflow To 3-5 Steps

Turn the skill's behavior into a short reusable workflow.

Rules:

- Use 3-5 steps by default.
- Each step must describe an action Codex performs.
- Merge similar steps.
- Keep the workflow general enough to reuse.
- Move detailed variant-specific knowledge into references only when needed.
- Avoid adding scripts or assets unless they clearly improve repeatability or reliability.

Output:

```markdown
Workflow:
1. ...
2. ...
3. ...
```

### 5. Convert To A SKILL.md Draft

Create a concise skill draft using proper frontmatter and instructions.

Include:

- `name`
- `description`
- Purpose
- Workflow
- Output format
- Assumptions, if any
- 2-3 test prompts

Use lowercase hyphen-case for the skill name.

Output:

```markdown
---
name: ...
description: ...
---

# ...

## Purpose

...

## Workflow

1. ...
2. ...
3. ...

## Output

...

## Assumptions

- ...

## Test Prompts

1. ...
2. ...
```

## Final Response Format

Return the result in this structure:

```markdown
## Skill Draft

...

## Assumptions

...

## Test Prompts

...
```

## Quality Bar

A good result should:

- Be short enough for Codex to reuse without context bloat
- Have a clear trigger description in frontmatter
- Have an actionable 3-5 step workflow
- Avoid unnecessary broad planning
- State assumptions explicitly
- Produce a concrete `SKILL.md` draft
- Include test prompts that reveal whether the skill behaves as intended
