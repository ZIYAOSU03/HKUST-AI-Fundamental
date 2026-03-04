# AGENTS.md

## Cursor Cloud specific instructions

This is a Python/PyTorch Jupyter Notebook project (MAIE5102 university assignment). All code lives in `assignment1_maie5102_release/assignment1.ipynb`.

### Services

| Service | How to start |
|---|---|
| Jupyter Lab | `cd assignment1_maie5102_release && jupyter lab --ip=0.0.0.0 --port=8888 --no-browser --ServerApp.token='' --ServerApp.password=''` |

### Dependencies

Python packages: `torch`, `numpy`, `matplotlib`, `jupyter` (installed via pip).

### Running the notebook

- The notebook loads CSV data files from the same directory (`2_cluster_*.csv`, `wine_*.csv`). The working directory must be `assignment1_maie5102_release/` when starting Jupyter.
- No GPU required — the code runs on CPU. CUDA references in the code are for optional GPU acceleration.
- There are no lint checks, automated tests, or build steps — this is a single Jupyter notebook assignment.

### Gotchas

- `~/.local/bin` must be on `PATH` for `jupyter` CLI to work (pip installs scripts there).
