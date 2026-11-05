# purrch-up.github.io

The site behind Purrch Up! challenge links, served by GitHub Pages from `main`.

- `/c/?t=<seed>&v=<generator version>&s=<score>`: a challenge link. With the game installed, Android App Links and
  iOS Universal Links open it in the game; otherwise this page offers the stores. The format lives in the game repo,
  `shared/src/commonMain/kotlin/game/Challenge.kt`.
- `.well-known/assetlinks.json`: Android signing certificates allowed to open the links. Add the upload key and the
  Play App Signing key from Play Console (Test and release → App integrity).
- `.well-known/apple-app-site-association`: Team ID and bundle ID of the iOS app.
- `.nojekyll`: without it, GitHub Pages drops the `.well-known` folder.
