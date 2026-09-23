308 DESK v2.33 — 308 Embroidery shop assistant
=============================================

v2.33 — Boot auth uses Drive about (drive.file) instead of oauth userinfo; no hanging silent token refresh — user taps Sign in.

v2.32 — Print/PDF uses each line's own blank (no weighted-average smear); description shows emb/dtg + blank breakdown; quote card says "blanks by line" when blanks differ.

v2.31 — Embroidery min/piece applies to stitch labor at all quantities; extra placement is added before quantity off, so discounted labor may fall below the minimum.

v2.28 — Added the 6+ quantity decoration discount tier (default 4%).

v2.27 — Dark theme by default (navy/charcoal + gold); Settings Dark/Light toggle; localStorage desk308_theme (device-only, not Drive sync). Print/PDF forced light.

v2.25 — blanksFromLineItems falls back to job-level blank when line items omit blank (fixes Print/PDF vs Subtotal mismatch on older Drive jobs).
v2.23 — Blank cost ($) on each quote line item; grand blanks total in breakdown (embroidery + DTG). Quote-level cBlank/dBlank removed.
v2.24 — Clarify per-line blank cost wording and add a line-item hint.

v2.22 — Drive live-sync: pushToDrive won't clobber newer remote; poll 15s; pull on window focus/pageshow; clearer "pulled from phone/Drive" status.

WHAT'S NEW IN V2.18 (Google Sign-In + Drive live sync)
------------------------------------------------------
1. Google Sign-In required (Google Identity Services) — soft-lock splash until signed in
2. Allowed accounts only: ronahlers@gmail.com, ron.ahlers@gmail.com (others get “Not authorized”)
3. Live sync file in Drive folder **308 Desk Sync** → **desk308-live.json**
4. Every save writes localStorage (`desk308`) then pushes to Drive (800ms debounce)
5. Pull on sign-in, app load, tab focus, and every 15s — newer `updatedAt` wins
6. Settings: signed-in email, sync status, Force pull / Force push / Sign out
7. Phone top bar: small sync indicator (Synced / Sync… / Offline / Err)
8. OAuth scope: drive.file (app-created sync folder/file only). CLIENT_ID placeholder must be replaced.
9. Manual Share to Drive / JSON import-export still available for **308 Desk Backups**

Earlier: v2.17 phone UI · v2.16 sidebar version · …

SETUP (one-time)
----------------
1. Google Cloud Console → create OAuth **Web** client ID
2. Authorized JavaScript origins: your Pages URL (and http://localhost if testing)
3. Replace in index.html:
     const GOOGLE_CLIENT_ID = "PASTE_CLIENT_ID.apps.googleusercontent.com";
4. Host the single HTML file (GitHub Pages or open from disk — GIS needs https origin
   except localhost)

PRIVACY
-------
- Quote/job data lives in Ron’s Google Drive (desk308-live.json), not on the host.
- localStorage key `desk308` is an offline cache on each device.
- The HTML is on the open web but unusable without Google sign-in.
- Rate tables are still visible in page source — do not share the URL widely.

PHONE TIP
---------
Open the live Pages URL in Safari/Chrome, sign in with Ron’s Google account,
then Add to Home Screen. Same Drive file = same quotes on phone, tablet, and PC.

308 Embroidery — Scottsbluff
