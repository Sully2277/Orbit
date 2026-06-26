# Orbit — full iPhone-only setup (no computer needed)

## 1. Put this site online (using GitHub, from your phone)

1. In Safari, go to **github.com** and sign in (or create a free account).
2. Tap the **+** → **New repository**. Name it `orbit` (or anything),
   keep it Public, then Create repository.
3. On the new repo page, tap **Add file → Upload files**.
4. Tap **choose your files**, then select every file in this folder
   (index.html, manifest.json, service-worker.js, token-generator.html,
   icon-192.png, icon-512.png, apple-touch-icon.png) — pick them all at
   once if your file picker allows it, or upload in a couple of batches.
5. Scroll down, tap **Commit changes**.
6. Go to the repo's **Settings** tab → **Pages** (left sidebar) →
   under "Build and deployment," set Source to **Deploy from a branch**,
   Branch: **main**, folder **/ (root)** → **Save**.
7. Wait about a minute, then refresh that Pages settings screen — it'll
   show your live URL, something like:
   `https://yourusername.github.io/orbit/`

That URL is your app from now on.

## 2. Create your MusicKit key (once your $99/yr membership is active)

1. In Safari, go to **developer.apple.com/account** → Certificates,
   Identifiers & Profiles → **Keys** → **+**.
2. Name it anything, check **MusicKit**, Continue → Register.
3. Tap **Download** — this saves a `.p8` file to your Files app
   (probably in Downloads). You only get this download once.
4. On the key's page, note the **Key ID** (10 characters).
5. Go back to the Membership page and note your **Team ID**.

## 3. Generate your developer token (in Safari, no computer)

1. Open `https://yourusername.github.io/orbit/token-generator.html`
   (swap in your actual URL from step 1).
2. Tap the file picker, choose the `.p8` file you downloaded.
3. Enter your Team ID and Key ID.
4. Tap **Generate token**, then **Copy token**.

Everything here runs locally in Safari — the private key file never
gets uploaded anywhere.

## 4. Connect it in the app

1. Open your main URL: `https://yourusername.github.io/orbit/`
2. Tap **Add to Home Screen** if you want it as an app icon (Share → Add
   to Home Screen).
3. Open the app, paste the token into the box, tap **Save token**.
4. Tap **Connect Apple Music**, sign in with your Apple Music account.
5. Search for a song, drag the wheel to highlight it, tap the center to
   play.

## If something goes wrong

- **"Search failed" / playback errors:** usually means the token is
  stale or mistyped — regenerate it in step 3 and paste the new one in
  (use the "use a different token" link on the connect screen).
- Tokens last about 175 days. When one expires, just come back to
  token-generator.html and make a new one.
