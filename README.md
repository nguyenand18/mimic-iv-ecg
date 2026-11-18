# MIMIC-IV-ECG | Build-a-Thon Data Preparation Workspace

**Project type:** Team research/data-preparation workspace for the 2026 Wake Forest ECG AI Build-a-Thon.  
**Status:** Historical working repository, **not** the final model submission or a standalone deployed application.

This repository records preliminary exploration of data access, eligible-patient filtering, and Lead I ECG preparation for a cross-device ECG similarity challenge. It documents one part of the team's larger workflow.

## Challenge context

The broader competition asked teams to score how likely two short Lead I ECG signals were to come from the same person across clinical and wearable devices. The **four-person team placed first overall** with a **0.97 official combined competition AUC**. Those results describe the **team's final model**, not a model or evaluation contained in this particular data-preparation workspace.

## What's in this repository?

| File | Purpose |
| --- | --- |
| [`GUIDE_download_mimiciv_awss3.md`](GUIDE_download_mimiciv_awss3.md) | Data-acquisition notes using AWS S3 |
| [`filter_eligible_patients.py`](filter_eligible_patients.py) | Candidate-record/patient filtering helper |
| [`eligible_patients.csv`](eligible_patients.csv) | Data-derived index; **sharing rights require review** |
| [`docs/DEVELOPMENT_LOG.md`](docs/DEVELOPMENT_LOG.md) | Archived September 2026 process notes |

The original working notes are retained rather than deleted so the exploration timeline remains traceable.

## Questions explored

- How can large ECG collections be downloaded selectively rather than all at once?
- Which subjects have multiple studies for a possible patient-disjoint comparison?
- How might lead extraction, sample-rate conversion, and fixed-length windows be prepared consistently for modeling?
- How should train/validation/test splits avoid leaking patients across partitions?

Some tasks in the original log were proposals or work in progress. **Do not infer that all proposed preprocessing steps or final validation safeguards were implemented here.**

## Scope, attribution, and results

This is a **team workspace**. The repository alone does not establish which teammate authored each script or data-preparation step. The final challenge ensemble used three Siamese 1D ResNet encoders; this repository should not be presented as the final trained model.

For a higher-level professional summary, see [Andrew Nguyen's portfolio](https://andrew-nguyen-portfolio-vercel-1.vercel.app). Andrew's documented contributions to the final team project centered on independent evaluation, checkpoint auditing, leakage review, ensemble/duration experiments, and documentation.

## Data and responsible use

MIMIC-IV-ECG data access and derivative redistribution may be subject to PhysioNet terms, credentialing, and data-use requirements. **Before sharing this repository further or citing its CSV as a public sample**, review whether the included `eligible_patients.csv` and any derivative artifacts may be redistributed. This README change does not establish those rights or remove material already in the repository.

Do not add raw ECG recordings, patient-related data beyond what is authorized, cloud credentials, or private course/client files to a public repository.

## Status for recruiters

This repo is supporting engineering research notes, not the polished standalone artifact for the first-place competition. For LinkedIn and resumes, the best project description is the team award and clearly attributed model-evaluation work, with a link to the public portfolio case study rather than treating this workspace as the final system.
