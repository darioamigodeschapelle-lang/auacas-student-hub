# Submissions page setup

The page now contains a complete on-page form. Students type directly into `submissions.html` and select **Send for review**. Their email application opens with a private message addressed to `darioamigodeschapelle@gmail.com`.

## Publishing approved contributions

Add reviewed submissions to `content-submissions.json`.

```json
{
  "items": [
    {
      "type": "advice",
      "title": "Review lecture objectives before class",
      "text": "Spend ten minutes previewing the objectives so the lecture has a clear structure.",
      "cohort": "Pre-Med 1",
      "subject": "Biology",
      "author": "Pre-Med 3 student",
      "date": "2026-09-25"
    }
  ]
}
```

For a resource, use `"type": "resource"` and add `"url": "https://..."`. Valid public types: `advice`, `resource`, `experience`.

## Important limitation

This email-based method works on a static website without a server, but the student must finish sending the prepared email. For automatic collection without opening an email application, connect the same visible form to Google Forms, Formspree, Netlify Forms, or a custom backend later.
