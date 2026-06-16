# SONICOM ecosystem HRTF visualization with hrtfpykit

This repository is a small integration example showing how `hrtfpykit` can generate HRTF visualizations from a SOFA file available through the SONICOM ecosystem.

The example uses the ARI dataset file `hrtf b_nh5.sofa`, available from:

https://ecosystem.sonicom.eu/datafiles/986

The goal is practical: load the SOFA file, create figures with `hrtfpykit`, and show how those figures can support on-the-fly HRTF visualization workflows in the SONICOM ecosystem.

## Repository layout

```text
.
├── README.md
├── data/
│   └── hrtf b_nh5.sofa
├── images/
│   ├── sonicom-ecosystem/
│   └── hrtfpykit/
│       ├── comparable/
│       └── additional/
└── notebooks/
    └── generate_hrtfpykit_plots.ipynb
```

The `images/sonicom-ecosystem/` images are reference exports downloaded from the SONICOM ecosystem page. The `images/hrtfpykit/` images were generated locally from the same SOFA file with `hrtfpykit`.

## Reproducing the hrtfpykit plots

Run the notebook from an environment where `hrtfpykit` is already installed:

```bash
jupyter notebook notebooks/generate_hrtfpykit_plots.ipynb
```

The notebook loads `data/hrtf b_nh5.sofa` and writes the generated figures into `images/hrtfpykit/`.

## Visual comparison with the SONICOM ecosystem

Each section shows the plot exported by the SONICOM ecosystem first, then the corresponding plot generated with `hrtfpykit` from the same SOFA file. The images are stacked at a fixed width so the comparison stays readable without filling the whole page.

### Energy time curves, horizontal plane, left ear

SONICOM ecosystem:

<img src="images/sonicom-ecosystem/etc-horizontal-left.png" alt="SONICOM ecosystem ETC horizontal plane left ear" width="720">

hrtfpykit, generated with `plot_etc_plane(hrtf, ear="left", plane="horizontal", azimuth_range_mode="-180-180")`:

<img src="images/hrtfpykit/comparable/etc-horizontal-left.png" alt="hrtfpykit ETC horizontal plane left ear" width="720">

### Energy time curves, horizontal plane, right ear

SONICOM ecosystem:

<img src="images/sonicom-ecosystem/etc-horizontal-right.png" alt="SONICOM ecosystem ETC horizontal plane right ear" width="720">

hrtfpykit, generated with `plot_etc_plane(hrtf, ear="right", plane="horizontal", azimuth_range_mode="-180-180")`:

<img src="images/hrtfpykit/comparable/etc-horizontal-right.png" alt="hrtfpykit ETC horizontal plane right ear" width="720">

### Spectral magnitude, median plane, left ear

SONICOM ecosystem:

<img src="images/sonicom-ecosystem/spectrum-median-left.png" alt="SONICOM ecosystem spectral magnitude median plane left ear" width="720">

hrtfpykit, generated with `plot_spectrum_plane(hrtf, ear="left", plane="median", freq_max=18000.0)`:

<img src="images/hrtfpykit/comparable/spectrum-median-left.png" alt="hrtfpykit spectral magnitude median plane left ear" width="720">

### Spectral magnitude, median plane, right ear

SONICOM ecosystem:

<img src="images/sonicom-ecosystem/spectrum-median-right.png" alt="SONICOM ecosystem spectral magnitude median plane right ear" width="720">

hrtfpykit, generated with `plot_spectrum_plane(hrtf, ear="right", plane="median", freq_max=18000.0)`:

<img src="images/hrtfpykit/comparable/spectrum-median-right.png" alt="hrtfpykit spectral magnitude median plane right ear" width="720">

### Absolute ITD, horizontal plane

SONICOM ecosystem:

<img src="images/sonicom-ecosystem/absolute-itd-horizontal.png" alt="SONICOM ecosystem absolute ITD horizontal plane" width="720">

hrtfpykit, generated with `plot_absolute_itd(hrtf)`:

<img src="images/hrtfpykit/comparable/absolute-itd-horizontal.png" alt="hrtfpykit absolute ITD horizontal plane" width="720">

### Source grid

SONICOM ecosystem:

<img src="images/sonicom-ecosystem/source-grid.png" alt="SONICOM ecosystem source grid" width="720">

hrtfpykit, generated with `plot_source_grid(hrtf)`:

<img src="images/hrtfpykit/comparable/source-grid.png" alt="hrtfpykit source grid" width="720">

## Additional hrtfpykit visualizations

The plots below are extra views generated from the same loaded `HRTF` object. They are included to show what `hrtfpykit` could add beyond the current SONICOM ecosystem visualizations.

### HRIR amplitude response

<img src="images/hrtfpykit/additional/amplitude-default.png" alt="hrtfpykit HRIR amplitude response" width="720">

### HRTF magnitude response

<img src="images/hrtfpykit/additional/magnitude-default.png" alt="hrtfpykit HRTF magnitude response" width="720">

### Signed ITD over the horizontal plane

<img src="images/hrtfpykit/additional/itd-horizontal.png" alt="hrtfpykit signed ITD over the horizontal plane" width="720">

### Signed ILD over the horizontal plane

<img src="images/hrtfpykit/additional/ild-horizontal.png" alt="hrtfpykit signed ILD over the horizontal plane" width="720">

### Frequency-dependent ILD over the horizontal plane

<img src="images/hrtfpykit/additional/ild-frequency-horizontal.png" alt="hrtfpykit frequency-dependent ILD" width="720">

### Source plane grid

<img src="images/hrtfpykit/additional/plane-grid.png" alt="hrtfpykit plane grid" width="720">

### Absolute ILD, horizontal plane

<img src="images/hrtfpykit/additional/absolute-ild-horizontal.png" alt="hrtfpykit absolute ILD" width="720">

### Elevation spectrum

Generated with `plot_elevation_spectrum(hrtf, freq_max=18000.0)`:

<img src="images/hrtfpykit/additional/elevation-spectrum-default.png" alt="hrtfpykit elevation spectrum" width="720">



