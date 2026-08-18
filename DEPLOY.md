# Launching galblatman.com

The site is three main pages (index.html, research.html, teaching.html), a blog powered by Jekyll (which GitHub Pages runs automatically, nothing to install), and an assets folder. Total time from here to live: about 30 minutes, most of it waiting on DNS.

## What each folder is

- `index.html`, `research.html`, `teaching.html`: the main pages.
- `blog/`: the blog index page.
- `_posts/`: one Markdown file per published post. See HOW_TO_POST.md.
- `_drafts/`: unpublished drafts. Nothing here appears on the site.
- `_layouts/`: the template that wraps every blog post. You should not need to touch it.
- `_config.yml`: site settings. You should not need to touch it.
- `assets/`: your headshot, CV PDF, and any blog images.

## 1. Before launch: two files and two links

1. Export your CV from Word as a PDF and save it as `assets/Gal_Blatman_CV.pdf` (exact name, it is linked from every page).
2. Add a professional headshot as `assets/headshot.jpg` (portrait orientation, roughly 800 px wide). Optionally add `assets/classroom.jpg`, a photo of you teaching or presenting, which appears on the Teaching page. Both photo slots hide themselves if the files are missing, so the site works before you add them.
3. When you have your Google Scholar and LinkedIn URLs, open each HTML file (including `_layouts/post.html`), find the comment marked `TODO` in the footer, and uncomment that line with your links filled in.
4. Optional: if you buy a domain other than galblatman.com, update the `url` line in `_config.yml` and the `canonical` links near the top of each HTML file.

## 2. Put it online with GitHub Pages (free)

Your account is github.com/GalBlatman, so the repository must be named exactly `GalBlatman.github.io`. Fastest lane first, since you have Git Bash.

### Lane A: Git Bash (about two minutes)

1. On github.com, click New repository. Name: `GalBlatman.github.io`. Visibility: Public. Create it completely empty (no README, no license, no .gitignore).
2. Unzip gal-blatman-site.zip somewhere permanent, for example `Documents/galblatman-site`.
3. In Git Bash:

```
cd ~/Documents/galblatman-site
git init -b main
git add .
git commit -m "Launch site"
git remote add origin https://github.com/GalBlatman/GalBlatman.github.io.git
git push -u origin main
```

4. The first push opens a GitHub sign-in window in your browser. Approve it once and the push completes; later pushes will not ask again.
5. For a repository with this exact name, GitHub Pages usually switches itself on. Give it two minutes, then open `https://galblatman.github.io`, blog included: GitHub detects the Jekyll files and builds them automatically. If nothing appears, go to Settings, then Pages, and set Source to "Deploy from a branch," branch `main`, folder `/ (root)`.

### Lane B: no command line

Create the same empty repository, click Add file, then Upload files, and drag in everything from the unzipped folder, including the underscore folders. Commit, then check Settings, Pages as above.

## 3. Buy the domain

1. Go to Cloudflare Registrar, Porkbun, or Namecheap and buy `galblatman.com`. Expect roughly 10 to 15 dollars per year.
2. Turn on auto-renew so it never lapses mid job market.

## 4. Connect the domain to the site

1. In your GitHub repository: Settings, Pages, Custom domain. Enter `galblatman.com` and save. GitHub adds a CNAME file to the repository; leave it there.
2. At your registrar, open the DNS settings for galblatman.com and add five records:
   - A record, host `@`, value `185.199.108.153`
   - A record, host `@`, value `185.199.109.153`
   - A record, host `@`, value `185.199.110.153`
   - A record, host `@`, value `185.199.111.153`
   - CNAME record, host `www`, value `galblatman.github.io`
3. Wait 15 to 60 minutes for DNS to propagate. Back in GitHub Pages settings, once the domain check passes, tick "Enforce HTTPS."
4. Visit https://galblatman.com and confirm the padlock shows.

## 5. After launch

- Add the URL to your CV header, email signature, LinkedIn, and Google Scholar profile.
- Publish your first real post (HOW_TO_POST.md has the three-step workflow, and a draft about the writing skills is waiting in `_drafts`).
- Search "Gal Blatman" on Google in a week or two; the site should start ranking near the top for your name.
- To update anything later, edit files in the GitHub web interface, or open the repository in Claude Code and describe the change in plain language.

## Content choices baked into this version

- No paper PDFs are posted. Working papers say "available on request," which is the safe default until each coauthor signs off on posting a draft.
- No target journals are listed publicly. They are on your CV, where the audience is right for them.
- The multiplicity paper uses the current framing (policy multiplicity, not the old interpretive-capacity version).
- The Selected Presentations list gives venue and year only, so it never conflicts with evolving paper titles.
- There is deliberately no contact form and no news section. Email is the contact method and the job market line is the freshness signal.
- The blog at /blog/ is the one living section. Posting instructions are in HOW_TO_POST.md; GitHub Pages builds it automatically, so there is nothing extra to configure.
- The blog and the research pages are kept visually consistent but clearly separated, so casual posts never read as research claims.
