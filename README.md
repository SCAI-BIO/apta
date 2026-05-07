
# APTA-BIOTECK · Task 01 Deliverable
## Curated Post-COVID Evidence Corpus — Dashboard & Structured Catalogues

**Prepared for:** APTA / BIOTECK  
**Prepared by:** Fraunhofer SCAI  
**Deliverable:** Task 01 · Foundation — Curated Post-COVID Study Corpus  
**Version:** v1.0  
**Delivery date:** 2026-05-07  
**Confidentiality:** Fraunhofer SCAI · APTA Collaboration · Confidential

---

## 1. Purpose of this delivery

This package delivers the Task 01 foundation corpus for the APTA Post-COVID evidence project. It provides a curated, reproducible evidence base focused on Post-COVID / Long COVID / PASC, related post-infectious conditions, interventional trials, pharmacological and non-pharmacological interventions, linked publications, and selected measurement/readout modalities.

The delivery is intended to support APTA review of corpus scope, trial/publication coverage, search strategy, linkage quality, and readiness for downstream Task 02/04/05 work such as common data modelling, text-to-graph extraction, and knowledge graph construction.

The key review interface is the interactive dashboard. The CSV files are the authoritative machine-readable catalogues.

---

## 2. Executive summary

The current corpus build contains:

| Asset | Count / scope |
|---|---:|
| Clinical trial records | 602 trials |
| Publication records | 2,282 articles |
| Unified evidence units | 2,802 evidence records |
| Trial–article links | 258 links |
| Prioritised high-evidence trial subset | 28 trials |
| Time span | 2020–2026 |

The dashboard summarises the corpus at multiple levels: search strategy, source coverage, temporal trends, trial publication gaps, disease-scope coverage, readout modalities, intervention landscape, evidence tiers, phase/status distribution, population/cohort characteristics, and knowledge-graph-oriented previews.

---

## 3. How to review the deliverable

### Option A — interactive hosted dashboard

Open the hosted dashboard link provided in the delivery email:

```text
[https://postcovid-apta.netlify.app/]
```

This is the recommended review mode for non-technical reviewers because it preserves the interactive charts, hover text, tables, and narrative sections.

### Option B — local HTML dashboard

Open the included HTML file directly in a modern browser:

```text
01_Dashboard/corpus_dashboard.html
```

or, if renamed for hosting:

```text
01_Dashboard/index.html
```

Recommended browsers: Chrome, Edge, Safari, or Firefox. Internet access may be required because the dashboard loads Plotly.js from an external CDN unless a fully offline Plotly bundle has been included.

### Option C — machine-readable catalogue review

Use the CSV files in:

```text
02_Catalogues_CSV/
```

These files are intended for technical review, downstream analysis, import into databases, and reproducible pipeline checks.

---

## 4. Recommended package structure

The professional handover package should be organised as follows:

```text
APTA_Task01_PostCOVID_Corpus_Deliverable_v1.0_2026-05-07/
│
├── README_Task01_Deliverable.md
│
├── 01_Dashboard/
│   ├── dashboard_link.txt
│   ├── corpus_dashboard.html
│   └── index.html                         # optional, used for Netlify/static hosting
│
├── 02_Catalogues_CSV/
│   ├── trials.csv
│   ├── articles.csv
│   ├── evidence_corpus.csv
│   ├── trial_article_links.csv
│   └── top_evidence_trials.csv
│
├── 03_Methods_Provenance/
│   ├── corpus_queries.yaml
│   ├── corpus_manifest.json
│   ├── coverage_report.txt
│   └── run_notes.txt
│
├── 04_AI_Audit_Trail/                      # include only if GPT-assisted iteration was used
│   ├── chatbot_logs/
│   └── chatbot_suggestions/
│
└── 05_Archive/
    └── dashboard_snapshot.pdf              # optional static record copy
```

If a hosted dashboard is used, the `dashboard_link.txt` file should contain the current review URL and the date/time of deployment.

---

## 5. Delivered files and intended use

| File | Description | Primary audience |
|---|---|---|
| `corpus_dashboard.html` / `index.html` | Interactive analytics dashboard generated from the corpus outputs. | APTA scientific and management reviewers |
| `trials.csv` | Trial-level catalogue from ClinicalTrials.gov, including trial identifiers, titles, status, phase, sponsor, interventions, eligibility, outcomes, and evidence-tier fields. | Scientific review, data import, KG design |
| `articles.csv` | Deduplicated publication catalogue from PubMed, Europe PMC, OpenAlex, and related literature sources, including identifiers, publication metadata, abstracts, citation fields, and source flags. | Literature review, bibliometric review |
| `evidence_corpus.csv` | Unified evidence-unit table combining trial and article evidence in a harmonised structure. | Downstream modelling and KG ingestion |
| `trial_article_links.csv` | Trial-to-publication linkage table, including NCT IDs, PMIDs/DOIs, article titles, and match strategy. | Linkage QA and publication-gap analysis |
| `top_evidence_trials.csv` | Prioritised subset of higher-evidence or review-relevant trials. | Expert review and prioritisation |
| `corpus_manifest.json` | Run manifest containing hashes, counts, timestamps, and provenance metadata. | Reproducibility and audit |
| `coverage_report.txt` | Human-readable run summary, source counts, and coverage diagnostics. | Quick QA |
| `corpus_queries.yaml` | Final search configuration used to generate the corpus. | Reproducibility, search refinement |
| `chatbot_logs/*.json` | Full GPT transcript logs, if AI-assisted curation was used. | AI audit trail |
| `chatbot_suggestions/*` | Suggested terms and verification gap reports, if AI-assisted curation was used. | Human review trail |

---

## 6. Suggested APTA review workflow

### Step 1 — dashboard review

Start with the interactive dashboard and review:

1. Executive summary and corpus size
2. Search strategy and term-family coverage
3. Source coverage and deduplication signal
4. Temporal trends across publications and trial starts
5. Trial publication gaps, especially completed trials without linked publications
6. Disease-scope and readout-modality coverage
7. Intervention landscape and evidence-tier views
8. Population/cohort characteristics
9. KG preview and endpoint/readout sections

### Step 2 — catalogue spot checks

Use the CSV files to inspect specific records and validate whether the dashboard summaries reflect the underlying data. Suggested spot checks:

- Confirm selected NCT IDs in `trials.csv`
- Confirm publication metadata in `articles.csv`
- Confirm trial-publication matches in `trial_article_links.csv`
- Inspect high-priority studies in `top_evidence_trials.csv`
- Review representative evidence rows in `evidence_corpus.csv`

### Step 3 — expert feedback

APTA domain experts should flag:

- Missing known RCTs or intervention studies
- Search terms that are too broad, too narrow, or missing
- Interventions that require expert grouping or normalisation
- Endpoint/readout categories that should be harmonised in Task 02
- Candidate trial/publication gaps requiring manual follow-up

### Step 4 — go / no-go decision

After review, APTA can decide whether the Task 01 corpus is sufficient as a foundation for the next project stage, or whether one additional refinement iteration is required before proceeding.

---

## 7. Scope and interpretation notes

This corpus is a structured evidence foundation, not a clinical guideline or a final evidence synthesis. Counts in the dashboard reflect the current search configuration, the public state of the queried sources at run time, and the filtering/linkage logic used by the pipeline.

Important interpretation points:

- Trial status and results availability can change over time.
- PubMed and other bibliographic databases are continuously updated.
- A trial without a linked publication in this corpus is not necessarily unpublished; it may be reported under a different identifier, in conference material, or outside the indexed sources.
- Trial–article linkage is strongest when explicit NCT identifiers are found; title or metadata-based matches should be reviewed more carefully.
- CSV files are the authoritative data tables; dashboard visualisations are summaries derived from them.

---

## 8. Reproducibility and provenance

The corpus is generated from a YAML search configuration and a deterministic pipeline. The standard reproducibility chain is:

```text
corpus_queries.yaml
      ↓
build_unified_corpus.py
      ↓
output CSV catalogues
      ↓
corpus_manifest.json with hashes and run metadata
      ↓
corpus_dashboard.html
```

Where GPT-assisted curation was used, the operating principle is:

```text
chatbot proposes → human reviews → accepted terms enter YAML → manifest records provenance
```

No AI suggestion should enter the final corpus configuration without human validation. GPT-generated trial or publication identifiers should be verified against live registries or bibliographic APIs before being treated as corpus gaps.

The manifest should be retained with every delivery because it records run metadata and file hashes. This allows future versions of the corpus to be compared against the delivered baseline.

---

## 9. Regenerating the dashboard from CSV outputs

From the pipeline directory:

```bash
python corpus_dashboard.py --indir output --outfile output/corpus_dashboard.html
```

For static hosting, rename or copy the generated file to:

```bash
cp output/corpus_dashboard.html output/index.html
```

Then deploy `index.html` through Netlify, Cloudflare Pages, GitHub Pages, or an internal company hosting platform.

---

## 10. Updating the hosted dashboard

If Netlify is used, the hosted site is updated by redeploying the corrected HTML or folder. Edit locally, regenerate the dashboard, then upload the updated folder again.

Recommended deployment folder:

```text
dashboard_site/
└── index.html
```

The public review URL usually remains the same after a new deploy.

For confidential delivery, prefer a controlled-access hosting location or a company-approved file-sharing system. If a public Netlify URL is used, confirm that no confidential or restricted data is exposed.

---

## 11. Confidentiality and access control

This package should be treated as confidential project material.

Recommended sharing options:

1. Company-approved secure file transfer or SharePoint/Nextcloud folder
2. Password-protected archive, with password sent through a separate channel
3. Controlled-access static hosting for the dashboard
4. Public Netlify/static link only if the content is approved for external access

Avoid sharing API keys, local secrets files, or private development paths. Do not include `config/secrets.env` or any API credentials in the delivery package.

---

## 12. Suggested email text for delivery

```text
Subject: Task 01 Deliverable — Curated Post-COVID Evidence Corpus

Dear [Name],

Please find attached the Task 01 deliverable package for the APTA Post-COVID evidence corpus.

The package includes:

1. An interactive dashboard for review of the curated corpus and key analytics
2. Structured CSV catalogues for trials, articles, evidence units, and trial–article links
3. Provenance and run metadata to support reproducibility
4. Optional AI-audit materials, where GPT-assisted search refinement was used

Interactive dashboard:
[insert dashboard link]

The CSV files should be treated as the authoritative machine-readable catalogues, while the dashboard is intended as the primary review and exploration interface.

Best regards,
[Your Name]
```

---

## 13. Versioning convention

Use explicit versioned folders and archives:

```text
APTA_Task01_PostCOVID_Corpus_Deliverable_v1.0_2026-05-07.zip
```

Recommended version meanings:

| Version | Meaning |
|---|---|
| `v1.0` | Initial formal Task 01 delivery |
| `v1.1` | Minor correction, e.g. dashboard formatting/mobile fix |
| `v1.2` | Small catalogue correction or metadata refinement |
| `v2.0` | New corpus build after substantial search-term or inclusion/exclusion changes |

Every version should include its own README, manifest, and delivery date.

---

## 14. Technical appendix — local build commands

These commands are for internal reproducibility and are not required for dashboard-only reviewers.

### Install dependencies

```bash
python3.11 -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install requests pandas pyyaml openai plotly rapidfuzz
```

### Build the corpus

```bash
python build_unified_corpus.py \
    --queries corpus_queries.yaml \
    --outdir output
```

### Build the dashboard

```bash
python corpus_dashboard.py \
    --indir output \
    --outfile output/corpus_dashboard.html
```

### Prepare dashboard for Netlify/static hosting

```bash
mkdir -p dashboard_site
cp output/corpus_dashboard.html dashboard_site/index.html
```

Upload the `dashboard_site/` folder to the static hosting service.

---

## 15. Troubleshooting

| Issue | Likely cause | Fix |
|---|---|---|
| Charts do not render | Plotly CDN blocked or offline environment | Use a local Plotly bundle or allow CDN access |
| Charts look wrong on iPhone | Dashboard needs responsive/mobile CSS and Plotly resize handling | Regenerate with the mobile-optimised dashboard generator |
| CSV opens with encoding issues | Spreadsheet software guesses encoding incorrectly | Import as UTF-8 / UTF-8-SIG |
| Hosted dashboard not updated | Old Netlify deploy still active or browser cache | Redeploy folder and hard refresh the browser |
| Links to ClinicalTrials.gov do not open | Corporate firewall or browser policy | Open in a different network/browser or copy NCT ID manually |
| Counts differ in a later run | Public databases changed after delivery date | Compare manifests and delivery version numbers |

---

## 16. Contact and follow-up

For scientific review, please record feedback at the level of trial IDs, article identifiers, search terms, and endpoint/readout categories wherever possible. This makes the next iteration actionable and auditable.

Recommended feedback template:

| Item | Identifier / term | Issue | Suggested action | Priority |
|---|---|---|---|---|
| Trial | NCTxxxxxxxx | Missing / incorrectly classified | Add search term / review linkage | High |
| Article | PMID / DOI | Missing / duplicate / wrong link | Review metadata | Medium |
| Search term | term | Too broad / too narrow / missing | Add/remove/refine | Medium |
| Endpoint | endpoint name | Needs harmonisation | Map in Task 02 CDM | High |

