# Multimodal Data Collection Platform
### Web-Based Psychometric Data Collection for IoT & AI Behavioral Observation

**Programme:** Erasmus Mundus CYBER (Cyberspace Behavior and E-Therapy)  
**Institutions:** Université Paris Cité
**Lab:** Centre Borelli (UMR9010), in collaboration with Thales AVS  

---

## Overview

A client-side single-page application (SPA) built in **HTML5, CSS3, and JavaScript**
for structured multimodal psychometric data collection. No server infrastructure
required -runs entirely in the browser or as a standalone desktop executable.

Developed as part of the master's project:
**"MultiModal Behavioral Observation during Psychometric Testing using IoT & AI"**

Available in two parallel language versions:
- 🇬🇧 `fullverEng.html` :English version
- 🇫🇷 `fullverFrench.html` : French version

---

## Features

| Module | Description |
|---|---|
| **Neutral baseline** | Rainbow Passage (Fairbanks, 1960) : standardised attentional priming before emotionally loaded content |
| **Consent Page** | Brief consent page and instructions |
| **Collection of PARTICIPANT INFORMATION** | NAME/ Birthdate/ Gender/ age raange/ email/ nationality. native language |
| **Instruction pages** | Instruction pages are displayed (BFI-2-S item · Plutchik Wheel · Russell grid) before each test begins |
| **HADS** | Hospital Anxiety and Depression Scale - 14 items (7 Anxiety / 7 Depression), with per-item ISO 8601 timestamps and automatic subscale scoring |
| **BFI-2-S** | 30-item Big Five personality assessment with automatic reverse-scoring and per-item ISO 8601 timestamps |
| **NAPS stimuli** | 20 affective images from the Nencki Affective Picture System (NAPS BE) |
| **Plutchik Wheel** | SVG-rendered interactive emotion category + intensity ring selection |
| **Russell Circumplex** | Canvas-rendered valence/arousal grid (−1 to +1 on both axes) |
| **CSV export** | Pseudonymized output (participant code format: `P-XXXXXXXXX`) : no server transmission |
| **GDPR compliance** | All data processed client-side; consent form integrated; no external API calls |

---

## How to Run

### Option 1 - Direct browser (simplest)
```bash
# No installation needed
# Just open the file in any modern browser
open fullverEng.html        # macOS
start fullverEng.html       # Windows
xdg-open fullverEng.html    # Linux
```

### Option 2 - Local server (recommended for development)
```bash
# Python 3
python -m http.server 8000

# Then open in browser:
# http://localhost:8000/fullverEng.html
```

### Option 3 - Desktop executable (Windows)
The app was packaged as a standalone Windows `.exe` using **pywebview**.
See the `packaging/` folder for build instructions.

---

## Repository Structure
> ⚠️ **NAPS images not included:** The NAPS BE stimulus images are not distributed
> in this repository as they require a separate license from the Nencki Institute
> of Experimental Biology (Warsaw). Request access at:
> https://naps.nencki.gov.pl/

---

## Session Flow
---

## CSV Output Format

Each exported CSV contains one row per participant with:

| Field | Description |
|---|---|
| `participant_code` | Pseudonymized ID (format: `P-XXXXXXXXX`) |
| `bfi2s_[domain]` | BFI-2-S domain scores (O, C, E, A, N) with reverse-scoring applied |
| `item_[n]_timestamp` | ISO 8601 timestamp per BFI-2-S item |
| `naps_[n]_emotion` | Plutchik emotion category for image n |
| `naps_[n]_intensity` | Plutchik intensity ring (1=HIGH, 2=MEDIUM, 3=LOW) |
| `naps_[n]_valence` | Russell valence coordinate (−1 to +1) |
| `naps_[n]_arousal` | Russell arousal coordinate (−1 to +1) |

---

## Privacy & GDPR

- All data processing is **client-side only** - no data is transmitted to any server
- Participant names are **never stored** in the data files
- Exported CSV contains only the pseudonymized participant code
- The consent form (paper, bearing participant name) is stored separately
  in accordance with GDPR pseudonymization requirements
- No cookies, no tracking, no external API calls

---

## Dependencies

No installation required. The app uses only:
- Vanilla HTML5 / CSS3 / JavaScript
- [jQuery v3.6.0](https://jquery.com/) - loaded via CDN
- [DM Sans + DM Mono](https://fonts.google.com/) —-Google Fonts (loaded via CDN)

For offline use, CDN resources can be downloaded locally
and paths updated in the HTML files.

---

## Browser Compatibility

Tested and confirmed working on:
- Chrome 120+
- Firefox 121+
- Edge 120+
- Safari 17+

---

## Related Repository

The statistical analysis pipeline and synthetic data generation scripts
are in a separate repository:
---

## Citation

If you use this platform, please cite:

> Song, H. (2026). *Multimodal Data Collection Platform for Psychometric
> Testing with IoT Behavioral Observation*. Master's project,
> Erasmus Mundus CYBER, Université Paris Cité 
> Centre Borelli (UMR9010).
> https://github.com/[yourname]/multimodal-data-collection-platform

---

## References

- Fairbanks, G. (1960). *Voice and articulation drillbook* (2nd ed.). Harper & Row.
  *(Rainbow Passage -neutral baseline text)*
- Marchewka, A., et al. (2014). The Nencki Affective Picture System (NAPS).
  *Behavior Research Methods, 46*(2), 596–610.
- Plutchik, R. (1980). *Emotion: A psychoevolutionary synthesis*. Harper & Row.
- Russell, J. A. (1980). A circumplex model of affect.
  *Journal of Personality and Social Psychology, 39*(6), 1161–1178.
- Soto, C. J., & John, O. P. (2017). Short and extra-short forms of the BFI-2.
  *Journal of Research in Personality, 68*, 69–81.

---

## License

MIT License : see `LICENSE` file.

> Note: The NAPS BE stimulus images are subject to a separate license
> and are not covered by this MIT License.
