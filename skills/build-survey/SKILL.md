---
name: build-survey
description: Create and publish an AhaSlides survey from a purpose, audience and list of topics. Use when the user asks for a survey, questionnaire, feedback form, pulse check or needs assessment.
---

# Build an AhaSlides survey

Use the AhaSlides MCP tools. If the tools are not available or sign-in is needed, ask the user to complete the AhaSlides sign-in prompt, then continue.

## Steps

1. Establish the purpose, audience, rough length and language. Ask only for what is missing.
2. If the request matches a known format (customer satisfaction, employee engagement, event feedback, pulse survey, training evaluation, needs assessment, or a survey from a document, presentation or course), call `load_workflow_skill` with a matching intent and follow the workflow it returns.
3. Call `load_survey_authoring_guide` once and follow its rules for question wording, order and length. Do not copy its content into your reply.
4. Create the survey with `create_survey` and a clear title.
5. Add sections with `add_survey_section` if the survey needs more than one page, then add the questions in batches with `add_survey_elements` (up to 20 per call). Use `add_survey_element` for a single question.
6. Read the result back with `get_survey` and check the order and wording.
7. Publishing makes the survey accept responses and may be visible to the public. Ask the user to confirm before calling `publish_survey`, unless they have already asked you to publish it.
8. Reply with the link returned by the tools and a one-line summary of each section. Never build a link by hand.

## Rules

- Never invent facts about the user's organisation; ask or leave a placeholder.
- To change an existing survey, use the `edit-survey` skill. To read responses, use `review-results`.
