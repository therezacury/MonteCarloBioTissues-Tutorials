# MonteCarloBioTissues-Tutorials

Interactive tutorials for Monte Carlo light-transport simulations in biological tissues. The examples use the Monte Carlo eXtreme stack (MCX/PMCX) to show how to build simple volumes, set optical properties, launch photons, and visualize fluence and energy deposition. A Portuguese version is included below.

## Contents
- `mcx_en.ipynb`: End-to-end notebook that installs PMCX, checks GPU availability, sets up a cubic volume with an inclusion, runs simulations for multiple output types (flux, fluence, energy), visualizes slices, and demonstrates saving/loading results in BJData (`.bnii`).
- `mcx_pt.ipynb`: Portuguese translation of the full notebook with the same steps and code.

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
- Direct link (EN): https://colab.research.google.com/github/therezacury/MonteCarloBioTissues-Tutorials/blob/main/mcx_en.ipynb
- Direct link (PT): https://colab.research.google.com/github/therezacury/MonteCarloBioTissues-Tutorials/blob/main/mcx_pt.ipynb
- Or manually: File → Open notebook → GitHub tab → paste `therezacury/MonteCarloBioTissues-Tutorials` → open the notebook you want.
- Switch runtime to GPU (Runtime → Change runtime type → GPU) and run cells top to bottom.
- If the repo is private, first run: `!git clone https://github.com/therezacury/MonteCarloBioTissues-Tutorials.git` then open the notebook from the left file browser.

## Conteúdo (PT)
- `mcx_pt.ipynb`: Notebook completo em português (instala PMCX, checa GPU, cria volume cúbico com inclusão, roda saídas flux/fluence/energy, visualiza cortes e demonstra salvar/carregar `.bnii`).

## Requisitos (PT)
- GPU NVIDIA com CUDA (recomendado; em CPU fica lento).
- Python 3.9+ com `pmcx`, `numpy`, `matplotlib`, `jdata`, `bjdata`, `iso2mesh`.
- O binário recente do MCX vem pelo pacote `pmcx`.

## Guia Rápido (PT)
1. Abra `mcx_pt.ipynb` no VS Code ou Jupyter com GPU.
2. Rode a célula de dependências (pip). Em VS Code, prefira Conda/venv com drivers CUDA.
3. Execute em ordem: checar GPU → configurar volume/cfg → rodar simulação → visualizar → salvar/carregar.

### Rodando no Google Colab (PT)
- Funciona com GPU T4/L4/A100. Vá em Runtime → Change runtime type → GPU.
- A primeira célula já instala dependências; o PMCX baixa o binário do MCX.
- Sessões do Colab são temporárias: salve `.bnii` no Drive se quiser reutilizar sem rerrodar.

#### Abrir do GitHub no Colab (PT)
- Link direto (PT): https://colab.research.google.com/github/therezacury/MonteCarloBioTissues-Tutorials/blob/main/mcx_pt.ipynb
- Ou manualmente: File → Open notebook → guia GitHub → cole `therezacury/MonteCarloBioTissues-Tutorials` → abra `mcx_pt.ipynb`.
- Troque o runtime para GPU e rode as células na ordem.
- Se o repositório for privado, rode: `!git clone https://github.com/therezacury/MonteCarloBioTissues-Tutorials.git` e abra `mcx_pt.ipynb` na barra lateral.

## Tips
- Increase `nphoton` for lower noise; expect longer runtimes.
- Use log-scale plots (`np.log10`) to inspect fluence/energy for high-contrast regions.
- When saving results, keep the `.bnii` files alongside the notebook to replot without rerunning GPU simulations.
