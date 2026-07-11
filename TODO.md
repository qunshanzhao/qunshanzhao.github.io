# TODO — open items

## Launch (Qunshan is doing this himself — see steps below)

The site will live at **https://qunshanzhao.github.io**. A GitHub *user* page must match the account name, and the personal account is `qszhao` — so the repo goes in a new (free) GitHub **organisation** named `qunshanzhao`. Steps:

- [ ] 1. Create the organisation (web UI only): <https://github.com/account/organizations/new> → choose the **Free** plan → Organization name: `qunshanzhao` → your account becomes the owner
- [ ] 2. `cd /Users/qzhao/Desktop/PersonalWebsite/qunshanzhao.github.io`
- [ ] 3. `gh repo create qunshanzhao/qunshanzhao.github.io --public --source=. --push`
- [ ] 4. On github.com/qunshanzhao/qunshanzhao.github.io: **Settings → Actions → General → Workflow permissions** → select **Read and write permissions** → Save
- [ ] 5. **Actions** tab → enable workflows if prompted; the **Deploy site** action runs on the push (re-run it from the Actions tab if it ran before step 4)
- [ ] 6. After the action succeeds (creates the `gh-pages` branch): **Settings → Pages** → Source: *Deploy from a branch* → Branch: **`gh-pages`**, folder `/ (root)` → Save
- [ ] 7. Visit https://qunshanzhao.github.io (allow a couple of minutes for the first Pages deployment)

## Content

- [ ] Replace `assets/pdf/Qunshan_Zhao_CV.pdf` (currently the Aug 2025 UofG snapshot) with a PDF export of the newer `CV_Zhao_Qunshan-faculty-Glasgow.docx` (Word → Save As → PDF), keeping the same filename.
- [ ] News item `_news/2025-01-01-ubdc-deputy-director.md` is dated 2025-01-01 because only the year of the Deputy Director appointment is public — correct the date if a more precise one is preferred. Likewise `2024-11-01` for the GISCup item (conference ran 29 Oct–1 Nov 2024).

## Post-launch

- [ ] Add a banner on the old Weebly site pointing to https://qunshanzhao.github.io, or retire it.
- [ ] Update the "personal website" link on the UofG staff profile and the UBDC profile (and in the CV, which still lists the Weebly address).
- [ ] Optional: buy a custom domain and add a `CNAME` file (see al-folio docs/INSTALL.md).
- [ ] Optional: set `analytics:` (e.g. a Google Analytics tag) and `google_site_verification` in `_config.yml`.
- [ ] Optional: restore upstream GitHub workflows that were removed to reduce noise (e.g. `update-citations`, `broken-links`, `prettier`) — copy from https://github.com/alshedivat/al-folio/tree/main/.github/workflows if wanted.
- [ ] Optional: add venue abbreviations/colours in `_data/venues.yml` and coauthor links in `_data/coauthors.yml` to enrich the publications page.
