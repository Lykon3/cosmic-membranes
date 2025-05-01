# Data Sources and Preprocessing

This directory contains data and preprocessing scripts for the cosmic web topology analysis project.

## Data Sources

### SDSS DR12 Filament Catalog

The primary dataset used in this analysis is the Malavasi et al. (2017) public `.NDskel` catalog derived from the SDSS DR12 spectroscopic sample. This catalog identifies filamentary structures in the cosmic web.

- **Source**: [SDSS SAS Archive](https://data.sdss.org/sas/dr12/)
- **Coverage**: Northern Galactic Cap
- **Redshift Range**: 0.02 < z < 0.14

### Simulation Data

For comparison with theoretical models, we use:

1. **Planck 2018 ΛCDM Simulations**
   - Based on parameters from Planck Collaboration et al. (2018)
   - Box size: 500 Mpc/h
   - Resolution: 2048³ particles

2. **Modified Topological Field Simulations**
   - Custom simulations incorporating membrane tension
   - Same resolution and box size as ΛCDM simulations

## Preprocessing Steps

The following preprocessing steps were applied to the raw filament catalog:

1. **Coordinate Conversion**
   - RA/Dec/z converted to Cartesian coordinates (X, Y, Z) in Mpc units
   - Conversion uses cosmological parameters: H₀ = 67.4 km/s/Mpc, Ωₘ = 0.315

2. **Filament Filtering**
   - Minimum length threshold: 5 Mpc
   - Removed filaments with significance below 3σ
   - Script: `preprocess_filaments.py`

3. **Node Deduplication**
   - Merged nodes within 2 Mpc spatial tolerance
   - Preserved topological connectivity
   - Script: `deduplicate_nodes.py`

4. **Persistence Threshold Filtering**
   - Applied 3σ persistence threshold
   - Isolated topologically robust structures
   - Script: `persistence_filter.py`

## Data Structure

### Preprocessed Files

- `sdss_filaments.csv`: Preprocessed filament segments with fields:
  - `node1_x`, `node1_y`, `node1_z`: Coordinates of first endpoint (Mpc)
  - `node2_x`, `node2_y`, `node2_z`: Coordinates of second endpoint (Mpc)
  - `length`: Length of filament segment (Mpc)
  - `density`: Local density contrast (δ = ρ/ρ̄ - 1)
  - `persistence`: Topological persistence value

- `sdss_nodes.csv`: Filament intersection points with fields:
  - `x`, `y`, `z`: Coordinates (Mpc)
  - `density`: Local density contrast
  - `node_type`: Classification (2, 3, or 4+ connected filaments)

## Reproducing the Preprocessing

To reproduce the preprocessing steps from raw data:

```bash
# Download raw data (requires SDSS credentials)
python download_sdss_data.py --username YOUR_USERNAME --password YOUR_PASSWORD

# Run preprocessing pipeline
python preprocess_pipeline.py --input raw/sdss_dr12_filaments.NDskel --output preprocessed/
```

## Adding New Data

If you wish to add new datasets or simulations, place them in the `raw/` directory and adapt the preprocessing scripts as needed.