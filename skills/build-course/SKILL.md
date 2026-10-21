---
name: build-course
description: Create an AhaSlides eLearning course with lessons, pages and content blocks from a topic, document or existing presentation. Use when the user asks for a course, lesson, training module or self-paced learning.
---

# Build an AhaSlides course

Use the AhaSlides MCP tools. If the tools are not available or sign-in is needed, ask the user to complete the AhaSlides sign-in prompt, then continue.

## Steps

1. Establish the topic, learners, number of lessons and language. Ask only for what is missing.
2. Call `load_course_authoring_guide` once and follow it. For a recognised format (compliance training, onboarding, microlearning, Bloom's taxonomy course, a course from a document, survey or presentation) also call `load_workflow_skill` with a matching intent. Do not copy their content into your reply.
3. Check what already exists with `list_courses` so you do not duplicate a course.
4. Create the course with `create_course`, then each lesson with `create_lesson`.
5. Call `list_lesson_block_types` before authoring blocks; it is the only source of each block type's content shape.
6. Add pages with `add_lesson_pages` (or `add_lesson_page`) and content with `add_lesson_blocks` (or `add_lesson_block`).
7. For images, use `search_images` as is, or `upload_image` with `destination` set to `elearning` (see `add-images`).
8. Read the result back with `get_course_tree` or `get_lesson_tree`. Share the `editor_url` returned by the tools as it is; never build a link by hand.
9. Keep the course unpublished. Publishing is a separate step the user asks for (see `edit-course`).

## Rules

- Never invent facts, statistics, names or links.
- To turn an existing presentation into a course, use the `convert-content` skill.
