# AhaSlides for Claude

![AhaSlides](logo.png)

Connect Claude to [AhaSlides](https://ahaslides.com), the interactive presentation platform, so you can build and run audience-engagement sessions by describing what you want. Ask Claude to create a presentation from a topic, turn notes into a quiz, add polls and word clouds, or summarise how your audience responded.

## What it includes

1. **AhaSlides connector.** A remote MCP server at `https://mcp.ahaslides.com/mcp` that lets Claude create, edit, organise and read your presentations, surveys, eLearning courses and audience responses.
2. **17 skills**, grouped by what you want to do. Each one points Claude at the right tools and at AhaSlides' own authoring guides, so the advice stays current.

### Skills

Create:

1. `build-presentation`: turns a topic or outline into an interactive deck.
2. `make-quiz`: builds a scored quiz presentation.
3. `build-survey`: creates and publishes a survey.
4. `build-course`: creates an eLearning course with lessons, pages and blocks.
5. `convert-content`: turns a presentation, survey, course or document into another form.
6. `powerpoint-addin`: embeds live AhaSlides slides into a PowerPoint file.
7. `custom-slide-types`: builds your own custom slide types.

Edit:

8. `edit-slides`: changes text, quiz settings, order, themes and visibility of existing slides.
9. `edit-survey`: rewords, reorders and restructures a survey.
10. `edit-course`: edits lessons, pages and blocks, and publishes or sets access.
11. `add-images`: finds stock photos and uploads images.

Manage and share:

12. `organise-presentations`: finds, renames, duplicates, moves, deletes and recovers presentations, and manages folders.
13. `share-and-collaborate`: shares presentations, folders, surveys and courses.
14. `personal-skills`: saves and manages your own reusable instructions, and browses the built-in recipes.

Run and review:

15. `moderate-live-qna`: reads and moderates audience questions live.
16. `review-results`: summarises responses to presentations, surveys and courses.
17. `create-insight-report`: builds a shareable report from response data.

Anything that deletes, shares, publishes or moderates asks you to confirm first.

## Install

Add AhaSlides from the Claude plugin directory (claude.ai, Cowork or Claude Code) and choose Install.

To try it from source in Claude Code, clone this repository and start Claude Code with:

```
claude --plugin-dir ./ahaslides-claude-plugin
```

## Sign in

The first time Claude uses an AhaSlides tool, you are asked to sign in to AhaSlides in your browser (email, Google or Microsoft). Sign-in uses OAuth. The plugin stores no passwords, API keys or tokens, and needs no configuration. You need an AhaSlides account; a free account works.

## Example prompts

- "Create a 10-slide AhaSlides presentation on the basics of project management for new starters."
- "Make a 12-question quiz on world geography for a team social."
- "How did my audience answer in my last presentation?"
- "Create a 5-question customer feedback survey and publish it."
- "Turn my onboarding deck into a course."
- "Show me the new audience questions and dismiss the off-topic ones."

## What data goes where

The plugin has no code of its own and runs nothing on your machine. It only declares the connector.

1. When you ask Claude to use AhaSlides, the content Claude sends to the connector (presentation titles, slide text, quiz questions, survey questions, course content, and requests to read responses) goes to AhaSlides at `mcp.ahaslides.com`.
2. The connector returns your presentations, slides and audience responses to Claude so that it can answer you. Audience responses can include names and answers that participants typed.
3. Nothing is sent anywhere else, and the plugin does not read your environment variables or local files.

AhaSlides handles this data under its [privacy policy](https://ahaslides.com/privacy/) and [terms of service](https://ahaslides.com/terms/).

## Support

- Help centre: https://help.ahaslides.com/
- Privacy policy: https://ahaslides.com/privacy/
- Terms of service: https://ahaslides.com/terms/
- Issues with this plugin: https://github.com/AhaSlides-Product/ahaslides-claude-plugin/issues

## Licence

MIT. See [LICENSE](LICENSE).
