# Passive Smart Dust (PSD)

Image-segmentation and data-processing code used in the Passive Smart Dust (PSD) project at BAM (Bundesanstalt für Materialforschung und -prüfung), Berlin.

This repository contains adjustable HSV-based image-segmentation filters and the associated data-processing notebooks for detecting and classifying solvatochromic paper sensors in UAV imagery.

## Repository contents

| File | Description |
|------|-------------|
| `Contour-area.ipynb` | Contour-based candidate detection and area/shape filtering of sensor strips. |
| `Datapoint-filter-and-visualisation.ipynb` | Filtering and visualization of hue/measurement data points. |
| `Filter_without_downscale_final.ipynb` | Full-resolution segmentation pipeline (no downscaling). |

## Associated publications

- **Fuel detection (UAV):** Nerger, T.; Neumann, P.P.; Weller, M.G. *Passive Smart Dust for Detecting and Classifying Fuel Spills: Drone-Based Colorimetric Imaging Using Solvatochromic Paper Sensors.* Drones **2026** (in revision).
- **Hazardous-chemical localization:** Nerger, T.; Neumann, P.P.; Weller, M.G. *Drone-Based Localization of Hazardous Chemicals by Passive Smart Dust.* Sensors **2024**, 24, 6195. https://doi.org/10.3390/s24196195

## Image-processing pipeline (overview)

1. ColorChecker-based color correction (24-patch reference, per-flight).
2. RGB → HSV conversion; HSV thresholding for activated strips.
3. Gaussian blur, adaptive thresholding, contour detection.
4. Circularity and area-percentile filtering of candidates.
5. DBSCAN clustering of detected centroids.
6. Safety-radius construction (distance to second-nearest centroid).

Full parameter values are listed in the Supplementary Material of the corresponding publication.

## Software environment

- Python 3.9.5
- OpenCV 4.10.0
- NumPy 1.26.4
- scikit-learn 1.5.1
- Pillow 11.3.0
- prettytable 3.3.0

## License

See the `LICENSE` file in this repository.

## Contact

Bundesanstalt für Materialforschung und -prüfung (BAM), Berlin, Germany.
