# Getting Back to Tri

Personal Progressive Web App for rehab, strength, mobility, circulation/recovery routines and swim/bike/run training logging.

Current release: **v1.6.1 PWA**.

## GitHub Pages
Publish from the `main` branch and `/(root)` folder.

## Files
Keep these five files at the repository root:
- `index.html`
- `manifest.webmanifest`
- `service-worker.js`
- `icon.svg`
- `README.md`

Training and recovery history are stored locally in the browser/PWA. Export CSV backups periodically.

## v1.6.1
- Adds technique-demo links to the Circulation Reset for the less-obvious movements.
- Diaphragmatic breathing: NHS Fife video.
- Ankle pumps: Lancashire Teaching Hospitals physiotherapy video.
- Gentle rebounder/basic bounce: beginner low-impact technique demonstration.
- The rebounder demo only appears when Gentle rebounder is selected.
- Timers remain fully usable offline; external demo videos require internet access.

## v1.6
- Adds a guided **Circulation Reset** quick-start routine.
- Six gentle movements: diaphragmatic breathing, ankle pumps/calf raises, easy marching, shoulder rolls/arm sweeps, a 2-minute rhythmic stage, and a relaxed breathing/shake-out finish.
- Choose the 2-minute stage as **March in place** or **Gentle rebounder**.
- Choose a use context: **Morning**, **After sitting**, or **Recovery**.
- 5-second changeovers; total guided duration **6:25**.
- Completed movements and the selected context/movement are recorded in training History.
- Wording deliberately avoids detox/medical-treatment claims.
- Introduces profile-specific Back-to-Tri storage keys and safely migrates existing v1.x local training/recovery data.
- Adds a persisted internal app-mode preference (`tri`) as groundwork for the multi-mode v1.7 release.

## v1.5
- Added a dedicated Pre-Walk Warm-Up quick-start routine.
- 8 hip-flexor clock positions at 15 seconds each.
- Wall-supported single-leg hip lift for 30 seconds left and right.
- 8-second changeovers; total guided duration 4:12.
- Completed intervals are saved individually in training History.

## v1.4
- Added the Recovery dashboard with personal baselines and Green / Amber / Red readiness.
- Tracks sleep, HRV, resting HR, Body Battery, stress, steps and optional sleep-stage data.
- Added recovery CSV export and paste-from-summary helper.

## v1.3
- Added the guided Daily Quick Routine.
- 12 × 30-second work intervals with 8-second changeovers.
- Total guided duration 7:28.
