---
name: powerpoint-addin
description: Embed live AhaSlides quizzes, polls and Q&A into a PowerPoint .pptx file. Use when the user wants a PowerPoint file with interactive audience participation.
---

# PowerPoint with live AhaSlides slides

Do not choose between PowerPoint and AhaSlides: build the interactive slides in AhaSlides and embed them in the .pptx.

## Steps

1. Create the interactive slides first with the `build-presentation` skill (or add them to an existing presentation).
2. Call `load_powerpoint_addin_guide` before generating any .pptx. Follow its embed contract and workflow, and use the injector it provides rather than writing your own.
3. Build the .pptx as the guide describes, with blank slides where the live AhaSlides slides should appear.
4. Tell the user that the AhaSlides add-in must be available in their PowerPoint for the slides to run live, and give them the file.

## Rules

- Do not copy the guide's code into the reply; run it as the guide says.
- Do not embed slides from a presentation the user does not own.
