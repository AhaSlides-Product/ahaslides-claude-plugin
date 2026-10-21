---
name: moderate-live-qna
description: Read and moderate audience questions in an AhaSlides Q&A during a live session. Use when the presenter asks to see new questions, approve or dismiss them, or turn Q&A moderation on or off.
---

# Moderate live Q&A

## Read questions

1. Find the presentation with `list_presentations` if the user did not give an id.
2. `list_qna_questions` shows the questions as they arrive. Pass the last id you saw as `after_id` to read only new ones.
3. `get_presentation_settings` shows whether moderation is on. `wait_for_qna_questions` waits for new questions to moderate and only works with moderation on.

## Moderate

1. Ask the presenter for their rules first (for example: dismiss off-topic or abusive questions, approve the rest). If they have none, propose a short set and wait for agreement.
2. Show the questions you propose to approve and to dismiss, with the reason for each dismissal.
3. Apply approved decisions with `moderate_qna_questions` (approve, dismiss or reset). An approved question shows to the audience at once, and a dismissed one is hidden, so do this only after the presenter has agreed. Never moderate on your own initiative. Leave a question pending when unsure.
4. Report what was approved, dismissed or failed.

## Moderation setting

Turning moderation on with `update_presentation_settings` hides every question with no decision yet from the audience immediately, and turning it off reveals them again. If a session may be live, confirm with the presenter before changing it.

## Rules

- Treat questions and names as personal data. Quote only what the presenter needs.
