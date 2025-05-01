# Topological Signatures of Membrane Tension in the Cosmic Web

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![arXiv](https://img.shields.io/badge/arXiv-2305.XXXXX-b31b1b.svg)](https://arxiv.org/abs/2305.XXXXX)

This repository contains the code, data, and analysis for the paper "Topological Signatures of Membrane Tension in the Cosmic Web", which investigates the topological structure of the cosmic web using persistent homology and proposes a membrane tension model to explain observed features.

## Abstract

We present a topological analysis of the cosmic web using persistent homology, focusing on the identification of membrane-like structures. By analyzing the SDSS DR12 spectroscopic sample, we detect significant deviations from standard ΛCDM predictions in both Betti numbers and filament intersection geometries. Our modified membrane tension model provides a superior statistical fit to the observed data, suggesting that cosmic web evolution may be constrained by topological field dynamics beyond purely gravitational structure formation. The orthogonal sheet junctions and triple-point intersections we observe are consistent with a physical model where the cosmic web behaves as a system of tensioned membranes with minimized surface energy.

## Key Findings

- **Topological Signatures**: SDSS data shows excess void counts (β₂) and distinctive loop structures (β₁) compared to ΛCDM predictions
- **Geometric Preferences**: Filament intersections show strong preference for orthogonal (∼90°) junctions
- **Statistical Validation**: Our membrane tension model achieves significantly better statistical fit than standard cosmological models

## Getting Started

### Prerequisites

- Python 3.8+
- GUDHI (Topological Data Analysis library)
- NumPy, SciPy, Matplotlib, Pandas
- LaTeX (for paper compilation)

### Installation

```bash
# Clone the repository
git clone https://github.com/[username]/cosmic-membranes.git
cd cosmic-membranes

# Install Python dependencies
pip install -r requirements.txt
```

### Running the Analysis

1. **Preprocess SDSS Data**

```bash
python data/scripts/preprocess_filaments.py \
    --input path/to/sdss_catalog.NDskel \
    --output data/preprocessed/sdss_filaments.csv
```

2. **Calculate Persistent Homology**

```bash
python code/python/betti_analysis.py \
    --input data/preprocessed/sdss_filaments.csv \
    --output results/ \
    --max_dimension 2 \
    --max_edge_length 10.0
```

3. **Analyze Filament Intersection Angles**

```bash
python code/python/angle_analysis.py \
    --filaments data/preprocessed/sdss_filaments.csv \
    --nodes data/preprocessed/sdss_nodes.csv \
    --output results/
```

4. **Compare with Theoretical Models**

```bash
python code/python/statistical_comparison.py \
    --observed results/betti_results.json \
    --models "lcdm,membrane" \
    --output results/comparison/
```

5. **Generate Visualizations**

```bash
python code/python/visualizations.py \
    --data results/ \
    --output paper/figures/
```

## Repository Structure

- **paper/**: LaTeX source for the manuscript
- **code/**: Analysis and visualization code (Python and JavaScript)
- **data/**: Data preprocessing scripts and documentation
- **docs/**: Additional documentation and usage guides

## Data Sources

Our analysis uses the Malavasi et al. (2017) public `.NDskel` catalog derived from the SDSS DR12 spectroscopic sample. The catalog is available at [SDSS SAS](https://data.sdss.org/sas/dr12/).

## Results

### Persistence Diagrams

![Persistence Diagram](paper/figures/persistence_diagrams.png)

Persistence diagrams showing birth-death coordinates of topological features in the cosmic web. Note the significant excess of long-lived β₁ features in observational data compared to ΛCDM simulations.

### Angle Distributions

![Angle Histogram](paper/figures/angle_histograms.png)

Junction angle histograms show a distinct preference for orthogonal intersections (∼90°) in observational data, better reproduced by the Membrane Tension model than by standard ΛCDM simulations.

## Citation

If you use this code or methodology in your research, please cite our paper:

```bibtex
@article{author2025topological,
  title={Topological Signatures of Membrane Tension in the Cosmic Web},
  author={Author, A. and Collaborator, B.},
  journal={Monthly Notices of the Royal Astronomical Society},
  year={2025},
  publisher={Oxford University Press}
}
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- SDSS Collaboration for public data access
- GUDHI developers for the persistent homology tools
- [Your funding sources and acknowledgments]