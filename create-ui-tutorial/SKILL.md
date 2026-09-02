---
name: create-ui-tutorial
description: Create step-by-step Markdown lessons for software and UI workflows using screenshots captured from the actual interface. Use for visual instructions, UI walkthroughs, onboarding guides, and app tutorials; do not use for explanations that do not depend on the current interface.
---

# Create UI Tutorial

Produce a self-contained Markdown lesson whose screenshots match the interface the learner will actually use.

## Before Capture

- Confirm the target application, the task to teach, and the learner's starting point from the request. Ask only when a missing detail would change the visible workflow.
- Load and follow the `computer-use` skill before interacting with a Windows application. If Computer Use is unavailable, stop and explain that an evidence-based visual guide cannot be completed.
- Use a safe demo file, account, or project when the workflow would expose personal or production data.
- Plan the fewest screenshots that still show every meaningful state change. Do not capture every click.
- Identify any step that deletes, overwrites, publishes, purchases, commits, or otherwise cannot be reliably undone. Do not perform such a step merely to obtain a screenshot.

## Capture the Workflow

1. Select the exact target window through Computer Use and verify the application, document, and visible state before acting.
2. Before an irreversible step, place a written warning immediately before the action. State exactly what will change, what data or scope is affected, whether recovery is possible, and any backup or prerequisite needed. Then obey Computer Use confirmation and safety requirements.
3. Capture a fresh screenshot after the interface settles at each meaningful teaching point.
4. Keep enough surrounding UI to establish context while making the relevant control readable. Crop empty or unrelated areas when useful.
5. Add minimal arrows, boxes, or numbered callouts only when the target is otherwise ambiguous. Do not alter labels, values, results, or application state.
6. Never substitute generated or reconstructed UI for evidence from the actual interface. If a required state cannot be reached, identify the missing image instead of inventing it.

Before saving an image, check for passwords, tokens, private messages, notifications, personal identifiers, and unrelated account data. Move to neutral demo data, crop, or redact as appropriate; never place secrets in the lesson.

## Save the Material

Create one lesson directory containing the Markdown file and an adjacent `images/` directory. Use short, ordered filenames such as:

```text
lesson/
|-- guide.md
`-- images/
    |-- 01-open-settings.png
    |-- 02-enable-option.png
    `-- 03-confirm-result.png
```

Reference images with relative paths and useful alt text:

```markdown
![The Settings window with the target option highlighted](images/02-enable-option.png)
```

## Write the Lesson

Use the user's language unless they request another language. Prefer this compact structure:

```markdown
# <Task outcome>

## What you will do
<One short outcome statement.>

## Before you start
<Only real prerequisites or safety notes.>

## Steps

### 1. <Action>
<Where to look and what to do. Use the exact visible UI label.>

![<What the screenshot shows>](images/01-<name>.png)

**Expected result:** <Visible confirmation that the step worked.>

> **Warning: irreversible action:** <What will change, affected scope, recovery options, and required backup.>

## Finished
<How to verify the final state.>

## If it looks different
<Only likely version, platform, or layout differences observed during capture.>
```

Write actions before their screenshots, use exact labels visible in the capture, and keep one learner action per numbered step. Explain the purpose of a control only when it helps the learner choose correctly. Do not claim a menu, shortcut, or result that was not verified in the captured workflow.

## Verify

- Open the finished Markdown and confirm every relative image path renders.
- Compare each instruction with its screenshot and the final application state.
- Check that the sequence can be followed without relying on omitted clicks or hidden prior knowledge.
- Recheck every image for sensitive or unrelated information.
- Confirm every irreversible action has a warning before the instruction, not after it.
- Report any uncaptured step, version-specific difference, or blocked state plainly.
