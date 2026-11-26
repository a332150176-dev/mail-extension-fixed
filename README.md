# Mail extension patch — v1.1.5

This repository contains the files changed to fix the "Continue where we left off" flow.

## What changed
- The Continue button returns to the existing Google tab instead of starting a fresh signup.
- The extension stores the last Google tab ID and URL, and focuses that tab when possible.
- If the tab was closed, it only reopens a validated saved Google URL; it no longer silently starts signup from the beginning.
- When Google requires phone verification, the extension keeps the current page and explains that Google requires verification. It does not repeatedly restart signup.
- The Chrome `tabs` permission is declared so the background worker can query Google tabs and read their URLs.

## Apply the patch
1. Keep a copy of your original extension folder.
2. Extract your original ZIP to a folder.
3. Download this repository as a ZIP.
4. Copy the files and folders from this repository over the matching paths in the original extension folder, allowing overwrite.
5. Open `chrome://extensions`, enable Developer mode, and click Reload on the extension.

This is a patch over the original extension, not a standalone full package: unchanged files (including `lib/jsQR.js`, `content/panel.js`, and `content/sms4free.js`) remain in your original folder.

**Important:** the patch does not bypass Google's mandatory phone-verification requirement. If Google requires verification, use one of the methods Google itself offers on that page.
