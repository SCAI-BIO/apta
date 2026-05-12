# APTA-BIOTECK · Task 01 Deliverable
## Curated Post-COVID Evidence Corpus — Dashboard & Structured Catalogues

**Prepared for:** APTA- BIOTECK  
**Prepared by:** Fraunhofer SCAI  
**Deliverable:** Task 01 · Foundation — Curated Post-COVID Study Corpus  
**Version:** v1.0  
**Delivery date:** 2026-05-19  
**Confidentiality:** Fraunhofer SCAI · APTA Collaboration · Confidential

---

## 1. Purpose

This package delivers the Task 01 foundation corpus for the APTA Post-COVID evidence project.

It provides a curated and reproducible evidence base covering Post-COVID / Long COVID / PASC, related post-infectious conditions, interventional trials, linked publications, interventions, and selected clinical readout modalities.

The package is intended to support APTA review of:

- corpus scope
- trial and publication coverage
- search strategy
- trial-publication linkage quality
- readiness for downstream Task 02 / Task 04 / Task 05 work

The interactive dashboard is the main review interface. The CSV files are the authoritative machine-readable catalogues.

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

---

## 3. How to review

### Option A — hosted dashboard

Open the hosted dashboard:

[Interactive hosted dashboard](https://postcovid-apta.netlify.app/)

This is the recommended option for scientific and management review.

### Option B — local HTML dashboard

Open the included HTML file in a modern browser:

```text
01_Dashboard/corpus_dashboard.html
```

### Option C — CSV catalogue review

Use the CSV files in:

```text
02_Catalogues_CSV/
```

These files are intended for technical review, downstream analysis, database import, and reproducibility checks.

---

## 4. Package contents

```text
APTA_Task01/
│
├── README_Task01.md
│
├── 01_Dashboard/
│   ├── dashboard_link.txt
│   └── corpus_dashboard.html
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
│   └── coverage_report.txt
```

---

## 5. Delivered files

| File | Description |
|---|---|
| `corpus_dashboard.html` | Interactive analytics dashboard generated from the corpus outputs |
| `trials.csv` | Trial-level catalogue from ClinicalTrials.gov |
| `articles.csv` | Deduplicated publication catalogue |
| `evidence_corpus.csv` | Unified evidence-unit table |
| `trial_article_links.csv` | Trial-to-publication linkage table |
| `top_evidence_trials.csv` | Prioritised high-evidence trial subset |
| `corpus_queries.yaml` | Final search configuration |
| `corpus_manifest.json` | Run metadata, hashes, and provenance |
| `coverage_report.txt` | Human-readable corpus summary and diagnostics |

---

## 6. Suggested APTA review workflow

1. Review the interactive dashboard.
2. Inspect selected records in the CSV catalogues.
3. Check trial-publication links for key studies.
4. Flag missing trials, missing publications, or unclear classifications.
5. Identify endpoint/readout categories that should be harmonised in Task 02.
6. Decide whether Task 01 is accepted as the foundation for the next project stage or whether one refinement iteration is needed.

---

## 7. Scope and interpretation notes

This corpus is a structured evidence foundation, not a clinical guideline or final evidence synthesis.

Important notes:

- Trial status and results availability can change over time.
- Publication databases are continuously updated.
- A trial without a linked publication in this corpus is not necessarily unpublished.
- Trial–article linkage is strongest when explicit NCT identifiers are available.
- Dashboard visualisations are summaries derived from the CSV catalogues.
- The CSV files and manifest should be retained as the authoritative delivery materials.

---

## 8. Reproducibility and provenance

The corpus is generated from a search configuration and reproducible pipeline.

```text
corpus_queries.yaml
      ↓
pipeline execution
      ↓
CSV catalogues
      ↓
corpus_manifest.json
      ↓
corpus_dashboard.html
```

The manifest records run metadata and file hashes. It should be retained with the delivery package so future versions can be compared against this baseline.

---

## 9. Confidentiality

This package is confidential project material for the Fraunhofer SCAI–APTA collaboration.

Do not share publicly unless explicitly approved.

Do not include or distribute:

- API keys
- credentials
- secrets files
- private development paths
- internal-only scripts unless specifically requested

---
