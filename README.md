# Ilhyun Lee — Portfolio

Static portfolio site: one HTML page, self-hosted fonts, no build step, no cookies, no trackers.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The portfolio page (English) |
| `impressum.html` | Legal notice required in Germany (§ 5 DDG) — fill in street and postcode before publishing |
| `datenschutz.html` | Privacy notice (DSGVO) for GitHub Pages hosting |
| `legal.css` | Styles for the two legal pages |
| `fonts/` | Manrope and JetBrains Mono (woff2, SIL Open Font License) served from this repo, so nothing loads from Google |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |
| `Ilhyun-Lee-CV-EN.pdf` | **Add this yourself** — the CV the download buttons point to |

## Publish on GitHub Pages (about 15 minutes)

1. Create a GitHub account if you don't have one.
2. Create a new **public** repository named `<your-username>.github.io`
   (e.g. `ilhyunlee.github.io`). The site address will then be `https://<your-username>.github.io`.
3. Upload every file and the `fonts/` folder from this package
   (repository page → *Add file* → *Upload files* → drag and drop → *Commit changes*).
   Also upload your CV as `Ilhyun-Lee-CV-EN.pdf`.
4. Repository → *Settings* → *Pages* → *Build and deployment*:
   Source = *Deploy from a branch*, Branch = `main`, folder = `/ (root)` → *Save*.
5. Wait one or two minutes, then open `https://<your-username>.github.io`. HTTPS is on by default.

## Before you publish — checklist

- [ ] `impressum.html`: replace `[Straße und Hausnummer]` and `[PLZ]` with your real address (legally required).
- [ ] Add `Ilhyun-Lee-CV-EN.pdf` to the repository root; check that the PDF contains no more personal data than you want public.
- [ ] `index.html`: replace the two placeholder GitHub links (`https://github.com/`) with your real repository URLs, and update `github.com/ilhyunlee` in the contact list.
- [ ] `index.html`: replace the certification "Verify" links with your personal Credly / PECB verification URLs if you have them.
- [ ] Confirm the Samsung SDS start year (currently 2023) in the timeline and in the experience card.

## Updating the site later

Edit `index.html` in the GitHub web editor (pencil icon) and commit. The site redeploys automatically within a minute.

## Custom domain (optional)

Buy a domain (for example `ilhyun-lee.de`), then: repository → *Settings* → *Pages* → *Custom domain* → enter it → *Save*.
At your domain registrar add a `CNAME` record for `www` pointing to `<your-username>.github.io`,
and four `A` records for the apex domain pointing to GitHub's IPs (listed in the GitHub Pages docs).
Tick *Enforce HTTPS* once the certificate has been issued.

## Next step: AWS

The PRD's target architecture is S3 + CloudFront + Route 53 deployed with Terraform through GitHub Actions (OIDC).
Moving this repo there is itself the first portfolio project; the HTML needs no changes.
