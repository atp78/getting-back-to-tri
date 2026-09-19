# Getting Back to Tri

Multi-mode, local-first Progressive Web App.

Current release: **v1.8a PWA**.

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
