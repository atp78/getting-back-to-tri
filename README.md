# Getting Back to Tri

Multi-mode Progressive Web App.

Current release: **v1.7 PWA**.

## Modes

### Getting Back to Tri
The existing private local exercise library, guided mobility/circulation routines, Recovery dashboard and swim/bike/run session logging.

### Morning Movement
A completely separate simple mode intended for a short guided morning movement routine:
- 7 guided movements
- 6:15 total including 5-second changeovers
- optional walk/march or gentle rebounder stage
- optional energy-before and energy-after ratings (1–5)
- optional notes
- separate History and Settings
- separate CSV export
- separate local-storage namespace from Back-to-Tri data

Morning Movement is a general wellbeing/movement tool, not a treatment for hypothyroidism and not a replacement for prescribed medication.

## Mode selection
On the first v1.7 launch, the app asks which mode to enter. The explicit selection is persisted locally in `gbtt_selected_mode_v1`. Either mode has a **Switch mode** button, and switching does not delete or mix data.

## Privacy / exercise-library architecture
The public GitHub application contains a generic local exercise-session engine. Personal Back-to-Tri exercise prescriptions remain in local browser/PWA storage and can be imported/exported separately as private JSON.

## GitHub Pages
Publish from the `main` branch and `/(root)` folder.

## v1.7
- Adds persisted first-use mode selection.
- Adds separate Morning Movement mode.
- Adds simple guided 6:15 morning routine.
- Adds energy-before/after logging and Morning-only history.
- Adds Morning settings, CSV export and optional vibration cues.
- Keeps Back-to-Tri and Morning data in separate local-storage namespaces.
