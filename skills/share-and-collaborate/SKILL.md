---
name: share-and-collaborate
description: Share AhaSlides presentations, folders, surveys or courses with other people, and change or remove their access. Use when the user asks who has access, wants to invite a colleague, or change a collaborator's role.
---

# Share and manage collaborators

Sharing sends email invitations and changes who can see or edit the user's work. Always look first, then confirm.

## Look first

1. Presentations and folders: `list_collaborators` with the target type and id.
2. Surveys: `list_survey_collaborators`.
3. Courses: `list_course_collaborators`.

Find ids with `list_presentations`, `list_folders` or `list_workspace_items`.

## Change access

1. Presentations and folders: `add_collaborators`; to remove, `remove_collaborators`.
2. Surveys: `add_survey_collaborators`, `update_survey_collaborator_role`, `remove_survey_collaborator`. Only the survey owner can do these.
3. Courses: `add_course_collaborators`, `update_course_collaborator_role`, `remove_course_collaborator`.

## Confirm first

Before any add, role change or removal, show the user the exact email addresses or people, the item, and the role, and wait for a clear yes. Adding people emails them an invitation. Removing people takes their access away immediately. Never infer email addresses; use only what the user gave you.

## Rules

- Do not share beyond what the user asked.
- Report the outcome per person, including any the tools reject.
