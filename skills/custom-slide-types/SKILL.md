---
name: custom-slide-types
description: Design, build and check the user's own custom AhaSlides slide types. Use when the user wants a slide type that does not exist, such as a custom interactive activity.
---

# Build a custom slide type

A custom slide type is a small web page with files, checks and a test presentation. The slide-type tools describe their own arguments, so read each tool's description before using it.

## Steps

1. Before building, read the build guide with `get_skill_for_intent("build_slide_type")`. It lists the intents of its sub-guides; fetch each one with `get_skill_for_intent` before the step that needs it.
2. Check what exists: `slide_type_list` (the user's own types), and `list_slide_types` for the built-in catalogue, in case a built-in already fits.
3. Create the type with `slide_type_create`, then work on its files with `slide_type_list_files`, `slide_type_read_file`, `slide_type_create_file`, `slide_type_edit_file`, `slide_type_move_file` and `slide_type_upload_file`. Change its details with `slide_type_update`.
4. Run `slide_type_check` after changes and fix what it reports.
5. Run the browser jobs in this order: `slide_type_start_preview_test`, `slide_type_start_live_verify`, then `slide_type_start_preview_build`. Poll each with `slide_type_job_status`. After `OUTCOME_UNKNOWN` on a job start, calling it again is safe: a job that is already running answers `BUSY` with its `job_id`.
6. Judge each surface yourself: `slide_type_judge_brief` returns its screenshots, criteria, the files to read with `slide_type_read_file` and a `judge_token`. Apply every criterion, then send your verdict, each failure and the token with `slide_type_record_judge`.
7. Try it with `slide_type_test_presentation` and finish with `slide_type_handoff_report`.

## When a call answers with a status

- `NO_SCREENSHOTS`: that surface's job has not run yet. Run it, wait for it to finish, then get the brief.
- `STALE_SCREENSHOTS`: files changed after the screenshots. Run that surface's job again first.
- `STALE`: the page changed after the brief. Get a new brief.
- `ALREADY_RECORDED`: that brief already has a verdict. Change the surface's files or run its job again, then get a new brief.
- `LIMIT`: the call went over a daily limit (jobs, new slide types, judge briefs or judges) or a size limit, named in the answer. Tell the user about a daily limit.

## Confirm first

- `slide_type_delete_file` removes a file from the user's slide type. Name the file and wait for a yes before calling it.
- `slide_type_share_link` turns sharing on for the slide type. Ask the user before calling it.

## Rules

- Nothing here publishes a slide type: it stays a draft in the user's account until AhaSlides publishes it, so do not claim the type is live.
- Your verdicts are self-reported: record PASS only when no criterion fails, and record every real failure.
- Do not copy the tools' guidance into the reply.
