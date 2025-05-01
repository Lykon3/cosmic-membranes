# Figures for "Topological Signatures of Membrane Tension in the Cosmic Web"

This directory contains the figures used in the paper. The following files should be generated using the analysis scripts and placed in this directory:

## Required Figures

1. **filament_network.png**
   - Comparison of filament networks across three models
   - Left panel: SDSS observational data
   - Middle panel: ΛCDM simulation
   - Right panel: Membrane Tension model
   - Resolution: 1200×800 pixels, 300 DPI

2. **angle_histograms.png**
   - Junction angle histograms comparing observations with models
   - Shows preference for orthogonal (∼90°) intersections
   - Includes statistical comparison metrics
   - Resolution: 1200×800 pixels, 300 DPI

3. **betti_evolution.png**
   - Evolution of Betti numbers with filtration scale
   - Three curves showing β₀, β₁, and β₂
   - Should include observed data and model predictions
   - Resolution: 1200×800 pixels, 300 DPI

4. **persistence_diagrams.png**
   - Birth-death coordinates for topological features
   - Panel (a): β₀ features
   - Panel (b): β₁ features
   - Should include observed data and ΛCDM comparison
   - Resolution: 1200×800 pixels, 300 DPI

## Generation Scripts

These figures can be generated using the provided Python scripts:

```bash
# Generate persistence diagrams and Betti evolution
python ../code/python/betti_analysis.py \
    --input ../data/preprocessed/sdss_filaments.csv \
    --output ../results/ \
    --max_dimension 2 \
    --max_edge_length 10.0

# Generate angle histograms
python ../code/python/angle_analysis.py \
    --filaments ../data/preprocessed/sdss_filaments.csv \
    --nodes ../data/preprocessed/sdss_nodes.csv \
    --output ../results/

# Generate filament network visualization
python ../code/python/visualizations.py \
    --data ../results/ \
    --output ./
```

## Figure Format for Publication

- All figures should be in PNG format at 300 DPI
- For MNRAS submission, figures should also be provided in EPS format
- Figure dimensions should match the column width (one-column or two-column) of the journal

## Example Visualizations

This directory includes placeholder examples that demonstrate the expected style and format. Replace these with your generated figures before submission.

## Figure Captions

Captions for each figure are provided in the main.tex document. Ensure that your generated figures match the descriptions in the paper.