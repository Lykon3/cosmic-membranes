# Cosmic Web Topology Analysis

This repository contains code and data for the paper "Topological Signatures of Membrane Tension in the Cosmic Web" which analyzes the topological structure of the cosmic web using persistent homology and proposes a membrane tension model to explain observed features.

## Repository Structure

```
cosmic-membranes/
├── paper/
│   ├── main.tex                 # Main LaTeX document
│   ├── references.bib           # Bibliography
│   └── figures/                 # Figure directory
│       ├── filament_network.png
│       ├── angle_histograms.png
│       ├── betti_evolution.png
│       └── persistence_diagrams.png
├── code/
│   ├── javascript/              # JavaScript implementation
│   │   ├── betti_calculator.js
│   │   ├── angle_distribution.js
│   │   ├── model_comparison.js
│   │   └── visualizations.js
│   └── python/                  # Python implementation
│       ├── requirements.txt
│       ├── betti_analysis.py
│       ├── persistence_diagrams.py
│       ├── statistical_comparison.py
│       └── visualizations.py
├── data/
│   ├── README.md                # Data sources and preprocessing instructions
│   ├── preprocessed/            # Preprocessed data files
│   └── raw/                     # Raw data files or instructions to download
└── README.md                    # Main repository README
```

## Installation

### Python Dependencies

```bash
pip install -r code/python/requirements.txt
```

### Required Python Packages

- numpy
- scipy
- matplotlib
- gudhi
- ripser
- pandas
- scikit-learn

## Data Sources

The analysis uses the Malavasi et al. (2017) public `.NDskel` catalog derived from the SDSS DR12 spectroscopic sample. The catalog is available at [SDSS SAS](https://data.sdss.org/sas/dr12/).

## Usage

### Generating Persistent Homology Analysis

```python
python code/python/betti_analysis.py --input data/preprocessed/sdss_filaments.csv --output results/
```

### Visualizing Results

```python
python code/python/visualizations.py --input results/betti_results.json --output paper/figures/
```

## Citation

If you use this code or methodology in your research, please cite our paper:

```
@article{author2025topological,
  title={Topological Signatures of Membrane Tension in the Cosmic Web},
  author={Author, A. and Collaborator, B.},
  journal={Monthly Notices of the Royal Astronomical Society},
  year={2025},
  publisher={Oxford University Press}
}
```

## License

This project is licensed under the MIT License - see the LICENSE file for details.