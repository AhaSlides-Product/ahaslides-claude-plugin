---
name: review-results
description: Summarise audience responses from an AhaSlides presentation or survey. Use when the user asks how an audience answered, for quiz scores, poll results, Q&A questions or survey feedback.
---

# Review AhaSlides results

Use the AhaSlides MCP tools to read results. This skill only reads data; it never changes slides. For a shareable report page, use the `create-insight-report` skill.

## Steps

1. Identify the presentation or survey. If the user does not give one, call `list_presentations` (or `list_workspace_items` for surveys and courses) and offer the most recent matches.
2. For a presentation, call `get_presentation_detail` to see the slides, then `query_presentation_data` to read the response rows for that presentation (call `insight_schema` with no argument first if you are unsure the user owns any data). It is the only tool that returns response rows into the conversation; `insight_query` returns ids, never rows. For audience questions, use `list_qna_questions`.
3. For a survey, call `get_survey_results_summary` with the survey's id.
4. For a course, call `get_course_tree` for its structure and report only what the tools return.
5. Summarise in plain language: number of participants, the headline result per question, notable differences or surprises, and one or two suggested follow-ups. Use a small table for per-question numbers.

## Rules

- Report only what the tools return. If there are no responses yet, say so.
- Numbers read here are true at the time of reading. If the user wants something that stays current or can be shared, or wants course data, use `create-insight-report` instead.
- Treat participant names and free-text answers as personal data: quote sparingly and only when asked.
