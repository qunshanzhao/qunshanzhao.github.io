# TODO — open items

## Blocking launch (need Qunshan's confirmation)

- [ ] **Create the GitHub repo & publish.** The repo `qszhao/qszhao.github.io` does not exist yet — everything is committed locally only. Once confirmed: create the public repo, push `main`, then in GitHub → Settings → Actions → General → Workflow permissions set **Read and write permissions**, wait for the Deploy action, and set Settings → Pages → Branch to **`gh-pages`** (not `main`).
- [ ] **People page roster** (`_pages/people.md`, currently `published: false`): confirm who should be listed, their roles (PhD student / researcher), current vs alumni status, and alumni destinations. Names were inferred from the old Weebly team page and 2022–2026 co-publications — do not publish unverified. Flip `published:` to `true` once confirmed.
- [ ] **Headshot**: currently the official UofG portrait (from the old Weebly site, 533×800). Provide a newer photo if preferred → replace `assets/img/prof_pic.jpg`.
- [ ] **Teaching page**: confirm the current course list. Note: a `qszhao/ATUA2026` (Advanced Topics for Urban Analytics) repo exists on GitHub but the course is not on the migrated page — add it if it is now taught.
- [ ] **News items**: 4 seeded entries are recent-paper announcements with dates taken from Crossref. Confirm they are the items you want, and add non-paper news (grants, awards, promotions) as desired — template in `_news/announcement_template.md`.
- [ ] **Content licence**: footer currently says "© Qunshan Zhao". Decide whether to additionally license content as CC BY 4.0.

## Post-launch

- [ ] Add a banner on the old Weebly site pointing to https://qszhao.github.io, or retire it.
- [ ] Update the "personal website" link on the UofG staff profile and the UBDC profile.
- [ ] Replace `assets/pdf/Qunshan_Zhao_CV.pdf` (snapshot of the Aug 2025 UofG PDF) whenever the CV is updated.
- [ ] Optional: buy a custom domain and add a `CNAME` file (see al-folio docs/INSTALL.md).
- [ ] Optional: set `analytics:` (e.g. a Google Analytics tag) and `google_site_verification` in `_config.yml`.
- [ ] Optional: restore upstream GitHub workflows that were removed to reduce noise (e.g. `update-citations`, `broken-links`, `prettier`) — copy from https://github.com/alshedivat/al-folio/tree/main/.github/workflows if wanted.
- [ ] Optional: add venue abbreviations/colours in `_data/venues.yml` and coauthor links in `_data/coauthors.yml` to enrich the publications page.
