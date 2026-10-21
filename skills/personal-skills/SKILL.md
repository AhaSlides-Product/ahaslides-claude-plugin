---
name: personal-skills
description: List, read, save, edit and delete the user's own saved AhaSlides skills (reusable instructions) and browse the built-in recipes. Use when the user wants to save a way of working, reuse a house style, or see what recipes exist.
---

# Personal AhaSlides skills

A personal skill is a short, saved instruction that AhaSlides applies to presentations, surveys or courses.

## Steps

1. Browse with `list_skills`, which returns titles and descriptions of the user's skills and the built-in recipes. Read one with `get_skill`.
2. To save one, draft it with the user, then call `create_skill`. Keep to the limits: title up to 80 characters, description up to 200, body up to 4000. `applies_to` can be presentation, survey or course.
3. To change one, call `update_skill` with only the fields that change. Built-in recipes cannot be changed; offer to save an edited copy instead.

## Confirm before changing or deleting

Show the user the exact text you will save or change and wait for approval. `delete_skill` removes a skill (it can be recovered from the trash): name the skill and wait for a yes first. Only touch skills the user named.

## Rules

- Do not put secrets, passwords or personal data in a saved skill.
