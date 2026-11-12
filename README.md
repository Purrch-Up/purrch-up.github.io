# purrch-up.github.io

The Purrch Up! website and the pages behind its challenge links, served by GitHub Pages from `main`.

- `/`, `/vi/`: the landing page, styled by `home.css`. Both languages share one layout, so change them together. The
  English page sends a Vietnamese phone to `/vi/` unless the visitor picked a language.
- `img/`: art for the landing page, made from the game's store captures (`docs/store/art/raw` in the game repo):
  screenshots cropped below the status bar, cats keyed off the icon backgrounds, and `play.mp4`, recorded on the
  simulator with the debug autopilot. `img/<lang>/` holds the official store badges (Google Play PNG, Apple SVG), shown
  at the same height, and the social image.
- `/c/?t=<seed>&v=<generator version>&s=<score>`: a challenge link. With the game installed, Android App Links and
  iOS Universal Links open it in the game; otherwise this page offers the stores. The format lives in the game repo,
  `shared/src/commonMain/kotlin/game/Challenge.kt`.
- `/privacy/`, `/vi/privacy/`: the privacy policy, linked from the game's Settings and given to Play Console, App Store
  Connect and AdMob's GDPR message. When the game starts collecting something new, update both languages and the
  effective date.
- `/support/`, `/vi/support/`: the App Store support URL. The English pages send a Vietnamese phone to `/vi/` unless the
  visitor picked a language with the EN/VI button.
- `.well-known/assetlinks.json`: Android signing certificates allowed to open the links. Add the upload key and the
  Play App Signing key from Play Console (Test and release → App integrity).
- `.well-known/apple-app-site-association`: Team ID and bundle ID of the iOS app.
- `.nojekyll`: without it, GitHub Pages drops the `.well-known` folder.

Pages link `style.css`, `home.css`, `icon.png` and `favicon.png` with `?v=N`; GitHub Pages lets browsers cache them for 10 minutes,
so bump N in every page whenever one of them changes, or new pages show with the old styles.
