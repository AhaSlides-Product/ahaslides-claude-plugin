---
name: review-results
description: Summarise audience responses from an AhaSlides presentation or survey. Use when the user asks how an audience answered, for quiz scores, poll results, Q&A questions or survey feedback.
---

# Review AhaSlides results

Use the AhaSlides MCP tools to read results. This skill only reads data; it never changes slides.

## Steps

1. Identify the presentation or survey. If the user does not give one, call `list_presentations` and offer the most recent matches.
2. For a presentation, call `get_presentation_detail`, then `query_presentation_data` for the responses. For audience questions, use `list_qna_questions`.
3. For a survey, call `get_survey_results_summary` with the survey's id.
4. Summarise in plain language: number of participants, the headline result per question, notable differences or surprises, and one or two suggested follow-ups. Use a small table for per-question numbers.

## Rules

- Report only what the tools return. If there are no responses yet, say so.
- Treat participant names and free-text answers as personal data: quote sparingly and only when asked.
