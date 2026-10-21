---
name: edit-slides
description: Edit slides in an existing AhaSlides presentation: change text, quiz settings and timing, reorder or skip slides, apply a theme, or modernise old content slides. Use when the user wants to change a deck they already have.
---

# Edit slides in an existing presentation

## Steps

1. Find the presentation (`list_presentations`) and read it with `get_presentation_detail` to get slide ids and types. Work only from those ids.
2. Before rewriting or restructuring slides, call `load_authoring_guide` and `load_slide_type_specs` for the types involved. For a request to improve a whole deck, also call `load_workflow_skill` with an improve-presentation intent.
3. Make the change with the narrowest tool:
   1. Text and content: `update_slide_content` (each slide needs its `id`, `slide_type` and the required fields for that type).
   2. Properties such as quiz points, time limits and chart type: `update_slide_properties`. Do not send the slide type; it cannot be changed this way.
   3. Order: `move_slide`, one slide per call.
   4. Hide a slide from the live show without deleting it: `skip_slide_when_presenting`.
   5. Add new slides: `create_slides`.
   6. Look: `get_themes` then `update_presentation_theme`.
   7. Old content slides: `convert_slides_to_content_v2` converts them into the newer content format as new slides.
4. Read the presentation back and summarise what changed. Act on any "Design check" lines the tools return.

## Confirm before deleting

Setting `deleted` to true through `update_slide_properties` removes a slide. Say which slides, by number and title, and wait for the user to say yes. Do not delete a slide the user did not name. Do not overwrite slide content the user did not ask you to change.

## Rules

- Keep slide text short: one idea per slide.
- Never invent facts or statistics.
