# Training Log — standalone web app

A 3-day training log built for Planet Fitness equipment. Runs entirely in the
browser, saves to the device, and installs to a phone home screen like a native app.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app — HTML, CSS, React and all logic in one file. No build step, no dependencies. |
| `manifest.json` | Lets phones install it as an app (name, icon, standalone window). |
| `sw.js` | Service worker. Caches the app so it opens with no signal at the gym. |
| `icon-192.png` / `icon-512.png` / `icon-180.png` | Home screen icons. |

## Try it right now

Open `index.html` by double-clicking it. Everything works except offline caching,
which needs the app to be served over http(s).

## Put it online (free, ~5 minutes)

### GitHub Pages
1. Create a GitHub account if you don't have one.
2. Make a new **public** repository — call it `training-log`.
3. Upload all the files in this folder to the root of the repo.
4. Repo **Settings → Pages → Source: Deploy from a branch → main → / (root)** → Save.
5. Wait about a minute. Your app is at `https://YOURNAME.github.io/training-log/`.

### Netlify Drop (no account needed to start)
1. Go to `app.netlify.com/drop`.
2. Drag this whole folder onto the page.
3. You get a live URL immediately.

Either host works. Both are free and neither needs a credit card.

## Install it on your phone

**iPhone / iPad (Safari):** open the URL → Share button → **Add to Home Screen**.
**Android (Chrome):** open the URL → menu → **Install app** / **Add to Home screen**.

It then opens full screen with no browser bars, and works without a connection.

## Where your data lives

Everything you log is stored in your browser's local storage, on that device only.

- It is never uploaded anywhere. There is no account and no server.
- It stays put through app closes, phone restarts, and offline use.
- It is **per device and per browser**. Logging on your phone will not show up on a laptop.
- Clearing your browser's site data or deleting the app will erase it. On iOS, also
  avoid "Clear History and Website Data" unless you mean it.

Use the **Backup** panel on the Loads page. **Export** downloads a `.json` file;
**Restore** takes the contents of that file back. Do this every few weeks — it's the only
copy of your training history.

## Updating it later

Replace `index.html` and bump `CACHE` in `sw.js` (e.g. `training-log-v2`) so phones
pick up the new version instead of the cached one. Your logged data is untouched by updates.

## The program

- 5-week blocks: weeks 1 & 3 heavy, weeks 2 & 4 volume, week 5 deload.
- 6 exercises per session, all doable on Planet Fitness equipment (Smith machine,
  dumbbells, fixed bars, selectorized machines — no free barbells or squat racks).
- Cardio is treadmill-only: speed intervals, incline walk, or endurance run/walk.
- Set your Smith bar weight on the Loads page first. PF bars are usually 20–25 lb, not 45.
