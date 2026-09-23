# 308 Desk

Shop quoting desk for **308 Embroidery** (Ron Ahlers).

## Theme (v2.28)

Quantity pricing now includes a 6+ decoration discount tier (default 4%).

Dark by default (navy/charcoal + gold). Settings → Dark/Light; stored in `localStorage` key `desk308_theme` (device only, not Drive sync).

## Live sync (v2.18)

- **Google Sign-In required** — app shows a navy/gold splash until you sign in.
- Quote data syncs through Google Drive folder **`308 Desk Sync`** → **`desk308-live.json`**.
- Browser **localStorage** key `desk308` is an offline cache only.
- Allowed Google accounts: `ronahlers@gmail.com`, `ron.ahlers@gmail.com`.

## Privacy

- HTML may be on the open web, but the desk is **unusable without Google sign-in**.
- Customer quotes stay in Ron’s Drive — not on GitHub.
- **Rate tables are still in page source** (View Source). Do not share the URL widely.

## OAuth setup

Replace in `index.html`:

```js
const GOOGLE_CLIENT_ID = "PASTE_CLIENT_ID.apps.googleusercontent.com";
```

Add Authorized JavaScript origins for:

- `https://ronahlers-cmyk.github.io`
- `http://localhost` (optional, for local testing)

Scope used: `https://www.googleapis.com/auth/drive.file` (app-created sync folder/file).

## Live

https://ronahlers-cmyk.github.io/308-desk/
