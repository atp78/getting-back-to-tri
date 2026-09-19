# Getting Back to Tri

Multi-mode, local-first Progressive Web App.

Current release: **v1.8b PWA**.

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
