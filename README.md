# QA Lead Assistant

Meeting summaries and urgent alerts for a QA lead and QA members, built from Google Calendar and
Gemini meeting notes. Runs as a cloud routine on each person's own Google account, so it works while
their computer is off. Times are Bangladesh time (Asia/Dhaka, GMT+6); cron runs in UTC.

## What it does
- Hourly, 9 AM-11 PM Dhaka (cron `5 3-17 * * *`): finds meetings that just ended, reads the Gemini notes in Drive,
  writes a summary and emails it to the person only.
- Template: Update | Blockers and where | Decisions | Action items | Questions/Follow-up | Risk flags.
- Marks meetings Attended or Missed, and flags overlapping meetings at 9 AM.
- Starts the subject with [URGENT] for new blockers, decisions that change scope or release dates, and action
  items due today or without a date.

## Files
- `MEMBER-SETUP.md`: one-time setup for a QA member and the prompt to paste.
- `prompts/lead-routine-prompt.md`: the lead's routine prompt (put your own team list in it).
- `config/summary-template.md`: the summary template.

## Not included
Team email addresses, meeting summaries and any credentials are kept out of this repo.

## Roadmap
1. Meeting summaries (done). 2. Team progress and project health from Karmo and Execute.io.
3. Google Chat mention alerts. 4. Dashboard inside Execute.io.
