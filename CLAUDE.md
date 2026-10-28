# STA_26 – Statistik og Dataanalyse for Softwareteknologi

Dansk kursusside for statistik, kørte i foråret 2026 (afsluttet). Det engelske valgfag STA1_26 er et separat kursus. Al tekst skrives på dansk (`language: da`, quiz `lang: da`); filnavne bruger ASCII-omskrivning (`oe`, `aa`, `ae`), fx `06_Fordelinger_af_stikproevestoerrelser_sampling_distributions`.

## Struktur

- Sessioner `01_...` til `12_...`. Sessionerne 01–10 har `README.md`, `Tutorial_N.md` og `Tutorial_N_notebook.ipynb` (N uden foranstillet nul), og notebooken står i nav som "Tutorial N (notebook)". 11 og 12 har kun `README.md`.
- Sessions-README: `## Sessionsmateriale` (notebook, markdown-tutorial, Recap og Sessionnoter på Google Drive), `## Video Materiale`, `## Sessionbeskrivelse`, `### Centrale begreber`, `## Øvelser` med `#### Øvelse N`.
- Markdown-tutorialen publiceres også (linket "Se tutorial som markdown"), så md og notebook skal stemme overens.
- To mapper starter med `10_`: `10_Goodness_of_fit_og_analyse_af_kategoriske_data` står i nav; `10_Variansanalyse_ANOVA` er tracket, men ikke i nav. Den indeholder egne konverteringsscripts (`md_to_notebook_tutorial10.py`, `sync_tutorial10_md.py`).

## Konfiguration, der afviger fra den globale opsætning

- `site_dir: ../site`, dvs. `C:\GitHub\site`, som deles med ALI1_26 og MSU1_26. Byg til en anden mappe (`mkdocs build --strict -d <mappe>`), hvis flere sites bygges efter hinanden.
- `mkdocs-jupyter` uden indstillinger (standard: notebooks afvikles ikke). Gem output i notebooken.
- CI bruger Python 3.12 (3.14 bryder mkdocs-jupyter/nbconvert) og kører kun `mkdocs gh-deploy --force`, uden `--strict`. Kør selv `mkdocs build --strict` før push. Den lokale `.venv` er i stykker (peger på en gammel OneDrive-sti), og den globale Python 3.14 kan ikke køre mkdocs-jupyter; `C:\GitHub\STA1_26\.venv\Scripts\mkdocs` virker (samme plugins).
- `.gitignore` dækker kun LaTeX-hjælpefiler og OS-filer, ikke `.venv/` eller `_site/`. Commit kun de filer, opgaven handler om.
