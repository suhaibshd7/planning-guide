# planning-guide

## Offline behavior

This app can work with no internet **only after the same device has loaded it successfully at least once while online**.

Why:
- GitHub Pages still serves a normal website first.
- The browser needs one successful visit to download `index.html`, install the service worker, and populate the cache.
- After that, the cached app shell should still reopen offline after a phone restart, unless the browser/site data is cleared by the user, OS, or browser.

## Important limitation

If a phone has **never opened the site before**, then **absolute zero-internet first launch will not work** from GitHub Pages alone. After the first successful online load, the cached shell should survive normal phone restarts, but it is still not guaranteed if site data gets cleared or purged. For true first-launch-without-internet behavior, you would need a packaged mobile app or a bundled offline distribution already stored on the device.

## Recommended test

1. Open the site on the target phone while online.
2. Wait for the page to finish loading.
3. Reopen it once.
4. Turn on airplane mode.
5. Reopen the site or the homescreen shortcut and confirm it still works.
