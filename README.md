# India ART Clinics Dataset

**639 government-registered fertility (ART) clinics across five Indian metros, with parsed registration levels.**

This dataset lists every clinic registered under India's ART (Regulation) Act 2021 in Bengaluru, New Delhi, Mumbai, Kolkata and Hyderabad, as published in the Government of India's **National ART and Surrogacy Registry**, normalized into a clean, analysis-ready table. Its distinguishing feature is the parsed **registration level**: each registry registration number encodes whether a clinic is registered as **Level 1 (basic ART services, such as IUI)** or **Level 2 (advanced ART, including IVF and ICSI)**. To our knowledge this is the only structured public dataset of Indian ART clinic registration levels.

Maintained by [Fertility Decoded](https://fertilitydecoded.org), India's free, independent guide to fertility care. A browsable version lives at [fertilitydecoded.org/clinics](https://fertilitydecoded.org/clinics).

## Contents

| City | Clinics | L1 | L2 | Level unverified |
| --- | --- | --- | --- | --- |
| Bengaluru | 161 | 43 | 105 | 13 |
| New Delhi | 160 | 48 | 109 | 3 |
| Mumbai | 125 | 61 | 64 | 0 |
| Kolkata | 58 | 22 | 35 | 1 |
| Hyderabad | 135 | 44 | 90 | 1 |
| **Total** | **639** | **218** | **403** | **18** |

One file: `art-clinics-india.csv` (UTF-8, header row, 639 data rows, 15 columns). Column definitions are in `data-dictionary.md`.

## Source and provenance

- **Primary source:** National ART and Surrogacy Registry, Government of India (Ministry of Health and Family Welfare). Per-city registry exports taken 18 June 2026 (Bengaluru) and 29 June 2026 (the other four cities).
- **Processing:** registration numbers (format `KA/AC/2022/10231/L1/Bengaluru Urban/067`) parsed into level, year, district, serial and application number; one scraped page-footer artifact and one exact duplicate row removed; clinic contact emails omitted from this distribution (available in the registry itself). No clinic details were added, edited or removed beyond this.
- A clinic appearing here means it is registered under the ART (Regulation) Act 2021. Registration is a legal baseline, not a quality rating. See [how we evaluate](https://fertilitydecoded.org/about/how-we-evaluate) and [registration explained](https://fertilitydecoded.org/about/registration-explained).

## Known limitations

- **Chennai / Tamil Nadu is not included.** The TN registration number format (`ART/CHE/serial/year`) does not encode the L1/L2 level, so those rows would lack the dataset's key field. They may be added if level data becomes available.
- A blank `reg_level` means the clinic is registered but its number did not parse to a level (18 rows).
- Some rows are in greater-metro districts (for example Navi Mumbai, Thane, Medchal); these carry `district_flag = "outside-core-metro?"`.
- Registry contents change as clinics register or lapse. This is a snapshot; check the registry or fertilitydecoded.org for the current picture.

## License and attribution

The underlying facts are public records of the Government of India. This compilation (normalization, parsing, cleaning) is released under **[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)**: use it freely, including commercially, with attribution.

**Attribution:** "India ART Clinics Dataset, Fertility Decoded (fertilitydecoded.org), derived from the National ART and Surrogacy Registry, Government of India."

## Contact

Fertility Decoded: [fertilitydecoded.org](https://fertilitydecoded.org) · 
