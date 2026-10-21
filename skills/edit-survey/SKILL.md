---
name: edit-survey
description: Change an existing AhaSlides survey: reword or reorder questions, add or remove sections, update settings. Use when the user wants to improve, fix or restructure a survey they already have.
---

# Edit an AhaSlides survey

## Steps

1. Find the survey: use the id the user gives, or `list_workspace_items` with `kinds` set to survey, or a `text_search`.
2. Call `get_survey` to read the sections and elements with their ids. Work only from those ids.
3. For an improvement request, call `load_workflow_skill` with an improve-survey intent and `load_survey_authoring_guide`, and apply their rules rather than your own.
4. Make the changes:
   1. Title, description or settings: `update_survey`.
   2. One question: `update_survey_element`, or `add_survey_element` for a new one; several at once: `add_survey_elements`.
   3. Order of questions: `reorder_survey_elements`.
   4. Sections: `add_survey_section`, `update_survey_section`.
5. Read the survey back with `get_survey` and summarise what changed.

## Confirm before deleting

`delete_survey_element` and `delete_survey_section` remove questions and may remove collected answers with them. Before calling either, list exactly what will be removed and wait for the user to say yes. Do not delete anything the user did not name.

## Rules

- Editing a published survey can change how earlier responses read; mention this if the survey already has responses (check with `get_survey_results_summary`).
- To publish, use `publish_survey` only after the user confirms.
