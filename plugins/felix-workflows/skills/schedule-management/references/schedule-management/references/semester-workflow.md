# Semester workflow

## Term manifest

Before writing, assemble one record per event family:

```yaml
term: Fall 2026
timezone: America/Los_Angeles
instruction:
  first_day: 2026-09-23
  last_day: 2026-12-04
weeks:
  - {date: 2026-09-28, title: Week 1}
holidays:
  - {date: 2026-11-11, title: Veterans Day, cancel_instruction: true}
courses:
  - canonical_name: MAT 150A Abstract Algebra
    lecture: {days: [MO, WE, FR], start: "10:00", end: "10:50", location: Wellman Hall 106}
    discussion: {days: [TH], start: "18:10", end: "19:00", location: TLC 3212, first_date: 2026-10-01}
    exams:
      - {title: Midterm 1, date: 2026-10-16, start: "10:00", end: "10:50", source: syllabus}
```

Use explicit dates for exceptions and exams. Record `TBA` internally for unresolved facts, but do not create a calendar event titled TBA unless the user requests a placeholder.

## Week derivation

1. Get the first and last days of instruction from the Registrar.
2. Call any instruction before the first Monday `Week 0`.
3. Label the first Monday on or after instruction starts `Week 1`.
4. Increment every Monday through `Week 10`.
5. Label the Monday after instruction ends `Final Week`.
6. Cross-check the derived dates against syllabus week labels when present.

## Recurrence reconciliation

For each lecture/discussion family, expand expected occurrences between its source-backed first and last dates. Remove dates that are official holidays or explicit course cancellations. Compare this expanded set with the active client for the target iCloud calendars, paying special attention to:

- Week 0 sections that start later than the lecture.
- Thanksgiving week and other holiday exceptions.
- Week 10 events after a prematurely ended recurrence.
- A final occurrence accidentally created on a Saturday or wrong weekday.

Never assume that a Discussion starts during Week 0 merely because its recurring weekday occurs then. Use the section's `first_date`; if a professor says the first week has no Discussion, the first generated occurrence must be in the next eligible week.

## Same-day missing-event audit

When the user says today's schedule seems incomplete:

1. Resolve “today” in `America/Los_Angeles`.
2. List every lecture, discussion, and lab whose normal weekday matches today.
3. Exclude meetings before `first_date`, after `last_date`, on official holidays, or canceled by a course announcement.
4. Compare the remaining expected meetings with the active calendar client by normalized title, start, end, and target iCloud calendar.
5. Add only genuinely missing events. Report intentionally absent meetings with the source-backed reason instead of treating them as omissions.

## Exam reconciliation

For each course, inspect syllabus, Canvas assignments/calendar, and announcements for `midterm`, `exam`, `quiz`, and `final`. Capture:

- exact date and time or due window;
- location or online/take-home format;
- whether it replaces a lecture;
- whether multiple midterms require numbering;
- source and last-verified date.

When a take-home exam has a release and due window, use a timed event spanning the authoritative window when practical and place the due time prominently in notes. When only a due time is authoritative, use the due-time event and state the release timing in notes.

Under the user's calendar policy, a confirmed Midterm always replaces that course's corresponding Lecture occurrence. During reconciliation, remove the Lecture occurrence on the Midterm class period and retain only the Midterm event in `考试`.

## Verification checklist

- Week markers are all-day on Mondays in `标记`.
- Holidays are all-day in `节假日` with official names.
- No lecture/discussion remains on an official holiday.
- Discussion titles omit `Discussion` and rely on `讨论` color.
- Every valid Week 10 class meeting exists through the last instruction day.
- Each confirmed midterm and final exists exactly once in `考试`.
- No Midterm class period also contains the corresponding Lecture event.
- Final titles end in `Final`, never `Final Exam`.
- TBA exams are reported, not guessed.

