# APTA-BIOTECK · Post-COVID Text-to-Graph Framework

**Project:** Text-to-Graph Framework for Post-COVID Mechanisms & Therapeutic Targeting  
**Prepared for:** APTA / BIOTECK  
**Prepared by:** Fraunhofer SCAI  
**Confidentiality:** Fraunhofer SCAI · APTA Collaboration · Confidential

---

## 1. Purpose

This repository/package contains the structured deliverables for the APTA-BIOTECK Post-COVID Text-to-Graph collaboration.

The overall objective is to transform fragmented Post-COVID / Long COVID / PASC clinical evidence into a structured, reproducible, and eventually graph-queryable evidence layer. The project is organised into modular tasks, each with its own deliverables, review point, and go/no-go decision.

The final goal is to support APTA in answering questions such as:

- What interventions have been tested for Post-COVID conditions?
- Which patient populations and cohort characteristics are represented?
- Which clinical endpoints and readouts are most consistently measured?
- Which mechanisms or therapeutic hypotheses are supported by evidence?
- Which findings are strong enough to inform future trial design or therapeutic prioritisation?

---

## 2. Project structure

The project follows the modular task structure defined in the cooperation proposal.

| Task | Name | Main deliverable |
|---|---|---|
| Task 01 | Foundation — Curated Post-COVID Study Corpus | Curated corpus, structured study catalogue, interactive dashboard/viewer |
| Task 02 | KG Schema & Common Data Model | Documented KG schema/CDM, entity mapping rules, harmonisation workflows |
| Task 03 | SCAIView Semantic Search Instance — optional | Annotated corpus and semantic search interface |
| Task 04 | Text-to-Graph Extraction | Normalised triple dataset for endpoints, readouts, cohort descriptors, and temporal context |
| Task 05 | Evidence-Weighted Knowledge Graph | Neo4j knowledge graph with evidence scoring, provenance, and query workflows |

Each task can be reviewed independently. APTA may make a go/no-go decision at task boundaries before proceeding to the next stage.

---

## 3. Recommended folder layout

```text
APTA_PostCOVID_TextToGraph/
│
├── README.md
│
├── 00_Project_Documents/
│   ├── APTA_Proposal.pdf
│   ├── project_timeline.pdf
│   └── decision_log.md
│
├── Task01_Curated_Corpus/
│   ├── README_Task01.md
│   ├── 01_Dashboard/
│   ├── 02_Catalogues_CSV/
│   ├── 03_Methods_Provenance/
│   ├── 04_AI_Audit_Trail/
│   └── 05_Archive/
│
├── Task02_KG_Schema_CDM/
│   ├── README_Task02.md
│   ├── schema_documentation/
│   ├── entity_mapping_rules/
│   ├── controlled_vocabularies/
│   └── review_materials/
│
├── Task03_SCAIView_Optional/
│   ├── README_Task03.md
│   ├── scaiview_instance_notes/
│   ├── annotation_configuration/
│   └── quality_review/
│
├── Task04_TextToGraph_Extraction/
│   ├── README_Task04.md
│   ├── extraction_outputs/
│   ├── normalised_triples/
│   ├── qa_reports/
│   └── provenance/
│
└── Task05_Evidence_KG/
    ├── README_Task05.md
    ├── neo4j_export/
    ├── graph_schema/
    ├── evidence_scoring/
    ├── example_queries/
    └── final_review_materials/