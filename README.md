# MonteCarloBioTissues-Tutorials

Interactive tutorials for Monte Carlo light-transport simulations in biological tissues. The examples use the Monte Carlo eXtreme stack (MCX/PMCX) to show how to build simple volumes, set optical properties, launch photons, and visualize fluence and energy deposition.

## Contents
- `mcx_en.ipynb`: End-to-end notebook that installs PMCX, checks GPU availability, sets up a cubic volume with an inclusion, runs simulations for multiple output types (flux, fluence, energy), visualizes slices, and demonstrates saving/loading results in BJData (`.bnii`).

## Requirements
- CUDA-capable NVIDIA GPU (recommended; MCX can run on CPU but will be slow).
- Python 3.9+ with `pmcx`, `numpy`, `matplotlib`, `jdata`, `bjdata`, `iso2mesh`.
- A recent MCX binary is bundled via the `pmcx` package.

## Quick Start
1. Open `mcx_en.ipynb` in VS Code or Jupyter with a GPU-enabled runtime.
2. Run the dependency cell (pip installs). If using VS Code, prefer a Conda/venv with GPU-enabled CUDA drivers.
3. Execute cells in order: GPU check → volume/config setup → simulation run → visualization → save/load demo.

### Running on Google Colab
- Works on Colab with the T4/L4/A100 GPU runtime. Go to Runtime → Change runtime type → GPU.
- Install dependencies in the first cell (already provided). PMCX downloads the MCX binary automatically.
- Colab sessions are ephemeral: save `.bnii` outputs to Google Drive if you want to reuse them without rerunning simulations.

#### Open from GitHub in Colab
- Direct link (public repo): https://colab.research.google.com/github/therezacury/MonteCarloBioTissues-Tutorials/blob/main/mcx_en.ipynb
- Or manually: File → Open notebook → GitHub tab → paste `therezacury/MonteCarloBioTissues-Tutorials` → open `mcx_en.ipynb`.
- Switch runtime to GPU (Runtime → Change runtime type → GPU) and run cells top to bottom.
- If the repo is private, first run: `!git clone https://github.com/therezacury/MonteCarloBioTissues-Tutorials.git` then open `mcx_en.ipynb` from the left file browser.

## Tips
- Increase `nphoton` for lower noise; expect longer runtimes.
- Use log-scale plots (`np.log10`) to inspect fluence/energy for high-contrast regions.
- When saving results, keep the `.bnii` files alongside the notebook to replot without rerunning GPU simulations.
