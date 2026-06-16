LICHEN Assessment Submission

Overview

This repository contains my technical assessment for the LICHEN project (Light-chain Immunoglobulin sequence generation Conditioned on the Heavy chain and Experimental Needs).

The assessment includes:

* Detailed project analysis
* Architecture and workflow documentation
* Dependency and technology review
* Challenges encountered during setup
* Improvement recommendations
* Implemented dependency fix

⸻

Repository Structure

docs/
├── Analysis_Report.pdf
└── Architecture diagram.png
improvements/
├── README.md
└── pyproject.toml

⸻

Implemented Improvement

Issue Identified

During installation and testing, importing the package failed with:

ModuleNotFoundError: No module named 'psutil'

Investigation showed that load_model.py imports psutil, but the dependency was not declared in pyproject.toml.

Fix Implemented

Added:

"psutil"

to the dependency list in pyproject.toml.

Benefit

* Prevents installation failures
* Ensures reproducible environments
* Improves onboarding experience for new users

⸻

Setup Instructions

Clone Repository

git clone https://github.com/oxpig/LICHEN.git
cd LICHEN

Install Dependencies

pip install .

Download Model Weights

Download model weights from the Zenodo link provided in the original repository README.

Run Example

from lichen import LICHEN
lichen_model = LICHEN("path/to/model_weights.pt")

⸻

Assumptions

* Repository source code reflects the published version of LICHEN.
* Model weights are compatible with the repository version.
* External tools such as ANARCII, Humatch, and AbLang2 operate as documented.
* Analysis was performed using source-code inspection and hands-on execution.

⸻

Key Findings

* Clear modular architecture.
* Good separation between tokenization, inference, and filtering.
* Packaging issue due to missing psutil dependency.
* Optional dependency loading could be improved.
* Installation process can be simplified.

⸻

Documents

* Analysis Report: docs/Analysis_Report.pdf
* Architecture Diagram: docs/Architecture diagram.png
