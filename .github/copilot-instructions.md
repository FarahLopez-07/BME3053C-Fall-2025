## Quick orientation

This repository contains course materials for BME3053C (lectures, interactive exercises and solved notebooks). The codebase is notebook-first (Jupyter) and organized into these high-level folders: `lessons/` (source lessons), `lessons-solved/` and `lessons_solved/` (instructor/student solved copies), `interactive-exercises/`, `files/` (data assets), and `temp/` (scratch notebooks).

Primary languages/tools: Python (notebooks), Pandas, NumPy, Matplotlib, scikit-learn and PyTorch. The runtime is driven by the environment in `requirements.txt`.

## What the agent should know (contract)
- Inputs: users will typically ask for edits to notebooks or to add small Python scripts that operate on CSV data found under `files/`.
- Outputs: updated notebooks or new Python scripts, with minimal disruption to existing lesson files (prefer `lessons-solved/` or `interactive-exercises/` for changes).
- Error modes: avoid changing original `lessons/` files unless explicitly asked; many notebooks are canonical lecture materials.

## Where to look first (key files & examples)
- `requirements.txt` — authoritative Python package list for reproducing the environment.
- `lessons/04_Pandas.ipynb` and `lessons_solved/04_Pandas_10_01_2025.ipynb` — good examples of data loading and pandas idioms used across the course (search for `pd.read_csv`).
- `files/` — local datasets (e.g. `cardio_train.csv`). Note: many notebooks read data from remote URLs rather than local files.

## Common tasks & patterns (be concrete)
- To prepare the environment: install packages from `requirements.txt` (pip install -r requirements.txt) and open JupyterLab/notebooks.
- When editing content: prefer adding or modifying notebooks under `lessons-solved/` or `interactive-exercises/` instead of changing `lessons/` in-place.
- Data loading: notebooks commonly use `pd.read_csv(...)` with URLs — if switching to local files, place CSVs under `files/` and update the read path accordingly.

## Editing guidelines for notebooks
- Preserve existing cell structure where possible. If you must re-order or combine cells, keep a brief comment at the top of the notebook describing the change and why.
- Small programmatic fixes (typos, import changes): apply them in minimal cells and add a short test cell demonstrating the fix (e.g., show head() of a DataFrame).

## Examples to cite in suggestions
- Show how to load data from `files/cardio_train.csv` if requested: `import pandas as pd\ndf = pd.read_csv('files/cardio_train.csv')\ndf.head()`
- Reference `lessons/04_Pandas.ipynb` when recommending pandas API usage or idioms (groupby, merge, filtering examples are present there).

## Conventions & repository-specific notes
- Notebook naming: many solved copies include dates (`*_MM_DD_YYYY.ipynb`). Keep that pattern when adding solved material.
- Prefer adding student-facing work to `lessons-solved/` or `lessons_solved/` rather than overwriting original `lessons/` files.
- There is no CI or tests in this repository; changes are validated by running notebooks interactively. Keep changes small and runnable.

## Integration & external dependencies
- Most data examples pull CSV files from remote URLs (Dropbox links, etc.). When introducing new local datasets, add them to `files/` and update any notebook cell that references remote URLs.

## Safety and scope limits for the agent
- Do not attempt to provision remote services, modify system-level configuration, or install OS packages. Focus on Python code and notebook content.
- When uncertain about instructor intent (e.g., modifying canonical lesson content), propose a change as a new notebook in `lessons-solved/` and ask for confirmation.

## If you make edits
- Add a one-line log at the top of the notebook describing the edit and date (e.g., "Edited 2025-11-03: fixed column name in data loading cell").
- When adding new helper scripts, put them in a top-level `scripts/` directory (create it) and include a short README entry in that folder.

## Minimal troubleshooting checklist
1. Install dependencies: `pip install -r requirements.txt`.
2. Open the notebook in JupyterLab and run the kernel for that notebook's Python environment.
3. If a data import fails, check `files/` first, then the notebook cell for a remote URL.

If anything above is unclear or you'd like more examples from specific notebooks, tell me which file(s) and I'll expand or merge additional content.
