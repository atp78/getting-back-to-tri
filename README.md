# Getting Back to Tri

Multi-mode, local-first Progressive Web App.

Current release: **v1.9 PWA**.

## v1.9 — A4 printable weekly training planner

Adds a dedicated **Planner** view and a printer-friendly A4 portrait weekly checklist.

- Uses the synced Weekly Plan as the repeating plan template.
- Select any week; dates are rendered Monday through Sunday.
- Splits plan text such as `Lower Body + Swim` into separate physical tick boxes.
- Shows planned totals for Swim, Bike, Run and Strength / Mobility.
- Includes optional `This week's focus`.
- Includes handwritten `Completed / Planned`, `Remaining` and `Notes / Adjustments` areas.
- `Print / Save PDF` uses the browser's standard print dialog and an A4-specific print stylesheet.
- A Home shortcut opens the planner directly.
- The Planner does not auto-tick completed app sessions in v1.9; the wall sheet remains a simple physical checklist.
- Weekly Plan remains a separate synced Drive file, providing a clean base for future planner enhancements.

## v1.8c.1 — purpose-specific cloud files

Google Drive now uses five clearly named active files under `My Drive / Getting Back to Tri`:

- `Getting_Back_to_Tri_Workout_Library.json`
  - reusable workout/session definitions only
  - designed to be shareable
  - excludes completed history, recovery data and weekly plan
- `Getting_Back_to_Tri_Workout_Session_History.json`
  - completed sessions from both Back-to-Tri and Morning Movement modes
  - preserves each original history record inside a mode wrapper
- `Getting_Back_to_Tri_Recovery_Data.json`
  - recovery history/snapshots and recovery baseline
- `Getting_Back_to_Tri_Settings.json`
  - Morning Movement and Circulation preferences
  - excludes selected app mode and Google credentials, which remain device-local
- `Getting_Back_to_Tri_Weekly_Plan.json`
  - current seven-day weekly plan
  - separate now so v1.9 can evolve the printable planner without mixing it into settings

### Migration
- A v1.8c `Getting_Back_to_Tri_Personal_Data.json` is detected and can be split into Session History, Recovery Data, Settings and Weekly Plan.
- An older combined `Getting_Back_to_Tri_Sync.json` is also supported as a migration source.
- Older source files are retained unchanged as safety copies.
- The existing v1.8c Workout Library file is reused rather than duplicated when available.

### Sync behaviour
- `Pull all` / `Push all` handles all five active files.
- Each file also has individual Pull / Push controls.
- Conflict protection is maintained per file.
- `Push all` checks all five remote modified times before it starts writing any file.

## v1.8c — split Workout Library and Personal Data
- Replaces the single active cloud sync JSON with two files inside `My Drive / Getting Back to Tri`:
  - `Getting_Back_to_Tri_Workout_Library.json`
  - `Getting_Back_to_Tri_Personal_Data.json`
- Workout Library contains reusable session definitions only.
- Personal Data contains training history, recovery data/baseline, Morning Movement data/settings, circulation preferences and the weekly plan.
- Detects the old combined `Getting_Back_to_Tri_Sync.json` and offers a one-time split migration.
- The old combined JSON is kept unchanged as a safety copy.
- Pull/Push All remains available, with separate conflict checks for each cloud file.
- Individual Pull/Push controls are available for the Workout Library and Personal Data.
- Library export is now shareable and excludes recorded history, recovery data and weekly plan.
- Importing a workout library preserves the receiving device's existing weekly plan.

## v1.8b — dedicated Google Drive folder
- Creates/uses `My Drive / Getting Back to Tri`.
- New sync files are created inside that folder.
- Detects the existing root-level v1.8a/v1.8a.1 sync file.
- Offers to move the existing sync file into the folder rather than creating a competing copy.
- Preserves the existing Google Drive file ID during migration, so already-linked devices keep referring to the same cloud file.
- Shows the Drive folder location in the Sync panel and adds an Open folder shortcut.

## v1.8a.1 — Google Identity Services loading fix
- Google Identity Services now retries on demand when Connect Google Drive is tapped.
- External Google requests bypass the PWA service-worker offline fallback.
- The service worker handles same-origin app files only.
- `index.html` is used as an offline fallback only for navigation requests.
- Adds a direct Google Identity Services connectivity-test link in the Sync panel.

## v1.8a — manual cross-device sync

This first sync release keeps local browser/PWA storage as the working copy and adds:
- complete JSON backup / restore
- optional Google Drive connection
- one private Drive sync file: `Getting_Back_to_Tri_Sync.json`
- explicit **Pull from Drive** and **Push to Drive**
- conflict protection: Push is blocked if the Drive file changed since this device last saw it
- device labels and sync timestamps
- selected mode remains device-local
- OAuth access token remains in memory only

### Synced data
- Back-to-Tri training history
- recovery history and baseline
- circulation preferences
- private local exercise library / weekly plan
- Morning Movement history and settings

### Not synced
- selected app mode
- Google OAuth Client ID / Drive file ID
- transient UI state or running timers

## Google Drive setup
1. Create/select a Google Cloud project.
2. Enable the Google Drive API.
3. Configure the OAuth consent screen.
4. Create an OAuth 2.0 Client ID for a Web application.
5. Add `https://atp78.github.io` as an authorised JavaScript origin.
6. Paste the Client ID into the app's Sync panel.
7. Connect Google Drive, then Find / create the sync file.

The app requests only `https://www.googleapis.com/auth/drive.file`.

## Safe v1.8a workflow
On a device that may be behind:
1. Connect Google Drive.
2. Find the sync file.
3. Pull.
4. Use the app.
5. Push when finished.

Automatic background sync is deliberately deferred until the manual file workflow has been proven reliable.
