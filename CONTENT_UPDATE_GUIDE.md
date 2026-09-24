# AUACAS Student Hub — Content Update Guide

You can update announcements, exams, and calendar events without changing `index.html`.

## Where to make updates

1. Open the `auacas-student-hub` repository on GitHub.
2. Select `content.json` at the repository root.
3. Select the pencil icon (**Edit this file**).
4. Make your changes carefully, keeping the JSON punctuation valid.
5. Select **Commit changes**.
6. Wait about 1–5 minutes, then refresh the live website.

## Weekly announcements

Add an item inside the `announcements` list:

```json
{
  "title": "Chemistry review session",
  "message": "The review session will take place after class in Room 2.",
  "published": "2026-09-23"
}
```

The announcement appears from its `published` date and expires seven days later. The website hides it automatically after seven days. The GitHub Action also removes it from `content.json` during its next daily run.

Multiple announcements must be separated by commas:

```json
"announcements": [
  {
    "title": "First announcement",
    "message": "Announcement text.",
    "published": "2026-09-23"
  },
  {
    "title": "Second announcement",
    "message": "Announcement text.",
    "published": "2026-09-24"
  }
]
```

## Upcoming exams

Add an item inside the `exams` list:

```json
{
  "title": "Chemistry Exam 2",
  "course": "Chemistry",
  "date": "2026-10-05T09:00:00-04:00",
  "location": "Room to be confirmed"
}
```

The countdown is calculated automatically. Exams also appear on the calendar.

For an exam without a confirmed time, use only the date:

```json
"date": "2026-10-05"
```

## Calendar events

Add an item inside the `events` list:

```json
{
  "title": "SGA student meeting",
  "date": "2026-10-08T12:00:00-04:00",
  "type": "Student meeting",
  "location": "Location to be confirmed",
  "description": "Open meeting for student updates and questions."
}
```

## Complete structure

```json
{
  "lastUpdated": "2026-09-23",
  "announcements": [],
  "exams": [],
  "events": []
}
```

## Important JSON rules

- Use straight double quotation marks: `"text"`.
- Separate multiple items with commas.
- Do not place a comma after the final item in a list.
- Dates must use `YYYY-MM-DD`.
- Timed events should include the Antigua time-zone offset: `YYYY-MM-DDTHH:MM:SS-04:00`.
- Only publish information that is confirmed and appropriate for the public website.

## Enable automatic deletion

The package includes `.github/workflows/expire-announcements.yml`.

After uploading the package:

1. Open the repository’s **Actions** tab.
2. Enable workflows if GitHub asks you to do so.
3. Open **Remove expired weekly announcements**.
4. You may select **Run workflow** to test it manually.

The workflow runs once per day. GitHub controls the exact start time, so physical deletion may occur several hours after the seven-day mark; the website itself hides the announcement immediately when it expires.

## Dark mode and privacy

The theme toggle applies only to the current visit. It intentionally does not use cookies or browser storage, preserving the site’s privacy-first promise.
