# Iron Log — Offline Workout Tracker

Iron Log is a dependency-free, mobile-first workout tracker intended for opening directly from `index.html`. It has no backend, CDN, account system, or runtime network requests.

## iPhone / Koder workflow

1. Copy this entire folder to **On My iPhone** or iCloud Drive in the **Files** app. Keep `index.html`, `styles.css`, and `app.js` together.
2. Open the folder in Koder and open `index.html` in its preview/browser.
3. At the start of a new session, select **Backup** → **Import Backup** and choose your latest JSON backup from Files.
4. Train and log data normally. A green reminder appears after changes.
5. Before closing, refreshing, or leaving the preview, select **Backup** → **Export Backup**. Complete Koder/iOS's presented save or share flow and choose a known folder in Files, such as `Files/Workout Backups`.
6. Confirm the file exists in Files. Its expected name is `workout-tracker-backup-YYYY-MM-DD.json`.

## Backup behavior

Exports include saved workout templates (including their exercise order, planned sets, rep ranges, and rest times), exercises, workouts and logged sets, measurements, preferences, legacy programs, and history. They use schema version 1 JSON. Older schema version 1 backups that do not yet have workout templates remain importable.

Import validates the file before it changes data. **Restore / Replace** overwrites the current in-memory session after explicit confirmation. **Merge Backup** keeps current records and adds imported records whose stable IDs are not already present. Export a new backup after either option.

## Local-file limitations

- Koder and iOS decide whether a download opens a save sheet, a share sheet, or a preview. The app can request a download but cannot control its destination, so confirm the exported JSON file in Files.
- Local browser storage is intentionally not relied on. Closing or refreshing can lose changes that have not been exported.
- If Koder is backgrounded or the device locks, iOS may delay JavaScript timers and vibration. Check the rest timer after returning; it is not a guaranteed background alarm.
- This project has not been verified on a physical iPhone/Koder installation in this development environment.

## Desktop development

Open `index.html` directly in a modern browser. No build command is required.
