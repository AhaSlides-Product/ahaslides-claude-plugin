---
name: convert-content
description: Turn existing AhaSlides content into a different form: a presentation into a course lesson or survey, a survey or course into a presentation, or a document into any of them. Use when the user says "make a course from this deck", "survey from my slides" or similar.
---

# Convert content between formats

The server holds step-by-step workflows for each conversion. Use them rather than improvising.

## Steps

1. Identify the source (a presentation, survey, course, or a document the user supplied) and the target. Find the source with `list_presentations`, `list_workspace_items`, `get_survey` or `get_course_tree`, and read it before converting.
2. Call `load_workflow_skill` with the matching intent, for example a presentation to a course, a presentation to a survey, a survey or course to a presentation, or a document to a presentation, survey or course. Follow the workflow it returns. `get_skill_for_intent` reads a built-in recipe by intent.
3. Build the target with the matching skill: `build-presentation`, `build-survey` or `build-course`, loading the authoring guide that skill names.
4. Reply with the link to the new item and a short summary of what carried over. State plainly anything you left out.

## Rules

- The source is never changed or deleted by a conversion.
- Never invent facts, numbers, names or links that are not in the source.
