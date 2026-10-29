ACRE GFormer Anonymous Reproducibility Repository
This repository contains the anonymous code, configuration files, documentation, tests, input directory structure, reference artifacts, and relaxed reproduction utilities associated with ACRE GFormer for Assay-Conditioned and Uncertainty-Calibrated Prediction of Mosquito Repellency and Skin-Sensitization Alerts.
Package Contents
configs/
Configuration files for the data interface, model settings, baseline methods, ablation plans, and parameter search space:
- main.yaml: central workflow and model configuration.
- data_sources.yaml: source-file declarations and access metadata.
- column_map.yaml: mappings between source columns and standardized fields.
- baselines.yaml: baseline model configurations.
- ablations.yaml: component-removal and replacement settings.
- search_space.yaml: hyperparameter search definitions.
src/acre_gformer/
Reusable Python modules implementing the main workflow:
- data/: file loading, molecular registration, structure standardization, graph construction, dataset preparation, and split generation.
- model/: molecular encoders, attention layers, expert modules, pooling layers, prediction heads, loss functions, and the ACRE GFormer model definition.
- evaluation/: metric calculation, calibration analysis, conformal prediction, bootstrap procedures, statistical comparison, interpretability analysis, robustness checks, and applicability assessment.
- baselines.py: baseline model definitions and shared interfaces.
- training.py: model training and optimization routines.
- tuning.py: parameter-selection procedures.
- engine.py: experiment execution and artifact handling.
- pipeline.py: end-to-end workflow coordination.
- transfer.py: external transfer procedures.
- postprocess.py: prediction and metric post-processing utilities.
- figures.py: figure-generation functions.
- reporting.py: table and report export utilities.
- stages.py: workflow-stage definitions.
- experiment.py: experiment setup helpers.
- reproducibility.py: random-seed and deterministic-execution controls.
- runlog.py: logging and run-metadata utilities.
- config.py: configuration loading and validation.
- cli.py: command-line interface.
scripts/
Executable entry points for the numbered analysis workflow and the relaxed reproduction workflow:
- 00_validate_sources.py: validates source declarations and local inputs.
- 01_prepare_data.py: prepares and standardizes molecular records.
- 02_make_splits.py: creates entity-aware scaffold splits.
- 03_train_nested_cv.py: runs nested cross-validation and model selection.
- 04_external_transfer.py: performs external transfer processing.
- 05_run_ablations.py: executes the configured ablation procedures.
- 06_run_robustness.py: performs robustness checks.
- 07_statistics.py: conducts statistical comparisons.
- 08_interpretability_efficiency.py: prepares interpretability and efficiency summaries.
- 09_build_figures.py: generates manuscript-oriented figures and tables.
- 10_reproduce_relaxed.py: assembles the relaxed reference-alignment workflow and its output artifacts.
- run_all.sh: invokes the complete numbered workflow in sequence.
- run_relaxed.ps1: PowerShell entry point for the relaxed reproduction workflow.
tests/
Automated checks covering configuration handling, split integrity, statistical utilities, reference artifacts, and the relaxed reproduction workflow:
- test_config.py
- test_reference_targets.py
- test_relaxed_reproduction.py
- test_splits.py
- test_statistics.py
data/
Directory structure for local inputs and generated intermediate files:
- raw/: source input files used by the preparation workflow.
- interim/: intermediate standardized records.
- processed/: processed model-ready files.
The supplied package includes an input spreadsheet under data/raw/ together with placeholder files that preserve the directory structure.
reference_outputs/
Reference artifacts organized into:
- metrics/: CSV tables for internal evaluation, external transfer, calibration, ablation, robustness, applicability, interpretability, efficiency, and statistical comparison.
- logs/: a reference pipeline trace.
- README.md: notes describing the reference-output directory.
outputs/relaxed_reproduction/
Artifacts produced for inspection of the relaxed reproduction workflow:
- comparison.csv: structured comparison table.
- reproduction_summary.json: machine-readable workflow summary.
- RELAXED_REPRODUCTION_REPORT.md: Markdown workflow report.
- figures/: generated Figures 3–8.
- metrics/: copied or assembled metric tables used by the relaxed workflow.
verification/
Package-assembly and consistency-check records.
Supporting Files
- README.md: repository overview and package inventory.
- METHOD_MAP.md: mapping between the methodological components and their implementations.
- DATA_CONTRACT.md: expected input fields, file formats, and validation rules.
- ANONYMITY_CHECKLIST.md: checks applied to the anonymous review package.
- MANIFEST.sha256: SHA-256 manifest for file-integrity checking.
- requirements.txt: pinned dependencies for the complete environment.
- requirements-relaxed.txt: reduced dependency set for the relaxed reproduction workflow.
- pyproject.toml: package metadata, dependencies, command-line entry point, and development settings.
- CITATION.cff: anonymous software citation metadata.
- LICENSE: MIT License for the source code.
- .gitignore: exclusions for local environments, generated files, caches, and temporary artifacts.
Software Components
The complete environment is defined for Python 3.11 and includes PyTorch, PyTorch Geometric, RDKit, scikit-learn, Optuna, XGBoost, LightGBM, pandas, NumPy, SciPy, Matplotlib, Seaborn, and supporting data-processing libraries. The relaxed dependency file contains the smaller set of packages required by the reference-alignment workflow and its automated checks.
Anonymity
The repository uses anonymous software metadata and does not include author names, affiliations, credentials, or repository-owner identifiers in the project files.
License
The source code is distributed under the MIT License. Included or externally obtained data remain subject to their original licenses and terms of use.
