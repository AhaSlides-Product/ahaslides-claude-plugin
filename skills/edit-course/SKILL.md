---
name: edit-course
description: Change an existing AhaSlides eLearning course: edit lessons, pages and blocks, reorder them, publish or unpublish, set access. Use when the user wants to improve or manage a course they already have.
---

# Edit an AhaSlides course

## Steps

1. Find the course with `list_courses` and read it with `get_course_tree` (or one lesson with `get_lesson_tree` and `list_lessons`). Work only from the ids it returns.
2. For an improvement request, call `load_course_authoring_guide` and `load_workflow_skill` with an improve-course intent, and apply their rules.
3. Make the changes:
   1. Course details: `update_course`.
   2. Lessons: `rename_lesson`, `reorder_lessons`, `create_lesson`.
   3. Pages: `update_lesson_page`, `reorder_lesson_pages`, `add_lesson_page`, `add_lesson_pages`.
   4. Blocks: call `list_lesson_block_types` first, then `update_lesson_block`, `move_lesson_block`, `reorder_lesson_blocks`, `add_lesson_block`, `add_lesson_blocks`.
4. Read the course back and summarise what changed.

## Confirm first

Ask the user to confirm, naming exactly what will change, before any of these:

1. `delete_lesson`, `delete_lesson_page`, `delete_lesson_block`: they remove learner-facing content.
2. `set_course_published`: publishing or unpublishing changes what learners can see.
3. `set_course_access`: locking a live course can affect people already taking it. Assigning learners is done in the AhaSlides app, not through these tools.

Sharing a course is covered by the `share-and-collaborate` skill.
