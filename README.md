# xarray-regrid: Regridding utilities for xarray.

<img align="right" width="100" alt="Logo" src="./docs/assets/logo.png">

With xarray-regrid it is possible to regrid between two rectilinear grids. The following methods are supported:
 - Linear
 - Nearest-neighbor
 - Conservative
 - Cubic
 - "Most common value" (zonal statistics)

Note that "Most common value" is designed to regrid categorical data to a coarse resolution. For regridding categorical data to a finer resolution, please use "nearest-neighbor" regridder.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.10203304.svg)](https://doi.org/10.5281/zenodo.10203304)

## Installation

```console
pip install xarray-regrid
```

## Usage
The xarray-regrid routines are accessed using the "regrid" accessor on an xarray Dataset:
```py
import xarray_regrid

ds = xr.open_dataset("input_data.nc")
ds_grid = xr.open_dataset("target_grid.nc")

ds.regrid.linear(ds_grid)
```

For examples, see the benchmark notebooks and the demo notebooks.

## Benchmarks
The benchmark notebooks contain comparisons to more standard methods (CDO, xESMF).

To be able to run the notebooks, a conda environment is required (due to ESMF and CDO).
You can install this environment using the `environment.yml` file in this repository.
[Micromamba](https://mamba.readthedocs.io/en/latest/user_guide/micromamba.html) is a lightweight version of the much faster "mamba" conda alternative.

```sh
micromamba create -n environment_name -f environment.yml
```

## Acknowledgements

This package was developed under Netherlands eScience Center grant [NLESC.OEC.2022.017](https://research-software-directory.org/projects/excited).
