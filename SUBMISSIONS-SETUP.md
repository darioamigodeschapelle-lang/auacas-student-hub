# Submissions page setup

1. Create a private Google Form with these recommended fields:
   - Contribution type
   - Student cohort
   - Course or subject
   - Title
   - Advice, description, or course experience
   - Resource URL (optional)
   - Display name preference (full name, first name, or anonymous)
   - Permission to publish checkbox
2. In `submissions.html`, replace `PASTE_GOOGLE_FORM_URL_HERE` with the form URL.
3. Optional: add the Google Form entry ID for “Contribution type” to `TYPE_ENTRY_ID` so buttons preselect a category.
4. Publish only reviewed entries in `content-submissions.json`.

Example approved entry:

```json
{
  "type": "advice",
  "title": "Review lecture objectives before class",
  "text": "Spend ten minutes previewing the objectives so the lecture has a clear structure.",
  "cohort": "Pre-Med 1",
  "subject": "Biology",
  "author": "Pre-Med 3 student",
  "date": "2026-09-25"
}
```

For a resource, use `"type": "resource"` and add `"url": "https://..."`. Valid types: `advice`, `resource`, `experience`.
