# f-ai
F-AI: Fluorescence Image Analyzer (v0.1.0)
# F-AI — Fluorescence Image Analyzer

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

Browser-based tool for quantitative fluorescence microscopy image analysis.  
No installation. No data upload. All processing runs locally in your browser.

---

## Live application

**[Launch F-AI →](https://fluorescent-ai.netlify.app/)**

---

## What it does

F-AI segments nuclei in fluorescence microscopy images and computes per-cell
quantitative metrics: the membrane-to-cytoplasm intensity ratio (M/C ratio),
nucleus-to-cytoplasm ratio (N/C ratio), and subcellular localization class.

**Analysis pipeline:**
1. Rolling-ball background subtraction
2. Automatic nucleus detection (Otsu thresholding)
3. Dilation-based membrane ring and cytoplasm region extraction
4. Per-cell intensity measurement (ring, cytoplasm, nucleus, background)
5. M/C ratio and N/C ratio computation per cell
6. Rule-based localization classification with confidence scoring

**Localization classes returned:**
- Plasma membrane — M/C ratio > 1.4
- Nucleus — N/C ratio > 1.5
- Cytoplasm — M/C and N/C both near 1.0
- Mitochondria-like — high cytoplasmic texture score
- Uncertain — confidence below 0.55

---

## How to use

1. Open the live link above in any modern browser (Chrome, Firefox, Edge, Safari)
2. Upload a JPG or PNG fluorescence image by clicking or drag and drop
3. Adjust parameters if needed (nucleus threshold, ring width, dilation)
4. Click **Analyze image**
5. Inspect the segmentation overlay and M/C heatmap
6. Download the results as CSV

No account, no login, no installation required.  
Your images never leave your computer.

---

## Supported formats

| Format | Supported |
|--------|-----------|
| JPG / JPEG | ✓ |
| PNG | ✓ |
| TIFF | — not supported in browsers |

If your microscope exports TIFF files, open them in FIJI and save as PNG
via File → Save As → PNG before uploading.

---

## Output

- Segmentation overlay — nucleus boundaries in cyan, membrane ring in yellow
- M/C heatmap — each cell coloured by its M/C ratio (blue = low, red = high)
- Per-cell results table — M/C ratio, N/C ratio, area, centroid, localization class, confidence
- CSV download — all per-cell metrics ready for GraphPad Prism,
---

## Citation
Kulbacka J. et al. (2025). F-AI: Fluorescence Image Analyzer (v0.1.0). GitHub. https://github.com/JulitaKul/f-ai
--

## Funding

This research was funded by the European Union (NextGenerationEU) as part of the National Recovery and Resilience Plan, supported by the Medical Research Agency. 
Project number KPOD.07.07-IW.07-0072/24 (PI: J. Kulbacka). Acronym: Onko-SPARK.

---
## Contact

Julita Kulbacka  
Department of Molecular and Cellular Biology, 
Faculty of Pharmacy  
Wroclaw Medical University, Poland  
julita.kulbacka@umw.edu.pl

---
## License

MIT — free for academic and non-commercial use.
