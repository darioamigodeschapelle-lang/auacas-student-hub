# AUACAS Class Portal Update Guide

The website now has a main hub and four separate class portals:

- `premed-1.html` uses `content-premed-1.json`
- `premed-2.html` uses `content-premed-2.json`
- `premed-3.html` uses `content-premed-3.json`
- `premed-4.html` uses `content-premed-4.json`

Each class file is independent. Updating Pre-Med 3 does not change the information shown to Pre-Med 1, 2, or 4.

## Update a class

1. Open the repository on GitHub.
2. Select the correct `content-premed-N.json` file.
3. Select the pencil icon.
4. Edit the information, keeping the JSON punctuation valid.
5. Select **Commit changes**.
6. Wait 1–5 minutes and refresh the class portal.

## Weekly announcement

Add an item inside `announcements`:

```json
{
  "title": "Weekly class update",
  "message": "Write the approved announcement here.",
  "published": "2026-09-24"
}
```

The portal automatically hides the announcement seven days after `published`. The GitHub workflow later removes it from the content file.

## Important class date

Add an item inside `events`:

```json
{
  "title": "Biology review session",
  "date": "2026-10-05T12:00:00-04:00",
  "location": "Room to be confirmed"
}
```

Use Antigua time (`-04:00`) for events with a confirmed time. If the time is unknown, use only `YYYY-MM-DD`.

## Approved resource link

Add an item inside `resources`:

```json
{
  "title": "Cell biology study guide",
  "course": "Cell Biology",
  "description": "Approved review material for the current unit.",
  "url": "https://example.com/resource"
}
```

Only `https://` and `http://` links will open. Do not publish private documents, copyrighted materials without permission, student records, passwords, or personal information.

## Complete class-file structure

```json
{
  "lastUpdated": "2026-09-24",
  "announcements": [],
  "events": [],
  "resources": []
}
```

Separate multiple items with commas. Do not add a comma after the final item in a list.

## Recommended approval process

1. A student sends a suggested announcement, date, or link to the class representative.
2. The representative verifies the information.
3. The site administrator reviews it for privacy and accuracy.
4. The administrator publishes it in the correct class content file.

Students do not directly edit the public repository, and the portals do not accept file uploads.

## Schedule source

The Fall 2026 schedules were transcribed from the AS Health Sciences schedule supplied by the site administrator. Dates, rooms, instructors, and lab start times should always be checked against current official communication.
