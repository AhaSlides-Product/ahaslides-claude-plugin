---
name: organise-presentations
description: Find, rename, duplicate, move, delete and recover AhaSlides presentations, and manage folders. Use when the user wants to tidy their workspace, find a file, or restore something deleted.
---

# Organise AhaSlides files

## Find things

1. `list_presentations` for presentations; `list_workspace_items` to browse one folder at a time across presentations, surveys and courses (with `kinds`, `text_search`, and `cursor` for the next page).
2. `list_folders` for the folder tree, or to search folders by name.
3. `get_presentation_detail` to look inside one presentation; `get_presentation_settings` for its settings.

## Change things

1. `rename_presentation`, `duplicate_presentation`, `create_folder`, `rename_folder`.
2. `move_presentations_to_folder` to move one or more presentations. Check the folder id with `list_folders` first.
3. `update_presentation_settings` changes only Q&A moderation today. Turning moderation on hides every undecided audience question at once, so confirm first if a session may be running (see `moderate-live-qna`).

## Confirm before destroying

`delete_presentations` and `delete_folder` move items to the trash. Before calling either, list the exact titles and ids that will be affected, and wait for the user to say yes. Never delete in bulk from a vague request such as "clean up". Deleting a folder also trashes the presentations in it.

`recover_presentations` restores items from the trash; offer it if the user says something was deleted by mistake.

## Rules

- Act only on items the user named or approved from a list you showed them.
- Report results using the links and titles returned by the tools.
