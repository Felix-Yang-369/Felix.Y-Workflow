---
name: schedule-management
description: Manage Felix Yang's iCloud-backed academic calendars from Apple Calendar on macOS or Notion Calendar on Windows. Use when building a university-term calendar or auditing, creating, correcting, and reconciling lectures, discussions, labs, exams, academic-week labels, holidays, cancellations, and campus activities from authoritative academic sources. Enforces canonical names, calendar categories, meeting bounds, recurrence scope, deduplication, synchronization-aware verification, and device-appropriate execution.
---

# 日程管理 SKILL

Use this skill to turn current-term academic sources into clean, auditable iCloud calendars. Apple Calendar on macOS and Notion Calendar on Windows are two clients for the same calendar data; they are not separate schedule sources.

## Load the governing rules

Read [references/calendar-policy.md](references/calendar-policy.md) before making calendar changes. Treat it as the user's canonical policy and this skill as the execution workflow. The user's newest explicit correction overrides both.

Read [references/semester-workflow.md](references/semester-workflow.md) when building or repairing a whole term, calculating academic weeks, or reconciling holidays and exams.

Read [references/notion-calendar-windows.md](references/notion-calendar-windows.md) before reading or changing calendars through Notion Calendar on Windows.

## Select the execution client

- On macOS, prefer Apple Calendar unless the user asks to use Notion Calendar or Apple Calendar is unavailable.
- On Windows, use the Notion Calendar desktop app or web app with the user's connected iCloud account. Write to the named iCloud calendars such as `专业课`, `讨论`, or `考试`; do not substitute a Notion database calendar.
- Treat the user's observed two-to-three-second iCloud synchronization delay as a normal baseline, not a guarantee. Do not immediately repeat a write just because another client has not refreshed yet.
- If the active client cannot expose a required field or an unambiguous recurring-event scope, stop that part of the mutation and report the limitation instead of approximating it.

## Source facts in this order

1. Instructor announcements, the current syllabus, and the current Canvas course.
2. Schedule Builder for enrolled section, meeting pattern, time, and room.
3. Registrar academic and final-exam calendars for instruction dates, holidays, and finals.
4. Email or conversation context supplied by the user.

Use the newest explicit course announcement when it supersedes an older syllabus. Do not infer a midterm date, time, room, or format from a grading percentage or a typical pattern. If a required exam fact remains TBA or conflicting, leave it uncreated and ask the user for the missing fact.

Treat tentative language such as “好像少了”, “可能”, or “是不是” as a request to audit, not as an authoritative schedule correction. Compare the date against the course's source-backed `first_date`, weekday, cancellations, and existing Calendar events before adding anything. An explicit statement such as “今天这节照常上” is a user correction and may override an older source.

## Normalize the calendar model

- Use `America/Los_Angeles` unless the user specifies another timezone.
- Put lectures in `专业课`, unless the user explicitly assigned a course to `水课`.
- Put discussions in `讨论`; use the canonical course title only, without `Discussion`.
- Put midterms and finals in `考试`.
- Put week markers in `标记` as all-day events on Monday.
- Put official holidays in `节假日` as all-day events, using the official holiday name without an artificial `Holiday —` prefix.
- Put non-course meetings and campus events in `活动`.
- Name a course `{SUBJECT} {NUMBER} {Official Short Title}`, for example `MAT 150A Abstract Algebra`.
- Name multiple midterms `{course_name} Midterm {number}`. Name a single unnumbered midterm `{course_name} Midterm Exam`. Name finals `{course_name} Final`; never append `Exam` to a Final title.

## Handle weeks and cancellations

- Treat pre-Week-1 instruction days as `Week 0`; do not create a Week 0 marker unless the user requests it.
- Create `Week 1` through `Week 10` on the Monday of each instructional week, then `Final Week` on the Monday of finals week.
- A week marker does not prove that every recurring section meets that week. Apply course-specific first/last-meeting rules from Canvas, syllabus, or announcements.
- Store an explicit `first_date` and `last_date` for every lecture, discussion, and lab family. Reject any generated occurrence that falls on the wrong weekday or outside that interval.
- On official university holidays and official no-instruction days, cancel/remove lecture and discussion occurrences. Keep only the all-day holiday label. Do not cancel an exam, make-up session, or special activity without an authoritative source.
- Every confirmed Midterm replaces the corresponding Lecture occurrence for that course. Keep the Midterm in `考试` and remove the overlapping Lecture occurrence so the same class period is not shown twice.
- Ensure recurring lecture and discussion series reach the Registrar's last day of instruction, including every valid Week 10 meeting.

## Execute safely

1. Inventory relevant calendars and existing events.
2. Build an explicit term manifest from sources before editing.
3. For a “missing today” report, build a same-day expected-versus-present table for every potentially matching course, including intentionally absent meetings and the source for each conclusion.
4. Compare by normalized title, start, end, calendar, and recurrence scope; reuse or correct existing events instead of duplicating them.
5. Preserve notes, location, URL, alerts, and attachments unless the source or user changes them.
6. For a recurring correction, determine whether it applies to one occurrence, future occurrences, or the entire series.
7. Before deleting events through the UI, present the exact deletion list and obtain action-time confirmation.
8. Apply confirmed additions and corrections.
9. Verify the result in the active calendar client's main view and by targeted search. When another synchronized client is available, wait for synchronization and cross-check there as well. Check Week 0, each holiday, Week 10, every exam, and every Midterm date for a duplicate Lecture separately.
10. Report completed changes, intentionally absent meetings, and unresolved TBA/conflicting facts.

## Completion gate

Finish only when titles, target iCloud calendars, all-day status, dates, times, rooms, timezone, recurrence end, holiday exceptions, synchronization state, and duplicates have all been checked. Leave uncertain exam events out rather than creating placeholders that look confirmed.

