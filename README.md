# Getting Back to Tri

Personal Progressive Web App for exercise logging, guided mobility/circulation routines, recovery tracking and swim/bike/run sessions.

Current release: **v1.6.3 PWA**.

## Privacy / exercise-library architecture
The public GitHub application contains the generic exercise-session engine only. Personal exercise names, ordering, sets, targets, technique cues, demo links and weekly plan are stored in browser/PWA local storage.

Use the app's **Export library JSON** function to back up that private local library. Do not commit a private exercise-library JSON file to a public repository.

## GitHub Pages
Publish from the `main` branch and `/(root)` folder.

## Files
Keep these files at the repository root:
- `index.html`
- `manifest.webmanifest`
- `service-worker.js`
- `icon.svg`
- `README.md`

## v1.6.3
- Removes the hard-coded personal strength/mobility exercise library from the public source.
- Adds a local **Private exercise library** manager.
- Create, rename and delete sessions locally.
- Add/edit/delete exercises and move them up/down to control session order.
- Store sets, targets, tags, demo URLs/search terms and technique cues locally.
- Optional per-session timer.
- Pin local sessions to the Home screen.
- Export/import the private exercise library as JSON.
- Weekly plan moved from public code into private local data.
- Existing training and recovery history remains separate and compatible.

## Built-in guided routines
The app continues to include the user-created Daily Quick Routine, Pre-Walk Warm-Up and Circulation Reset, plus swim/bike/run quick logging and the Recovery dashboard.
