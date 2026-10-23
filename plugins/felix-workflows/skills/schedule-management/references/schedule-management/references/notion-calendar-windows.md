# Windows execution through Notion Calendar

Read this reference only when the calendar task is being executed from Windows through Notion Calendar.

## Architecture and boundary

Notion Calendar is the Windows client; the connected iCloud calendars remain the shared calendar store. Events created in the iCloud calendars should synchronize to Apple Calendar on Apple devices. A Notion database shown inside Notion Calendar is a different data source and must not replace `专业课`, `讨论`, `考试`, `活动`, `标记`, or `节假日`.

The user's current setup normally reflects changes across Notion Calendar and Apple Calendar in roughly two to three seconds. Treat that as an observed baseline only. Network conditions, account refresh, or provider throttling can make synchronization slower.

## Preflight

Before editing:

1. Confirm Notion Calendar desktop or web is signed in and the intended iCloud account is connected.
2. Confirm the exact target iCloud calendar is visible and writable. Do not create a similarly named Notion database or local calendar as a workaround.
3. Confirm the displayed timezone is `America/Los_Angeles` unless the user specified another timezone.
4. Inventory matching events before writing. Match title, date, start, end, all-day state, target calendar, and recurrence scope.

Do not request, expose, or store the user's Apple app-specific password in the skill or repository. If the iCloud connection is broken, ask the user to reconnect it through Notion Calendar settings.

## Write and synchronization verification

After each coherent batch:

1. Save the event in the exact iCloud calendar.
2. Re-open or search for the event in Notion Calendar and verify its title, calendar, time, location, and all-day or recurrence state.
3. Allow the normal two-to-three-second synchronization window. If the other client has not updated, wait and refresh for a bounded period of up to 15 seconds before concluding that synchronization failed.
4. Do not repeat the write while synchronization is pending. First search both clients for the original event to avoid duplicates.
5. When Apple Calendar or another iCloud view is available, verify the same event there. If it is not available, report that Notion Calendar was verified but cross-client synchronization was not independently observed.

For a large semester build, write and verify a small representative batch first: one timed event, one all-day event, and—only if the interface exposes an unambiguous scope—one recurring event. Continue only after the target calendars and synchronization behavior are correct.

## Recurring events and destructive changes

Do not assume iCloud recurring-series controls are identical to Apple Calendar. Before changing a recurring event, inspect whether Notion Calendar explicitly offers the intended scope: this occurrence, this and future occurrences, or the entire series. If the required scope is absent or ambiguous, leave the series unchanged and report the limitation.

Before deleting events through the interface, follow the main skill's deletion confirmation rule. After a confirmed one-occurrence deletion or cancellation, verify that adjacent occurrences remain intact. After a confirmed series-level change, inspect the first occurrence, a middle occurrence, the last expected occurrence, and known holiday exceptions.

## Current product references

- Notion Calendar apps: <https://www.notion.com/help/notion-calendar-apps>
- Manage calendars and events: <https://www.notion.com/help/manage-your-calendars-and-events>
- Create a Notion Calendar account and connect iCloud: <https://www.notion.com/help/create-a-notion-calendar-account>

These product capabilities can change. When a UI option or provider capability matters to a risky mutation, prefer the current official documentation and the options actually visible in the connected account.
