# Data dictionary: art-clinics-india.csv

One row per registered ART clinic. 639 rows, 15 columns, UTF-8, comma-separated, quoted where needed.

| Column | Type | Description |
| --- | --- | --- |
| `city` | string | City slug: `bangalore`, `delhi`, `mumbai`, `kolkata`, `hyderabad`. |
| `city_display` | string | Display name: Bengaluru, New Delhi, Mumbai, Kolkata, Hyderabad. |
| `name` | string | Clinic name as published in the registry. |
| `address` | string | Street address as published in the registry. |
| `state` | string | Indian state per the registry export (e.g. KARNATAKA, DELHI, MAHARASHTRA). |
| `reg_no` | string | Full registration number as published, e.g. `KA/AC/2022/10231/L1/Bengaluru Urban/067`. |
| `reg_level` | string | Parsed registration level. `L1` = basic ART services (e.g. IUI). `L2` = advanced ART including IVF/ICSI. Blank = registered, level not parseable from the number format. |
| `reg_year` | integer | Registration year parsed from `reg_no`. May be blank if unparseable. |
| `reg_district` | string | District segment parsed from `reg_no` (e.g. Bengaluru Urban). May be blank. |
| `reg_serial` | string | Trailing serial segment of `reg_no`. May be blank. |
| `reg_app_no` | string | Application-number segment of `reg_no`. May be blank. |
| `reg_valid` | boolean | `True` if `reg_no` parsed cleanly into the expected format; `False`/blank otherwise. |
| `reg_note` | string | Free-text parsing note for irregular registration numbers. Usually blank. |
| `district_flag` | string | `outside-core-metro?` when the clinic's district is in the greater metro area (e.g. Navi Mumbai, Thane, Medchal/Rangareddy) rather than the core city. Usually blank. |
| `source_id` | string | Row identifier from the registry's per-state export. **Unique only within a city**, not globally; use (`source_id`, `city`) as the key. |

## Notes

- Level counts: 218 L1, 403 L2, 18 level-unverified (blank `reg_level`).
- Names and addresses keep the registry's original casing and punctuation, including inconsistencies; they identify the clinic as officially registered, so they were not editorialized.
