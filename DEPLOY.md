# Publishing to GitHub Pages

The repo is already initialized and committed. You need to do three things: create an empty
repo on GitHub, push to it, and flip Pages on.

## 1. Create the repo on GitHub

Go to <https://github.com/new>.

- **Repository name:** `shlokas-and-mantras`
- **Public** — Pages needs this on a free account.
- Leave *Add a README*, *.gitignore* and *license* all **unchecked**. The folder already has
  its own files, and pre-filling them will cause a conflict on the first push.

Click **Create repository**. Don't run the setup commands GitHub shows you — use the ones below.

## 2. Push

Open Terminal and paste this, replacing `YOUR-USERNAME`:

```bash
cd "/Users/saurabhdp/Documents/Aaru/Web-Project/shlokas-and-mantras"
git remote add origin https://github.com/YOUR-USERNAME/shlokas-and-mantras.git
git push -u origin main
```

If it asks for a password, GitHub no longer accepts your account password over HTTPS. Either:

- install the GitHub CLI (`brew install gh`, then `gh auth login`) and push again, or
- create a personal access token at <https://github.com/settings/tokens> with the `repo`
  scope, and paste that token when Git asks for a password.

## 3. Turn Pages on

In the repo on GitHub: **Settings** → **Pages** (left sidebar).

- **Source:** Deploy from a branch
- **Branch:** `main`, folder `/ (root)`
- **Save**

Wait a minute or two, then your site is live at:

```
https://YOUR-USERNAME.github.io/shlokas-and-mantras/
```

The first build takes a couple of minutes. Refresh the Pages settings screen — it shows the
live link once it's ready. You can also watch progress under the **Actions** tab.

## On your kid's phone or tablet

Open the URL, then:

- **iPhone / iPad:** Share button → *Add to Home Screen*
- **Android:** browser menu → *Add to Home screen*

It gets its own icon and opens full-screen with no address bar. Note that it still needs a
connection each time — offline support wasn't included.

## Pushing changes later

```bash
cd "/Users/saurabhdp/Documents/Aaru/Web-Project/shlokas-and-mantras"
git add -A
git commit -m "describe what changed"
git push
```

Pages redeploys on its own within a minute or so.

## Two things worth knowing

**Audio needs a tap first.** Browsers block autoplay, so nothing sounds until your kid taps a
god. That's already how the site works, so it isn't a problem — just don't expect sound on load.

**The repo is public.** Anyone with the link can see the artwork and audio. If the assets are
licensed for personal use only, keep the URL to yourself, or use a private repo with Cloudflare
Pages instead, which serves private repos on the free tier.
