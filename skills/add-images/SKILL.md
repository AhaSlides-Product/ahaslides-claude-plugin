---
name: add-images
description: Find stock photos or upload an image for AhaSlides slides and course pages. Use when the user wants a picture on a slide, a cover image, or to upload a logo or photo.
---

# Add images

## Steps

1. To find a photo: `search_images` with a short, concrete query. Show the user the candidates and let them pick unless they asked you to choose.
2. To use an image in a presentation: upload it with `upload_image` (from a public URL, or base64 data with a filename) and use the hosted URL it returns on the slide. Never hot-link a foreign URL; a slide's own upload URL is the one to use.
3. For eLearning, put a `search_images` URL in as it is, and upload anything else with `upload_image` using `destination` set to `elearning`. A slides upload URL expires, so do not reuse one in a course.
4. Add the image to the slide through `create_slides` or `update_slide_content`, or to a course through `update_course` (the `cover`) or the lesson block tools.

## Rules

- Only upload images the user supplied or that came from `search_images`.
- Do not upload personal or sensitive images unless the user asks.
