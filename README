# ASCEND.exe — deploy guide

## What's in this folder
- `index.html` — the whole site. One file, no build step, no dependencies.
- `config.json` — holds your contract address. The only file you'll ever edit after launch.

---

## Upload to GitHub (no terminal needed)

1. Go to https://github.com/new and create a new repository (public is fine, free either way).
2. On the new repo's page, click **"uploading an existing file"** (the link right under the big green Code button on an empty repo).
3. Drag both `index.html` and `config.json` into the box.
4. Scroll down, click **Commit changes**.

That's it — both files are now in your repo.

If you'd rather use git from a terminal instead:
```bash
cd goddess-site
git init
git add .
git commit -m "ascend site"
git remote add origin https://github.com/YOURNAME/YOURREPO.git
git branch -M main
git push -u origin main
```
GitHub will ask for a username + a **personal access token** as the password (not your real
password — GitHub Settings → Developer settings → Personal access tokens → generate one with
`repo` scope).

---

## Deploy it live — Vercel (free)

1. Go to https://vercel.com and sign in with your GitHub account.
2. Click **Add New → Project**.
3. Pick the repo you just made. Framework preset: **Other**. Leave build command and
   output directory blank.
4. Click **Deploy**. ~30 seconds later you get a live URL like `yourrepo.vercel.app`.

From now on, any time you edit `config.json` in GitHub and commit, Vercel redeploys
automatically in a few seconds — no need to repeat any of these steps.

---

## Put your own domain on it

1. Buy the domain anywhere (Namecheap, Porkbun, Cloudflare).
2. In Vercel: your project → **Settings → Domains** → add `yourdomain.com`.
3. Vercel shows you exact DNS records to add at your registrar — usually:

| Host | Type | Value |
|---|---|---|
| `@` | A | `76.76.21.21` |
| `www` | CNAME | `cname.vercel-dns.com` |

(Use whatever values Vercel actually shows you if they differ.)

4. HTTPS turns on by itself once DNS resolves — usually 5–30 minutes.

---

## Posting your contract address (CA)

1. Once your coin exists on pump.fun, copy its mint address.
2. Go to `yourdomain.com/?admin=ascend` on your live site.
3. Paste the mint. Click **Preview here** first — this only shows it in your own
   browser, nobody else sees it yet.
4. Click **Copy config.json**.
5. In GitHub, open `config.json` in your repo, click the pencil (edit) icon,
   paste over the contents, commit.
6. Vercel redeploys in a few seconds — the CA is now live for everyone, no code changes,
   no rebuild.

## Testing before any of this
Open `index.html` on your own computer (just double-click it) and add `?ca=YOURMINT`
to the address bar. Full live site, your eyes only — good for checking it works before
you push anything anywhere.
