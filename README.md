# Research homepage

Plain HTML and CSS, four pages (this is the simple version; the version with research topics and "In simple words" explanations is kept on the `full-version` branch): `index.html` (home), `research.html`, `talks.html`, `teaching.html`. No build step, no Jekyll, no dependencies. Edit a page and push.

The navigation bar is copied at the top of each page. If you add or rename a page, update it in all four files.

## Before publishing

1. Put your email address in `index.html` (search for `YOUR_EMAIL`).
2. Add your Google Scholar URL, or delete that line (search for `scholar.google.com`).
3. Add `photo.jpg` (square, at least 200×200 px) to this folder. If `photo.jpg` is missing, the page simply shows no photo.
4. Re-host anything that only lives on Owlstown: QIP 2024 slides, the qualifying-exam slides, the CRA-WP poster. Put them in a `files/` folder and link them from `talks.html` (there is a TODO next to QIP 2024).
5. If you want the job search visible, uncomment the job-market line in `index.html`.
6. Fill in the dates of the invited seminars in `talks.html`.

## Option A: GitHub Pages, free

1. Create a public repository named exactly `<your-github-username>.github.io`.
2. Upload the contents of this folder (all `.html` files, `style.css`, `.nojekyll`, `cv.pdf`, `photo.jpg`) to the root of the repository.
3. In the repository, go to Settings → Pages. Under "Build and deployment", choose "Deploy from a branch", branch `main`, folder `/ (root)`.
4. After a minute the site is live at `https://<your-github-username>.github.io/`.

## Option B: your own domain on top of GitHub Pages

Do Option A first. The domain only changes the address, hosting stays free.

1. Buy a domain (for example `nadyavoronova.com` or `voronova.org`). Typical price is about 10–15 € per year. Registrars with fair renewal prices: Cloudflare, Porkbun, Gandi, OVH.
2. At the registrar, add DNS records:
   - for the bare domain: four `A` records pointing to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - for `www`: a `CNAME` record pointing to `<your-github-username>.github.io`
3. In the repository, Settings → Pages → Custom domain: enter the domain and save. GitHub creates a `CNAME` file in the repository. Tick "Enforce HTTPS" once it becomes available (can take up to a day).

Check the current GitHub Pages IP addresses in the GitHub docs before setting them, in case they changed.

## Leaving Owlstown

Before cancelling, replace the Owlstown front page with a one-line note pointing to the new address, and keep it for a few months if you can. Update the link everywhere it appears: IRIF profile, email signature, arXiv and conference profiles, LinkedIn, application materials.

## Adding a paper

Papers live in `research.html`, in the "Papers" list (newest first). To add one, copy an existing `<li class="paper">…</li>` block and change it:

- `id="..."` is a short name for the paper. The overview at the top of the page and the home page link to it as `#that-name`.
- `data-tags="..."` lists its topics, separated by spaces: `streaming`, `communication`, `queries`, `polynomials`. These drive the filter buttons. Also update the visible `<span class="tag ...">` labels to match.
- Under each paper, `<div class="more">` holds two fold-outs: `<details class="abstract">` with the abstract, and `<details class="simple">` with the "In simple words" explanation. Opening one closes the other. Maths in abstracts is written as `$...$` and rendered by KaTeX on the page. If a paper has no abstract yet, there is an "Abstract on arXiv" link in its place.

When a preprint is accepted, replace "Preprint, 2026" with the venue, and add a line to "What's new" on the home page.

## The research page

The page opens with two cards, "Topics" and "List of papers". Each shows one view and hides the other. The views are `<div class="view" id="overview">` and `<section class="view papers-block" id="papers">`. A link to `research.html#papers` opens the list, and a link to a single paper (for example `research.html#bhm`) opens the list and highlights that paper. Without JavaScript both views are simply shown one after the other.

"What I work on" in the Topics view is three short sections (streaming, communication, queries and polynomials). Each mentions papers with links like `<a href="#random-order">…</a>`, so one paper can come up in more than one section. Each section has an "Explain it simply" box.

## Simple explanations

Every overview section and every paper has a `<details class="simple">` block. Readers open them one by one, or all at once with the "open all simple explanations" button at the top of the research page.

## CV

`cv/cv.pdf` is the CV the site links to. The CV itself is written and kept in the job-search materials, not here. When it changes, replace `cv/cv.pdf` with the new PDF (same file name) so the link keeps working.
