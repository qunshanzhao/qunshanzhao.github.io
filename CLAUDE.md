# CLAUDE.md — working notes for this repository

Personal + lab academic website of **Prof Qunshan Zhao** (Urban Analytics, University of
Glasgow; Urban Sensing & Analytics Lab). Live at **https://qunshanzhao.github.io** —
al-folio v1 "thin starter" (theme code lives in the `al_folio_*` gems; local files
override gem files of the same path).

This is a **content site**, not the al-folio development repo. The starter-shipped
docs (`AGENTS.md`, `docs/BOUNDARIES.md`, `.github/copilot-instructions.md`) describe
the upstream theme ecosystem — background reading only; the guidance in THIS file
takes precedence here. In particular, local `_includes`/`_layouts` overrides are the
intended customisation route for this site (see below), even though upstream docs
discourage them for theme development.

The owner usually gives instructions in Chinese; reply in Chinese, write site content
in English (except the bilingual blog posts, which are English + full Chinese).

## Deploy chain — always verify after pushing

Push to `main` → GitHub Actions **"Deploy site"** workflow (Jekyll build + purgecss)
→ `gh-pages` branch → GitHub Pages CDN.

- After pushing, wait for the "Deploy site" run **for your commit SHA** to succeed
  (`gh run list`), then the follow-up "pages build and deployment" run; then verify
  the change on the live URL with curl/grep. The CDN caches ~10 minutes and
  **ignores query strings**, so `?x=1` cache-busting does not work.
- A green run for the *previous* commit is a classic false positive — match the SHA.
- The owner has authorised pushing straight to `main` to go live — no PR and no
  confirmation question needed (26 Jul 2026). Still verify the deploy afterwards.

## Layout of the content

| What | Where | Notes |
|---|---|---|
| Homepage/About | `_pages/about.md` | pronunciation line, Service/Honours bullets, lab section |
| Research themes | `_projects/*.md` | 7 theme cards; Team rows use hardcoded 40px avatar chips |
| Major funded projects & talks | `_pages/research.md` | grouped PI / Co-I / mentor+studentships, year-desc order |
| Publications | `_bibliography/papers.bib` + `_pages/publications.md` | Enlighten-derived; custom fields `selected`, `firstauthor`, `corresponding` |
| People | `_data/people.yml` + `_pages/people.md` | roster data; filter buttons + jump links |
| Impact | `_pages/impact.md` | case-study cards + "📄 Policy documents" callouts; covers in `assets/img/impact/` |
| News | `_news/*.md` | `inline: true` = one-liner; with `title:` + `inline: false` = own page |
| Opportunities | `_pages/opportunities.md` | **always bump the `*Update: DD/MM/YYYY*` line when editing this page** |

## People & photos conventions

- Each member in `people.yml` has `slug`; avatar resolves to `photo:` path if set,
  else `assets/img/people/<slug>.svg` (generated initials).
- When a member gains a real photo: save a square jpg to
  `assets/img/people/<slug>.jpg`, add `photo:` in `people.yml`, **and** swap
  `<slug>.svg → <slug>.jpg` in every `_projects/*.md` chip that references them
  (grep for the slug).
- Titles: Dr for PhD holders/graduates, Prof for Qimin Cheng / Zhenfeng Shao;
  thesis titles are bold links to theses.gla.ac.uk.
- PhD-student links in publications render green (#0ca678) via the local
  `_layouts/bib.liquid` override (slug list inside it); other lab members pink.

## Local overrides of gem files — do not delete casually

- `_includes/head.liquid` — vendored copy of the gem's + **Cloudflare Web Analytics
  beacon** at the end (token in `_config.yml → analytics.cloudflare`).
- `_includes/plugins/al_cookie_scripts.liquid` — **critical fix**: replaces the
  `al_cookie` gem's consent script. The gem (v1.0.0) never updated Google Consent
  Mode to "granted", so every GA4 hit carried `gcs=G100` and was silently dropped.
  This override calls `CookieConsent.acceptedCategory('analytics')`, re-applies
  consent on every page load (`onConsent`), and uses `wait_for_update`.
  Reverting it makes GA4 permanently report zero.
- `_layouts/bib.liquid`, `_includes/hook/bib.liquid` — author self-priority,
  student colouring, first/corresponding-author badges.
- `_includes/news.liquid` — homepage `include.limit` branch + year-grouped news page.
- When upgrading `al_folio_*` gems, re-vendor these files against the new versions.

## Analytics

- GA4 `G-QP2E5GYNY2` — consent-gated: only counts visitors who click "Accept all";
  standard reports lag 24–48 h. Working correctly only since 26 Jul 2026.
- Cloudflare Web Analytics — cookie-less, counts everyone; numbers will exceed GA4.
- Verification trick: on the live site, check the `/g/collect` request's `gcs`
  parameter — `G101` good, `G100` means consent broken again.

## Gotchas learned the hard way

- Markdown `##` headings inside HTML `<div>` blocks do **not** render — use literal
  `<h2>` tags (publications/people sections do this).
- Front-matter `description:` must be plain text — HTML there breaks `<meta>` tags.
- Liquid: `remove_last` does not exist; `regex_replace` is available.
- Hand-written SVGs must be valid XML (`xmllint --noout`) — qlmanage renders
  duplicate attributes leniently but browsers show an XML error page.
- `glasgow.gov.uk`, `local.gov.uk`, `royalsociety.org`, `thebritishacademy.ac.uk`
  block curl (403/timeout) — verify those links in a real browser before declaring
  them dead. The Royal Society publishes **no per-project pages**.
- UBDC project pages live at `/research-theme/<theme>/<slug>`; old
  `/research/research-projects/...` URLs soft-redirect to a listing page.
- LinkedIn profile photos: a public profile's `og:image` is fetchable server-side
  with a `facebookexternalhit/1.1` user agent (only when the photo is public);
  never take `displayphoto` URLs from page bodies — they belong to sidebar people.
- GtR: the UBDC grants (ES/L011921/1, ES/S007105/1) and UKRI4008 do not list
  Qunshan by name — his roles (Co-I / Fellowship Mentor) are confirmed by him.

## Editorial judgement

- Verify every fact and link before publishing; prefer official sources (university,
  funder, publisher). If a link can't be verified, leave the text unlinked.
- Never invent URLs. Never guess grant amounts, dates, or titles — check the CV
  (`assets/pdf/Qunshan_Zhao_CV.pdf`) or ask the owner.
- Currency amounts are deliberately omitted from the Major funded projects list
  (owner preference). Project display names are short (e.g. "ColdHome",
  "Building Decarbonisation", "Human Mobility in Greenspace").
