# Personal Toolkit — GitHub Pages PWA

This package is ready to publish as a static GitHub Pages site. It includes the existing Personal Toolkit HTML, PWA manifest, install icons, and an offline service worker. Google Drive sync options are not included.

## Publish on GitHub Pages

1. Download and unzip this package.
2. Create a GitHub repository (for example, `personal-toolkit`).
3. Upload **all files inside this folder** to the repository's top level. Make sure `index.html` is at the repository root, not inside another nested folder.
4. In the repository, open **Settings → Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**.
6. Select branch `main` and folder `/(root)`, then save.
7. Wait for GitHub Pages to publish. The URL will look like `https://YOUR-USERNAME.github.io/personal-toolkit/`.

## Install on Android

1. Open the published HTTPS URL in Chrome.
2. Let the page finish loading once while online.
3. Open Chrome's menu and choose **Install app** or **Add to Home screen**.
4. Launch Personal Toolkit from the new home-screen icon. After the first successful load, the app shell can open offline.

## Important notes

- Keep `index.html`, `manifest.webmanifest`, `service-worker.js`, `registerSW.js`, and the icon files together at the published site root.
- The service worker caches the app shell for offline launch. App records and uploaded Kit Finder PDFs remain in that browser's local storage/IndexedDB; they are not synced between devices.
- Browser storage can be cleared by the user or operating system. Export important data where the app offers that capability.
- The guest five-minute session and three-hour cooldown use browser storage and are suitable for casual access control, not tamper-proof security.
- After publishing an update, reopen the site online to let the service worker refresh the app shell. If an old version persists, close the installed app completely and reopen it while online.
- GitHub Pages serves over HTTPS, which is required for service workers and installable PWAs.


### Saving and restoring backups
The **Save** and **Restore** controls are in the app header rather than floating over the workspace. On browsers that support the Save File Picker, **Save** lets you choose the filename and destination. Otherwise, the browser downloads the JSON backup to its default Downloads location. **Restore** lets you select a previously saved backup JSON file.
