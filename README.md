# Qubits and Semiconductor Dynamics

A topic-organized set of Jupyter notebooks and assets exploring qubit dynamics (Hamiltonians, Rabi oscillations, rotating frames) and core semiconductor concepts (Fermi energy). Each topic is isolated in its own directory for clarity and reproducibility.

Key topic folders:
- [Qubits et Hamiltoniens](./Qubits%20et%20Hamiltoniens/): Qubit models, time evolution, and visualizations. Example notebooks:
  - [chevron_experience_rabi.ipynb](./Qubits%20et%20Hamiltoniens/chevron_experience_rabi.ipynb)
  - [creation_animation_detuning.ipynb](./Qubits%20et%20Hamiltoniens/creation_animation_detuning.ipynb)
  - [positionnement_axe_rotation.ipynb](./Qubits%20et%20Hamiltoniens/positionnement_axe_rotation.ipynb)
  - [referentiel_fixe_et_tournant.ipynb](./Qubits%20et%20Hamiltoniens/referentiel_fixe_et_tournant.ipynb)
  - Assets folder: [Animations](./Qubits%20et%20Hamiltoniens/Animations/)
- [Semi-Conducteurs](./Semi-Conducteurs/): Semiconductor notebooks and plots, e.g.:
  - [fermi_energies.ipynb](./Semi-Conducteurs/fermi_energies.ipynb)
- [Puits de potentiel](./Puits%20de%20potentiel/): Potential well models and numerics:
  - [Potentiel Quadratique](./Puits%20de%20potentiel/Potentiel%20Quadratique/)
  - [Potentiel Rectangulaire ](./Puits%20de%20potentiel/Potentiel%20Rectangulaire%20/) (note the trailing space in the folder name)

## Highlights and techniques

Grounded in the provided notebooks and directory structure:

- Rabi oscillations and Chevron plots
  - Parameter sweep over detuning Δ to visualize Rabi frequency vs detuning as a 2D map (see [chevron_experience_rabi.ipynb](./Qubits%20et%20Hamiltoniens/chevron_experience_rabi.ipynb)).
  - Uses QuTiP’s master-equation solver for time evolution and expectation values: [mesolve](https://qutip.org/docs/latest/guide/dynamics/dynamics-time.html) with `e_ops` to compute ⟨σ_z⟩.
  - Dense 2D visualization with Matplotlib’s [pcolormesh](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.pcolormesh.html) for fast, gridded heatmaps.

- Rotating frames and driven two-level systems
  - Time-independent rotating-frame Hamiltonians H = −Δ/2 σ_z − g/2 σ_x; expectation dynamics via QuTiP operators (`sigmax`, `sigmay`, `sigmaz`).
  - Bloch-sphere visualization utilities via QuTiP’s [Bloch](https://qutip.org/docs/latest/apidoc/classes.html#qutip.bloch.Bloch) object for pedagogical state trajectories.

- Numerical setup for scans and grids
  - Structured grids for time and detuning with NumPy’s [linspace](https://numpy.org/doc/stable/reference/generated/numpy.linspace.html), keeping units explicit in labels (e.g., time in 2π/g).
  - Organized parameter blocks, reusable plotting routines, and per-topic folders for outputs.

- Potential wells and discretized operators (by topic folder)
  - Harmonic and rectangular wells under [Puits de potentiel](./Puits%20de%20potentiel/), typically implemented via finite-difference Hamiltonians and discrete Laplacians over a spatial grid.
  - Sparse operators and eigenvalue problems are commonly handled via SciPy’s [sparse](https://docs.scipy.org/doc/scipy/reference/sparse.html) and linear algebra routines.

- Animations and media
  - Matplotlib’s [animation API](https://matplotlib.org/stable/api/animation_api.html) is often used to generate instructional animations (see [Animations](./Qubits%20et%20Hamiltoniens/Animations/)).
  - For embedding generated videos on the web, standard HTML media elements apply: MDN’s [HTMLVideoElement](https://developer.mozilla.org/docs/Web/API/HTMLVideoElement) and [HTMLMediaElement](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement).

## Non-obvious technologies and libraries

Observed and commonly-adjacent tools for this domain:

- QuTiP (Quantum Toolbox in Python): operators, time evolution, and visualization primitives for quantum systems. [QuTiP](https://qutip.org/)
- Matplotlib: scientific plotting and animation. [Matplotlib](https://matplotlib.org/)
- NumPy: array programming and vectorization. [NumPy](https://numpy.org/)
- SciPy: eigenproblems, sparse matrices, and numerical methods. [SciPy](https://scipy.org/)
- Jupyter Notebooks: interactive workflows and reproducible outputs. [Jupyter](https://jupyter.org/)
- FFmpeg (when exporting animations): robust encodes to mp4/gif from frames. [FFmpeg](https://ffmpeg.org/)
- Optional/adjacent
  - SymPy for symbolic checks and derivations. [SymPy](https://www.sympy.org/)
  - ipywidgets for interactive sliders and parameter sweeps in notebooks. [ipywidgets](https://ipywidgets.readthedocs.io/)

Fonts and other external assets:
- No custom fonts are referenced in the notebooks inspected. If plots or web pages adopt custom typefaces later, add them here with links to their sources.

## Project structure

```text
.
├── README.md
├── Puits de potentiel/
│   ├── Potentiel Quadratique/
│   └── Potentiel Rectangulaire /
├── Qubits et Hamiltoniens/
│   └── Animations/
└── Semi-Conducteurs/
```

Directory notes
- Qubits et Hamiltoniens/: Qubit systems, Hamiltonians, rotating frames, Rabi experiments; contains teaching visuals in [Animations](./Qubits%20et%20Hamiltoniens/Animations/).
- Semi-Conducteurs/: Semiconductor topics such as Fermi energies and distributions.
- Puits de potentiel/: Spatial discretizations and eigenproblems for common model potentials.
- A few system files (e.g., `.DS_Store`) are present; consider a `.gitignore` to avoid committing platform artifacts.

Linked examples
- Qubits: [chevron_experience_rabi.ipynb](./Qubits%20et%20Hamiltoniens/chevron_experience_rabi.ipynb), [creation_animation_detuning.ipynb](./Qubits%20et%20Hamiltoniens/creation_animation_detuning.ipynb), [positionnement_axe_rotation.ipynb](./Qubits%20et%20Hamiltoniens/positionnement_axe_rotation.ipynb), [referentiel_fixe_et_tournant.ipynb](./Qubits%20et%20Hamiltoniens/referentiel_fixe_et_tournant.ipynb)
- Semi-conductors: [fermi_energies.ipynb](./Semi-Conducteurs/fermi_energies.ipynb)