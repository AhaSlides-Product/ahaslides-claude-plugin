---
name: custom-slide-types
description: Design, build and check the user's own custom AhaSlides slide types. Use when the user wants a slide type that does not exist, such as a custom interactive activity.
---

# Build a custom slide type

A custom slide type is a small web page with files, checks and a test presentation. The slide-type tools describe their own arguments, so read each tool's description before using it.

## Steps

1. Check what exists: `slide_type_list` (the user's own types), and `list_slide_types` for the built-in catalogue, in case a built-in already fits.
2. Create the type with `slide_type_create`, then work on its files with `slide_type_list_files`, `slide_type_read_file`, `slide_type_create_file`, `slide_type_edit_file`, `slide_type_move_file` and `slide_type_upload_file`. Change its details with `slide_type_update`.
3. Run `slide_type_check` after changes and fix what it reports.
4. Verify in a browser with the long-running jobs `slide_type_start_preview_build`, `slide_type_start_preview_test`, `slide_type_start_live_verify` and `slide_type_start_judge`, and poll each with `slide_type_job_status`. Do not start a job again while one is running.
5. Try it with `slide_type_test_presentation`, share it with `slide_type_share_link`, and finish with `slide_type_handoff_report`.

## Confirm first

`slide_type_delete_file` removes a file from the user's slide type. Name the file and wait for a yes before calling it.

## Rules

- Users do not publish slide types from here; publishing is done by Slide Lab, so do not claim the type is live.
- Do not copy the tools' guidance into the reply.
