# Cosmic Web Topology Analysis

## GitHub Package Contents

This package contains all necessary files for the paper "Topological Signatures of Membrane Tension in the Cosmic Web" and is ready for upload to GitHub.

### Repository Structure

```
cosmic-membranes/
├── LICENSE                        # MIT License file
├── README.md                      # Main project README
├── requirements.txt               # Python dependencies
├── paper/
│   ├── main.tex                   # Main LaTeX document
│   ├── references.bib             # Bibliography
│   └── figures/
│       ├── README.md              # Figure placeholder instructions
│       ├── filament_network.png   # Placeholder
│       ├── angle_histograms.png   # Placeholder
│       ├── betti_evolution.png    # Placeholder
│       └── persistence_diagrams.png # Placeholder
├── code/
│   ├── javascript/
│   │   ├── README.md              # JavaScript code documentation
│   │   ├── betti_calculator.js    # Betti number calculation
│   │   ├── angle_distribution.js  # Angle distribution analysis
│   │   ├── model_comparison.js    # Statistical comparison tools
│   │   └── visualizations.js      # D3.js visualization code
│   └── python/
│       ├── README.md              # Python code documentation
│       ├── requirements.txt       # Python dependencies
│       ├── betti_analysis.py      # Persistent homology analysis
│       ├── angle_analysis.py      # Angle distribution analysis
│       ├── statistical_comparison.py # Model comparison
│       └── visualizations.py      # Matplotlib visualization code
├── data/
│   ├── README.md                  # Data sources documentation
│   ├── preprocessed/              # Storage for preprocessed data
│   │   └── .gitkeep               # Ensures directory is created
│   └── scripts/
│       ├── preprocess_filaments.py  # Filament preprocessing
│       ├── deduplicate_nodes.py     # Node deduplication
│       └── persistence_filter.py    # Persistence threshold filtering
└── docs/
    ├── installation.md            # Installation guide
    ├── usage.md                   # Usage examples
    └── presentation/
        └── slides.md              # Markdown slide templates
```

### Key Components

1. **Paper**: Complete LaTeX manuscript formatted for MNRAS, including all mathematical formalism, figures, and citations.

2. **Python Analysis Code**: 
   - `betti_analysis.py`: Persistent homology calculation using GUDHI
   - `angle_analysis.py`: Filament intersection angle distribution analysis
   - `statistical_comparison.py`: Model comparison and statistical testing

3. **Visualization Code**:
   - JavaScript D3.js visualizations for web-based interactive plots
   - Python Matplotlib/Seaborn static visualizations for publication

4. **Data Processing**:
   - Scripts for preprocessing SDSS filament catalogs
   - Tools for coordinate conversion and filtering

5. **Documentation**:
   - Detailed README files for each directory
   - Installation and usage guides
   - Data source references

### Setup Instructions

The following steps are included in the main README.md to help users get started:

1. Clone the repository
2. Install Python dependencies (`pip install -r requirements.txt`)
3. Run preprocessing scripts on SDSS data
4. Execute analysis scripts to generate results
5. Compile LaTeX paper using generated figures

All code is extensively documented and includes example command-line usage.