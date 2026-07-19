# jonathanchillman.com

Landing site for *The Kindle Kitchen* by Jonathan C. Hillman.
Plain static HTML/CSS, deployed via GitHub Pages, no build step.

## Files
- `index.html` — the whole site (styles are inline in the `<head>`)
- `CNAME` — tells GitHub Pages to serve this repo at jonathanchillman.com
- `bonus-chapter.pdf` — the 15-recipe bonus chapter linked from the book's QR code
  **(replace this placeholder with the real, final PDF before publishing the book)**

## Deploy (GitHub Pages)
1. Push this repo to GitHub (public repo, any name — e.g. `kindle-kitchen-site`).
2. Repo → Settings → Pages → Source: "Deploy from a branch" → Branch: `main`, folder `/ (root)`.
3. Save. GitHub gives you a `https://<username>.github.io/<repo>` URL — wait for the first deploy to go green under the Actions tab.
4. Repo → Settings → Pages → Custom domain: enter `jonathanchillman.com` → Save.
   (This is what writes/confirms the CNAME file — it's already in the repo, but GitHub re-checks it here.)

## Point the domain at it (Namecheap DNS)
In Namecheap → Domain List → Manage → Advanced DNS, add:

| Type  | Host | Value               |
|-------|------|----------------------|
| A     | @    | 185.199.108.153      |
| A     | @    | 185.199.109.153      |
| A     | @    | 185.199.110.153      |
| A     | @    | 185.199.111.153      |
| CNAME | www  | <username>.github.io |

Remove any existing Namecheap "parking page" A/CNAME records for `@` and `www` first.
DNS propagation can take anywhere from a few minutes to ~24 hours.

Back in GitHub Pages settings, once DNS resolves, check "Enforce HTTPS."
