# Vanuatu Administrative Divisions / Vanuatu



## Overview

| Item | Details |
|------|---------|
| Province | 6 |
| Area Council | 66 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/vu](https://openadmindata.org/vu/) |
| API | [openadmindata.org/api/vu](https://openadmindata.org/api/vu/) |
| Flag | [PNG](https://onlygames.me/flags-png/vu/) · [SVG](https://onlygames.me/flags-svg/vu/) · [PDF](https://onlygames.me/flags-pdf/vu/) |
| National Anthem | [🎵 Listen & Download Vanuatu National Anthem MP3](https://onlygames.me/national-anthems/vu/) |

## Browse by Province

| # | Province | Area Councils | Link |
|---|----|----|------|
| 1 | Malampa | 10 | [Browse](divisions/malampa-vu04/) |
| 2 | Penama | 10 | [Browse](divisions/penama-vu03/) |
| 3 | Sanma | 10 | [Browse](divisions/sanma-vu02/) |
| 4 | Shefa | 18 | [Browse](divisions/shefa-vu05/) |
| 5 | Tafea | 11 | [Browse](divisions/tafea-vu06/) |
| 6 | Torba | 7 | [Browse](divisions/torba-vu01/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-province.json](data/all-province.json) | JSON | All 6 province records |
| [all-area_council.json](data/all-area_council.json) | JSON | All 66 area council records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-province.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['area_council']} area councils")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-province.json", "utf-8"));
console.log(`Total: ${data.length} provinces`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=province, 2=area council |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{province-slug}/
```

Area Councils are listed inline in each province's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-province links
- [Per-province data](docs/llms-full/) — Full data by province

## Citation

```
Vanuatu Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/vanuatu-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
