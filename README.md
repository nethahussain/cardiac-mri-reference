# Hjärt-MR Referensomvandlare

### [▶ Öppna verktyget / Launch the tool](https://nethahussain.github.io/cardiac-mri-reference/)

**Cardiac MRI Reference Converter** — a browser-based clinical tool for radiologists reporting cardiac MRI examinations. Instantly compares ventricular volumes against age- and sex-specific reference ranges.

## What it does

1. Enter patient demographics (sex, date of birth, weight, height)
2. Enter raw cardiac MRI measurements (EDV, ESV, LV mass) for left and right ventricles
3. The tool automatically calculates:
   - **BSA** (Mosteller formula)
   - **Stroke Volume** (SV = EDV − ESV)
   - **Ejection Fraction** (EF = SV/EDV × 100%)
   - **BSA-indexed values** (EDV/BSA, ESV/BSA, SV/BSA, LV mass/BSA)
4. Each indexed value is compared against the correct reference range for the patient's age decade and sex
5. Results are color-coded: **Normalt** (green), **Förhöjt** (red), **Lågt** (amber)
6. A formatted clinical report can be copied to clipboard with one click for pasting into RIS/EMR

## Screenshot

Open `index.html` in any browser and click **Ladda demo** to see it in action.

## Reference ranges

Age- and sex-specific reference values for ages 20–79, covering:

| Chamber | Parameters |
|---------|-----------|
| **Left ventricle (Vä kammare)** | EDV/BSA, ESV/BSA, SV/BSA, EF, LV mass/BSA |
| **Right ventricle (Hö kammare)** | EDV/BSA, ESV/BSA, SV/BSA, EF |

Reference data based on **David Molnar, v.2025-05-02**.

## Usage

No installation required. Just open the HTML file in any modern browser.

### Option A — Local file
Download `index.html` and double-click to open.

### Option B — GitHub Pages
If hosted via GitHub Pages, access directly at:
```
https://nethahussain.github.io/cardiac-mri-reference/
```

## Features

- **Single file, zero dependencies** — everything runs in one self-contained HTML file
- **Works offline** — only Google Fonts require internet (falls back to system serif fonts)
- **Instant calculation** — results update in real time as you type
- **Visual gauge bars** — see at a glance where values fall relative to normal ranges
- **Clipboard report** — one-click copy of formatted report text (Swedish clinical format with Vä kammare / Hö kammare)
- **Flexible date input** — type YYYYMMDD or YYYY-MM-DD
- **Responsive** — works on desktop, tablet, and mobile
- **No patient data stored** — everything is in memory only, nothing persists

## Language

The interface is in **Swedish** with English medical terminology (EDV, ESV, Ejection fraction, LV mass, etc.), designed for use in Swedish clinical environments.

## Credits

- **Reference values**: David Molnar, v.2025-05-02
- **BSA formula**: Mosteller (√(weight × height / 3600))
- **Original tool**: Based on `MRI_Reference_Converter_Updated_20251108.xlsm` by David Molnar

## Contact

For bug reports or errors in the code, contact: **nethahussain@gmail.com**

## License

This project is released under [CC0 1.0 Universal](LICENSE) — dedicated to the public domain. No rights reserved.
