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

Each section shows the plot exported by the SONICOM ecosystem first, then the corresponding plot generated with `hrtfpykit` from the same SOFA file. The SONICOM images are left untouched. The comparable hrtfpykit figures are exported with the same aspect ratio as the SONICOM reference images.

### Energy time curves, horizontal plane, left ear

SONICOM ecosystem:

![SONICOM ecosystem ETC horizontal plane left ear](images/sonicom-ecosystem/etc-horizontal-left.png)

hrtfpykit, generated with `plot_etc_plane(hrtf, ear="left", plane="horizontal", azimuth_range_mode="-180-180")`:

![hrtfpykit ETC horizontal plane left ear](images/hrtfpykit/comparable/etc-horizontal-left.png)

### Energy time curves, horizontal plane, right ear

SONICOM ecosystem:

![SONICOM ecosystem ETC horizontal plane right ear](images/sonicom-ecosystem/etc-horizontal-right.png)

hrtfpykit, generated with `plot_etc_plane(hrtf, ear="right", plane="horizontal", azimuth_range_mode="-180-180")`:

![hrtfpykit ETC horizontal plane right ear](images/hrtfpykit/comparable/etc-horizontal-right.png)

### Spectral magnitude, median plane, left ear

SONICOM ecosystem:

![SONICOM ecosystem spectral magnitude median plane left ear](images/sonicom-ecosystem/spectrum-median-left.png)

hrtfpykit, generated with `plot_spectrum_plane(hrtf, ear="left", plane="median", freq_max=18000.0)`:

![hrtfpykit spectral magnitude median plane left ear](images/hrtfpykit/comparable/spectrum-median-left.png)

### Spectral magnitude, median plane, right ear

SONICOM ecosystem:

![SONICOM ecosystem spectral magnitude median plane right ear](images/sonicom-ecosystem/spectrum-median-right.png)

hrtfpykit, generated with `plot_spectrum_plane(hrtf, ear="right", plane="median", freq_max=18000.0)`:

![hrtfpykit spectral magnitude median plane right ear](images/hrtfpykit/comparable/spectrum-median-right.png)

### Absolute ITD, horizontal plane

SONICOM ecosystem:

![SONICOM ecosystem absolute ITD horizontal plane](images/sonicom-ecosystem/absolute-itd-horizontal.png)

hrtfpykit, generated with `plot_absolute_itd(hrtf)`:

![hrtfpykit absolute ITD horizontal plane](images/hrtfpykit/comparable/absolute-itd-horizontal.png)

### Source grid

SONICOM ecosystem:

![SONICOM ecosystem source grid](images/sonicom-ecosystem/source-grid.png)

hrtfpykit, generated with `plot_source_grid(hrtf)`:

![hrtfpykit source grid](images/hrtfpykit/comparable/source-grid.png)

## Additional hrtfpykit visualizations

The plots below are extra views generated from the same loaded `HRTF` object. They are included to show what `hrtfpykit` could add beyond the current SONICOM ecosystem visualizations.

### HRIR amplitude response

![hrtfpykit HRIR amplitude response](images/hrtfpykit/additional/amplitude-default.png)

### HRTF magnitude response

![hrtfpykit HRTF magnitude response](images/hrtfpykit/additional/magnitude-default.png)

### Signed ITD over the horizontal plane

![hrtfpykit signed ITD over the horizontal plane](images/hrtfpykit/additional/itd-horizontal.png)

### Signed ILD over the horizontal plane

![hrtfpykit signed ILD over the horizontal plane](images/hrtfpykit/additional/ild-horizontal.png)

### Frequency-dependent ILD over the horizontal plane

![hrtfpykit frequency-dependent ILD](images/hrtfpykit/additional/ild-frequency-horizontal.png)

### Source plane grid

![hrtfpykit plane grid](images/hrtfpykit/additional/plane-grid.png)

### Absolute ILD, horizontal plane

![hrtfpykit absolute ILD](images/hrtfpykit/additional/absolute-ild-horizontal.png)

### Elevation spectrum

Generated with `plot_elevation_spectrum(hrtf, freq_max=18000.0)`:

![hrtfpykit elevation spectrum](images/hrtfpykit/additional/elevation-spectrum-default.png)



