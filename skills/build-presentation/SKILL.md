---
name: build-presentation
description: Build an interactive AhaSlides presentation from a topic, outline or notes. Use when the user asks to create, draft or generate a presentation, deck or training session in AhaSlides.
---

# Build an AhaSlides presentation

Use the AhaSlides MCP tools to create the deck in the user's account. If the tools are not available or sign-in is needed, ask the user to complete the AhaSlides sign-in prompt, then continue.

## Steps

1. Confirm the essentials in one short message if they are missing: topic, audience, length (default 10 slides) and language. Do not ask more than that.
2. Create an empty presentation with `create_presentation`, using a clear title.
3. Before building two or more slides, call `load_authoring_guide` once and follow its layout and density rules. Use `list_slide_types` and `load_slide_type_specs` to see the available slide types and their fields.
4. Add the slides with `create_slides`. Open with a title or welcome slide. Mix static content with interactive slides (polls, quizzes, word clouds, scales, Q&A): roughly 40% interactive unless the user wants static only. Put speaker notes in each slide's `notes` field.
5. If a theme is requested, use `get_themes` then `update_presentation_theme`.
6. Reply with the presentation's link as returned by the tools, a one-line summary of each slide, and an offer to adjust. Never build a link by hand.

## Rules

- Keep slide text short: one idea per slide.
- Never invent facts or statistics; mark anything uncertain for the user to check.
- Do not delete or overwrite existing presentations unless the user asks.
