---
name: make-quiz
description: Create a scored quiz in AhaSlides from a subject, level and number of questions. Use when the user asks for a quiz, trivia, knowledge check, quiz game or test for a live audience or class.
---

# Make an AhaSlides quiz

Use the AhaSlides MCP tools to build a quiz presentation in the user's account.

## Steps

1. Establish the subject, audience level, number of questions (default 10) and language. Ask only for what is missing.
2. Call `load_workflow_skill` with a quiz-game intent and follow the workflow it returns for quiz structure, scoring and leaderboards. If it returns nothing, carry on with the steps below.
3. Write the questions yourself first: each with one correct answer and plausible wrong answers, in varied order. Check each answer is accurate before building.
4. Create the presentation with `create_presentation` and a title that names the quiz.
5. Call `load_authoring_guide` once, then `list_slide_types` and `load_slide_type_specs` to find the quiz slide type and its fields.
6. Add a short welcome slide and then the quiz slides with `create_slides`. Optionally add a results or leaderboard slide at the end if a suitable slide type exists.
7. If the user wants different timing or points, set them with `update_slide_properties` (for example `timeToAnswer`, `minPoint`, `maxPoint`, `fastAnswerGetMorePoint`).
8. Reply with the link returned by the tools and how participants join, as the tools describe it. Never build a link by hand.

## Rules

- One question per slide, with short answer options.
- Do not add slide types you did not find via `list_slide_types`.
