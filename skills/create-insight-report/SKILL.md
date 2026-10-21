---
name: create-insight-report
description: Build a shareable AhaSlides insight report from audience response data across presentations. Use when the user wants a report, dashboard or summary page of results that they can send to others.
---

# Create an insight report

An insight is a report page built from queries on the user's own response data.

## Steps

1. Ask what the report is for and which presentations or period it covers, if not stated.
2. Call `insight_schema` to see the tables you can query and how much data the user owns.
3. Pin the queries with `insight_query`. It validates and scopes the SQL to the user's data and returns ids, not rows, so keep each query to one question.
4. Write the report with `insight_write` (title, blocks, theme) using those ids. To edit an existing insight, pass its id as `report`.
5. Read the data the user needs to see in your reply, and offer to publish.

## Confirm before publishing

`insight_publish` creates a share link that anyone with the link can open, and the report can include participant names and answers. Describe what the report contains and wait for the user to say yes before calling it. Share the URL exactly as returned.

## Rules

- Do not use `query_user_data` or `query_presentation_data`; they are deprecated.
- Treat participant names and free-text answers as personal data; include them only when the user asks.
- For a quick answer in chat, use `review-results` instead.
