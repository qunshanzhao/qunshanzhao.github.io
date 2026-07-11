# qszhao.github.io

Personal and lab website of **Qunshan Zhao** — Professor of Urban Analytics and Deputy Director of the [Urban Big Data Centre](https://www.ubdc.ac.uk/), University of Glasgow.

Live site: <https://qszhao.github.io>

Built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) theme (v1.x). Pushing to `main` triggers the bundled GitHub Action, which builds the site and publishes it to the `gh-pages` branch.

## Editing quick reference

| What                   | Where                                        |
| ---------------------- | -------------------------------------------- |
| Homepage bio           | `_pages/about.md`                            |
| Research theme cards   | `_projects/*.md`                             |
| Publications           | `_bibliography/papers.bib` (Enlighten export; `selected={true}` shows on homepage) |
| People (draft)         | `_pages/people.md` (`published: false` until roster confirmed) |
| Opportunities          | `_pages/opportunities.md`                    |
| Teaching               | `_pages/teaching.md`                         |
| News items             | `_news/*.md` (see `announcement_template.md`) |
| CV page / PDF          | `_pages/cv.md` / `assets/pdf/Qunshan_Zhao_CV.pdf` |
| Featured repositories  | `_data/repositories.yml`                     |
| Contact & social links | `_config.yml` + `_data/socials.yml`          |

Open items before/after launch are tracked in [TODO.md](TODO.md).

## Local development

The system Ruby on macOS is too old for this theme; use Docker instead:

```bash
docker compose up
# then open http://localhost:8080
```

## License

Theme code is distributed under the [MIT License](LICENSE) (© the al-folio contributors). Site content — text, images, CV, and bibliography — is © Qunshan Zhao.
