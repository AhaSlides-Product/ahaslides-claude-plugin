---
name: build-presentation
description: Build an interactive AhaSlides presentation from a topic, outline or notes. Use when the user asks to create, draft or generate a presentation, deck, workshop, icebreaker or training session in AhaSlides.
---

# Build an AhaSlides presentation

Use the AhaSlides MCP tools to create the deck in the user's account. If the tools are not available or sign-in is needed, ask the user to complete the AhaSlides sign-in prompt, then continue.

## Steps

1. Confirm the essentials in one short message if they are missing: topic, audience, length (default 10 slides) and language. Do not ask more than that.
2. If the request matches a known format (workshop, icebreaker, retrospective, town hall, classroom lesson, deck from a document, deck from a survey or course), call `load_workflow_skill` with a matching intent and follow the workflow it returns. Call `get_skill_for_intent` to read a built-in recipe by intent, or `list_skills` to browse them.
3. Create an empty presentation with `create_presentation`, using a clear title. If the user wants it in a folder, find the folder with `list_folders` and later move it with `move_presentations_to_folder`.
4. Before building two or more slides, call `load_authoring_guide` once and follow its layout and density rules. Use `list_slide_types` and `load_slide_type_specs` to see the available slide types and their fields; `load_slide_skills` gives deeper reference for one slide type.
5. For imagery, use `search_images`, then `upload_image`; never hot-link a foreign URL (see the `add-images` skill).
6. Add the slides with `create_slides`. Open with a title or welcome slide. Mix static content with interactive slides (polls, quizzes, word clouds, scales, Q&A): roughly 40% interactive unless the user wants static only. Put speaker notes in each slide's `notes` field.
7. If a theme is requested, use `get_themes` then `update_presentation_theme`.
8. Reply with the presentation's link as returned by the tools, a one-line summary of each slide, and an offer to adjust. Never build a link by hand.

## Rules

- Keep slide text short: one idea per slide.
- Never invent facts or statistics; mark anything uncertain for the user to check.
- Do not delete or overwrite existing presentations unless the user asks. To change slides in an existing deck, use the `edit-slides` skill.
