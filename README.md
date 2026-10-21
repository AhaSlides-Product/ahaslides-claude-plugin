# AhaSlides for Claude

![AhaSlides](logo.png)

Connect Claude to [AhaSlides](https://ahaslides.com), the interactive presentation platform, so you can build and run audience-engagement sessions by describing what you want. Ask Claude to create a presentation from a topic, turn notes into a quiz, add polls and word clouds, or summarise how your audience responded.

## What it includes

1. **AhaSlides connector.** A remote MCP server at `https://mcp.ahaslides.com/mcp` that lets Claude create, edit, organise and read your presentations, surveys and audience responses.
2. **`build-presentation` skill.** Turns a topic or outline into an interactive deck with a sensible mix of content, polls, quizzes and Q&A.
3. **`make-quiz` skill.** Builds a scored quiz presentation from a subject, a level and a number of questions.
4. **`review-results` skill.** Reads the responses to a presentation or survey and summarises them.

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

## What data goes where

The plugin has no code of its own and runs nothing on your machine. It only declares the connector.

1. When you ask Claude to use AhaSlides, the content Claude sends to the connector (presentation titles, slide text, quiz questions, survey questions, and requests to read responses) goes to AhaSlides at `mcp.ahaslides.com`.
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
